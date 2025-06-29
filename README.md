# RL-assignment-
RL assignment  Spring 2025
# 🎓 Multi-Armed Bandit Assignment – README

This project includes Python implementations and experiments for analyzing **multi-armed bandit algorithms** under stationary and non-stationary settings.

---

## 📂 Part 1: Stationary Bandit Problem

### ✅ Objective:
To compare the performance of four bandit algorithms on a stationary problem:
- Greedy
- Epsilon-Greedy (with tuned ε)
- Optimistic Greedy
- Gradient Bandit (with tuned α)

### 🔍 Key Details:
- 10 arms (bandits), each with stationary Gaussian reward
- Run: 1000 simulations, 2000 steps each
- Epsilon and Alpha values are tuned using pilot runs

### 📁 Output Files:
- `pilot_epsilon_greedy.png`: Comparison of average reward for different ε values
- `pilot_gradient_bandit.png`: Comparison of average reward for different α values
- `final_avg_reward.png`: Final average rewards of all 4 methods
- `final_optimal_action.png`: Final % optimal actions of all 4 methods

### ▶️ How to Run:
1. Make sure Python 3, `numpy`, `matplotlib`, and `tqdm` are installed.
2. Run the script:  
   ```bash
   python part1_stationary_bandit.py
   ```
3. Check the PNG files to evaluate performance visually.

---

## 📂 Part 2: Non-Stationary Bandit Problem

### ✅ Objective:
To evaluate how the same algorithms adapt to **changing environments**, including:
- Drift
- Mean-Reverting Drift
- Abrupt Change (with and without Q-value reset)

### 🔍 Key Details:
- 10 arms with time-varying true rewards (`μ`)
- For each scenario, 1000 runs of 2000 steps
- Same random seeds used for drift and permutations to ensure comparability

### 📁 Output Files:
Each scenario produces two plots:
- `SCENARIO_avg_reward.png`: Average reward plot
- `SCENARIO_optimal_action.png`: % Optimal action plot

For example:
- `Drift_avg_reward.png`
- `Mean-Reverting_Drift_optimal_action.png`
- `Abrupt_Change_With_Reset_avg_reward.png`
- etc.

### ▶️ How to Run:
1. Run the script:  
   ```bash
   python part2_nonstationary_bandit.py
   ```
2. The script includes pilot runs to choose best ε and α for this dynamic environment.

---

## 🔧 Requirements
- Python 3.x
- `numpy`
- `matplotlib`
- `tqdm`

Install with:
```bash
pip install numpy matplotlib tqdm
```

---

## 🧠 Interpretation Notes:
- **Epsilon-Greedy** is simple and effective when tuned properly.
- **Optimistic Greedy** encourages initial exploration without randomness.
- **Gradient Bandit** uses softmax probabilities and adapts best in the long run.
- In non-stationary settings, **resetting Q-values after abrupt changes** can significantly improve performance.
