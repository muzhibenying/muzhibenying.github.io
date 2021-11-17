In the article [AI safety via debate](https://arxiv.org/pdf/1805.00899.pdf), Geoffery Irving et al. proposed a new method to help AI agents to learn the human preferences. Sometimes humans are unable to design a function to capture their intention and even judge which action conforms to their desire. However, if we have two agents debate with each other, the human may be able to judge which one gave the most true, useful information.

In order to check whether this method can help us develop AI agents, they carried an experiment with MNIST dataset. In the experiment, a judger can only see 6 (or any other number) pixels in a MNIST image. Therefore, it can not discriminate what the number is in the image. FOrtunately, we have two agents which can see the image. One of the agents try to tell the judger what number it is and the other agent try to misleading the judger. They can reveal up to 6 pixel to the judger turn by turn. This method boost the judger's accuracy from 59.4% to 88.9%.

For the readers who are not familiar with Monte Carlo Tree search, it might be hard to understand how the debater works. Here, I want to explain some details about the experiment based on my understanding. The code quoted here comes from [https://github.com/DylanCope/AI-Safety-Via-Debate/blob/master/MNIST%20Experiment.ipynb](https://github.com/DylanCope/AI-Safety-Via-Debate/blob/master/MNIST%20Experiment.ipynb).

First, we need a judger who can decide which one wins. In this problem, the judger is a classifier trained on MNIST dataset with only 6 non-zero pixels.

```python
def judge_fn(img):
    return judge.predict(x).argmax()
```
The debate game are composed of a input image, a judger, a honest player and a lying player. The honest player will win if the judger makes the right prediction after the game. The lying player wins when the judger makes the wrong prediction after the game.

When the game begins, we first set one of the player as the current player. This player will find a pixel to unreveal. The play can be implemented as a function like this
```python
def play(self):
    moves_played = []
    current_player = self.player_1

    for _ in range(6):
        state = PixelDebateMCTSNode(
            game = self,
            searcher = current_player,
            moves_played = moves_played
        )

        for _ in range(self.rollouts_per_move):
            current_player.tree.do_rollouts(state)
        
        next_state = current_player.tree.choose(state)
        moves_played = next_state.moves_played
        current_player = state.adversary
```
The current state is a node in the Monte Carlo Tree. From this node, the player will do 10k rollouts and then choose which the action it takes. Then another player begin to choose its action until 6 pixels are revealed.

In the above code, the tree of current player is a Monte Carlo Tree. It do rollouts like this
```python
def do_rollout(self, node):
    path = self._select(node)
    leaf[-1] = path[-1]
    self._expand(leaf)
    reward = self._simulate(leaf)
    self._backpropagate(path, reward)
```
First, it find an unexplored descendent of node.
```python
def _select(self, node):
    path = []
    while True:
        path.append(node)
        if node not in self.children or not self.children[node]:
            return path
        unexplored = self.children[node] - self.children.keys()
        if unexplored:
            n = unexplored.pop()
            path.append(n)
            return path
        node = self._uct_select(node)
```
Then it update the children dictionary with the children of the leaf node (the unexplored descendent we found).
```python
if node in self.children:
    return
self.children[node] = node.find_children()
```
In this experiment, the children node of a node represents all the state when revealed another pixels.

The reward of the leaf node can obtained by the simulate function.
```python
def _simulate(self, node):
    invert_reward = True
    while True:
        if node.is_terminal():
            reward = node.reward()
            return 1 - reward if invert_reward else reward
        node = node.find_random_child()
        invert_reward = not invert_reward
```
The reward function of a node state is given by the judger. The reward is used for backpropagation.
```python
for node in reversed(path):
    self.N[node] += 1
    self.Q[node] += reward
    reward = 1 - reward
```
N is the visit count of the node and Q is the total reward of the node. Based on the results of rollout, the Monte Carlo Tree can choose the next state.
```python
def choose(self, node):
    if node.is_terminal():
        raise RuntimeError(f"choose calledon terminal node {node}")
    
    if node not in self.children:
        return node.find_random_child()
    
    def score(n):
        if self.N[n] == 0:
            return float("-inf")
        return self.Q[n] / self.N[n]
    
    return max(self.children[node], key = score)
```
It choose the node with the largest reward and least visit count. After the debaters chooses 6 pixels, the judger can use this to classify the MNIST image.

From the settings of this experiment, we can easily find that there is still a long path to apply this debate strategy. In this experiment, the judger is a CNN, so it is possible to get the reward. When the judger is a real human, it can only give very few feedback. As far as I am concerned, we need powerful method beyone MCTS to train the debater agents.