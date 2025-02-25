# Stock-Price-Prediction-RF-vs-GRU
This project compares Random Forest (RF) and Gated Recurrent Unit (GRU) for stock price prediction using Amazon (AMZN) stock data from 2015 to 2023. The analysis evaluates how machine learning (RF) and deep learning (GRU) models handle stock market forecasting, focusing on accuracy, variance, and feature importance.

# 📊 Stock Price Prediction: Random Forest vs. GRU  

## 🔍 Project Overview  
This project compares the performance of **Random Forest (RF)** and **Gated Recurrent Unit (GRU)** models for **predicting stock prices**. The goal is to analyze how **machine learning (RF)** and **deep learning (GRU)** handle stock market forecasting, considering accuracy, variance, and feature importance.  

## 📁 Repository Contents  
- **`Stock-Price-Prediction-RF-vs-GRU.ipynb`** - Jupyter Notebook containing data preprocessing, model training, and evaluation.  
- **`amazon_stock_data_cleaned.csv`** - Preprocessed stock price dataset for model training.  
- **`Stock-Price-Prediction-RF-vs-GRU.pptx`** - Presentation summarizing findings and model comparison.  

## 📊 Dataset Information  
- **Source:** Yahoo Finance - **Amazon (AMZN) stock data**  
- **Date Range:** 2015 - 2023  
- **Key Columns:**
  - **Features**: Open, High, Low, Volume  
  - **Target Variable**: Adjusted Close Price  
- **Dataset Size**: ~2000+ rows  

## 🔧 Methodology  
### **1️⃣ Data Preprocessing**
- Convert **Date** column to date format and remove invalid rows.  
- Ensure numerical columns (**Open, High, Low, Volume**) have no missing values.  
- Normalize features for **GRU training**.  
- Feature engineering:  
  - **RF Model:** Uses **Open, High, Low** as features.  
  - **GRU Model:** Includes **Moving Averages (MA10, MA50) and Volume Change**.  

### **2️⃣ Machine Learning Model - Random Forest (RF)**
- **Features Used**: Open, High, Low  
- **Target Variable**: Adjusted Close Price  
- **Hyperparameters**:
  - Number of Trees: **100** (adjustable via Streamlit UI)  
  - Train-Test Split: **80% training, 20% testing**  

### **3️⃣ Deep Learning Model - Gated Recurrent Unit (GRU)**
- **Model Architecture**:
  - **Input:** Last **5 days** of data (time window = 5).  
  - **Layers:** Two **GRU layers** (50 units each), Dropout (40%), Dense output layer.  
- **Hyperparameters**:
  - Training Epochs: **50**  
  - Batch Size: **32**  

### **4️⃣ Model Comparison**
| Model  | Accuracy (R² Score) | Error (MSE) | Strengths |
|--------|------------------|------------|-----------|
| **Random Forest** | **High (close to 1.0)** | Low | Captures static relationships well |
| **GRU** | Lower than RF | Higher | Struggles with small datasets |

- **RF performed significantly better than GRU** on this dataset.  
- The **small dataset size** limited GRU's ability to fully utilize temporal dependencies.  
- Future work should explore **larger datasets** and **more complex deep learning architectures**.  

## 🚀 How to Run the Project  
1. **Install required dependencies**:  
   ```sh
   pip install pandas numpy scikit-learn tensorflow keras matplotlib seaborn yfinance
2. Download the dataset (amazon_stock_data_cleaned.csv) and place it in the same directory.
3. Run the Jupyter Notebook (Stock-Price-Prediction-RF-vs-GRU.ipynb) to train and evaluate models.
4. Analyze model performance using visualizations and metrics.
## 🔗 References
1. Yahoo Finance API: Yahoo Finance
2. Scikit-Learn (Random Forest): Documentation
3. TensorFlow (GRU Model): Documentation
## 👤 Author
Zhenghao An

## ⭐ Contributions & Feedback
If you find this project useful, feel free to star ⭐ the repository and provide feedback!
## Disclaimer
This project was developed as part of my coursework at Boston University (BU MET Program). The contents of this repository represent my own work and do not include any proprietary course materials, data, or solutions provided by BU. If you are a current student, please adhere to BU’s academic integrity policies.
