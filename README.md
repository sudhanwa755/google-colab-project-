# 📈 Apple Stock Price Prediction using Linear Regression

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/sudhanwa755/google-colab-project-/blob/main/Stock_Prediction_using_Linear_Regression_final_TAE.ipynb)

Predicting Apple Inc. (AAPL) stock prices using a simple **Linear Regression** model.  
Implemented in Python and designed to run seamlessly in **Google Colab**.

---

## 📂 Files

- `Stock_Prediction_using_Linear_Regression_final_TAE.ipynb` — Main Colab notebook  
- `AAPL.csv` — Dataset (historical Apple stock prices)  
- `apple-stock-prediction-ml.pdf.pdf` — Project report  
- `README.md` — This file  

---

## 📌 Dataset Details

- **Source:** Historical stock data for Apple Inc.  
- **Format:** CSV  
- **Columns:** `Date`, `Open`, `High`, `Low`, `Close`, `Volume`  

---

## 🧠 Libraries Used

- `pandas`  
- `numpy`  
- `matplotlib`  
- `seaborn`  
- `scikit-learn`  

---

## 🚀 Run the Project

To run this project in **Google Colab**:

1. Click the **"Open in Colab"** badge above.  
2. Clone the repository and navigate into it:  
   ```bash
   !git clone https://github.com/sudhanwa755/google-colab-project-.git
   %cd google-colab-project-


## 📝 Project Overview

The primary goal of this project was to forecast the closing price of Apple stock using a Linear Regression model — 
a supervised learning algorithm suitable for predicting continuous values.

Key Steps and Implementations:

1. Data Loading and Preparation:
   - Loaded historical Apple stock dataset (AAPL.csv).
   - Converted 'Date' column to datetime format.
   - Selected relevant columns: Open, High, Low, Close, Volume.
   - Detected and treated outliers using Interquartile Range (IQR) method, replacing extreme values with median to reduce volatility impact.

2. Feature Engineering:
   - Created new features to improve model accuracy:
     * Moving Averages (MA5, MA20, MA50): rolling averages of closing price.
     * Daily Return: percentage change day-over-day.
     * Relative Strength Index (RSI): 14-day momentum indicator.
   - Handled missing values introduced by rolling calculations with forward fill.
   - Dropped 'Date' column before modeling as it is not a direct feature.

3. Data Scaling and Splitting:
   - Separated features (X) and target variable (y = closing price).
   - Scaled features with StandardScaler to normalize.
   - Split data chronologically into train (70%), validation (15%), and test (15%) sets without shuffling to preserve time order.

4. Model Training and Evaluation:
   - Trained Linear Regression model on training data.
   - Evaluated using:
       - Mean Absolute Error (MAE): 2.79
       - Root Mean Squared Error (RMSE): 15.99
       - R-squared (R²) Score: 0.94 (excellent fit)
   - Performed threshold-based classification on trend direction (up/down) with:
       - Trend Classification Accuracy: 98.73%
       - Precision, Recall, F1-score ~0.98-0.99 for both classes.

5. Visualization:
   - Plotted actual vs predicted closing prices.
   - Created confusion matrix for trend classification.
   - Validated model's trend-following behavior.

Conclusion:
- Linear Regression demonstrated strong stock price prediction ability with R²=0.94.
- Feature engineering, outlier handling, and scaling improved model stability and performance.
- High trend classification accuracy indicates reliable direction prediction.
- Limitations remain due to market volatility and lack of complex sequential pattern handling.
