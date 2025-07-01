# 🛡️ CICIDS2017 - Monday Anomaly Detection

This project focuses on analyzing and detecting anomalies in the **CICIDS 2017 Monday dataset** using unsupervised machine learning methods. The dataset simulates normal and malicious network traffic generated in a controlled environment, specifically from **Monday's working hours (BENIGN only)**.

---

## 📁 Dataset Overview

- **Source**: [CICIDS2017 Dataset](https://www.unb.ca/cic/datasets/ids-2017.html)
- **File Used**: `Monday-WorkingHours.pcap_ISCX.csv`
- **Rows**: ~490K  
- **Columns**: 71  
- **Label**: Only `BENIGN` traffic is present in this file.

---

## 📊 Objective

The objective is to:
- **Clean & preprocess** the dataset,
- **Visualize** it using PCA & statistical plots,
- Apply **unsupervised anomaly detection** via **Isolation Forest**,
- Evaluate model performance on clean network data.

---

## 🔧 Steps Performed

### ✅ Data Cleaning
- Removed **duplicate rows** (~66k).
- Handled **missing values**.
- Replaced **infinite values** with NaN and filled with mean.
- Reset and renamed messy column headers (`F0`, `F1`, ..., `F69`, `Label`).

### 📉 Preprocessing
- Converted `Label` to numerical format (BENIGN = 0).
- Verified feature distributions before and after cleaning.
- Saved the cleaned dataset for reuse.

### 📌 Visualization
- PCA plots generated:
  - Before cleaning
  - After cleaning
- Distributions of features using `seaborn` and `matplotlib`.

### 🧠 Anomaly Detection
- Used **Isolation Forest** (unsupervised).
- Identified outliers in what should be "clean" benign traffic.

```text
              precision    recall  f1-score   support

      BENIGN       1.00      0.98      0.99    423758
     Anomaly       0.00      0.00      0.00         0

    accuracy                           0.98    423758
   macro avg       0.50      0.49      0.49    423758
weighted avg       1.00      0.98      0.99    423758

🚀 How to Run (Google Colab)
Open monday_to_sunday.ipynb in Google Colab.

Upload the dataset (Monday-WorkingHours.pcap_ISCX.csv) from CICIDS2017.

Run cells step by step for:

Cleaning & preprocessing

PCA visualizations

Model training & anomaly detection

💡 Future Improvements
Combine with Tuesday to Friday data for multi-class classification.

Apply supervised learning (e.g., RandomForest, XGBoost).

Compare unsupervised methods like One-Class SVM, AutoEncoders, LOF.

Build a full intrusion detection pipeline using all days of CICIDS2017.

🧠 Technologies Used
Python 3.x

pandas, numpy

matplotlib, seaborn

scikit-learn

Google Colab

📌 Project Structure
sql
Copy
Edit
📁 cicids2017-monday-anomaly-detection
├── monday_to_sunday.ipynb       ← Jupyter Notebook with full workflow
└── README.md                     ← Project documentation
📚 References
CICIDS2017 Dataset

Isolation Forest - Scikit-learn

🔖 Topics / Tags (GitHub)
Add these in repo settings (Topics):

css
Copy
Edit
cybersecurity, anomaly-detection, intrusion-detection, cicids2017, isolation-forest, unsupervised-learning, pca, data-cleaning, network-traffic
🧑‍💻 Author
Br7eleven
