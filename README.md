# Cryptocurrency Price Analysis & Prediction (Top 10)

A comprehensive machine learning project for analyzing and predicting cryptocurrency prices using historical OHLCV (Open, High, Low, Close, Volume) data for the top 10 cryptocurrencies.

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)
![ML](https://img.shields.io/badge/Machine%20Learning-Random%20Forest-green.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

## 📊 Project Overview

This project analyzes historical cryptocurrency price data and builds predictive models to forecast future prices across multiple timeframes (5 days, 1 month, 3 months, 6 months, and 1 year). The analysis includes data exploration, correlation analysis, feature engineering, and machine learning model development using Random Forest Regression.

### Key Features

- **Data Analysis**: Comprehensive exploration of cryptocurrency market data
- **Visual Analytics**: Interactive candlestick charts and popularity rankings
- **Correlation Analysis**: Identify relationships between price features
- **Feature Engineering**: Moving averages, lagged values, and daily returns
- **Multi-Timeframe Predictions**: Forecast prices for 5 different time horizons
- **Model Evaluation**: MSE-based performance metrics

## 📁 Project Structure

```
cryptos-price-analysis/
│
├── cryptos_price_analysis.ipynb    # Main analysis notebook
├── README.md                         # Project documentation
├── requirements.txt                  # Python dependencies
│
└── data/
    └── cryptos-ohlcv-daily.csv      # Historical cryptocurrency data
```

## 🚀 Getting Started

### Prerequisites

- Python 3.8 or higher
- Jupyter Notebook or JupyterLab
- pip (Python package manager)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/cryptos-price-analysis.git
   cd cryptos-price-analysis
   ```

2. **Create a virtual environment** (optional but recommended)
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install required packages**
   ```bash
   pip install -r requirements.txt
   ```

4. **Launch Jupyter Notebook**
   ```bash
   jupyter notebook
   ```

5. **Open and run** `cryptos_price_analysis.ipynb`

## 📦 Dependencies

```
pandas>=1.5.0
numpy>=1.23.0
matplotlib>=3.6.0
seaborn>=0.12.0
plotly>=5.11.0
scikit-learn>=1.2.0
requests>=2.28.0
```

## 📈 Analysis Workflow

### 1. Data Preparation

- **Load Dataset**: Import historical OHLCV data for top 10 cryptocurrencies
- **Handle Missing Data**: Clean and preprocess the dataset
- **Explore Trends**: Visualize daily price movements using candlestick charts
- **Popularity Analysis**: Analyze cryptocurrency weights based on trading volume

### 2. Correlation Analysis

- Calculate correlation matrix between price features (open, high, low, close, volume)
- Visualize correlations using heatmaps
- Identify strong relationships between variables

### 3. Feature Engineering

Created features include:
- **Moving Averages**: 5-day and 20-day moving averages
- **Lagged Features**: Previous 3 days' closing prices
- **Daily Returns**: Percentage change in closing price
- **Target Variables**: Future prices for 5 timeframes (5d, 30d, 90d, 180d, 365d)

### 4. Model Development

#### Train-Test Split
- **80-20 split**: 80% training data, 20% testing data
- **Time-based split**: Preserves sequential nature of time-series data
- **Training Period**: Historical data up to cutoff date
- **Testing Period**: Data from cutoff date onwards

#### Model Selection
- **Algorithm**: Random Forest Regressor
- **Configuration**: 100 estimators, random state for reproducibility
- **Multi-Target**: Separate models for each timeframe

### 5. Model Evaluation

- **Metric**: Mean Squared Error (MSE)
- **Timeframes Evaluated**:
  - 5-day predictions
  - 1-month predictions
  - 3-month predictions
  - 6-month predictions
  - 1-year predictions

### 6. Results & Visualization

- Price prediction summary for all cryptocurrencies
- Individual coin prediction plots (2x5 grid)
- Combined prediction trends (logarithmic scale)
- Formatted currency predictions

## 📊 Key Visualizations

### 1. Candlestick Charts
Interactive daily price charts for each cryptocurrency showing:
- Open, High, Low, Close prices
- Historical price trends
- Monthly tick marks

### 2. Popularity Rankings
Bar chart displaying:
- Weighted popularity scores (1-10 scale)
- Color-coded by weight
- Trading volume-based rankings

### 3. Correlation Matrix
Heatmap showing:
- Relationships between OHLCV features
- Color-coded correlation coefficients
- Strong positive correlations (close to 1.0)

### 4. Price Predictions
- **Individual Plots**: Separate prediction charts for each cryptocurrency
- **Combined Plot**: All cryptocurrencies on logarithmic scale for comparison
- **Timeframe Trends**: How predictions evolve across different time horizons

## 🎯 Model Performance

The Random Forest models are evaluated using Mean Squared Error (MSE) for each prediction timeframe. Lower MSE values indicate better model performance and more accurate predictions.

### Why Random Forest?

- **Ensemble Learning**: Combines multiple decision trees for robust predictions
- **Feature Importance**: Identifies which features contribute most to predictions
- **Non-linear Relationships**: Captures complex patterns in cryptocurrency data
- **Handles Outliers**: Robust to extreme price movements
- **No Overfitting**: Built-in regularization through averaging

## 📋 Results Format

Predictions are presented in a comprehensive summary table:

| Symbol | Current Price | 5D Prediction | 1M Prediction | 3M Prediction | 6M Prediction | 1Y Prediction |
|--------|--------------|---------------|---------------|---------------|---------------|---------------|
| BTC    | $XX,XXX.XX   | $XX,XXX.XX    | $XX,XXX.XX    | $XX,XXX.XX    | $XX,XXX.XX    | $XX,XXX.XX    |
| ETH    | $X,XXX.XX    | $X,XXX.XX     | $X,XXX.XX     | $X,XXX.XX     | $X,XXX.XX     | $X,XXX.XX     |
| ...    | ...          | ...           | ...           | ...           | ...           | ...           |

## 🔍 Key Insights

1. **High Correlation**: OHLCV features show strong correlations (near 1.0), indicating consistent price movements
2. **Moving Averages**: Smoothing techniques help identify trends and reduce noise
3. **Time-Series Nature**: Preserving temporal order in train-test split is crucial for accurate predictions
4. **Multi-Timeframe Approach**: Different models for different prediction horizons improve accuracy
5. **Exponential Weighted Moving Average**: Used for target calculation to capture recent price trends

## 🛠️ Future Improvements

- [ ] Implement additional models (LSTM, GRU, XGBoost)
- [ ] Add more technical indicators (RSI, MACD, Bollinger Bands)
- [ ] Incorporate sentiment analysis from social media
- [ ] Real-time data fetching and prediction
- [ ] Web dashboard for interactive predictions
- [ ] Model hyperparameter tuning
- [ ] Cross-validation for better performance estimates
- [ ] Feature importance analysis

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👤 Author

**Nay Zaw Lin**
- GitHub: [@nayzawlin](https://github.com/nayzawlin)
- Email: nayzawlin07@gmail.com

## 🙏 Acknowledgments

- Historical cryptocurrency data from public APIs
- Plotly for interactive visualizations
- Scikit-learn for machine learning algorithms
- The cryptocurrency community for continuous innovation

## ⚠️ Disclaimer

**This project is for educational and research purposes only.** Cryptocurrency markets are highly volatile and unpredictable. The predictions made by this model should **NOT** be used as financial advice or the sole basis for investment decisions. Always:

- Do your own research (DYOR)
- Consult with financial advisors
- Invest only what you can afford to lose
- Be aware of the risks involved in cryptocurrency trading

Past performance does not guarantee future results.

## 📞 Contact

For questions, suggestions, or collaborations:
- **Email**: nayzawlin07@gmail.com
- **GitHub Issues**: [Create an issue](https://github.com/yourusername/cryptos-price-analysis/issues)

---

⭐ If you found this project helpful, please consider giving it a star!

**Built with ❤️ by CYNASOFT**
