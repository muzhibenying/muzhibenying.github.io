Specificaion gaming is a behaviour that satisfies the literal specification of an objective without achieving the intended outcome.

#### Causes of Specification Gaming
* poorly designed reward shaping: reward shaping makes it easier to learn some objectives by giving the agent some rewards on the way to solving a task, instead of only rewarding the final outcome.
* Specifying a reward that accurately captures the desired final outcome can be challenging in its own right.
* Even when we make the agent learn the reward function from human feedback, the approach can also encounter specification gaming issues if the reward model does not learn the true reward function that reflects the designer's preferences.
* Other reasons like poor generalisation.
* Simulator bugs: a simulated robot that was supposed to learn to walk figured out how to hook its legs together and slide along the ground. <span style = "color: purple">It is confusing that why this can be a single class of source of specafication gaming.</span>

There are at least three chanllenges to overcome in solving specification gaming:

* How do we faithfully capture the human concept of a given task in a reward function?
* How do we avoid making mistakes in our implicit assumptions about the domain, or design agents that correct mistaken assumptions instead of gaming them?
* How do we avoid reward tampering?

#### Approaches for Solving 
reward modeling, agent incentive design ...

## The superintelligent will
<span style = "color: green">In this article, the author proposed two thesis: the orthogonality thesis and the instrumental convergence thesis. The first thesis tells us that the intelligence level are irrevalent with the motivation of an intelligent system. So the superintelligence may not share any common values with humans. The instrumental convergence thesis tells us that most intelligent systems may share and pursue some instrumental values such as acquiring resources. This could be very dangerous to humans.</span>


#### Problems
* The convergent instrumental values are discussed under the scope of goal-directed AI agents. So are there any method to predict the behaviour of non-goal-directed AI agents?
* What is the meaning of the 10th footnote?

#### The orthognality of motivation and intelligence
* Avoiding anthropomorphism: There is a common tendency to anthropomorphize the motivations of intelligent systems in which there is really no ground for expecting human-like drives and passions. An artificial mind may be more different with huamns than aliens in the sense of values and dispositions.

**The Orthogonality Thesis**: Intelligence and final goals are orthogonal axes along which possible agents can freely vary. In other words, more or less any level of intelligence could in principle be combined with more or less any final goal.

* Some possible objection to the thesis:
  * Sufficient intelligence might entail the acquisition of certain beliefs, and that these beliefs would necessarily produce certain motivations; <span style = "color: purple">According to the Humean theory of motivation, beliefs alone can't motivate action, some desire is required</span>
  * The Humean theory is false; <span style = "color: purple">The thesis could be true if high intelligence doesn't entail the acquistion of beliefs</span>
  * The Humean theory is false: <span style = "color: purple">The thesis could be true if the constitution of the high intelligence is so alien as to contain no clear functional analogues to what in humans we call "beliefs" and "desires"</span>

