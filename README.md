# 🛒 Customer Segmentation using RFM and Clustering (KMeans & DBSCAN)

This project focuses on analyzing transactional data from a retail database using **RFM (Recency, Frequency, Monetary)** analysis to segment customers and identify key patterns in their purchasing behavior. The goal is to help the business improve marketing strategies, enhance customer engagement, and increase retention.

---

## 📊 Problem Statement

Businesses often treat all customers the same, which can lead to missed opportunities for targeted marketing. This project aims to cluster customers into distinct groups based on how recently they made a purchase (Recency), how often (Frequency), and how much they spent (Monetary).

---

## 📂 Data Source

- Extracted from Microsoft SQL Server database `BikeStores`.
- Tables used:
  - `Sales.OrderItem`
  - `Sales.Order`
  - `Production.Product`

After joining these tables, we built a transactional dataset with the following key fields:
- `OrderID`, `ProductID`, `OrderDate`, `OrderTotal`, `Product Name`

---

## 🔧 Tools & Technologies

- **Python**
  - `pandas`, `numpy`, `matplotlib`, `seaborn`
  - `scikit-learn` for clustering and evaluation
  - `pyodbc` for SQL connection
- **SQL Server** for raw data storage
- **Jupyter Notebook** for analysis

---
## 🧠 Project Workflow

### 1. Data Extraction
- Connected to SQL Server and imported relevant tables.

### 2. Data Cleaning & Preprocessing
- Merged datasets
- Parsed date fields
- Handled data types and duplicates

### 3. Feature Engineering (RFM Analysis)
- **Recency**: Days since last purchase
- **Frequency**: Total number of transactions
- **Monetary**: Total purchase value

### 4. Exploratory Data Analysis (EDA)
- Visualized relationships between R, F, and M.
- Found strong correlations:
  - High frequency → high monetary value
  - High recency → low frequency

---

## 🔁 5. Clustering (KMeans & DBSCAN)

- Applied **KMeans Clustering**:
  - Standardized RFM values using `StandardScaler`.
  - Used **Elbow Method** and **Silhouette Score** to determine the optimal number of clusters (`k = 4`).
  - Successfully segmented customers into distinct groups based on behavioral patterns.

- Applied **DBSCAN Clustering**:
  - Used density-based clustering to identify non-linear cluster shapes and outliers.
  - Tuned `eps` and `min_samples` parameters.
  - Compared DBSCAN results with KMeans using **Silhouette Score**.

- **Result**: 
  - KMeans produced more meaningful and well-separated customer clusters based on the business context.
  - DBSCAN identified noise points and dense clusters but required careful parameter tuning and gave mixed results.

- Visualizations included to compare cluster structures for both methods.

---
