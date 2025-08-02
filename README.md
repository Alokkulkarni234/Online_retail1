# 🛍️ Sales Forecasting and Inventory Optimization

## 📌 Project Overview

This project focuses on helping small businesses improve decision-making in their Point-of-Sale (POS) systems. It uses historical sales data to:
- 📈 Forecast future sales for each product
- 📦 Recommend inventory restock quantities
- 📊 Generate summary reports (top products, forecasted revenue)

---

## 📊 Dataset Overview

- **Name:** Online Retail Dataset  
- **Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/352/online%2Bretail)  
- **Records:** ~541,000 transactions  
- **Time Period:** Dec 2010 – Dec 2011  
- **Type:** Real-world e-commerce transactions

### ✨ Key Columns:
| Column        | Description |
|---------------|-------------|
| `InvoiceNo`   | Invoice ID (prefix "C" = cancellation) |
| `StockCode`   | Product/item code |
| `Description` | Product name |
| `Quantity`    | Units sold (negative = returns) |
| `InvoiceDate` | Date/time of transaction |
| `UnitPrice`   | Price per unit (in GBP) |
| `CustomerID`  | Customer ID (nullable) |
| `Country`     | Country of customer |

---

## 🧠 ML Pipeline

1. **Preprocessing**
   - Removed nulls
   - Converted `InvoiceDate` to datetime
   - Created `TotalSales = Quantity × UnitPrice`
   - Extracted time features: `day`, `month`, `weekday`

2. **Modeling**
   - Regression using **XGBoost** and **RandomForestRegressor**
   - Bonus: Time-series forecasting with **Prophet**

3. **Inventory Optimization**
   - Predicted sales → added 20% safety buffer
   - Flagged products needing restock or with overstock risk

4. **Visualization**
   - Built an interactive **Streamlit dashboard** for:
     - Sales trends
     - Restocking alerts
     - Forecasted revenue and t
