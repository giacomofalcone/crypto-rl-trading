# Crypto RL Trader

A reinforcement learning-based automated trading system for cryptocurrencies.  
This project explores the use of **Proximal Policy Optimization (PPO)** to train an intelligent agent capable of making buy, sell, or hold decisions in a simulated crypto market, aiming to maximize returns while managing risk.

## 🚀 Project Goals

- Train a trading agent using **reinforcement learning (RL)**
- Incorporate **technical indicators** (e.g., RSI, MACD, EMA) as part of the state space
- Evaluate performance against traditional strategies (e.g., Buy & Hold)
- Explore extensions like position sizing, stop loss, and multi-asset trading

## 🧠 Technologies Used

- `Python`
- `Stable-Baselines3` – RL algorithms (PPO, A2C, etc.)
- `Gym` – Custom trading environment
- `pandas`, `numpy` – Data manipulation
- `pandas_ta` – Technical analysis indicators
- `matplotlib`, `seaborn` – Visualization
- `yfinance` or Binance API – Historical crypto data

## 📁 Project Structure

```
crypto-rl-trader/
│
├── data/             # Historical crypto price data (CSV or pulled from APIs)
├── notebooks/        # Jupyter Notebooks for exploration and training
├── scripts/          # Python scripts for training, evaluation, and environment setup
├── models/           # Saved agent models and checkpoints
├── requirements.txt  # Python dependencies
└── README.md         # Project overview (this file)
```

## ⚙️ Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/crypto-rl-trader.git
   cd crypto-rl-trader
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run training (example with PPO):
   ```bash
   python scripts/train_agent.py
   ```

## 📊 Evaluation

Agent performance will be evaluated using:
- Cumulative returns
- Sharpe ratio
- Maximum drawdown
- Comparison against baselines (e.g., Buy & Hold)

## 📌 Notes

- This project is for educational and research purposes only. It does **not** constitute financial advice.
- Reinforcement learning in trading involves high variance and requires careful validation.

## 🧾 License

This project is licensed under the MIT License.
