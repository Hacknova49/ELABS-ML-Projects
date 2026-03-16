# RL-Navigator: Autonomous Taxi Optimization

Efficient route planning is crucial in transportation systems to minimize travel time and fuel consumption. In this project, a **Q-learning agent** is trained using the **Taxi-v3 Gymnasium environment** to learn optimal pickup and drop-off routes for passengers. 

The goal is to build a state-action value table (Q-Table), balance exploration and exploitation through an epsilon-greedy strategy, and tune hyperparameters such as learning rate ($\alpha$), discount factor ($\gamma$), and epsilon decay ($\epsilon$).

---

## Features

- **Training Pipeline**: Comprehensive `train.ipynb` to train the Q-learning agent for 10,000 episodes over the environment.
- **Evaluation Engine**: Included `evaluate.ipynb` to watch the trained agent effectively pick up and drop off passengers visually via `pygame` rendering.
- **Performance Tracking**: Built-in learning curves plotting the moving average of rewards and steps over the episodes to prove the convergence of the model.
- **Jupyter Notebook Workflows**: The entire project components (`agent`, `environment`, `train`, `evaluate`) are all fully formatted as interactive `.ipynb` files.

## Q-Learning Parameters
- **Algorithms**: Tabular Q-learning (Bellman Equation)
- **Episodes**: 10,000
- **Epsilon ($\epsilon$)**: Starts at 1.0, decays at 0.995 per episode, with a 0.01 minimum to guarantee exploration initially and exploitation at the end.
- **Learning Rate ($\alpha$)**: Defaults to 0.1
- **Discount Factor ($\gamma$)**: Defaults to 0.9

## Getting Started

### 1. Installation

Ensure you have Python and Jupyter installed. You can install all project dependencies via the `requirements.txt` file, plus `import-ipynb` which allows the local notebooks to import each other:

```bash
pip install -r requirements.txt
pip install "gymnasium[toy-text]" jupyter import-ipynb
```

### 2. Usage

To run the training or evaluation loops, start up Jupyter:

```bash
jupyter notebook
```

From here, you can interact with the project:
1. Open `src/train.ipynb` to execute the training loop. Make sure to run `import import_ipynb` in your top cell if you need to import from `agent.ipynb` natively.
2. The notebook will automatically save the converged `q_table.npy` to the `model/` directory and plot the performance metrics to the `data/` directory.
3. Open `src/evaluate.ipynb` to see the agent run logically and render visually!

## Results

By episode ~1500, the Q-learning agent successfully converges, reaching a positive average reward. The steps taken per episode stabilize to the lowest optimal paths. The moving averages can be visualized inside the `data` directory after running the training script.

---

*This project showcases practical reinforcement learning for real-world routing and navigation problems.*
