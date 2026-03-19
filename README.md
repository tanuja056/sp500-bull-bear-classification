# Stock Price Prediction using HMM, Kalman Filter, DBN, and XGBoost

## 📘 Overview
This project compares four different time‑series forecasting models—Hidden Markov Model (HMM), Kalman Filter, Dynamic Bayesian Network (DBN), and XGBoost—for predicting S&P 500 stock prices. The goal is to evaluate how each model performs across different window sizes using Mean Absolute Percentage Error (MAPE) as the primary metric.

The analysis shows that:
- **HMM** is the most stable and accurate among the probabilistic models.
- **Kalman Filter** performs well for small windows but becomes unstable for large windows.
- **DBN** shows moderate performance but degrades with larger windows.
- **XGBoost** outperforms all three classical models, especially for large window sizes.

---

## 📂 Dataset
This project uses the **S&P 500 historical price dataset**.

Place the dataset inside a folder named `data/` before running the notebook.

---

## 🔧 Methods

### **1. Hidden Markov Model (HMM)**
- Learns hidden market states and transition probabilities.
- Performs consistently well across most window sizes.
- Warning for large windows (>200):  
  “Some rows of transmat_ have zero sum because no transition from the state was ever observed.”  
  This occurs when the model does not observe enough state transitions in long sequences.

### **2. Kalman Filter**
- Performs well for small windows (5–50).
- Error increases sharply for large windows (100–200).
- Highly sensitive to noise and long‑range dependencies.

### **3. Dynamic Bayesian Network (DBN)**
- More stable than Kalman for large windows.
- Still shows increasing MAPE as window size grows.
- Underperforms compared to HMM.

### **4. XGBoost**
- Added as a modern baseline.
- Shows **steady improvement** as window size increases.
- Achieves the **lowest MAPE across all window sizes**.
- Most consistent and scalable model in the study.

---

## 📊 Results

### **MAPE Comparison Across Models**
- **HMM**: Best among classical models; stable across windows.
- **Kalman Filter**: Good for small windows; unstable for large windows.
- **DBN**: Moderate performance; error increases with window size.
- **XGBoost**: Best overall; lowest MAPE for all window sizes.

### **Key Observations**
- HMM handles both small and large windows effectively.
- Kalman Filter struggles with long sequences due to state estimation drift.
- DBN is more stable than Kalman but still inferior to HMM.
- XGBoost adapts extremely well to larger windows and outperforms all other models.

### **Visualizations Included**
- Line plot of S&P 500 prices  
- Bar charts comparing MAPE across models  
- Heatmaps showing MAPE across window sizes  
- Combined plots including XGBoost  

---

## ▶️ How to Run

1. Place the dataset inside a folder named `data/`.
2. Open the notebook: code.ipynb
3. Run all cells in order.

---

## 🛠️ Technologies
- Python  
- NumPy, Pandas  
- hmmlearn (HMM)  
- pykalman (Kalman Filter)  
- pgmpy (DBN)  
- XGBoost  
- Matplotlib, Seaborn  

---

## 📄 License
MIT License

