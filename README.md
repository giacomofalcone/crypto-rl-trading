# Crypto RL Trader

A **Reinforcement Learning (RL)**-based automated trading agent for cryptocurrencies.
This project applies **Proximal Policy Optimization (PPO)** to develop an agent that learns to **buy**, **sell**, or **hold** Bitcoin and Ethereum using a custom Gym environment enriched with technical indicators and portfolio state.

---

## 📌 Project Summary

This project was developed as part of a Master’s thesis in Computer Engineering and Fintech (5 CFU).
It demonstrates the full pipeline: custom environment design, reward shaping, agent training, and performance evaluation under realistic crypto market conditions.

---

## 🗂️ Project Structure

```
crypto-rl-trading/
├── README.md
├── data/                         # Processed datasets (BTC, ETH)
├── experiments/                  # Experiment-specific notebooks & models
│   ├── 00_data_preparation_and_eda/  # Data processing & exploratory analysis
│   ├── 01_OnlyLong/                  # Baseline: long-only agent
│   ├── 02_AddedShort/                # Long + short, no portfolio in state
│   └── 03_FinalModel/                # Long, short, hold + full portfolio state
├── report.pdf                       # LaTeX report and figures
```

---

## 🚀 Goals

* ✅ Design a **custom Gym trading environment** with support for long, short, and hold actions.
* ✅ Engineer a rich **state space**: price history, technical indicators, and **portfolio state**.
* ✅ Train PPO agent using **Stable-Baselines3**.
* ✅ Evaluate performance on **BTC (training & validation)** and **ETH (testing)**.
* ✅ Analyze generalization and interpretability.

---

## 🧠 Technologies

* `Python`, `NumPy`, `pandas`, `matplotlib`
* `Gymnasium` – custom trading environment
* `Stable-Baselines3` – PPO implementation
* `scikit-learn` – feature scaling
* `pandas-ta` / `finta` – technical indicators
* `CoinGecko`, `MarketWatch` – market data

---

## 🧪 Agent Features

* **Action space**: Buy (long), Sell (short), Hold

* **Observation**:

  * 30-day window of OHLCV and indicators (SMA, RSI, etc.)
  * Long-term features: normalized distance from SMA, price percentile
  * Portfolio state: cash, BTC held, BTC shorted, current position
  * Feature correlation metric (proxy for multicollinearity)

* **Reward**:

  * % change in net worth from previous step
  * Bonus for closing a profitable position
  * Small incentive for taking action (to reduce inactivity)

---

## 📊 Evaluation Metrics

Evaluated using:

| **Metric**               | **Description**                                                                                                                                    |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Cumulative Return**    | Measures total percentage gain/loss from the initial balance at the end of the trading period.                                                     |
| **Realized Wallet Plot** | Visual comparison of the agent’s net worth vs. market price, with annotated long/short/hold positions. Helps interpret trading behavior over time. |

---

## 📈 Results (Final Model)

* The final PPO agent demonstrated the ability to learn effective trading strategies, achieving positive performance on the Bitcoin (BTC) validation set. Generalization to the Ethereum (ETH) test set was observed, though with more modest results compared to BTC.
* Incorporating the agent's portfolio status into its observation vector contributed to more stable trading behavior, aiding in the reduction of drawdowns.

---

## ⚠️ Disclaimer

This is a research/educational project. It does **not** provide financial advice or live trading capability.

---

## 🧾 License

MIT License – free for personal and academic use.
