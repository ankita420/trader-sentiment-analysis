# Trader Performance vs Market Sentiment Analysis

A comprehensive analysis of how Bitcoin market sentiment (Fear/Greed Index) correlates with trader behavior and performance on Hyperliquid.

**Submitted for**: Primetrade.ai Data Science Intern - Round 0 Assignment  
**Analysis Period**: 2018-2026 (2,644 trading days)  
**Traders Analyzed**: 32 unique accounts  
**Total Trades**: 211,224 transactions  

---

## 📋 Project Overview

This project analyzes the relationship between market sentiment and trading performance, answering key questions:
- Does trader performance differ significantly between Fear vs Greed market conditions?
- How do traders adjust their behavior based on market sentiment?
- What trader segments emerge, and what are their characteristics?
- What actionable trading rules can we derive from sentiment patterns?

---

## 🎯 Key Findings

### 1. **Sentiment Drives Trading Volume**
- Fear markets generate **61,837 trades (29.2%)** - highest activity
- Extreme Fear shows lowest participation: **21,400 trades (10.1%)**
- Conclusion: Traders are most active during fearful market conditions

### 2. **Extreme Greed = Best Average Returns**
- Extreme Greed: **₹67.89 average PnL/trade** (highest)
- Fear: **₹34.73 average PnL/trade**
- Win rate improves from 37% (Extreme Fear) to 46% (Extreme Greed)

### 3. **Position Size = Sentiment Indicator**
- Fear markets: Largest average position size (**$7,816**)
- Extreme Greed: Smallest position size (**$3,112**)
- Traders are most confident (largest bets) when markets are fearful

### 4. **Trader Segmentation Reveals Winners**
- **Consistent Winners** (25%): Low drawdown, stable profits ₹533,472 avg
- **Average Traders** (50%): Mixed results, high variability
- **Inconsistent Traders** (25%): High risk, inconsistent returns

### 5. **Trading Frequency > Leverage**
- Frequent traders: **₹677,729 average profit** (52.6% of total)
- Infrequent traders: **₹113,690 average profit**
- **5.9x profit difference** between frequent and infrequent traders

### 6. **Market Sentiment Bias Shifts**
- **Extreme Fear**: Long bias (1.045 buy/sell ratio) - buyers accumulate
- **Extreme Greed**: Short bias (0.814 ratio) - sellers dominate
- Traders inverse their bias at market extremes

---

## 🚀 Quick Start

### Prerequisites
- Python 3.8+
- pip or conda package manager
- 500MB+ free RAM
- 100MB+ disk space

### Installation

1. **Clone/Download the repository**
```bash
git clone <repo-url>
cd trader-sentiment-analysis
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

3. **Download datasets** (if not included)
- Fear-Greed Index: Place as `fear_greed_index__1_.csv`
- Trading Data: Place as `historical_data__1_.csv`

### Running the Analysis

#### Option A: Jupyter Notebook
```bash
jupyter notebook Untitled117__2_.ipynb
```
Then open in browser and run all cells.

#### Option B: Streamlit Dashboard (Interactive)
```bash
streamlit run streamlit_dashboard.py
```
Opens interactive dashboard at `http://localhost:8501`

#### Option C: Python Script (Batch)
```bash
python analysis_script.py
```

---

## 📁 File Structure

```
trader-sentiment-analysis/
├── README.md                              # This file
├── METHODOLOGY_AND_INSIGHTS.md            # Detailed write-up
├── SUMMARY.md                             # Executive summary
├── requirements.txt                       # Python dependencies
│
├── Untitled117__2_.ipynb                  # Main analysis notebook
├── analysis_script.py                     # Standalone Python script (optional)
│
├── datasets/
│   ├── fear_greed_index__1_.csv          # Sentiment data
│   └── historical_data__1_.csv           # Trading data
│
├── outputs/
│   ├── charts/
│   │   ├── sentiment_distribution.png
│   │   ├── performance_by_sentiment.png
│   │   ├── trader_segments.png
│   │   └── ... (more charts)
│   │
│   ├── tables/
│   │   ├── sentiment_statistics.csv
│   │   ├── trader_performance.csv
│   │   └── segment_comparison.csv
│   │
│   └── models/
│       └── profit_predictor_model.pkl
│
├── streamlit_dashboard.py                 # Interactive dashboard
└── setup.py                               # Automated setup
```

