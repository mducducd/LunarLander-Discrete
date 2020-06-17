# LunarLander-Discrete
# Project Details

The interaction with the environment is based on the following four discrete actions:

1. do nothing
2. fire left orientation engine
3. fire main engine
4. fire right orientation engine.

The environment returns the state vector, where the first two comprises coordinates. The episode finishes if the lander crashes or comes to rest. LunarLander-v2 defines "solving" as getting an average reward of 200 over 100 consecutive trials. The environment is solved by using DQN algorithm

# Getting Started

In order to train the model or inference the computed weights, the following need to be installed:

pytorch
pybox2d
gym

# Instructions

Since the repository provides the jupyter notebook, follow the steps of execution.
