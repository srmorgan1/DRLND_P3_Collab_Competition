[//]: # (Image References)

[image1]: https://user-images.githubusercontent.com/10624937/42135623-e770e354-7d12-11e8-998d-29fc74429ca2.gif "Trained Agent"
[image2]: https://user-images.githubusercontent.com/10624937/42135622-e55fb586-7d12-11e8-8a54-3c31da15a90a.gif "Soccer"

# Multi-Agent DDPG - Tennis

This is the final project from the Udacity **Deep Reinforcement Learning Nanodegree**.

### Introduction

For this project, we will work with the Unity [Tennis](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#tennis) environment.

![Trained Agent][image1]

This deep reinforcement learning study trains two agents to play tennis cooperatively with each other, using the Unity Tennis environment
to simulate the tennis physics. The agents are rewarded for keeping the ball in play as long as possible.

In this environment, the two agents control rackets to bounce a ball over a net. If an agent hits the ball over the net, it receives a reward of +0.1.  If an agent lets a ball hit the ground or hits the ball out of bounds, it receives a reward (penalty) of -0.01.  Thus, the goal of each agent is to keep the ball in play. The agents act to achieve this goal independently but their individual goals are such that the
result is cooperative play.

### Solving the Environment

The observation space consists of 8 variables corresponding to the position and velocity of the ball and racket. Each agent receives its own, local observation of reward, along with the velocity and position of both agents and the ball. Two continuous actions are available,
corresponding to movement toward or away from the net, and jumping.

The task is episodic, and in order to solve the environment, the agents must get an average score of +0.5 (over 100 consecutive episodes, after taking the maximum over both agents). Specifically,

- After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 2 (potentially different) scores. We then take the maximum of these 2 scores.
- This yields a single **score** for each episode.

The average of this score over 100 consecutive episodes must exceed +0.5.

### Setup Instructions

You need to set up the following dependencies to run the MADDPG model.

1. Install the <a href="https://www.anaconda.com/download/">Anaconda distribution of Python 3.</a>

2. Install PyTorch, Jupyter Notebook and Numpy in the Python3 environment.

3. Clone the <a href="https://github.com/udacity/deep-reinforcement-learning">Udacity DRLND repo</a> and install the dependencies as follows:

    git clone https://github.com/udacity/deep-reinforcement-learning.git

    cd deep-reinforcement-learning/python

    pip install .

4. If you will be running the code on the Udacity server, the Tennis.ipynb notebook is already set up to use the Tennis environment
   already present on the server. Otherwise follow the instructions below if you plan to run it on your local machine.
   a. Download the environment from one of the links below.  You need only select the environment that matches your operating system:
    - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Linux.zip)
    - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis.app.zip)
    - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86.zip)
    - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86_64.zip)
    
    (_For Windows users_) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

    (_For AWS_) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Linux_NoVis.zip) to obtain the "headless" version of the environment.  You will **not** be able to watch the agent without enabling a virtual screen, but you will be able to train the agent.  (_To watch the agent, you should follow the instructions to [enable a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md), and then download the environment for the **Linux** operating system above._)
    b. Place the file in the repository folder (the same folder as this README file is in) and unzip (or decompress) the file.

### Instructions To Run The Code

To run the project, open the Jupyter notebook file `Tennis.ipynb` by running the command below from the folder containing
the notebook:
`jupyter notebook` (or alternatively `jupyter lab`)

Then you can run the notebook by clicking the "Run" button, which will then train the collaborative ageents to solve the environment and
generate a graph of the training performance. If you are running on your local computer or on AWS with a virtual screen, the notebook will
also allow you to watch the trained agents in action, which can be done by loading the trained network weights in the four "checkpoint" files.