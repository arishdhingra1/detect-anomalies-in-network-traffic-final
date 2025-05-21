# 📘 Network Traffic Anomaly Detection Using Machine Learning

**Author:** Arish Dhingra  
**Contact:** 📧 arish_dhingra@outlook.com

---

## 🧭 Executive Summary

This project applies machine learning techniques to detect anomalies in network traffic—particularly malicious behavior such as Distributed Denial-of-Service (DDoS) attacks. Using the CICIDS 2017 dataset, we conducted exploratory data analysis (EDA), built multiple supervised and unsupervised models, tuned them using cross-validation and grid search, and evaluated their performance across multiple metrics. The top-performing model (Random Forest) achieved near-perfect classification, forming the basis for real-time anomaly detection systems.

---

## 🎯 Problem Statement

In an increasingly digital world, both enterprise and home networks are vulnerable to persistent threats. Unfortunately, many users lack the tools to detect abnormal activity until it's too late. This project seeks to bridge that gap by leveraging machine learning to identify suspicious patterns in network traffic and flag potential security risks proactively.

**Research Question:**  
Can we detect anomalies in network traffic that may indicate suspicious or malicious activity using machine learning models trained on historical traffic patterns?

---

## 📊 Dataset

**Primary Source:** CICIDS 2017 Dataset (Canadian Institute for Cybersecurity)  
**File Used:** `Friday-WorkingHours-Afternoon-DDos.pcap_ISCX.csv`  
- Contains both benign and DDoS traffic
- Publicly available

**Planned Extension:** Use live traffic logs captured via Zeek and Wireshark to expand dataset and support real-time inference.

---

## 🧪 Methodology

### 🔧 Data Preprocessing
- Replaced or removed missing, infinite, and invalid values
- Removed features with constant values or extreme magnitudes
- Converted labels to binary anomaly indicator (Benign vs. Not Benign)
- Standardized all numeric features

### 📈 Exploratory Data Analysis (EDA)
- Correlation heatmaps to identify redundant features
- Visualized class imbalance and key feature distributions

### 🤖 Modeling and Evaluation
Models Implemented:
- **Logistic Regression (baseline)**
- **Random Forest**
- **Isolation Forest** (unsupervised)
- **Autoencoder** (unsupervised deep learning)

**Model Tuning:**
- Performed **GridSearchCV** for Logistic Regression and Random Forest
- Used **5-Fold Cross-Validation** to assess robustness

**Metrics Used:**
- Accuracy, Precision, Recall, F1-Score
- ROC AUC
- Confusion Matrix

---

## 📌 Results Summary

| Model               | Accuracy | Precision | Recall | F1-Score | ROC AUC |
|--------------------|----------|-----------|--------|----------|---------|
| Logistic Regression| 99.85%   | 99.86%    | 99.88% | 99.87%   | 99.85%  |
| Random Forest      | **99.99%** | **100.00%** | **99.99%** | **99.99%** | **99.99%** |
| Isolation Forest   | 34.49%   | 7.45%     | 1.31%  | 2.23%    | 39.87%  |
| Autoencoder        | 40.65%   | 38.16%    | 6.70%  | 11.40%   | 46.16%  |

- **Random Forest** outperformed all others, including Logistic Regression, in every metric.
- **Unsupervised models** struggled due to class imbalance and generic reconstruction heuristics.
- Confusion matrices visually confirmed classification reliability for top-performing models.

---

## 📌 Key Technical Components

- Multiple ML models evaluated and compared
- Grid search for hyperparameter optimization
- 5-fold cross-validation for evaluation stability
- Appropriate selection of metrics for imbalanced classification
- Autoencoder used for anomaly detection based on reconstruction error
- Confusion matrices and ROC curves for visual insight

---

## 🔄 Next Steps - Shared steps in report.

- ✅ Integrate live network data from home routers using Zeek and Wireshark
- ✅ Retrain models nightly and evaluate drift
- ✅ Automate prediction pipeline in Docker
- ✅ Deploy models to AWS (via ECS or Lambda) 
- ✅ Build dashboard for anomaly visualization
- ✅ Integrate Slack alerts for real-time incidents

---

## 📂 Project Deliverables

- [Link to notebook: Final Jupyter Notebook](https://github.com/arishdhingra1/detect-anomalies-in-network-traffic-final/blob/main/project_final.ipynb)
- [Report](https://github.com/arishdhingra1/detect-anomalies-in-network-traffic-final/blob/main/project_final.ipynb)
- [Presentation](https://github.com/arishdhingra1/detect-anomalies-in-network-traffic-final/blob/main/project_final.ipynb)

---

## 📬 Contact

For questions, collaboration, or more information:
**Email:** arish_dhingra@outlook.com
