# Final Year Project: Goal Conditioned Reinforcement Learning - Nanyang Technological University  
Latest updates from my Final Year Project dedicated at **Solving Sparse Reward Problem with Goal Conditioned Reinforcement Learning.** that I have completed during my Bachelors Degree at time at Nanyang Technological University. This is a year long-project done under the supervision of Professor Arvind Easwaran and Dr. Arambam James Singh. The following was the research objective given:

> Goal-conditioned reinforcement learning(GCRL) is a sub-field of RL where the objective is to train an agent to achieve multiple goals in an environment. The problem setting in GCRL is slightly different from a traditional RL setting where the agent only learns to maximize a long-term reward, such setting is considered to be a single goal setting. However, in GCRL with multiple goals, our aim is to develop an agent which can learn a more generalized behavior(or diverse skills) for the distribution of goals.

After a year of work, the conclusion of the project yielded positive results in the production of a novel algorithm for sub-goal generation to increase training efficiency in reward sparse environments. This new algorithm is not included in this doc for confidentially matters. However, it will be included now. This document contains a background about Goal Conditioned Reinforcement Learning and the problem of Sparse Rewards. Note that if you are a beginner to Reinforcement Learning, it will benefit you to know about basics of Reinforcement Learning before. There are countless learning resources available. Many of them are free too. I have also written a blog on Reinforcement Learning on my website that you can check out too. The following section describes the Sparse Reward Problem and the Goal Conditioned Reinforcement Learning.  

## Why Standard RL fails? The problem of Sparse Rewards 
Standard Reinforcement Learning is adept at playing games, solving mazes, etc. However, as the environments get increasingly complexed, these algorithms become too inefficient. Now what does a complex environment mean? There are many definitions of complex environments. For example, a complex environment can be characterized by the size of its state space, or its stochasticity. However, in this article, when I refer to complex environment, I will not be refering to these characteritistcs. In this article, a complex environment will be defined only by the reward sparsity(the ratio of states in an environment that yield a reward to the agent to states that yield no reward). In a typical sparse reward environment, there is only 1 state that provides a reward and this goal is too far away. Let's consider the following environment. In this environment, the agent has to arrive at the goal. If you already have experience with RL, you will understand how difficult it's for standard RL to arrive at this goal. But let me just explain once again. Standard RL depends on exploring the goal through exploring random moves. I want to put emphasis on the plurarity of moves. this is because to arrive at a goal, an agent must exhibit a specific set of moves. Not only that but these moves need to be in the correct order. So we rely on producing random moves that get thr agemt to its requried state. tje probability of this happening is veru low. While the premise of RL states that random moved help it to discover its goal, this is a very unstable process that relies on chance and luck. As environments become too reward sparse, the solution worsens. The chance to make the correct moves decreases. 

Unfortunately real life scenarios demand sparse reward environments. Real life tasks are concerned with meeting a goal. Either you meet a goal or you don't. For example, either a robot picks up box or it does not. Player solved the maze or it does not. There is no in between. In such environments, the reweard signal is binary. And the agent only receives this reward when it accomplishes the final goal. This is hard because the goa is too far and sparse. In real-life this might translate to something like asking a person to learn a programming language from scratch with no help provided in the form of key presses. This a very difficult process. How can we solve this problem? Do you have any ideas? For an analogy, think of a dream that you have, that seems impossible. You probably don't know how to accomplish this. What strategies will you use to reach your goal or at least realize the steps you will take to get there?


## Literature Solutions 
There are a number of intuitive solutions proposed in literature. I strongly recommend you to read them in your spare time. Each solution is inspired by a natural human way of thinking. In this section, I have gone through a list of very popular solutions in literature, their pros and cons and their usage. 


### Distance based reward shaping
This method involves designing an artificial reward function that rewards the agent for actions that get the agent closer to the goal. It is like equipping our agent with a compass. This compass howerver, is not the ordinary compass which always points to the North. Rather, it always points to the goal that the agent requires. If you have watched Pirates of the Carribean, then this compass is just like Captain Jack Sparrow's compass, aka Tia Dalma's compass. As our agent approaches closer to the goal, it gets an even higher reward. By doing so, the reward sparsity problem is eliminated because the agent receives a guiding reward at every time step. Thus, training efficiency is improved and standard algorithmms can be applied without any modification. In existing implemntations, researchers implement different metrics for measuring closeness to the goal. These include simple distance measures such as Manhattan Distance, euclidean distance, Wasserstein Distance, etc. This solution is a straightforward solution. However, it comes with a lot of flaws. Firstly, in real-life there is no existing compass that our agent can use. We humans have to design a compass. Now any form of human intervention during training that involves a human giving information or a human designed hard-coded module giving information defeats the purpose of renforcement learning. RL is designed to be autonomous. So we should focus on designing tasks that are autonomous and can perform on bare sparse environments. Another disdvantage is that reward shaping requires the agent to always know how to shape reward function.  

#### Pros
- Simple to implement
- No Change to algorithm
- Improve training efficiency

#### Cons
- Although straightforward, still requires humans to design a reward function
- New reward function introduces local optima problems
- Need to ensure that the reward functoin is optimum


### Hindsight Experience Replay

In the previous section on distance-based reward shaping, we saw a class of methods that artifically create a dense reward environment. However, these methods require magicial tools like Jack Sparrow's compass which are not available. Designing these tools is also problematic. Besides, we humans can still reach goals without such devices today. The way we do this is through intutiive strategies that are so important in learning. We start discussing these strategies by firstly talking about Hindsight Experience Replay. Hindsight Experience Replay is inspired from human decision making in cases of failures. In real life, when we encounter failure, we have the ability to reflect on the experience and understand how much we have gained? Although, we have failed in reaching the environment goal, we have at least been able to reach some state. We have at least gained some information. A great example of this could be some wonderful athletes.  

https://m.youtube.com/watch?v=xqa21aY7HIk&pp=ygUVTGVhcm5pbmcgZnJvbSBmYWlsdXJl

### Exploration Maximizatoin.


### Subgoal Generation


### 


in Progress 👨‍💻🚧
