# ML-TASK-4
# Market Basket Analysis using Association Rule Mining

## 📌 Objective

Identify associations between products to optimize inventory management and cross-selling strategies.

## 📝 Short Description

This project analyzes transaction data using Association Rule Mining (Apriori algorithm) to uncover patterns in customer purchases. It helps recommend product pairings, guide promotions, and enhance business decision-making. The implementation is done on Google Colab using Python.

---

## 📂 Dataset

- **File**: `Online Retail.xlsx`
- **Source**: UCI Machine Learning Repository  
- **Attributes**:  
  - `InvoiceNo`: Transaction ID  
  - `StockCode`, `Description`: Product information  
  - `Quantity`: Items purchased  
  - `InvoiceDate`: Purchase timestamp  
  - `UnitPrice`: Price per item  
  - `CustomerID`: Unique customer ID  
  - `Country`: Customer location

---

## 🚀 Project Workflow

### 1. **Data Preprocessing**
- Remove rows with missing `InvoiceNo` or `Description`.
- Exclude cancelled transactions (InvoiceNo starts with 'C').
- Filter data for **United Kingdom** to reduce memory usage.
- Convert invoices into list of items for each transaction.

### 2. **Transaction Encoding**
- Use `TransactionEncoder` to one-hot encode transaction data for algorithm input.

### 3. **Association Rule Mining**
- Apply **Apriori** algorithm (`min_support = 0.02`).
- Generate **association rules** with `lift ≥ 1.0`.

### 4. **Output**
- Display top 5 rules based on `lift`:
  - `antecedents`: items bought
  - `consequents`: items likely to be bought with them
  - `support`, `confidence`, `lift`: evaluation metrics

---

## 🔍 Example Output

| Antecedents       | Consequents       | Support | Confidence | Lift |
|-------------------|-------------------|---------|------------|------|
| {item A}          | {item B}          | 0.03    | 0.45       | 2.8  |
| {item C}          | {item D}          | 0.025   | 0.42       | 2.5  |

---

## 🧠 Tips

- You can adjust `min_support` and `lift` thresholds to control rule granularity.
- Visualize product relationships using network graphs or heatmaps (optional).
- Extend to real-time recommendation systems using FP-Growth or scalable tools.

---

## 📚 Libraries Used

- `pandas`
- `mlxtend`
- `openpyxl` (used implicitly for reading Excel)

Install dependencies in Google Colab:
```python
!pip install mlxtend openpyxl --quiet
