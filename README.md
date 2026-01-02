# Trader Behavior Analysis Under Bitcoin Market Sentiment


## 📌 Project Overview
This project analyzes how trader behavior and performance vary across different Bitcoin market sentiment regimes using the **Fear & Greed Index** and **historical trade-level data from Hyperliquid**.  
The goal is to uncover behavioral patterns, assess risk-taking tendencies, and derive insights that can inform smarter trading and risk management strategies in crypto markets.


## 📊 Datasets Used

### 1. Bitcoin Market Sentiment (Fear & Greed Index)
- Granularity: Daily
- Key Columns:
  - `date` – Calendar date
  - `classification` – Market sentiment  
    *(Extreme Fear, Fear, Neutral, Greed, Extreme Greed)*

This dataset represents overall market psychology.


### 2. Historical Trader Data (Hyperliquid)
- Granularity: Trade-level
- Key Columns Used:
  - `account` – Trader identifier
  - `symbol` – Asset traded
  - `size_usd` – Trade size in USD (risk proxy)
  - `closed_pnl` – Profit or loss per trade
  - `side`, `direction` – Trade direction
  - `Timestamp IST` – Trade execution timestamp

This dataset captures individual trading decisions and outcomes.


## 🛠️ Data Preparation & Integration

- Converted trade timestamps to datetime format and extracted trade dates.
- Standardized column names for readability and consistency.
- Removed invalid trades, zero-size trades, and extreme PnL outliers (top 1%).
- Aligned both datasets at the **date level** and merged them so each trade is enriched with its corresponding market sentiment.

This integration allows sentiment-conditioned analysis of trader behavior.


## 🔍 Analysis Performed

### 1. Market Sentiment Overview
- Distribution of sentiment regimes
- Frequency of Fear vs Greed cycles

### 2. Trader Performance vs Market Sentiment
- Average PnL by sentiment
- Median PnL by sentiment
- Win rate (percentage of profitable trades)
- Trade volume across sentiment regimes

### 3. Risk Behavior Analysis
- Average trade size (`size_usd`) by sentiment
- Trading fee trends as a proxy for trading intensity

### 4. Downside Risk Assessment
- Worst-case losses (minimum PnL) across sentiment regimes
- Volatility patterns in fearful vs greedy markets


## 📈 Key Insights

- Greed and Extreme Greed regimes are associated with higher average profitability.
- Extreme Fear periods show lower win rates and deeper downside losses.
- Trade sizes tend to increase during Fear regimes, indicating reactive or defensive behavior.
- Consistent performance is more closely linked to disciplined position sizing than aggressive exposure.
