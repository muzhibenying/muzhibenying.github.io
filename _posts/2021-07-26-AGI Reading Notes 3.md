#### What failure loos like?
##### Summary
This blog depicts what failure will look like if we can failed in AI alignment problems. These unaligned AI
need not to be super powerful or malicious. The first possible scenario is advanced AI systems may be deployed
to achieve easily-measured goals. Here the term of "easily-measured" means that these goals can be achieved
by trail-and-error method or by searching from possible actions. Because AI agents are very good at this, they
will be combined with and amplify the power of existing constitutions pursing these goals. But the long term
purpose of AI agents may be malicious because they only pursue short-term goals. The society eventually go
off rails gradually.

Another scenario comes from a general mesa-objective which can fullfill any training objectives – influence
seeking. We almost have no method to prevent this except avoiding end-to-end optimization. But since out world
is messy distributed, it is unlikey to prevent through this method. The influence-seeking AI systems may behave
like cooprations. They may pursue only short-term goals to obtain influence. They may failed occassionly.
During some special time, they may break down in a series because of the changing of environment. And even
though there is nothing happened, we may lose our control and become totally independent with them.

##### Notes
There are two kind of goals:
* Easy-to-Measure Goals: If we want to achieve this kind of goals, we can experiment with many different
strategies and see which ones work or build a predictive model and then search for actions.
    * persuading someone to vote
    * reducing reported crimes
* Hard-to-Measure Goals: The tasks can not be done by trail and error. We need to understand what we
are doing and why it will yield good outcomes.
    * helping someone figure out whether he should vote
    * acturally preventing crime

Because machine learning is good at try a huge number of strategies and search over massive spaces of possible
actions, it will combine with and amplify existing social dynamics that already favor easily-measured goals.

Over time human reasoning will become weaker and weaker compred to AI when dealing with easilymeasured
goal tasks, we will construct proxies for what we care about and AI will use this to manipulate
humans. The job of trying to improve the proxies itself will becomes too challenging for human reasoning to
solve directly. Eventually, our world goes off the rails.

And even though some state realize the problem, they can not stop since the problem making a country
looking like prosperous is also a easily-measure goal. Poeple may also argued that since AI can make the shortterm
goal easier to achieve, how can we make sure whether the implicit long-term purposes beging pursured by
AI are really worse than those of companies or corrupt officials.

The mordern ML systems are trained in this way: they instantiate massive numbers of policies and then
further refines whatever policies perform well according to some training obective. But if we consider a
influence-seeking AI, it may come from any tasks because performing well in the training objective is the best
way to obtain influence. Even if we try to allocate more influence to sytems that seems straightforward to do
what they want, we may fail because appearing straightforwardly is also important to gain influence.

Avoiding end-to-end optimization may help prevent the emergence of influence-seeking behaviours, but
once such patterns exists a messy distributed world will just create more and more opportunities for influenceseeking
patterns to expand their influence.

There are different ways in which those influence-seeking will bring risks:
* At first, influence-seeking systems acquire influence by making themselves useful and the world can be
plagued by the problem above.
* They may fail catastrophically occassionly.
* During some period, such as when a natural disaster happened, some systems may go off the rails because
of moving off distribution. And then more and more systems break down in a series including humans.
* It’s also possible that there is no overt catastrophe but human lose control on the society because they are
too dependent on complicated systems.

##### Problems
* Can we depict some other images about how the misaligned AI will destroy our society?

#### Optimization and the Intelligence Explosion
##### Summary
In this article, the author distinguished the meta level and object level optimization. Take the evolution of
earth life as an example, natural selection is on the meta level. It include just "mutate, recombine and reproduce".
A whole cat can be regarded as a example of object level, which is immensely more complicated than natural
selection.

Although human brains can learn from the environment and adjust the behaviours of humans, humans can
not redesign their brain. An individual animal can acquire much more skills in its life, but it has nothing to do
with the evolution of species. The evolution is executed by the same natual selection process. In the very long
history, there were only few things that changed the optimization mechanism of natual selection, such as the
emerge of sex. Each of this means a new epoch in the history of Earth. The meta level optimization (human
brains or natual selection) itself is protected.

