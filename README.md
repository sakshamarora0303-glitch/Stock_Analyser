# Adaptive Crossover Reliability Indicator (ACRI)

An interpretable, machine-learning-assisted system for evaluating the reliability of individual moving-average crossover events in the stock market.

## Problem Statement
Golden Cross and Death Cross signals are widely used in technical analysis, but their effectiveness varies across market conditions. Crossovers during sideways or highly volatile markets may produce false signals. ACRI aims to evaluate the reliability of individual crossovers instead of treating every crossover as an automatic Buy or Sell signal.

## How It Works
1. Collect historical stock price and volume data.
2. Calculate moving averages and detect Golden Cross and Death Cross events.
3. Extract features such as MA separation, MA slope, momentum, volume, volatility, and market regime.
4. Label historical crossover events as successful or unsuccessful based on a predefined future-performance rule.
5. Train a Logistic Regression model on the labelled events to estimate the probability of success.
6. Convert the estimated probability into an ACRI reliability score from 0–100.
7. Compare the system with a conventional crossover strategy using historical backtesting.

## ACRI Score
For a probability-based implementation:

`ACRI = P(success) × 100`

The project also explores a weighted composite score using normalized features and weights that may vary according to market regime. The final implementation will define how this score relates to the Logistic Regression output.

## Technology Stack
- **Frontend:** React
- **Backend:** Python, FastAPI
- **Machine Learning:** scikit-learn
- **Data Processing:** Pandas, NumPy
- **Database:** PostgreSQL
- **Visualization:** Interactive charts for stock prices, crossover events, and reliability scores

## Evaluation
The proposed system will be evaluated using:
- False-signal rate
- Post-signal returns
- Maximum drawdown
- Risk-adjusted performance
- Robustness across different market regimes

Chronological or walk-forward testing will be used to reduce data leakage and avoid using future information during training.

## Expected Outcome
A web dashboard displaying historical crossover events, their estimated reliability scores, and backtesting results comparing ACRI with a conventional moving-average crossover strategy.

## Future Scope
- Test different moving-average combinations.
- Improve market-regime detection.
- Compare Logistic Regression with other interpretable models.
- Evaluate performance across multiple stocks and market conditions.

## Team
- **Saksham Arora** — 25BCE0487
- **Hrishikesh Khanna** — 25BCE2500
- **Project Guide:** Raghul J, Assistant Professor, SCOPE

**Course:** BACSE291 — Innovative Design Project, Fall 2026

## Disclaimer
This project is an academic prototype for research and decision support, not investment advice. All scoring methods and performance claims must be validated experimentally.
