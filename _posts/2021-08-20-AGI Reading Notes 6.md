Some other topics about AGI safety.
# Embedded Agents
When we want to build an agents to achieve some goals in real world, we don't even know what does it means. There are two kinds of agents easy to understand. They are dualistic because they exist outdise of their environment. The only thing they need to do is choosing actions based on the obseravtion and the model of environment to achieve highest reward.

For an agent which is playing in the real world, it doesn't have well-defined i/o channels. It is smaller than the environment so it's impossible to store an accurate detailed world model within it. It's able to reason about itself and self-improve. It is made of parts similar to the environment. 

The author splits the topic into four subproblems. Decision thoery is about embedded optimization. In this case, we don't have a clear thoery to answer what optimization means here. Embedde world-model is about how to make a good world-model that are able to fit within an agent that is much smaller than the world. Robust delegation is about how to deal with the more intelligent sucessor. Subsystem alignment is about how to have a base-optimizer that doesn't spin up adversarial optimizers.

In conclusion, embedded agency is a different field with previous paradigm. When we can't regard agent and the environment as two individual parts, there are many things waiting to define and to explore.

# Zoom In: An Introduction to Circuits
Many important points in the history of science have been moments when science zoomed in. In the history of biology, the point is when we beagn to observe cells. Most work on interpretability aims to give simple explanations of an entire neural network's behavior, but the author think we should check each neron and even each weight carefully to zoom in.

Like the three claims about cells, the author proposed three claims about nerual networks. First, features are the fundamental unit of neural networks. They correspond to directions. These features can be rigorously studied and understand. Second, features are connected by weights, form circuits. These circuits can also be rigorously studied and understood. At last, analogous features and circuits form across models and tasks.

The researchers studying interpretablity have struggled for a long time. There isn't method to evaluate their results. Unlike other works, the claim of circuits can be rigiously checked. If we can understand circuits well, it will be useful for us explain the behavior of neural networks.