### Technical blog on Animal-AI Olympics

Animal-AI Olympics is introduced with the aim of building AI-agent capable of showing some basic cognitive capabilities found in animal species. The mapping from animal’s behavior to the AI-agent action is not straight forward. Tests in animal cognition are focused on some common traits such as Vision, Navigation and Food Retrieval. These tests can be converted to modern machine learning systems; artificial agents can convert visual information into navigation-type of behavior.

The tasks in Animal Olympics are designed in such a way that some tasks require knowledge of basic cognition which can be solved by Reinforcement Learning, some other tasks require knowledge of “higher cognition”. It would be interesting to find out if learning algorithm can go beyond basic learning and into something which is called “general intelligence”.

The Animal-AI Olympics with present AI with tasks that are unknown immediately prior to testing. Every possible configuration of environment could be considered part of the data set. However, the test set is not simply a sampling from all possible configurations. The test set is designed to have very small percentage of possible configuration, yet it will test for the cognitive abilities that biological entities possess.

There are different categories of tasks that an agent is expected to solve in this Olympics. They are:

**Food**: This category tests agent’s ability to retrieve food. Food item provides positive reward for the agent.
![Food](/images/animal_ai_blog/1-Food.png)

**Preferences**: This category tests if an agent prefers one action to another action because of maximized reward it will gain.
![Preferences](/images/animal_ai_blog/2-Preferences.png)

**Obstacles**: The environment of this category will contain immovable objects which might impede agent’s navigation. This category tests agent’s exploration ability.
![Obstacles](/images/animal_ai_blog/3-Obstacles.png)

**Avoidance**: This category tests agent’s ability to avoid certain objects or areas that bring negative rewards or cause death to the agent. Agent may also have to push certain movable objects during exploration.
![Avoidance](/images/animal_ai_blog/4-Avoidance.png)

**Spatial Reasoning**: In this type of environment, agent has to learn explore environment in restricted mood. It also tests agent’s memory of exploration, and understanding of gravity.
![Spatial Reasoning](/images/animal_ai_blog/5-SpatialReasoning.png)

**Generalization**: In this type of environment, certain objects that had certain colors may not have those colors. Colors and shapes can change. So, it tests agent’s ability to generalize environment configuration.
![Generalization](/images/animal_ai_blog/6-Generalization.png)

Some other categories are Internal models, Object permanence, Advanced preferences, and Causal Reasoning. Description of all of these categories can be found at [here](https://www.mdcrosby.com/blog/animalaieval.html) and [here]( https://mdcrosby.com/blog/animalai2.html).



