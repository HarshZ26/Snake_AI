# Snake game AI

#### Created in [Gym-Snake](https://github.com/grantsrb/Gym-Snake.git) environment.

## Description
![](https://i.imgur.com/DLDVj7C.gif)


It is an attempt to solve classic snake game using Reinforcement learning Tabular method i.e Q-learning.

## Implementation
### Action Space
One important thing to note is that all the actions and directions are relative to snake's head. They are related by following relation-

Current Directions(as mentioned in snakeEnv)-

	UP - 0
	RIGHT - 1
	DOWN - 2
	LEFT -4
	
New relative actions-
	
	LEFT - d-1
	RIGHT - d+1
	FORWARD -d 
	BACKWARD - abs(d-2)
where d is the direction of snake's head wrt. environment. All the exceptions are handled for particular direction.For example- if a head is facing UP , so relatively LEFT action must be 3 not -1. Similarly other exceptions are handled. 
### State Space
State-space is visualized as 4-D array which tells information about environment. First is direction of food wrt. snake's head.
Other three tells about presence of obstacle adjacent to snake's head in all three directions.

	0 - Obstacle or wall
	1 - Free space

### Reward function
* +1 for eating the food
* -1 for hitting with wall or its body

Except above two conditions by default value of reward function is 0.

### Algorithm
Off-policy learning method namely Q-learning is used to train agent. While following it's behaviour policy μ(a|s), it evaluates optimal policy π(a|s) to get optimal Q(s,a) values.

## Results
### Training
![](https://i.imgur.com/BUzFVQv.png)



### Testing
![](https://i.imgur.com/lqs13Rz.png)

## Limitations
* With this approach optimal policy cannot be obtained because snake's obstacle avoidance logic can dodge only immediate obstacles.
* Since the agent can only see its immediate obstacles, there are high possibilities of agent being entangled in a loop which results in death after few steps.
# Environment

#### Created in response to OpenAI's [Requests for Research 2.0](https://blog.openai.com/requests-for-research-2/)

## Description
gym-snake is a multi-agent implementation of the classic game [snake](https://www.youtube.com/watch?v=wDbTP0B94AM) that is made as an OpenAI gym environment.

The two environments this repo offers are snake-v0 and snake-plural-v0. snake-v0 is the classic snake game. See the section on SnakeEnv for more details. snake-plural-v0 is a version of snake with multiple snakes and multiple snake foods on the map. See the section on SnakeExtraHardEnv for more details. 

Many of the aspects of the game can be changed for both environments. See the Game Details section for specifics.

## Dependencies
- pip
- gym
- numpy
- matplotlib

## Installation
1. Clone this repository
2. Navigate to the cloned repository
3. Run command `$ pip install -e ./`


