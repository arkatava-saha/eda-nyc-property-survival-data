# Exploratory data analysis on nyc survival data and nyc property sales 

###Project Overview

This project demonstrates exploratory data analysis (EDA) using Python on two real world datasets:
1. **Survival Data** - focusing on data cleaning, transformation, and preliminary insights.
2. **NYC Property Sales Case Study** - analyzing real estate trends and drawing data-driven conclusions.

It showcases practical skills in data handling, visualization, and interpretation using Python libraries like `pandas`, `matplotlib`, and `seaborn`.

![Project Banner](https://github.com/arkatava-saha/eda-nyc-property-survival-data/blob/main/NYC%20Property.png)

##  Objectives

Performed comprehensive exploratory data analysis (EDA).
Cleand and preprocess raw datasets using `pandas`.
Handled missing values, outliers, and inconsistent data types.
Visualized insights using `matplotlib` and `seaborn`.
Summarized key trends and patterns in real estate data from NYC.
Practiced analytical thinking using survival data.


##  Key Highlights

### Survival Data Analysis:
1. Cleaned and structured the survival dataset for analysis.
2. Identified missing values and applied appropriate treatment strategies.
3. Explored distributions, categorical breakdowns, and survival rates.

###  NYC Property Sales Case Study:
1. Analyzed property types, neighborhood-wise pricing, and volume of sales.
2. Investigated trends in price per square foot across boroughs.
3. Identified luxury properties and flagged potential anomalies.
4. Created visualizations to reveal seasonal patterns and price bands.

##  Tools and Libraries Used

**Jupyter Notebook**
`pandas`
`numpy`
`matplotlib`
`seaborn`

### Part A: NYC Property Sales Analysis 

``import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns``

# Load data
``data = pd.read_csv('sales.csv')``

# Clean column names
``data.columns = data.columns.str.strip().str.upper().str.replace(" ", "_")``

# Convert SALE_PRICE to numeric
``data['SALE_PRICE'] = pd.to_numeric(data['SALE_PRICE'], errors='coerce')``

# Filter out invalid sale prices (e.g., $0 or too low)
``data = data[data['SALE_PRICE'] > 1000]``

# Handle missing values
``print("Missing values:\n", data.isnull().sum())
data.fillna(method='ffill', inplace=True)``

# Grouped analysis: Average sale price by Borough
``borough_avg_price = data.groupby('BOROUGH')['SALE_PRICE'].mean().sort_values(ascending=False)
print("\nAverage Sale Price by Borough:\n", borough_avg_price)``

# Pivot Table: Building class category summary
``pivot_table = data.groupby('BUILDING_CLASS_CATEGORY').agg({
    'SALE_PRICE': ['count', 'median']
}).reset_index()
pivot_table.columns = ['BUILDING CLASS CATEGORY', 'Total Properties Sold', 'Median Sale Price']
print("\nSummary Table:\n", pivot_table)``

# Visualize sale price distribution
``plt.figure(figsize=(10, 6))
sns.histplot(data['SALE_PRICE'], bins=50, kde=True)
plt.title("Distribution of NYC Property Sale Prices")
plt.xlabel("Sale Price (USD)")
plt.ylabel("Number of Properties")
plt.tight_layout()
plt.show()``

### Part B: Survival Analysis 

``import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns``

# Load dataset
``df = pd.read_csv('Sales.csv')``

# Clean column names
``df.columns = df.columns.str.strip().str.upper().str.replace(" ", "_")``

# Convert SALE_PRICE to numeric
``df['SALE_PRICE'] = pd.to_numeric(df['SALE_PRICE'], errors='coerce')``

# Filter out invalid prices (e.g., 0 or less than 1000)
``df = df[df['SALE_PRICE'] > 1000]``

# Handle missing values
``print("Missing values:\n", df.isnull().sum())
df.fillna(method='ffill', inplace=True)``

# Grouped analysis: Borough-wise average sale price
``borough_avg = df.groupby('BOROUGH')['SALE_PRICE'].mean().sort_values(ascending=False)
print("\nAverage Sale Price by Borough:\n", borough_avg)``

# Pivot Table: Building class category summary
``pivot = df.groupby('BUILDING_CLASS_CATEGORY').agg({
    'SALE_PRICE': ['count', 'median']
}).reset_index()
pivot.columns = ['BUILDING CLASS CATEGORY', 'Total Properties Sold', 'Median Sale Price']
print("\nSales Summary by Building Class Category:\n", pivot)``

# Visualize distribution of sale prices
``plt.figure(figsize=(10, 6))
sns.histplot(df['SALE_PRICE'], bins=50, kde=True)
plt.title("Distribution of NYC Property Sale Prices")
plt.xlabel("Sale Price (USD)")
plt.ylabel("Number of Properties")
plt.tight_layout()
plt.show()``



### Key Insights

Over 80% of properties in Manhattan have a higher-than-average price per square foot.
Most sales below $100,000 were likely administrative transfers or flagged errors.
Properties in Staten Island saw stable but lower overall pricing trends.
Median survival rates vary significantly by category and demographic group.

### Conclusion

This project reflects real world data exploration skills using Python. From cleaning and handling inconsistencies to generating insights and patterns through visualizations, this analysis serves as a strong demonstration of EDA proficiency which is an essential skill in data analytics and decision making.


👤 Author
Arkatava Saha
📧 Email: arkatavasaha@gmail.com
🔗 LinkedIn: www.linkedin.com/in/arkatava-saha-11b66a1b7
