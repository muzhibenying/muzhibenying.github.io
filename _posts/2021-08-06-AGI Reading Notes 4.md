People have different interpretations of the goal "learn what I want":

* The AI learns humans' preferences over (very) long-term outcomes.
* The AI learns the narrower subgoals and instrumental values humans' are pursuing.

<span style = "color:purple">So the preference model of humans can not make sure what humans really want to do. It dependens on the timescale we are talking.</span>

### The ambitious apprpach
The author did not write a clear definition of the ambitious approach. I think it is about developing an AI which can always pursue long-term benefial goals for us.

Because it requires the AI understand humans real preferences in domains where humans are very uncertain, most researchers dod not think it as a practical research goal.

### The narrow approach
The narrow approach means we want to build machines that:

* be able to understand what we are trying to do and what instrumental values guide our behavior
* at least do as well as a human when the "preferences" of humans are underdetermined or inconsistent, and can make kinds of reliable improvements

## In Defense of the Narrow Approach
### Instrumental goals
AI agents can learn those clear instrumentabl goals like "remaining in effective control of the AI systems I deploy". This requires learning robust formulations of concepts like "effective control", but we can escape cases where humans have conflicting intuitions.
### Process
It is hard to infer human preferences over very long distant object, but AI might be able to infer human preferences well enough to guide a process of deliberation without understanding of the big-picture values.

<span style = "color: purple">Could it be possible to infer human preferences when the AI do not know the final objective? For example, if a player is playing chess, he may sacrifice some of its pieces. How can the AI decide whether the person makes a real mistake or not.</span>

Such a process of error-corrected deliberation could be used a more robust definition of values.

### Bootstrapping
When AI can only help us achieve short-term goals, we can potentially form and execute very sophisticated plans with their assistance.

## Summary
People have many different interpretations about the goal of "learning what I want". The most extreme cases are AI should help us achieve goals which are long-term beneficial and AI should pursue our short-term subgoals or insuturmental values. Because there are many cases where humans' long-term goals are undertermined or inconsistent, it seems impossible for the ambitious approach. However, the narrow approach has its values. The narrow approach means AI agents can understand people's perferences or do at least as well as humans when the long-term prefernces are undertermined or inconsistent.

There are at least three ways the narrow approach can help us. First, AI agents can learn instrumental goals like "keep AI in the effective control of humans". These goals are always determined and consistent. Secondly, if they can infer the preferences in a process of deliberation, they can be used as a error-correction model when people take action which is harmful to their short-term goals in their deliberation procss. At last, people might be able to form and carry out complex plans with the help of AI assitants.

## Problem
<span style = "color: red">My biggest question is how we can know about short-term goals in a deliberation process? Suppose we trying to play a game where we have to deal with many kinds of resources to defeat another one, I think what the AI can do is like it can help us find strateges to maximize the production of copper. So humans have to think out a optimal plan about subgoals in each stage of the game. However, will how can we know our subgoals clearly to avoid the AI task extreme actions?</span>

# Flint's Summary of Assistance Games
## Assistance Games
Traditionally, information about the human's objective are transmitted to the machine via a one-time data dump, after which it remains fixed all the time, but in many cases humans are not able to capture everything they care about in a formal metric. 

Assistance game is where the human wants something from the machine and it is the machine's job to both figure what it is and fufill it. 

The old model, cooperative inverse reinforcement learning (CIRL) and reinforcement are three examples of the assistance game.

## Going beyond Agents
A strong assumption in previous researchs is that both the human and the machine are well-modelled as having objectives.

If we want to build a machine that provides assistance to a rainforest, the rainforest have no objectives. Humans are not perfectlly modelled as agents. Machines are not ideal agent either. Because any AI deployed on real hardware in the real world is made of the same basic building blocks as the world itself, and is only approximately modelled as an agent with a set of objectives.

## Summary
Traditionally, we model the human and the machine as both agents with objectives. The human's objective is transmitted to the machine entriely before the training. Because it is difficult for the human to capture all information about its objective into a formal metric, the capability of the machine is limited. Assistance game where the machine have to deduce what is the human's objective and fulfill it is a broader research field. The traditional model, CIRL, RL are three examples of assistance games. However, we can still relax the assumption because the human and the machine are both not well-modelled agents. Sometimes we need the machine to be an assistant of some systems, like a rainforest, which have no objectives.

## Problem
<span style = "color: red">What does the agent mean here? I think it means a system having clearly defined objectives. Why the author says humans are made of the same basic building blocks as the world around them so agent is only an approximate description of the human?</span>

# Learning from Human Preferences
Removing the need for humans to write goal functions will be good at building safe AI systems. Becuase using a simple proxy for a complex goal can lead to undesirable and even dangerous behavior.

There are simple tasks which is challenge to specify, such as teach the AI to learn to backflip.s

* The AI agent start by acting randomly in the environment.
* Two video clips are given to a human, and the human decides which one is closest to fulfuill its goal.
* The AI builds a model of the goal of the task by finding the reward function that best explain the human's judgement.
* It uses RL to learn how to achieve that goal.
* It continues to ask for human feedback on pairs where it is most uncertain to refine its understanding of the goal.

## Challenges
The algorithm's performance is only as good as the human evaluator's intuition about what behaviors look correct.

## Summary
Human designed goal function is often only a proxy of the complex goal. This can lead to undesirable and even dangerous behaviors. In this paper, the goal of the AI agent is learning to backflip. At first, the agent took actions randomly. The video clips of its action were presented to humans and they decide which clip is close to the goal. The AI agent would use this feedback to model what the goal is in a form of reward function. RL then taught the agent how to achieve the goal. After that, the agent would continue to ask humans on the clips where it is most uncertain about whether the action is good to refine its goal model.

The challenge is there are many cases where humans can not decide which behavior is correct.

## Problem
<span style = "color: red">Every time when we want to define something or evaluate something, we encounter difficiluties. It seems we can not define the goal, we can not define the reward function and can not define what behavior is right. If we are facing a task, where we can not evaluate at all, like the life of person (we can not decide what means success, money, happiness, length), how should we design the assistant?</span>