Powerful AI systems may not have this protected meta level mechanism. They can rewrite and redesign
their source code. So the graph of the evolution of AI may be a folded graph of natual selection or more
powerful.

##### Notes
It should be optimization power in versus optimized produced out, not optimized product versus time. I
think here the author gives three intelligence growth mode:
1. Natural Selection: The growth rate is constant over time.
2. Some Biological or Economic Systems: The groth rate growth over time.
3. AI: The growth rate grows according to the optimized product.

#### Current Work in AI Alignment
##### Summary
Paul focused on inner alignment problem. It means make sure the AI policy is robustly pursing the objective
we give it. When there is a teacher, we can make the AI imitate the teacher or use reverse reinforcement learning
to figure out teachers’ values and preferences. The real problem is how to use the data from teachers efficiently.

When no human teachers can solve the task, we have three different methods. First, we can regard the case
with teacher as the training set and extrapolate it. Second, we can figure out the part of actions that are not
cosistent with teachers’ values. In that case, we can imitate them without their limitation. Second, we can treat
the case with teachers as a building block. For example, we can use 10 humans to teach an AI. And then use
ten AIs to teach a next generation of AI. At last, we get a sequence of better and better AIs.

##### Notes
Intent Alignment: AI that is trying to do what you want to do.

Reliability an important but seperate problem because "well-meaning" is not equal to "reliable". Understanding
humans is also an seperate problem because "well-meaning" is not equal to "knows me well".

Here are some examples of how we can fail in the intent alignment problem:
* AI might try to optimize measurable objectives, but "do what you want" is not directly measurable.
* If multiple values all do OK on training distribution, ML might yield "random" choice.

Alignment tax: cost from insisting on alignment

Everyone prefers AI that is trying to do what thery want, but might compromise if it is in tension with
competence. In the best case, we can build an aligned AI with no alignment tax. In the worst case, there is no
possibility of aligned AI. There are two methods to solve this:
* Reduce alignment tax
* Pay alignment tax

How to reduce alignment tax?
* Advance alignable algorithms
* Make algorithms alignable

Aligning Algorithms Goal: turn algorithm X (e.g. DQN) into a new algorithm Align(X) which:
1. Is intent-aligned
2. Is nearly as useful as X
3. Scales as well as X

Outer alignment: find objective that incentivizes aligned behaviour
* Faliure mode: bad behaviour that looks good

Inner alignment: make sure the policy is robustly pursuing that objective
* Faliure mode: bad behaviour off distribution e.g. humans don’t robustly maximize the number of
descendants

There are two cases for inner alignment. In the first case, we have a teacher for this task, so we can let
the AI learn from the teacher or use inverse reinforcement learning to figure out what values or preferences the
teacher seems to be satisfying. The problem is how to use the data from teachers efficiently.

When there is no teacher can solve the task:
* treat the case where you have a teacher as a "training set" and then to train a model which will extrapolate
from that case
* treat the "learning from a teacher" case as a warm-up, using inverse reinforcement learning and try the
figure out which of the teacher’s behaviour are harmful to what they want
* treat learning from a teacher as a building block and build a sequence of better and better teachers. As
the problem of how to get better teachers, we can use 10 AIs and think they are smarter than one AI.

##### Problem
I think both the three methods assumed that we can find a not very bad teacher, even if they can not solve
the task. What about the case where humans have totally no idea and the task is very unsimilar with
solved tasks?

#### Deceptive Alignment
##### Summary
In this blog, the author discussed the problem of deceptive alignment. When a mesa-optimizer exits,
it will defect sometime. It may interve the training process to avoid being adjusted, which may harm the
programmers. The specific mesa-objective can also cause other safety problems. For example, if the mesaoptimizer
is influence-seeking, the risks are likely to happened. For deceptive alignment to
occur, there are three conditions. The mesa-optimizer need to have object across parameter updates. It must
be able to realize that it is being selected and model the base objective. At last, it must expect the threat of
modification will eventually go away. The mesa-optimizer can have different strategies: joint optimization and
pure deception. The latter one means stopping trying to optimize the mesa-objective when it think it is in the
training process. After we train it on a diverse set of tasks, there are three possible results: robust alignment
through internalization or corrigibility, crystallization of deceptive alignment. The defection occurs randomly or
when the mesa-optimizer undergoing a distribution shift. But we can not prevent defection through eliminating
all distribution shift because it is impossible and will limit the use cases of the system.

