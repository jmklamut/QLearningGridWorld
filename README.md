# Q-Learning GridWorld Implementation

This repository contains an implementation of a GridWorld environment and a Q-learning algorithm for reinforcement learning experiments. The implementation explores different maps and evaluates Q-learning performance based on rewards and learned Q-values.

## Features

- **GridWorld Environment**: A grid-based environment where an agent starts at a predefined location and aims to reach the goal while avoiding holes.
- **Tabular Q-learning**: An implementation of Q-learning to update Q-values for state-action pairs.
- **Epsilon-Greedy Policy**: Action selection using an epsilon-greedy approach for balancing exploration and exploitation.
- **Visualization**: 
  - Plotting rewards per episode.
  - Visualizing Q-values for snapshots of learning progression.

## Code Structure

### GridWorld Class
The `GridWorld` class represents the environment. 

#### Key Methods:
- **`reset()`**: Resets the agent's position to the start location.
- **`step(action)`**: Executes the given action and returns the next state, reward, and whether the episode is done.
- **`print()`**: Displays the current state of the environment.

#### Features:
- Supports stochastic transitions.
- Configurable rewards for steps, goals, and falls.

### TabularTD Class
This class implements the Q-learning agent.

#### Key Methods:
- **`reset()`**: Initializes the Q-table.
- **`update(state, action, reward, next_state, done)`**: Updates Q-values based on the Bellman equation.

### EpsilonGreedyPolicy Function
Implements epsilon-greedy action selection. Balances exploration and exploitation based on a specified epsilon value.

## Maps
The project includes four maps with different complexities:
- **MAP1**: Simple 2x2 grid.
- **MAP2**: 5x5 grid with holes.
- **MAP3**: Larger grid with obstacles and holes.
- **MAP4**: Complex grid with multiple paths and stochastic transitions.

Each map is represented as a string with:
- `s`: Starting position
- `g`: Goal position
- `0`: Empty space
- `1`: Hole

## Experiments

### Q-Learning Parameters:
- Discount factor (`gamma`): `0.99`
- Learning rate (`alpha`): `0.1`
- Epsilon (`eps`): `0.1`

### Conducted Experiments:
1. **Reward Per Episode**:
   - Tracks total rewards obtained per episode for different maps.
2. **Q-value of Initial State**:
   - Tracks the Q-value of the initial state-action pair over episodes for MAP2.
3. **Q-value Snapshots**:
   - Visualizes max Q-values for MAP4 after specific numbers of episodes (e.g., 0, 10, 100, 500, 1000).

### Visualization:
- **Reward Plots**: Total rewards per episode.
- **Q-value Heatmaps**: Display the learned Q-values across the grid.

## Usage

1. Clone this repository:
   ```bash
   git clone <repository_url>
   cd <repository_folder>
   ```

2. Install required packages:
   ```bash
   pip install numpy matplotlib
   ```

3. Run the code:
   ```bash
   python main.py
   ```

4. Explore results through the generated plots.

## Example Plots
- **Reward Per Episode**:
  Displays how total rewards evolve as the agent learns.

- **Q-value Heatmaps**:
  Shows the progression of Q-values for the grid.

## Results
![episode0](https://github.com/user-attachments/assets/447291e2-f3cb-4aa5-8d7a-fe1bc3cdb384)
![episode10](https://github.com/user-attachments/assets/16e828a7-b1b3-47cc-abad-ea7d459ba30b)
![episode100](https://github.com/user-attachments/assets/544d4d55-dabd-42f8-aca6-49a2ee277d76)
![episode500](https://github.com/user-attachments/assets/0ba2ca01-c730-4e16-ad2b-fd095bef58e0)
![episode1000](https://github.com/user-attachments/assets/8bd5889f-c0c2-49c4-88e3-b18329faf3b3)

## References
- Reinforcement Learning concepts from "Reinforcement Learning: An Introduction" by Sutton and Barto.
- GridWorld environment inspired by OpenAI Gym environments.
