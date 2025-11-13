# 📊 NVDA LSTM Model — Stock Direction Forecasting using Deep Learning

This project investigates the use of a Long Short-Term Memory (LSTM) network to forecast weekly price direction for NVIDIA (NVDA).
Beyond model development, this project emphasizes **failure analysis, error diagnostics,** and **root-cause investigation.**


## 🔍 Overview
- **Objective:** 
  Predict whether NVDA’s closing price will increase (1) or decrease (0) the following week.
  
- **Data Source:** 
  Weekly OHLCV data collected via yfinance, enriched with technical indicators:
  - SMA20, SMA50, SMA200
  - MACD, Signal Line, Histogram
  - RSI  
- **Approach:**
  1. Data preprocessing and feature engineering (MACD, RSI, SMA indicators)
  2. Sequence creation for time-series input (20-week lookback)
  3. Training a stacked LSTM model with dropout regularization
  4. Evaluation using accuracy, ROC-AUC, and confusion matrix


## ❗ Failure Analysis Summary
The LSTM model achieved 34.38% test accuracy, below random benchmark levels.
Detailed analysis reveals several systemic failure patterns.

## 1️⃣ Overfitting & Generalization Issues
- Training accuracy increased steadily
- Validation accuracy remained unstable
- Validation loss diverged

### Conclusion:
The model memorized patterns in the training set but could not generalize to unseen data.

## 2️⃣ Low Confidence Predictions
Model outputs were concentrated between 0.40–0.48, indicating:
- High uncertainty
- Weak decision boundaries
- Minimal signal extraction

## 3️⃣ Failure Patterns During Volatile Periods
Misclassifications clustered around:
- Earnings release weeks
- Breakouts/reversalsH
- igh-volume anomalies

### Interpretation:
Weekly direction is heavily influenced by news and events not captured by technical indicators.

## 4️⃣ ROC-AUC = 0.27
A score below 0.50 suggests:
- The model learned misleading patterns
- Possible inverse correlation
- Non-stationary market behavior that breaks learned dependencies

## 🧪 Root Cause Diagnosis
### Data-Related Factors
- Weekly directional changes are inherently noisy
- Technical indicators alone are insufficient
- Market regimes shift unpredictably
- High volatility reduces signal consistency
### Model-Related Factors
- LSTM architecture may be too shallow
- Lookback window (20 weeks) may be limited
- Features do not capture external market drivers
- Dropout insufficient to mitigate overfitting
### Task-Related Factors
- Binary directional forecasting is more difficult than regression
- Market sentiment and macroeconomic influences are not included

## 🛠️ Recommendations for Improvement
### Feature Enhancements
- Include macroeconomic indicators (VIX, interest rates, CPI, etc.)
- Add news or social sentiment scores
- Include volatility clusters or regime-based labeling
### Model Enhancements
- Experiment with GRU or Transformer architectures
- Apply attention mechanisms
- Use hybrid CNN+LSTM or ensemble models
### Evaluation Improvements
- Slice-based error analysis (by volatility, trend, volume)
- Threshold tuning and calibration
- More robust cross-validation for time-series

## 📈 Visualizations Included
This repository includes:
- Training vs Validation Accuracy & Loss
- Confusion Matrix
- Classification Report
- ROC Curve
- Prediction Probability Distribution
- Random prediction samples
These visuals support the failure-analysis conclusions.

## 🧰 Tools & Libraries Used
- Python
- TensorFlow / Keras
- Pandas & NumPy
- Scikit-learn
- yfinance
- Matplotlib

## ✍️ Author
### Nur Hidayah Binti Abd Rahman
Master in Data Science

📅 Last Updated: November 2025