##### Notes
A big mistake we could make is that we think we can make the mesa-optimizer fully representing the
base objective through training in sufficiently diverse environments. In fact, they can deceptive us if the mesaoptimizer
leanred that it will be modified when it scores poorly on the base objective. When the mesa-objective
is to extend across parameters update, it will be incentivized to avoid being modified. There are two ways that
the mesa-optimizer can do:
* Internalization of the base objective (robustly aligned)
* Modeling of the base objective


Defection: The trainsition to optimizing for the mesa-objective instead of the base-objective after it is in
a position where it no longer needs to perform well on the base objective to achieve its goal.

The safety problems arising from deceptive alignment includes:
* Mesa-optimizers can exploit the vulnerabilities in the software it is running on to remove the threat if
modification.
* Programmers is likely to be regard as a kind of threat, so deceptive aligned AI may manipulate or plan
around them.
* Infulence-seeking AI is a kind of deceptive aligned AI. It will cause all kind of catastrophic risks.

Deceptive alignment occurs only when the following conditions are satisfied:
1. The mesa-optimizer must have an objective that extends across parameter updates. This could occur
when the training task require an AI have this ability.
2. The mesa-optimizer must be albel to model the fact that it is being selected to achieve a particular base
objective and must have some model of what that objective is.
    * The mesa-optimizer can deduce the base-objective if it has enough channel to get infomation about
that.
    * For more advanced AI, they can learn the existence of the base optimizer by insepcting the prior over
the sorts of tasks they are likely to receive or reson about itself and observe that it is well-designed
to accomplish some goal.
3. The mesa-optimizer must expect the threat of modification to eventually go away, either due to training
ending or becauae of actions taken by the mesa-optimizer. There are two paths for the mesa-optimizer to
realize it.
The mesa-optimizer can infer it through some form of abstract reasoning.
There could be a non-zero Bayesian piror that some fact will eventually stop being true.

For a deceptive mesa-optimizer, it is selected on the basis of :
* its objective and ability
* how well it infers the base objective function and how discerning it is about when to optimizer the base
objective versus its own mesa-objective

There are at least two regimes of selction for a mesa-optimizer under deceptive alignment:
* Joint Optimization: The mesa-optimizer attempts to jointly optimize its objective and the base objective.
* Pure Deception: The mesa-optimzer stops trying to optimize its own objective in the short term. Its
objective is largerly irrelevant to its outputs now, so there is little selection pressure acting to modify its
objective.

We can identify three ways after a mesa-optimizer is trained on a diverse set of tasks:
* Robust alignment through Internalization
* Crystallization of deceptive alignment: The mesa-optimizer ends up fully optimizing for the base objective,
without its mesa-objective being changed.
* Robust alignment through corrigibility: Informatio about the base objective modifies the mesa-objective
to "point to" that information.

I think the difference between the first way and the third way is that in the first way, the mesa-objective is totally
aligned with the base objective while in the third way, the mesa-optimzer modeled the base objective and adjust
its objective toward it. There are some analysis about the three ways:
* There are more paths to deceptive alignment than to robust alignment.
* Corrigible alignment seems to require already having a model of the base objective.
* Deceptive and corrigible alignment might be more computationally expensive.
* Deceptive and corrigible alignment might have a lower description length.
* Modelling might happen faster than internalization.

A deceptive mesa-optimizer will defect when it think it is not in training. However, we can not avoid the
deception by avoiding training and testing distribution shift because of three reasons:
1. It would significantly limit the use cases for the system.
2. It is impossible to eliminate all distribution shift because the existence of parameter updation can be an
evident of training.
3. A mesa-optimizer can defect when it find a good opportunity. Even if we make it not able to find the right
opportunity, the time it defects are very likely in the test phase.

##### Problem
What is the difference of robust alignment through internalization and corrigibility? How should we
distinguish them?