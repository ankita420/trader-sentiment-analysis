Trader Behavior vs Market Sentiment Analysis
Overview

This project analyzes how cryptocurrency traders behave under different market sentiment conditions using the Fear & Greed Index.

The analysis investigates:

Profitability under different sentiment regimes
Trading frequency changes during Fear vs Greed
Long/Short behavior
Position sizing behavior
Risk metrics (Drawdown, Exposure)
Trader segmentation
Predictive modeling of future trader performance
Dataset
1. Historical Trading Data

Contains individual trade-level information including:

Account
Coin
Execution Price
Size USD
Size Tokens
Direction
Closed PnL
Fee
Timestamp

⚠️ Not included in this repository because the file exceeds GitHub size limits.

Place the file in the project root directory:

project/
│
├── historical_data.csv
├── fear_greed_index.csv
├── trader-sentiment-analysis.ipynb
├── README.md
└── METHODOLOGY_AND_INSIGHTS.md
2. Fear & Greed Dataset

Contains daily market sentiment:

Feature	Description
timestamp	Unix timestamp
value	Fear & Greed score
classification	Extreme Fear, Fear, Neutral, Greed, Extreme Greed
date	Calendar date
Project Structure
Trader-Sentiment-Analysis/
│
├── trader-sentiment-analysis.ipynb
├── fear_greed_index.csv
├── METHODOLOGY_AND_INSIGHTS.md
├── README.md
└── historical_data.csv (download separately)
Key Questions Answered
Performance Analysis
Does trader profitability differ during Fear vs Greed markets?
How does win rate change across sentiment conditions?
Behavioral Analysis
Do traders increase position sizes during Greed?
Does long/short preference change with sentiment?
How does trading activity vary across sentiment regimes?
Risk Analysis
Exposure Ratio
Drawdown Proxy
Daily PnL
Trading Frequency
Segmentation

Traders are grouped into:

High vs Low Risk
Frequent vs Infrequent Traders
Consistent vs Inconsistent Performers
Methodology
Data Preparation
Convert timestamps to datetime
Extract trading date
Merge trading data with Fear & Greed data using date
Aggregate trader activity daily
Feature Engineering

Features created:

Daily PnL
Win Rate
Trade Frequency
Exposure Ratio
Drawdown Proxy
Long/Short Ratio
Position Size Metrics
Analysis
Descriptive statistics
Sentiment comparison
Trader segmentation
Correlation analysis
Predictive modeling
Installation
Clone Repository
git clone https://github.com/ankita420/trader-sentiment-analysis.git

cd trader-sentiment-analysis
Create Environment
python -m venv venv

Activate environment:

Windows

venv\Scripts\activate

Linux/Mac

source venv/bin/activate
Install Dependencies
pip install pandas
pip install numpy
pip install matplotlib
pip install seaborn
pip install scikit-learn
pip install jupyter

or

pip install -r requirements.txt
Running the Project
Start Jupyter Notebook
jupyter notebook

Open:

trader-sentiment-analysis.ipynb

Run all cells sequentially.

Main Outputs

The notebook generates:

Tables
Average PnL by sentiment
Win rate by sentiment
Long/Short ratios
Exposure metrics
Trader segments
Visualizations
Sentiment distribution
PnL by sentiment
Trade frequency analysis
Drawdown analysis
Trader segmentation charts
Models
Next-day profitability prediction
Future volatility prediction
Feature importance analysis
Key Findings

Examples of findings generated:

Extreme Greed periods showed the highest average profit per trade.
Fear periods generated the highest overall trading activity.
High-risk traders experienced significantly larger drawdowns.
Trading behavior changed noticeably across sentiment regimes.

See:

METHODOLOGY_AND_INSIGHTS.md

for complete discussion and conclusions.

Technologies Used
Python
Pandas
NumPy
Matplotlib
Seaborn
Scikit-Learn
Jupyter Notebook
Author

Ankita Agrawal

Data Science & Machine Learning Student

Future Improvements
Advanced predictive models (XGBoost, LightGBM)
Interactive dashboards using Streamlit
Real-time sentiment integration
Portfolio-level risk analytics

Also create a requirements.txt file in the repository with:

pandas
numpy
matplotlib
seaborn
scikit-learn
jupyter

This makes your repository look much more professional for internship reviewers and recruiters.
