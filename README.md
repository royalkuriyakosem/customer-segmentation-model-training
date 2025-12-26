# Customer Segmentation Model Training

## Project Overview
This project focuses on customer segmentation using **RFM (Recency, Frequency, Monetary) Analysis** and **K-Means Clustering**. By analyzing transactional data, we can identify distinct customer groups to tailor marketing strategies and improve customer retention.

## Dataset
The dataset (`data.csv`) consists of transactional records including:
- **InvoiceNo**: Unique transaction identifier.
- **StockCode**: Product code.
- **Description**: Product name.
- **Quantity**: Number of items purchased.
- **InvoiceDate**: Date of transaction.
- **UnitPrice**: Price per item.
- **CustomerID**: Unique customer identifier.
- **Country**: Country of the customer.

## Dependencies
To run the notebook, you will need the following Python libraries:
- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `scikit-learn`

You can install them via pip:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

## Workflow

### 1. Data Cleaning
- Missing values in `CustomerID` are removed.
- Transactions with non-positive `Quantity` or `UnitPrice` are filtered out.
- Duplicates are removed.
- `TotalPrice` is calculated (`Quantity` * `UnitPrice`).

### 2. RFM Feature Engineering
We calculate three key metrics for each customer:
- **Recency**: Days since the last purchase.
- **Frequency**: Total number of unique invoices.
- **Monetary**: Total spend across all transactions.

### 3. Data Normalization
Since RFM metrics are on different scales, we use `StandardScaler` to normalize the data before clustering.

### 4. K-Means Clustering
- The **Elbow Method** is used to determine the optimal number of clusters (k).
- K-Means is applied to segment customers into k distinct groups.

### 5. Cluster Analysis
The resulting clusters are analyzed to understand the characteristics of each segment (e.g., "High Spenders", "Loyal Customers", "Risky Customers").

## Usage
1. Clone the repository.
2. Ensure `data.csv` is in the project directory.
3. Open `customer-segmentation.ipynb` in Jupyter Notebook or JupyterLab.
4. Run all cells to execute the analysis.
