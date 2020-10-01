[//]: # (Image References)

[video_random]: https://github.com/JavRodriPM/DDRLN-Project1-BananaCacher/misc/random_agent.gif "Random Agent"

[video_trained]: https://github.com/JavRodriPM/DDRLN-Project1-BananaCacher/misc/trained_agent.gif "Trained Agent"

# Project 1: Navigation

## Introduction

The purpose of this project is to train an agent to play in a plain squared Unity 3D environment to collect yellow bananas and avoid blue bananas. A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana.

The state space has 37 dimensions given by Unity, which contains the agent's velocity, along with ray-based perception of objects around the agent's forward direction. Given this information, the agent has to learn how to best select between the available action:
	0 - move forward.
	1 - move backward.
	2 - turn left.
	3 - turn right.


The task is episodic, and in order to solve the environment, your agent must get an average score of +13 over 100 consecutive episodes.

Here we have an example of how the agent behaves in random mode, and how it does after DRL-DQN implementation and training.


| Random agent             |  Trained agent |
:-------------------------:|:-------------------------:
![Random Agent][video_random]  |  ![Trained Agent][video_trained]


## Getting Started

1. Download the environment from one of the links below.  You need only select the environment that matches your operating system:
    - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux.zip)
    - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana.app.zip)
    - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86.zip)
    - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86_64.zip)
    
    (_For Windows users_) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

    (_For AWS_) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux_NoVis.zip) to obtain the environment.

2. Place the file in the project folder, decompress the file and then write the correct path in the argument for creating the environment under the noteboo`Navigation_solution.ipynb`:

```python
env = UnityEnvironment(file_name="[your drive]:/[Your path]/Banana.exe")

```

## Description

- `BananaDQNsetup.pth`: saved model weights for the original DQN model
- `BananaDDQNsetup.pth`: saved model weights for the Double DQN model
- `Navigation_exploration.ipynb`: explore the unity environment in random mode
- `Navigation_solution.ipynb`: notebook containing the solution of an RL agent trained to explore the unity envirnonment

## Instructions

Follow the instructions in `Navigation_solution.ipynb` to get started with training your own agent! 
To watch a trained smart agent, follow the instructions below:

- **DQN**: If you want to run the original DQN algorithm, use the checkpoint `dqn.pth` for loading the trained model. Also, choose the parameter `qnetwork` as `QNetwork` while defining the agent and the parameter `update_type` as `dqn`.
- **Double DQN**: If you want to run the Double DQN algorithm, use the checkpoint `ddqn.pth` for loading the trained model. Also, choose the parameter `qnetwork` as `QNetwork` while defining the agent and the parameter `update_type` as `double_dqn`.

## Enhancements

Several enhancements to the original DQN algorithm have also been incorporated:

- Double DQN [[Paper](https://arxiv.org/abs/1509.06461)]
- Experience replay 
- Pytoch LR optimizer

## Results

Plot and figures showing the score per episode over all the episodes and a summary of the figures. 
The environment was solved in **500** episodes.

 DQN | Double DQN
-------------------------|-------------------------
![dqn-scores](https://github.com/JavRodriPM/DRLNN-Project1-BananaCacher/tree/main/misc/dqn_scores.png) | ![double-dqn-scores](https://github.com/JavRodriPM/DRLNN-Project1-BananaCacher/tree/main/misc/ddqn_scores.png)

## Dependencies

You will need to install a standard python package as anaconda along with python pip package administrator in your computer along with the following dependencies.
Use the `requirements.txt` file (in the following(https://github.com/JavRodriPM/DDRLN-Project1-BananaCacher/) folder) to install the required dependencies via `pip` or follow the course instructions at: (https://github.com/udacity/deep-reinforcement-learning#dependencies).

```
pip install -r requirements.txt

```
