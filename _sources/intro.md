# Introduction to Reinforcement Learning

## What is reinforcement learning?
Reinforcement Learning is a study of agents and how they learn by trial and error. An agent takes an action and recieves a reward/punishment which makes the agent more likely to repeat or forgo that behaviour in the future.

## Key Concepts
The main characters in Reinforcement Learning are the agent and the environment. Environment is the world that the agent interacts with. At every step, the agent sees an observation(maybe partial)
of the state of the environment and decides to take an action. The action changes the state of the environment and the agent recieves a reward signal. The reward signal tells the agent how good or bad the current state of the environment is. The goal of the agent is to maximize the cumulative reward (also called **return**).

### State
A state s, is a complete description of the world. An observation is a partial description of the state which may remove some information from the state. An example of a state would be joint angles and velocities of a robot or an RGB matrix of pixel values in case of atari games. When the agent is able to observe complete state of the environment, the environment is fully observable; while if the agent can only observe a partial observation, that environment is partially observable.

### Action space
An action space is a set of valid actions in an environment. Some environments have **discrete action space** where there are only a finite number of actions available to the agent. Other more complex environments like robot navigation in a physical world may have **continuous action space** where there are a lot of actions to choose from. In a continuous action space environment, the actions are represented by real-valued vectors.

### Policy
A policy is a rule used by an agent to decide what action to take. A policy can be **deterministic** or **stochastic**.  A **deterministic policy** allows the agent to decide an action using only an observation of the state of the environment. It is denoted by $\mu$. The action taken on a deterministic policy can be written as
        $
            a_t = \mu(s_t)
        $

A stochastic policy on the other hand needs random samples of trajectories from the current state in order to decide the action. It is denoted by $\pi$. The action taken on a stochastic policy can be written as
        $
            a_t \sim \pi(.|s_t)
        $
        
There are **parameterized** versions of deterministic and stochastic policies as well. Output of a parameterized policy is a function that depends on a set of parameters which we can adjust to change the behaviour. The parameters are geenrally denoted by $\phi$ or $\theta$ and the action taken on the parameterized policy is defined as  $a_t = \mu_{\theta}(s_t)$ in case of deterministic policy and  $a_t\sim \pi_{\theta}(.|s_t)$ in case of stochastic policy.

#### Deterministic Policy
A deteministic policy has a finite number of actions that can be taken from a given state. Here we are totally certain choose a particular action $a$ in an aribtrary state $s$. Deterministic policy can be written in the form $\pi(s): S -> A$ 