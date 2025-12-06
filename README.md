# Market Sentiment & Trader Performance Analysis

## Overview

This project analyzes the relationship between Bitcoin's Fear & Greed Index and trading performance on the Hyperliquid platform. The analysis examines **52,497 trades** from **32 traders** throughout 2024, revealing critical insights about how market sentiment impacts trading profitability.

## Key Findings

### 🎯 Main Discovery

Traders are significantly more profitable during **bullish (greed) periods**, while **bearish (fear) periods** result in net losses despite high win rates—a classic risk-reward inversion pattern.

### 📊 Performance by Sentiment

| Sentiment   | Total Trades | Win Rate | Total PnL       | Avg PnL/Trade |
| ----------- | ------------ | -------- | --------------- | ------------- |
| **Bearish** | 1,451        | 73.1%    | **-$87,196**    | -$183.57      |
| **Neutral** | 1,293        | 55.1%    | +$88,120        | +$157.64      |
| **Bullish** | 49,747       | 84.6%    | **+$3,563,464** | +$136.71      |

### 🔍 Critical Insights

1. **98% of all profits** come from bullish sentiment days
2. **Risk-Reward Paradox**: Bearish periods show 73.1% win rate but net losses due to large occasional losses
3. **Trader Behavior**: 68% of traders (21 out of 32) only trade during bullish periods
4. **Position Sizing**: Traders use smallest positions during most profitable periods (sophisticated risk management)
5. **Coin Selection**: Shift from major coins (ETH/BTC) during fear to meme coins (HYPE/@107) during greed

## Project Structure

```
Anythingai-Data-Science-Assignment-Task/
│
├── data/
│   ├── historical_data.csv          # 211,224 trades from Hyperliquid
│   └── fear_greed_index.csv         # Bitcoin Fear & Greed Index data
│
├── notebooks/
│   ├── task1.ipynb                   # Complete analysis notebook
│
├── images/
│   ├── executive_dashboard.png       # Summary dashboard
│   ├── sentiment_performance_overview.png
│   ├── risk_reward_paradox.png
│   ├── trader_participation.png
│   ├── position_sizing_behavior.png
│   └── top_coins_by_sentiment.png
│
├── DS Task.pdf                      # Assignment description
├── LICENSE                          # MIT License
└── README.md                        # This file
```

## Dataset Information

### Historical Trading Data

- **Total Records**: 211,224 trades
- **Time Period**: 2024 (52,497 trades analyzed)
- **Unique Traders**: 32 accounts
- **Unique Coins**: 246 cryptocurrencies
- **Columns**: Account, Coin, Execution Price, Size Tokens, Size USD, Side, Timestamp IST, Start Position, Direction, Closed PnL, Transaction Hash, Order ID, Crossed, Fee, Trade ID, Timestamp

### Fear & Greed Index Data

- **Total Records**: 2,644 daily observations
- **Time Period**: 2018-02-01 to 2025-05-02
- **2024 Coverage**: 365 days
- **Columns**: timestamp, value, classification, date
- **Sentiment Categories**: Extreme Fear, Fear, Neutral, Greed, Extreme Greed

## Requirements

### Python Version

- Python 3.7 or higher

### Dependencies

```python
pandas >= 1.3.0
numpy >= 1.21.0
matplotlib >= 3.4.0
seaborn >= 0.11.0
jupyter >= 1.0.0
```

### Installation

```bash
# Clone the repository
git clone <repository-url>
cd Anythingai-Data-Science-Assignment-Task

# Install dependencies
pip install pandas numpy matplotlib seaborn jupyter

# Or using requirements.txt (if available)
pip install -r requirements.txt
```

## Usage

### Running the Analysis

1. **Start Jupyter Notebook**:

   ```bash
   jupyter notebook
   ```

2. **Open the analysis notebook**:

   - Navigate to `notebooks/task1.ipynb` for the complete analysis
   - Or `notebooks/task.ipynb` for initial exploration

3. **Execute cells sequentially**:
   - The notebook loads data from `../data/` directory
   - Performs data cleaning and merging
   - Generates visualizations saved to `../images/` directory

### Key Analysis Steps

1. **Data Loading**: Load historical trading data and Fear & Greed Index
2. **Data Cleaning**: Parse dates, filter for 2024, handle missing values
3. **Data Merging**: Merge trading data with sentiment data by date
4. **Performance Analysis**: Calculate win rates, PnL, and metrics by sentiment
5. **Behavioral Analysis**: Analyze position sizing, coin selection, trader participation
6. **Visualization**: Generate 6 comprehensive visualizations

## Visualizations

The analysis generates 6 key visualizations:

1. **Performance Metrics Overview** (`sentiment_performance_overview.png`)

   - Total PnL, Average PnL, Win Rate, Trading Volume by sentiment

2. **Risk-Reward Paradox** (`risk_reward_paradox.png`)

   - Distribution of wins vs losses during bearish periods
   - Cumulative PnL showing the inversion pattern

3. **Trader Participation** (`trader_participation.png`)

   - Active traders and trading intensity by sentiment

4. **Position Sizing Behavior** (`position_sizing_behavior.png`)

   - Average position sizes and Buy/Sell distribution

5. **Top Coins by Sentiment** (`top_coins_by_sentiment.png`)

   - Coin preferences shift across market sentiments

6. **Executive Dashboard** (`executive_dashboard.png`)
   - Comprehensive summary with key metrics and insights

## Methodology

### Sentiment Grouping

- **Bearish**: Fear + Extreme Fear
- **Neutral**: Neutral
- **Bullish**: Greed + Extreme Greed

### Performance Metrics

- **Win Rate**: Percentage of trades with positive PnL
- **Total PnL**: Sum of all Closed PnL values
- **Average PnL**: Mean PnL per trade
- **Non-Zero PnL Analysis**: Focuses on completed positions (excludes 48.4% zero-PnL trades)

### Data Filtering

- Filtered historical data to 2024 only (52,497 trades from 211,224 total)
- Merged with sentiment data on date
- Analyzed only trades with non-zero PnL for accurate performance metrics

## Key Conclusions

1. ✅ **Bullish sentiment periods are highly profitable** (84.6% win rate, +$136 avg PnL)
2. ✅ **Most traders recognize this** and concentrate activity during greed periods
3. ❌ **Bearish sentiment periods are unprofitable** despite high win rates (risk-reward inversion)
4. ❌ **Trading during fear requires exceptional risk management** that most traders lack

### Strategic Implications

- **For Traders**: Avoid heavy trading during fear periods; capitalize on bullish momentum
- **For Risk Managers**: Implement sentiment-based portfolio allocation; reduce capital during bearish periods
- **For Strategy**: The data suggests reducing activity during bearish periods and capitalizing aggressively during bullish trends

## Limitations

1. **Sample Size Imbalance**: Bearish periods represent only 2.8% of total trades
2. **Survivorship Bias**: Dataset only includes traders who remained active through 2024
3. **Temporal Causality**: Correlation doesn't prove causation; other market factors may be involved
4. **Platform-Specific**: Patterns are specific to Hyperliquid traders
5. **2024 Bias**: Predominantly bullish year (72% greed days); results may differ in bear markets
6. **Sentiment Lag**: Fear & Greed Index is a lagging indicator

## Author

**Harshil Patel**

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Data provided by Hyperliquid platform
- Bitcoin Fear & Greed Index data from alternative.me
- Analysis conducted as part of AnythingAI Data Science Assignment

---

## Contact

For questions or feedback about this analysis, please open an issue in the repository.

---

**Note**: This analysis is for educational and research purposes. Trading involves risk, and past performance does not guarantee future results.
