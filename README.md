# Exploratory data analysis on nyc survival data and nyc property sales 

#Project Overview
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

## Sample Code Snippets

### 1. Handling Missing Values

data.isnull().sum()
data.fillna(method='ffill', inplace=True)

### 2. Grouped Analysis
df.groupby('borough')['sale_price'].mean().sort_values(ascending=False)

### 3. Visualizing Distributions
sns.histplot(df['sale_price'], bins=50, kde=True)
plt.title("Distribution of NYC Property Sale Prices")

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
