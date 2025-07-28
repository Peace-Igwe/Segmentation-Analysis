# 🧠 User Segmentation on Mobile Money Transaction Data (PaySim)

This project applies unsupervised machine learning to discover behavioral segments in a mobile money ecosystem using the **PaySim synthetic financial transaction dataset**. The primary objective is to uncover user patterns, support fraud detection, and enable targeted service strategies.

---

## 🔍 Project Overview

In mobile financial platforms, user behavior varies widely. Some are casual transactors, others are frequent users, and a few exhibit red-flag patterns. By clustering users based on their transaction history, we enable:

- 🎯 Precision marketing and personalization
- 🛡️ Targeted fraud risk management
- 📊 Customer lifecycle analytics

---

## 📚 Dataset Summary

- **Source**: PaySim (Simulated mobile money transactions)
- **Volume**: ~6.3 million transaction records
- **Features used**:
  - `step` – Hourly time index  
  - `type` – Transaction type  
  - `amount` – Transaction amount  
  - `oldbalanceOrg`, `newbalanceOrig` – Sender account balances  
  - `oldbalanceDest`, `newbalanceDest` – Recipient balances  
  - `isFraud`, `isFlaggedFraud` – Fraud indicators

---

## ⚙️ Methodology

### 🧼 Preprocessing & Feature Engineering
- Removed irrelevant/system-generated entries
- Created user-level aggregates:
  - Total transaction amount
  - Frequency of transactions
  - Average transaction size
  - Fraud frequency
- Scaled data with `MinMaxScaler`
- Encoded categorical variables using one-hot encoding

### 📈 Clustering
- **Model used**: K-Means Clustering
- **Number of clusters**: 4 (via Elbow Method & Silhouette Score)
- **Visualization**: PCA (Principal Component Analysis)

---

## 🔢 Segmentation Results

| Cluster | Segment Name     | % of Users | Key Traits |
|--------:|------------------|------------|------------|
| 0       | Dormant          | ~42%       | Minimal activity, low risk |
| 1       | Frequent Users   | ~25%       | Regular usage, medium spend |
| 2       | High Spenders    | ~18%       | Low frequency, large transactions |
| 3       | VIP Users        | ~15%       | High frequency + high value, fraud-prone |

---

## 🧠 Segment Interpretations

### Cluster 0 — Dormant
- Users with near-zero engagement  
- No fraud exposure  
- Potential for re-engagement or pruning  

### Cluster 1 — Frequent Users
- Consistent, mid-value transactions  
- Good candidates for loyalty programs and upsell opportunities  

### Cluster 2 — High Spenders
- Infrequent but large-value transfers  
- Higher fraud risk; needs periodic review  
- Strong potential for premium service offerings  

### Cluster 3 — VIP Users
- High-frequency, high-value users  
- Exhibit business-like activity  
- Justifies fraud surveillance and premium onboarding  

---

## 🎯 Business Impact

- **Fraud Detection**: Segments 2 & 3 highlighted as high-risk  
- **Customer Retention**: Segment 1 targeted for rewards  
- **Reactivation Campaigns**: Dormant users flagged for marketing re-engagement  
- **Data-Driven Personalization**: Segment-based customer journeys and notifications  

---

## 🛠️ Tools & Technologies

- **Language**: Python  
- **Libraries**: Pandas, NumPy, Scikit-learn, Seaborn, Matplotlib  
- **Modeling**: K-Means Clustering, PCA  
- **Environment**: Google Colab  

---

## 🔮 Future Work

- Integrate time-based behavioral features  
- Combine segmentation with supervised fraud detection  
- Deploy segmentation in real-time with Kafka + Spark  

---

## 📌 Summary

This project showcases how unsupervised learning can extract **hidden behavioral segments** from transaction data. By labeling customers as Dormant, Frequent, High Spenders, or VIPs, businesses can:

✅ Improve fraud monitoring  
✅ Personalize financial products  
✅ Optimize marketing investments  

