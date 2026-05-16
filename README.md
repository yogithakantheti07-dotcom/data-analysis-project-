# data-analysis-project-
import pandas as pd

# Load dataset

df = pd.read_csv("sales_data.csv")

# Display dataset
print("Dataset:\n")
print(df)

# Basic Information
print("\nSummary Statistics:\n")
print(df.describe())

# Total sales

df['Total_Sales'] = df['Price'] * df['Quantity']

print("\nTotal Sales by Product:\n")
print(df[['Product', 'Total_Sales']])

# Grouping

category_sales = df.groupby('Category')['Total_Sales'].sum()

print("\nCategory Wise Sales:\n")
print(category_sales)

# Insights

highest = df.loc[df['Total_Sales'].idxmax()]

print("\nHighest Selling Product:")
print(highest['Product'])