---

## 📊 Data Description

### Fear-Greed Index Dataset
| Column | Description |
|--------|-------------|
| `date` | Trading date |
| `value` | Index value (0-100) |
| `classification` | Sentiment: Extreme Fear / Fear / Neutral / Greed / Extreme Greed |
| `timestamp` | Unix timestamp |

**Total Records**: 2,644 days  
**Date Range**: 2018-02-01 to 2025-06-20

### Historical Trading Data
| Column | Description |
|--------|-------------|
| `Account` | Trader wallet address (32 unique accounts) |
| `Coin` | Trading pair/symbol |
| `Side` | BUY or SELL |
| `Size USD` | Position size in USD |
| `Execution Price` | Entry price |
| `Start Position` | Initial position |
| `Closed PnL` | Profit/Loss from trade |
| `Leverage` | Risk multiplier |
| `Fee` | Trading fee |
| `Timestamp IST` | Trade timestamp (IST) |

**Total Records**: 211,224 trades  
**Date Range**: 2023-2025

---

## 🔬 Analysis Methodology

### Part A: Data Preparation ✓
1. **Loading**: 
   - Fear-Greed: 2,644 rows × 4 columns (0 nulls)
   - Trading data: 211,224 rows × 16 columns (0 nulls)

2. **Cleaning**:
   - No missing values
   - No duplicate rows
   - Timestamp conversion to consistent format

3. **Alignment**: Merged on date (left join on trades)

4. **Metrics Created**:
   - Daily PnL per account
   - Win rate (profitable trades %)
   - Leverage ratio (Size USD / Start Position)
   - Exposure ratio (Size USD / absolute position)
   - Daily trade count
   - Long/short ratio by sentiment

### Part B: Core Analysis ✓

**Question 1: Does performance differ by sentiment?**
- Yes: 46% win rate in Extreme Greed vs 37% in Extreme Fear
- Average PnL: ₹67.89 (Extreme Greed) vs ₹34.73 (Fear)
- Total PnL: Fear has highest (₹126M) due to volume

**Question 2: Do traders change behavior by sentiment?**
- Yes: Position sizes 2.5x larger in Fear vs Extreme Greed
- Leverage higher in neutral conditions
- Long bias in extreme fear, short bias in extreme greed

**Question 3: Trader Segmentation**
- **By Exposure**: High/Medium/Low leverage users
- **By Frequency**: Frequent/Moderate/Infrequent traders
- **By Profitability**: Consistent Winners/Average/Inconsistent

**Question 4: 3+ Insights with Charts**
- ✓ Trade frequency histogram by sentiment
- ✓ Performance scatter (profit vs drawdown)
- ✓ Position size by segment and sentiment
- ✓ Leverage distribution analysis
- ✓ Win rate comparison

### Part C: Actionable Strategy ✓

**Rule of Thumb 1 - Fear Market Strategy**:
During Fear/Extreme Fear sentiment:
- Consistent Winners: Increase exposure moderately (position size +15-20%)
- Inconsistent Traders: Reduce leverage (target <10x)
- Rationale: Data shows traders overexpose in fear periods

**Rule of Thumb 2 - Greed Market Strategy**:
During Greed/Extreme Greed sentiment:
- Cap position sizes (max 2x normal)
- Avoid increased leverage (stay <15x)
- Increase trade frequency only for proven traders
- Rationale: Inconsistent traders blow up in greed markets

---

## 🤖 Bonus: Machine Learning Model

A Random Forest classifier predicts next-day profit buckets:
- **Accuracy**: 53% (vs 33% baseline)
- **Features**: 9 (position size, leverage, win rate, trade count, etc.)
- **Classes**: Low Profit / Medium Profit / High Profit
- **Top Predictors**: Position size, leverage, trading history

---

## 📈 Interactive Dashboard

Run the Streamlit dashboard for interactive exploration:
```bash
streamlit run streamlit_dashboard.py
```

**Features**:
- 6 analysis pages
- 30+ interactive charts
- Real-time filtering
- Export capabilities

---

## 📚 Key Metrics Explained

### Sentiment Classifications
| Classification | Range | Market Condition |
|---|---|---|
| Extreme Fear | 0-24 | Panic selling |
| Fear | 25-44 | Bearish |
| Neutral | 45-54 | Balanced |
| Greed | 55-74 | Bullish |
| Extreme Greed | 75-100 | FOMO buying |

