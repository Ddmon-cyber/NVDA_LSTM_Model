# 📊 NVDA LSTM Model — Stock Direction Forecasting using Deep Learning

This project applies a **Long Short-Term Memory (LSTM)** neural network to forecast the **weekly directional movement** (up or down) of **NVIDIA Corporation (NVDA)** stock.  
The model integrates **technical indicators** such as Moving Averages (SMA20, SMA50, SMA200), **MACD**, and **RSI** to capture trend and momentum behavior from historical price data.


## 🔍 Overview
- **Objective:** Predict whether NVDA’s stock price will close higher or lower in the following week.  
- **Data Source:** Weekly OHLCV (Open, High, Low, Close, Volume) data collected via `yfinance`.  
- **Approach:**
  1. Data preprocessing and feature engineering (MACD, RSI, SMA indicators)
  2. Sequence creation for time-series input (20-week lookback)
  3. Training a stacked LSTM model with dropout regularization
  4. Evaluation using accuracy, ROC-AUC, and confusion matrix


## 🧠 Model Architecture
- Two stacked **LSTM** layers (64 and 32 units)  
- **Dropout (0.2)** to reduce overfitting  
- **Dense (sigmoid)** output for binary classification  
- Optimizer: **Adam**  
- Loss function: **Binary Crossentropy**


## 📈 Results Summary
- The LSTM achieved **~34% test accuracy**, showing the **difficulty of capturing weekly stock direction** using only technical indicators.  
- Results highlight the **non-linear and volatile nature** of financial time-series data.  
- Future work could explore:
  - Incorporating **GRU** or **Transformer** architectures  
  - Adding **sentiment or macroeconomic features**  
  - Using **ensemble or hybrid models** for improved stability  


## 🧰 Tools & Libraries
- Python 🐍  
- TensorFlow / Keras  
- Pandas & NumPy  
- Scikit-learn  
- Matplotlib  
- yfinance  


## 📚 Learning Outcomes
This project demonstrates the **data mining workflow** — from data understanding to model evaluation.  
It provides hands-on insight into:
- The challenges of **machine learning-based financial forecasting**
- The role of **feature engineering and data scaling**
- The importance of **realistic performance evaluation** rather than chasing accuracy.


### ✍️ Author
**Nur Hidayah Binti Abd Rahman**  
Master in Data Science*  


### 📅 Last Updated
October 2025
