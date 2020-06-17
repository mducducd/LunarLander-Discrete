# LunarLander-Discrete

# The description of the task

Landing pad is always at coordinates (0,0). Coordinates are the first two numbers in state vector. Reward for moving from the top of the screen to landing pad and zero speed is about 100..140 points. If lander moves away from landing pad it loses reward back. Episode finishes if the lander crashes or comes to rest, receiving additional -100 or +100 points. Each leg ground contact is +10. Firing main engine is -0.3 points each frame. Solved is 200 points. Landing outside landing pad is possible. Fuel is infinite, so an agent can learn to fly and then land on its first attempt. Four discrete actions available: do nothing, fire left orientation engine, fire main engine, fire right orientation engine.

Source: https://gym.openai.com/envs/LunarLander-v2/

# DQN Algorithm
The deep Q-learning algorithm that includes experience replay and ϵ-greedy exploration is as follows:
```
initialize replay memory R
initialize action-value function Q (with random weights)
observe initial state s
repeat
	select an action a
		with probability ϵ select a random action
		otherwise select a= argmaxa′Q(s,a′)
	carry out action a
	observe reward rr and new state s’
	store experience <s,a,r,s> in replay memory R
	sample random transitions <ss,aa,rr,ss′>from replay memory R
	calculate target for each minibatch transition
		if ss’ is terminal state then tt =rr otherwise tt =rr + γmaxa′Q(ss′,aa′)
	train the Q network using (tt−Q(ss,aa))2 as loss
	s=s′
until terminated
```
# Project Details

The interaction with the environment is based on the following four discrete actions:

1. do nothing
2. fire left orientation engine
3. fire main engine
4. fire right orientation engine.

The environment returns the state vector, where the first two comprises coordinates. The episode finishes if the lander crashes or comes to rest. LunarLander-v2 defines "solving" as getting an average reward of 200 over 100 consecutive trials. The environment is solved by using DQN algorithm

# Getting Started

In order to train the model or inference the computed weights, the following need to be installed:
* pytorch
* pybox2d
* gym

# Instructions

Since the repository provides the jupyter notebook, follow the steps of execution.