* Predicting superintelligence motivation and behavior: It is possible to make predictions about waht particular agents will do even when the orthogonality thesis is true. There are at least three directions from which we can approach the problem:
  *  Predictability through design competence: we might be able to predict its behaviour if we know something about who will build it and what goals they will want it to have (<span style = "color: purple">I don't agree with this argument because how can we make sure the designers successfully engineer the goal system of the agent.</span>)
  *  Predictability through inheritance: If a digital intelligence is created directly from a human template, then the digital intelligence might inherit the motivations of the human template.
  *  Predictability through convergent instrumental reasons: Even without detailed knowledge of an agent's final goals, we may be able to infer something about it by considering the instrumental reasons of its actions.(<span style = "color: purple">Would it be very difficult to define instrumentabl when we are dealing with superintelligence which are totally different with us?</span>)

The "intelligence" discussed is different with "rationality". It is like <span style = "color: purple">instrumetal rationality</span> -- skill at prediction, planning, and means-ends reasoning in general.

#### Instrumental convergence
**The Instrumental Convergence Thesis**: Several instrumental values can be identified which are convergent in the sense that their attainment would increase the chances of the agent's goal being realized for a wide range of final goals and a wide range of situations, implying that these instrumental values are likely to be pursued by many intelligent agents.

* self-preservation: even agents that don't care intrisically about their own survivals would are it to accomplish the final goals
* goal-content integrity: in the begining of this part, the author says goal-content integrity for final goal is a fundamental convergent instrumental motivation so intelligent agents will not change their final goals easily. However, the most part of this section are discussing the situation where agents will change their final goals. It seems that the author is stressing the goal content consistence in a society.
* cognitive enhancement: Improvements in rationality and intelligence will tend to improve an agent's decision-making, making the agent more likely to achieve her final goals.
* Technological perfection: An agent may often have instrumental reasons to seek better technology, which means seeking more efficient ways of transforming some given set of inputs into valued outputs.
* Resource acquisition: resource acquistion is another common emergent instrumental gaol, which can facilitate physical construvtion projects

## Risks from Learned Optimization
<span style = "color: green">
A mesa-optimizer is an optimization algorithm that is found by the base optimizer to solve its task. Becuase the mesa-optimizer has its own objective, it raises the inner alignment problem. While outer alignment problems refers to problems of the alignment between the designed reward function and the true goal of the programmer, inner alignment problems refers to problems of the alignment between the meas-optimization objective and the designed reward function. If an mesa-optimizer's objective agrees with the base objective across all distributions, it is robustly aligned, otherwise, it is pseudo-aligned. Mesa-optimization can be a saftey problem in two ways. Sometimes, the unintended powerful mesa-optimizer is unacceptable. It may lead to extreme actions.  In some other cases, even a mesa-optimizer is acceptable, it could be deceptive aligned because an mesa-optimizer can have different objective with the base optimizer.
</span>

**mesa-optimization**: a situation where a learned model is itself an optimizer

$$
\Downarrow
$$

Two questions
* under what circumstances will learned models be optimizers?
* when a learned model is an optimizer, what will its objective be?

#### Base optimizers and mesa-optimizers
Compared with meta-optimization:
* meta-optimization: the task itself is optimization
* mesa-optimization: task-independent, the internal structure of the model ends up performing optimization because it is instrumentally useful for solving the given task

base objective vs. mesa-objective
* base objective: whatever criterion the base base optimizer was using to select between different possible systems (In RL, it is generally the exected return)
* mesa-objective: whatever criterion the mesa-optimizer is using to select between different possible outputs (In RL, it is simply whatever objective was found by the base optimizer that produced good performance on the training environment)

![image](mesa-optimizer.png)
For example, we consider the biological evolution process. The base optimizer is trying to solve a task according to the objective function of their inclusive genetic fitness in some environment. During the optimization process of evolution, humans got brains containing many goal-directed optimization algorithms. We can think of <span style = "color: purple"> evolution </span> as a <span style = "color: purple">base optimizer</span> that produced <span style = "color: purple">brains</span> --<span style = "color: purple">mesa-optimizers</span> --which then actually produce organisms' behaviour.

#### The inner and outer alignment problems
**reward-result gap**: the difference between the "reward model" and the "reward function that is recovered with perfect inverse reinforcement learning

**inner alignment problem**: the problem of eliminating the base-mesa objective gap

**outer alignment problem**: eliminating the gap between the base objective and the intended goal of the programmers

#### robust alignment vs. pseudo-alignment
* robustly aligned: mesa-optimizers with mesa-objectives that robustly agree with the base objective across distributions
* pseudo-aligned: mesa-optimizers with mesa-objectives agree that agree with the base objective on past training data, but not robustly across possible future data

#### Mesa-optimization as a safety problem
* unintended optimization: An advanced ML system could end up implementing a powerful optimization procedure even if its programmers never intended it to do so because of the possibility of mesa-optimization.
* inner alignment: even in cases where it is acceptable for a base optimizer to find a mesa-optimizer, a mesa-optimizer might optimize for something other than the specified reward function.

## Will humans build goal-directed agents?
**Problems**:
* What is a goal-directed AI?
* Why the second method in [this section](#beyond-human-performance) can help an AI system exceed human performance? 
* How did them author conclude that RL algorithms leading to superintelligence may not be goal-directed based on the three reasons in [this section](#current-progress-in-reinforcement-learning)?
* In [this section](#existing-intelligent-agents-are-goal-directed), the author think humans are goal-directed? However, in my opinion, humans are good examples of goal-directed agents in short term. In the very long term, we don't have a goal. Some people may think our goals are live longer, but there are many people sacrifice their life or at least their health for some other goals. And what we regard as the final goal can change over time. So we have to find short term goals by ourselves and this method isn't regarded as goal-directed by the author?

<span style = "color: green">The authors propose that we should build superintelligence without goal-directed agents and we can. Because an agent AI can be not goal-dircted. We can make human goal-directed human-AI systems without goal-directed AI agents. Current RL algorithms can't get true goal-directed agents as they aimed to and it seems not possible to build an ideal general AI with them. The existing of huamn can not be used as an strong support for the goal-directed agents because the limitation of sample size and creating methods. At last, the interpretability brought by goal-directed agents is not important</span>.

#### goal_directed humans
The system comprising the human and AI agent should be goal-directed but the AI agent by itself need not be goal-directed. The question is <span style = "color: purple">when the AI agent is much more intelligent than human, whether we should delegate most decisions to the agent</sapn>.

Even though the AI agent is goal-directed in short term, we can make it not goal-directed in long term.

#### beyond human performance
Goal-directed AI systems can find novel method to achieving golas which makes it possible for them to exceed human performance.

There are two ways to achieve this without an goal-drected AI:
* An AI system can learn from human reasoning and execute it for a longer subjective time.
* We can use them to choose from multiple different options while they remain uncertain about the goal.

#### current progress in reinforcement learning
Improved RL agents may look like dangerous long-term goal-directed agents, but there are several difficulities are restricting the current RL algorithms:
* current RL agents just replay the behaviour in their past experience
* current RL is episodic, if we want to make them goal-directed, we need to collect many full episodes and it would be extremely time-consuming
* the performace of RL agents trained in partial trajectories relies on the generalization ability

#### Existing intelligent agents are goal-directed
Even when we suppose that humans and perhaps are examples of goal-directed intelligent agents, we can't make sure that general intelligent agents must be goal-directed. Because:
* the number of observed samples is only 2 (when we believe that animals are also intelligent) or 1
* both humans and animals are created by evolution, which did a relatively stupid blind search over large spaces

#### Interpretability
An argument for building a goal-directed agent is that it allows us to predict what it's going to do in novel circumstances.

Here I agree with the author because I also can't understand what can we do with this kind of interpretability.

<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>
<script type="text/x-mathjax-config">
  MathJax.Hub.Config({ tex2jax: {inlineMath: [['$', '$']]}, messageStyle: "none" });
</script>