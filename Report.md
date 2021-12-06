# Learning Algorithm 
For this project, I chose the second version environment, that is, the Unity Reacher environment with 20 agents. If you take a look at the video on the Unity Reacher environment, you will realize that all the robotic arms are independent and identical, that is, they are exposed to the same type of environment and make decisions independently. This multi-agent framework can be reduced to a single agent framework if the agent is designed to take 20 independent actions for 20 independently given states. 
Deep Deterministic Policy Gradient (DDPG) is an actor-critic method that takes advantage of both the policy-based method and the value-based method. Moreover, as its name suggests, it uses a deterministic policy instead of a stochastic policy. 
These facts made me to make a few minor changes to the previous project’s learning algorithm. 
1.	Add a policy network to `model.py`: DDPG is an actor-critic method where the actor network estimates the policy, and the critic network evaluates the policy produced by the actor using the Q function. Thus, `model.py` in project 2 has two networks.
2.	Ornstein–Uhlenbeck noise: DDPG uses deterministic policies. Thus, in order to avoid exploitation-exploration dilemma, we need to add a noise to the action selection process. This project uses the Ornstein–Uhlenbeck noise, which is described in `class` `OUNoise` in `ddpg_agent.py`
3.	Multi-agent framework: In order to embrace multiple agents, the variable `agent_size` is added to `class` `Agent()` in `ddpg_agent.py`.

# Ideas for Future Work
I want to try soft actor-critic method for future work. Unlike DDPG, which use deterministic policies, soft actor-critic uses a stochastic policy. Moreover, soft actor-critic model works in a similar manner to temporal difference approach. The critic in soft actor-critic model uses both the Q function and the value function. Thus, it might provide better performance compared to DDPG.
