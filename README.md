

# ML-Based Regime-Switching Trading Strategy 📈

**Techfest X Jane Street: Algo Trading Competition (IIT Bombay)**

**Team ID:** Algo-250644  | **Participant:** Ajay Teja K 
**Status:** Round 3 Submission

## Overview

This repository contains the architecture and presentation for an **Adaptive Intelligence Trading System** developed for the Techfest X Jane Street Algo Trading Competition.

Static trading strategies typically underperform up to 70% of the time because they fail to adapt to changing conditions—markets spend approximately 40% of the time moving sideways, 30% bullish, and 30% bearish. To solve this, our system utilizes a machine learning framework to identify real-time market regimes and dynamically switch between three specialized sub-strategies (Momentum, Defensive, and Mean Reversion).

## Machine Learning Framework

The backbone of the strategy is a robust **Random Forest Algorithm** consisting of an ensemble of 200 decision trees. The model leverages majority voting to provide emotion-free, daily regime predictions.

* 
**Data Labeling:** Training data is categorized based on 20-day forward returns: Bull (> +2.5%), Bear (< -2.5%), and Sideways (between -2.5% and +2.5%).


* 
**Feature Engineering:** The model ingests 15 distinct market indicators to capture comprehensive market dynamics:


* 
*Volatility Metrics:* Historical volatility, Average True Range (ATR), and Bollinger Band width.


* 
*Momentum Signals:* RSI, ROC, MACD, and price returns.


* 
*Trend Components:* SMA crossover, ADX, and linear regression.





## Dynamic Sub-Strategies

The engine automatically routes capital into the appropriate strategy based on the ML regime prediction:

### 1. Bull Strategy (Momentum Trading)

Deployed during identified market uptrends to maximize upside capture.

* 
**Entry Criteria:** RSI > 50, price above 20-day moving average, and volume exceeding 150% of the average.


* 
**Position Sizing:** Aggressive 95% capital deployment across a maximum of 15 stocks (8-10% allocation per stock).


* 
**Expected Results:** 5-7% expected return per trade with a high 65-70% win rate.



### 2. Bear Strategy (Defensive & Capital Preservation)

Activated during market downtrends where capital preservation is the primary goal.

* 
**Core Logic:** Maintain a 70-80% passive cash position on the sidelines.


* 
**Selective Trading:** Only trade extreme oversold bounces (RSI < 25) confirmed by high capitulation volume spikes.


* 
**Risk Limits:** Maximum 30% of capital deployed (3-5% sizing) with rigid -2% stop losses.



### 3. Sideways Strategy (Mean Reversion)

Engineered for range-bound markets to capture statistical deviations.

* 
**Entry Criteria:** Price touching the lower Bollinger Band, RSI < 30, and ADX < 20 (confirming a lack of directional trend).


* 
**Position Sizing:** 70-80% capital deployed across 10-12 stocks (7-8% allocation per stock).


* 
**Expected Results:** 4-5% gains with a 60-65% win rate.



## Expected Overall Performance

* 
**Annual Returns Target:** 25-35%.


* 
**Win Rate (Statistical Edge):** 62-68%.


* 
**Drawdown Management:** Capped at -12% maximum drawdown.
