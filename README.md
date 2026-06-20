📊 Trader Behavior Insights from Fear & Greed Sentiment Analysis
Overview

This project analyzes the relationship between crypto market sentiment (Fear & Greed Index) and trader behavior/performance using historical trading data.

The objective is to determine whether traders modify their trading strategies, risk exposure, and profitability under different market sentiment conditions such as:

Extreme Fear
Fear
Neutral
Greed
Extreme Greed

The project combines sentiment data with transaction-level trading data to generate actionable insights, trader segments, and predictive models.

Business Problem

Market sentiment often influences trader decisions.

This project investigates:

Does trader profitability differ between Fear and Greed periods?
Do traders change behavior based on sentiment?
Trade frequency
Position sizing
Long/Short bias
Risk exposure
Which trader segments perform best?
Can future profitability or volatility be predicted using sentiment and behavioral features?
Dataset Description
Historical Trading Data

Contains trade-level information including:

Feature	Description
Account	Unique trader identifier
Coin	Cryptocurrency traded
Execution Price	Trade execution price
Size Tokens	Number of tokens traded
Size USD	Dollar value of trade
Side	Buy/Sell
Direction	Buy, Sell, Close Long, Close Short
Closed PnL	Realized profit/loss
Fee	Transaction fee
Timestamp IST	Trade execution timestamp
Fear & Greed Index Data
Feature	Description
value	Fear & Greed score (0-100)
classification	Sentiment category
date	Observation date

Sentiment Classification:

Score Range	Sentiment
0-24	Extreme Fear
25-49	Fear
50-74	Greed
75-100	Extreme Greed
Methodology
1. Data Preprocessing
Converted timestamps to datetime format
Extracted trading date
Removed inconsistencies
Merged trading data with sentiment data on date
2. Feature Engineering

Generated additional metrics:

Daily PnL

Measures trader profitability per day.

Win Rate

Percentage of profitable trades.

Trade Frequency

Number of trades executed per day.

Long/Short Ratio

Measures directional bias.

Exposure Ratio

Approximates trading aggressiveness.

Drawdown Proxy

Measures decline from peak cumulative profitability.

3. Exploratory Data Analysis

Performed:

Sentiment distribution analysis
PnL analysis by sentiment
Trade frequency analysis
Position size analysis
Long vs Short analysis
Drawdown analysis
4. Trader Segmentation

Traders were segmented into groups such as:

High vs Low Risk Traders
Frequent vs Infrequent Traders
Consistent vs Inconsistent Performers

using behavioral and profitability metrics.

5. Predictive Modeling

Built machine learning models to predict:

Next-day profitability
Future PnL volatility

using:

Sentiment score
Trade frequency
Exposure ratio
Position size
Historical performance

Models used:

Random Forest Regressor
Random Forest Classifier
Key Findings
Insight 1: Sentiment Impacts Profitability

Extreme Greed periods generated the highest average profit per trade.

Insight 2: Trading Activity Changes with Sentiment

Trade frequency increased significantly during Fear and Greed periods compared to Neutral markets.

Insight 3: High-Risk Traders Experience Larger Drawdowns

Aggressive traders generated higher returns but suffered larger drawdowns.

Insight 4: Long/Short Bias Varies Across Sentiment Regimes

Traders displayed stronger directional bias during extreme sentiment conditions.

Strategy Recommendations
Strategy 1

During Extreme Fear periods:

Reduce exposure
Focus on capital preservation
Avoid excessive leverage
Strategy 2

During Extreme Greed periods:

Increase participation selectively
Maintain risk controls
Use trailing exits to protect profits
Repository Structure
Trader-Sentiment-Analysis/
│
├── trader-sentiment-analysis.ipynb
├── fear_greed_index.csv
├── historical_data.csv
├── METHODOLOGY_AND_INSIGHTS.md
└── README.md
Requirements

Install required libraries:

pip install pandas numpy matplotlib seaborn scikit-learn jupyter
How to Run
Step 1: Clone Repository
git clone <repository-url>
cd Trader-Sentiment-Analysis
Step 2: Place Dataset

Download or obtain:

historical_data.csv

and place it in the project root directory.

Final structure:

Trader-Sentiment-Analysis/
│
├── historical_data.csv
├── fear_greed_index.csv
├── trader-sentiment-analysis.ipynb
└── README.md
Step 3: Launch Jupyter Notebook
jupyter notebook

Open:

trader-sentiment-analysis.ipynb
Step 4: Run All Cells

Execute notebook cells sequentially:

Kernel → Restart & Run All
Technologies Used
Python
Pandas
NumPy
Matplotlib
Seaborn
Scikit-Learn
Jupyter Notebook
Future Improvements
Streamlit Dashboard Deployment
Real-time Sentiment Integration
Advanced ML Models (XGBoost, LightGBM)
Portfolio Risk Analytics
Reinforcement Learning Based Trading Strategies
Author

Ankita Agrawal
Data Science & Machine Learning Enthusiast
