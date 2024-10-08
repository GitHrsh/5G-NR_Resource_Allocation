# 5G-NR Resource Allocation

Problem Statement:
How to optimize resource block allocation?
5G networks are intended to give users desired QoS. This poses requirements such as high data rates, low power consumption, low latency, better user exposure. Given the varying channel conditions, traffic due to expanding user equipment numbers and user requirements, it is necessary to perform optimal resource allocation to maximize QoS.

This problem is set up as a resource allocation problem
Statement: Given a 5G base station with limited number of RBs:
What is the best way to allocate a limited number RBs to Users
How to dynamically assign RBs to changing channel states
Finding an optimal tradeoff between throughput/total data rate and fairness

Set up:
A single Base station as a central agent allocating RBs to multiple users. The CSI of users dynamically changes.

### Approach 1: HNN
The first approach is made using a 2D Hopfield Neural Network. This NN was chosen as weights have to be explicitly set. Thus, using our previous convex function, as well as  a General Proportional Fairness factor, we can explicitly set weights to achieve a good tradeoff. We exploit the minimization of the HNN’s energy function to achieve optimization.
### Approach 2: DQN
The next approach involves the use of a DQN using Pytorch to learn optimal resource allocation. This approach sought to test the effectiveness of an RL algorithm in predicting resource requirements. The base station acts as the agent allocating RBs to UEs. The state contains channel conditions, channel gains, RB allocation status and previous allocation history. The reward is designed to reflect the performance of the network, maximizing data rates and ensuring fairness across UEs.

