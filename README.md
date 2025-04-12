# CartPole Reinforcement Learning: Q-Learning vs Double SARSA

This project implements and compares two reinforcement learning algorithms—Q-learning and Double SARSA—within the CartPole-v1 environment using OpenAI Gym. It evaluates learning performance, decision strategies, and robustness under identical training conditions.

## 🎯 Objectives

- Balance the pole using RL agents trained in CartPole-v1
- Compare the performance of Q-learning and Double SARSA
- Analyze training stability and convergence
- Conduct sensitivity analysis on learning rate and discount factor

## 🧠 Algorithms

### Q-Learning (Off-policy)
- Learns from max future Q-values
- Can overestimate returns
- Fast policy optimization

### Double SARSA (On-policy)
- Maintains two Q-tables
- Updates using alternate estimates
- Reduces overestimation bias
- Produces more stable learning

## ⚙️ Environment Setup

- **CartPole-v1** from `gym`
- **State Space**: Discretized into bins for:
  - Cart position
  - Cart velocity
  - Pole angle
  - Angular velocity
- **Action Space**: 0 (left), 1 (right)
- **Reward**: +1 per timestep if pole is upright

## 📊 Key Evaluation Metrics

- Episode length over time
- Q-value heatmaps
- Policy visualizations
- Convergence analysis
- Sensitivity to hyperparameters (Double SARSA)

## 🔍 Sensitivity Tests

- **Learning rate**: Compared 0.1 vs 0.5  
- **Discount factor**: Compared 0.6 vs 0.99  
- Double SARSA proved more stable at lower learning rates and higher discounting

## 🛠 Libraries Used

- `gym` for environment simulation
- `numpy` for computation
- `matplotlib` and `seaborn` for plotting
- `pickle` for storing Q-tables
- `pygame` for rendering

## 📁 Repository Structure

├── report.pdf # Full write-up with analysis ├── code.py # Python implementation ├── README.md

shell
Copy code

## 🚀 Results

- Double SARSA showed smoother episode progression and Q-value distribution
- Q-learning was more aggressive but less stable
- Both algorithms solved the environment (~200 avg reward) with different convergence dynamics

## ℹ️ How to Run and Visualize

### 1. Install Dependencies
```bash
pip install gym numpy matplotlib seaborn pygame
2. Run the Script
Modify the main script to include:

python
Copy code
run(render=True)  # Enables visualization
The simulation will show the cart balancing the pole in real time. Be patient—training may take a while.

3. Output Visuals
Reward progression plots

Q-value heatmaps

Policy decision heatmaps

These help understand the behavior and stability of both agents.
