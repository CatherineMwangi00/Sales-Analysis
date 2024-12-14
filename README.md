# Sales Analysis Project

## **Overview**
In this project, we analyze a retail store's sales data to uncover trends, identify key insights, and provide actionable recommendations for improving sales performance. The project demonstrates data cleaning, exploratory data analysis, and visualization skills, showcasing how to derive value from raw data.

---

## **Project Objective**
The primary goal is to analyze historical sales data to:
- Understand sales trends over time.
- Identify top-performing products and categories.
- Determine sales distribution across regions.
- Recommend strategies to boost revenue.

---

## **Dataset**
- **Name:** Retail Sales Dataset
- **Source:** [Kaggle's Sample Retail Dataset](https://www.kaggle.com/datasets/catherinemwangi00001/sample-sales-data).
- **Contents:**
  - `Order ID`: Unique identifier for each order
  - `Product`: Product name
  - `Category`: Product category
  - `Order Date`: Date of order placement
  - `Region`: Geographic region of the order
  - `Quantity`: Number of items ordered
  - `Unit Price`: Price per unit
  - `Total Price`: Total value of the order

---

## **Tools and Technologies**
- **Python Libraries:** pandas, NumPy, Matplotlib, Seaborn
- **Jupyter Notebook** for analysis
- **Microsoft Excel** (optional) for preliminary data exploration

---

## **Step-by-Step Process**

### **Step 1: Importing Libraries**
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

---

### **Step 2: Loading the Data**
- Load the dataset into a pandas DataFrame.
```python
data = pd.read_csv('sales_data.csv')
```
- Preview the first few rows to understand its structure.
```python
data.head()
```

---

### **Step 3: Data Cleaning**
1. **Check for missing values** and handle them appropriately:
```python
print(data.isnull().sum())
```
- Fill or drop missing values:
```python
data['Total Price'].fillna(data['Quantity'] * data['Unit Price'], inplace=True)
data.dropna(subset=['Product', 'Category'], inplace=True)
```

2. **Ensure data types are correct:**
```python
data['Order Date'] = pd.to_datetime(data['Order Date'])
data['Quantity'] = data['Quantity'].astype(int)
```

3. **Remove duplicates:**
```python
data.drop_duplicates(inplace=True)
```

---

### **Step 4: Exploratory Data Analysis (EDA)**

#### 4.1 Sales Trends Over Time
- Group by month/year and calculate total sales:
```python
data['Month-Year'] = data['Order Date'].dt.to_period('M')
sales_trend = data.groupby('Month-Year')['Total Price'].sum()
```
- Plot the trend:
```python
plt.figure(figsize=(12, 6))
sales_trend.plot(kind='line', marker='o', title='Sales Trend Over Time')
plt.ylabel('Total Sales')
plt.show()
```

#### 4.2 Top Products
- Find top-selling products:
```python
top_products = data.groupby('Product')['Total Price'].sum().sort_values(ascending=False).head(10)
```
- Plot the results:
```python
top_products.plot(kind='bar', title='Top 10 Products by Sales', color='skyblue')
plt.ylabel('Total Sales')
plt.show()
```

#### 4.3 Regional Performance
- Aggregate sales by region:
```python
region_sales = data.groupby('Region')['Total Price'].sum()
```
- Visualize using a pie chart:
```python
region_sales.plot(kind='pie', autopct='%1.1f%%', title='Sales by Region')
plt.ylabel('')
plt.show()
```

---

# Sales Analysis Project
plt.ylabel('Total Sales')
plt.show()
```

#### 4.2 Top Products
- Find top-selling products:
```python
top_products = data.groupby('Product')['Total Price'].sum().sort_values(ascending=False).head(10)
```
- Plot the results:
```python
top_products.plot(kind='bar', title='Top 10 Products by Sales', color='skyblue')
plt.ylabel('Total Sales')
plt.show()
```

#### 4.3 Regional Performance
- Aggregate sales by region:
```python
region_sales = data.groupby('Region')['Total Price'].sum()
```
- Visualize using a pie chart:
```python
region_sales.plot(kind='pie', autopct='%1.1f%%', title='Sales by Region')
plt.ylabel('')
plt.show()
```

---

### **Step 5: Insights and Recommendations**
**Key Findings:**
1. Sales peak during specific months (e.g., holiday seasons).
2. "Wireless Earbuds" contributes the most revenue; consider promoting it further.
3. "North Region" has untapped potential for growth compared to others.

**Recommendations:**
1. Launch targeted marketing campaigns during high-sales months.
2. Increase stock levels and advertising for top-performing products.
3. Explore strategies to boost sales in underperforming regions.

---

## **Project Files**
1. **Data File:** [sales_data.csv](./sales_data.csv)
2. **Jupyter Notebook:** [sales_analysis.ipynb](./sales_analysis.ipynb)
3. **Visuals:** Saved plots as `.png` images in the `/visuals` folder.

---

## **Conclusion**
This sales analysis project demonstrates practical skills in data cleaning, exploratory analysis, and visualization. It highlights the ability to draw actionable insights from data, making it relevant for employers seeking data analysts.


---

Feel free to explore the attached files and codebase for a deeper dive into the analysis process.

**Recommendations:**
1. Launch targeted marketing campaigns during high-sales months.
2. Increase stock levels and advertising for top-performing products.
3. Explore strategies to boost sales in underperforming regions.

---

## **Project Files**
1. **Data File:** [sales_data.csv](https://www.kaggle.com/datasets/catherinemwangi00001/sample-sales-data)
2. **Jupyter Notebook:** [sales_analysis.ipynb](./sales_analysis.ipynb)
3. **Visuals:** Saved plots as `.png` images in the `/visuals` folder.

---

## **Conclusion**
This sales analysis project demonstrates practical skills in data cleaning, exploratory analysis, and visualization. It highlights the ability to draw actionable insights from data, making it relevant for employers seeking data analysts.



Feel free to explore the attached files and codebase for a deeper dive into the analysis process.

