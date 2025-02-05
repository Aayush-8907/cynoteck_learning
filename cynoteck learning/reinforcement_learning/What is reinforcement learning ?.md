Reinforcement Learning (RL) is a type of machine learning where an agent learns to make decisions by interacting with an environment. The agent takes actions, receives rewards or penalties based on those actions, and improves its strategy over time to get more rewards.


## Task in Reinforcement learning 

There are two task in the reinforcement learning

- Episodic Task - 
	- The task consists of episodes with a clear ending.
	- The	agent learn from multiple episode to improve the decision-making.
	- The agent resets after each episode and starts fresh.
	- For example -
		- Playing a game(chess)

- Continuous Task - 
	- The task never ends, and the agent jeeps interacting with the environments indefinitely.
	- The goal is to mazimize rewards over an infinite time horizon
	- The agent continuously refines its policy without resetting
	-  For example - 
			- Balancing a robot on one leg

## Policy

The action perform by agent in each situation, this is learned by agent through trial and error 

### **Types of Policies**

1. **Deterministic Policy
    
    - Always selects the same action for a given state.
    - Example: If you're a self-driving car and always turn left at a specific intersection, your policy is deterministic.
    
2. **Stochastic Policy
    
    - Outputs a probability distribution over possible actions.
    - Example: In poker, an AI might choose to **bet, fold, or call** with different probabilities based on the situation.

## Environment

The environment is essentially the world in which the agent learns to make decisions based on feedback(rewards) from the actions it takes.

### Key Aspects of the Environment:

1. **State (s)**:
    
    - The **current condition** or situation of the environment.
    - For a self-driving car, the state could be the **position** of the car, **speed**, and **traffic conditions**.
2. **Action (a)**:
    
    - The agent’s **choices** that affect the environment.
    - In a self-driving car, possible actions might be **turn left, accelerate, brake, turn right**.
3. **Transition**:
    
    - The change in the state when the agent takes an action.
    - E.g., if the car accelerates, its state changes: it moves forward.
4. **Reward (r)**:
    
    - The feedback received by the agent after taking an action.
    - In the car example, the agent might get a positive reward for **staying in the lane** and a negative reward for **colliding with an obstacle**.
5. **Episode**:
    
    - In episodic tasks, the environment **resets** after reaching a goal or terminal state.
    - For a car, an episode might end when it reaches a destination or crashes.

## Value
In reinforcement learning (RL), value is a score that tells how good a state (situation) is. The higher the value, the better that state id

## All of the above concepts (states, actions, rewards, transitions, and policies) are part of the **Markov Decision Process (MDP)** framework, which is used to formally define the reinforcement learning problem.

### **The Markov Property**

The **Markov Property** means that **the future only depends on the current state and action**, not on the past history.  
In simple words:

- "The present tells you everything you need to know about the future."  
    For example, in the self-driving car, you don’t need to remember every traffic light you’ve seen in the past—just the current light matters.

## Model in Reinforcement Learning

The model is used to predict the future of the action taken by the agent.

- **Model-Based Learning**: The agent **uses a model** to simulate the future outcome of its actions. If the predicted outcome is good (positive feedback), it takes the action in the real environment; otherwise, it avoids it.
- **Model-Free Learning**: The agent has **no model** of the environment. It learns by directly taking actions, observing the rewards, and adjusting its strategy based on the results.