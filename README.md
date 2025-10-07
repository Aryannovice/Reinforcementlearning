# Real-Time Finance RL Trading System

A hands-on exploration of reinforcement learning algorithms (DQN, PPO, A2C) applied to live financial markets using real-time data from Yahoo Finance.

## What This Is

This is my personal "fuck around and find out" journey into RL-based algorithmic trading. Started with vanilla implementations, broke them, fixed them, and gradually built up to something that doesn't immediately lose money.

## What's Inside

**Implemented Algorithms:**
- DQN (Deep Q-Network) - Value-based learning
- PPO (Proximal Policy Optimization) - Policy gradient method
- A2C (Advantage Actor-Critic) - Actor-critic hybrid
- SD2 (experimental variant)

**Key Features:**
- Real-time market data via yfinance API
- Transaction cost modeling (0.1% per trade)
- Risk-aware reward function (profit - drawdown penalty)
- 13 technical indicators (RSI, MACD, Bollinger Bands, etc.)
- Percentage-based position sizing (7 actions: Sell 100%/50%/25%, Hold, Buy 25%/50%/100%)
- Proper train/test temporal splits (no lookahead bias)

**Preprocessing Pipeline:**
- Automatic indicator calculation
- NaN handling (forward-fill, no cheating)
- Data normalization
- Feature engineering for state space

**Hybrid Experiments:**
- Ensemble predictions (averaging multiple models)
- Regime-based switching
- Custom reward shaping variants

## Current Status

**What Works:**
- ✅ Risk management (max drawdown ~18% vs 40%+ for vanilla RL)
- ✅ Transaction cost awareness (agents trade less frequently)
- ✅ Technical indicator utilization (agents learned RSI/MACD patterns)
- ✅ Stable training (no catastrophic failures)

**What Doesn't:**
- ❌ Beating buy-and-hold consistently (12% RL vs 15% B&H on AAPL)
- ❌ Generalization across different stocks
- ❌ Handling regime changes (trained on bull market, struggles in volatility)

**The Reality:**
RL learns to be *safe* but not *optimal*. Drawdown penalty works too well - agents prefer holding cash over taking calculated risks. It's a feature and a bug simultaneously.


## Try it out

Enter your favorite stock market dataset and carry out the task.



<img width="751" height="223" alt="image" src="https://github.com/user-attachments/assets/03eaa718-c9e0-463b-a371-5291c7a43505" />