### Trader Performance Segments
| Segment | Characteristic | Avg Profit | Risk Level |
|---------|---|---|---|
| **Consistent Winners** | High risk-adj return | ₹533K | Low drawdown |
| **Average Traders** | Mixed results | ₹201K | High volatility |
| **Inconsistent** | Low return/high risk | ₹113K | High drawdown |

---

## 🔍 How to Reproduce Results

1. **Ensure data files are present**:
   ```bash
   ls -la fear_greed_index__1_.csv historical_data__1_.csv
   ```

2. **Run notebook (recommended)**:
   ```bash
   jupyter notebook Untitled117__2_.ipynb
   # Run all cells in order
   ```

3. **Expected output**:
   - 20+ visualizations
   - 5+ statistical tables
   - Trader segmentation results
   - ML model performance metrics

---

## 📊 Outputs Generated

### Charts (in `outputs/charts/`)
- Trade frequency by sentiment
- Performance metrics by sentiment
- Trader segment distribution
- Profit vs maximum drawdown scatter
- Leverage distribution
- Long/short ratio analysis
- Position size comparison
- Win rate by segment

### Tables (in `outputs/tables/`)
- Sentiment statistics
- Daily PnL statistics
- Trader segment metrics
- Risk metrics by segment
- Feature importance (ML model)

### Models (in `outputs/models/`)
- Trained Random Forest classifier
- Feature engineering pipeline

---

## 🎓 Learning Outcomes

This analysis demonstrates:
- ✓ Data cleaning & preprocessing at scale (200K+ records)
- ✓ Statistical analysis & hypothesis testing
- ✓ User segmentation & behavioral analysis
- ✓ Sentiment-driven trading patterns
- ✓ Feature engineering for ML
- ✓ ML model development & evaluation
- ✓ Data visualization best practices
- ✓ Business insight extraction

---

## 🐛 Troubleshooting

### Error: "File not found"
```bash
# Ensure CSV files are in current directory
ls -la *.csv
```

### Error: "ModuleNotFoundError"
```bash
# Reinstall dependencies
pip install --upgrade -r requirements.txt
```

### Jupyter kernel crash
```bash
# Restart kernel: Kernel → Restart → Clear Output
# Then run cells sequentially
```

### Slow dashboard load
```bash
# First load is slow (200K records). Subsequent loads are instant.
# Wait 2-3 seconds for initial load.
```

---

## 📞 Contact & Questions

For any questions about methodology or findings, refer to:
- **METHODOLOGY_AND_INSIGHTS.md** - Detailed explanations
- **SUMMARY.md** - Executive summary
- **Notebook comments** - Code-level documentation
- **Dashboard tooltips** - Interactive help

---

## 📝 References

**Data Sources**:
- Bitcoin Fear-Greed Index: Publicly available index
- Hyperliquid Trading Data: Anonymous trader accounts

**Libraries Used**:
- pandas: Data manipulation
- numpy: Numerical computing
- matplotlib/seaborn: Visualization
- plotly: Interactive charts
- scikit-learn: Machine learning
- streamlit: Dashboard framework

---

## ✅ Submission Checklist

- [x] Data preparation complete (Part A)
- [x] Core analysis complete (Part B)
- [x] Actionable strategies provided (Part C)
- [x] Bonus: ML model + Dashboard
- [x] README with setup instructions
- [x] Methodology documentation
- [x] All outputs generated
- [x] Clean, reproducible code
- [x] Clear insights with evidence

---

## 📄 License & Attribution

This analysis is submitted as part of the Primetrade.ai internship application.
All code is original unless otherwise attributed.

---

**Version**: 1.0  
**Last Updated**: 2024  
**Status**: ✅ Complete & Ready for Submission

---

## 🎯 Quick Navigation

- **Want to run the notebook?** → Start with `jupyter notebook Untitled117__2_.ipynb`
- **Want interactive exploration?** → Run `streamlit run streamlit_dashboard.py`
- **Want detailed findings?** → Read `METHODOLOGY_AND_INSIGHTS.md`
- **Want quick summary?** → Read `SUMMARY.md`
- **Need setup help?** → Follow the Installation section above
