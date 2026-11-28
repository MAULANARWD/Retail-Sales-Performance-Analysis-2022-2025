# Retail Sales Performance Analysis 2022–2025


## 📌 A. Project Overview
The project is an independent data analytics project exploring sales transaction history of a retail company from 2022 to 2025 using a publicly available dataset from Kaggle. The project focuses on evaluating overall business performance by exploring five key dimensions, such as geographic performance, customer performance, product performance, operational performance, and promotion performance. The findings are used to develop data-driven insights and actionable business strategy recommendations that may help identify business opportunities and support future decision-making.


## 🎯 B. Project Objectives
This analysis aims to address the following objectives:
1. Evaluating business performance based on sales, profit, profit margin, order volume, and quantity sold.
2. Determining the countries with the largest contributions to overall revenue and profit.
3. Analysing sales and profit trends across countries over the reporting period.
4. Identifying customer demographic groups with the highest transaction volumes.
5. Understanding sales channel preferences among different customer groups.
6. Identifying high-performing product categories and subcategories across countries and customer segments.
7. Comparing the sales, profit, and costs of all product subcategories.
8. Determining the months and days with the highest transaction activity.
9. Understanding customer preferences for shipping and payment methods.
10. Identifying promotion codes that are most frequently used by customers.
11. Assessing how effectively promotion codes drive purchase quantities and generate profit.


## 📂 C. Dataset Information
The project uses a retail sales dataset containing 18,045 transaction records and 36 columns with variables as follow:
| No. | Variable | Description |
|---:|---|---|
| 1 | `Transaction_ID` | Unique identifier assigned to each transaction. |
| 2 | `Order_ID` | Unique identifier assigned to each order. |
| 3 | `Customer_ID` | Unique identifier assigned to each customer. |
| 4 | `Customer_Name` | Name of the customer associated with the transaction. |
| 5 | `Customer_Age` | Age of the customer at the time of the transaction. |
| 6 | `Customer_Gender` | Gender of the customer. |
| 7 | `Customer_Segment` | Classification of customers based on their business segment. |
| 8 | `Order_Date` | Date when the order was placed. |
| 9 | `Order_Time` | Time when the order was placed. |
| 10 | `Sales_Channel` | Channel through which the purchase was made. |
| 11 | `Store_ID` | Unique identifier assigned to each store. |
| 12 | `Store_Name` | Name of the store associated with the transaction. |
| 13 | `Country` | Country where the transaction took place. |
| 14 | `Region` | Geographic region associated with the transaction. |
| 15 | `City` | City where the transaction took place. |
| 16 | `Product_ID` | Unique identifier assigned to each product. |
| 17 | `Product_Name` | Name of the product purchased. |
| 18 | `Product_Category` | Main category to which the product belongs. |
| 19 | `Product_Subcategory` | More specific classification within a product category. |
| 20 | `Quantity` | Number of units purchased in a transaction. |
| 21 | `Unit_Price` | Price of one unit of the product. |
| 22 | `Discount_Percentage` | Percentage discount applied to the transaction. |
| 23 | `Sales_Amount` | Total sales revenue generated from the transaction. |
| 24 | `Cost_Amount` | Total cost associated with the products in the transaction. |
| 25 | `Profit` | Profit generated from the transaction. |
| 26 | `Payment_Method` | Payment method used to complete the transaction. |
| 27 | `Order_Status` | Current status of the order. |
| 28 | `Shipping_Method` | Shipping method selected for the order. |
| 29 | `Delivery_Days` | Number of days required to deliver the order. |
| 30 | `Return_Flag` | Indicator showing whether the transaction involved a product return. |
| 31 | `Return_Reason` | Reason provided for returning a product. |
| 32 | `Sales_Representative` | Name or identifier of the sales representative handling the transaction. |
| 33 | `Promotion_Code` | Promotional code applied to the transaction, if any. |
| 34 | `Customer_Rating` | Rating provided by the customer regarding their purchase experience. |
| 35 | `Inventory_Level` | Available inventory level associated with the product. |
| 36 | `Order_Year` | Year in which the order was placed. |


## 🛠️ D. Tools & Technologies
The tools used throughout the analysis process are as follows:
1. **Google Colaboratory:** Used as the working environment to write and execute Python code for data cleaning, feature engineering, and exploratory data analysis.
2. **Python:** Used to process and analyse the sales transaction dataset, including removing duplicates, handling missing values, standardising data formats, detecting outliers, and creating new analytical variables.
3. **Pandas:** Used to manipulate, clean, transform, and analyse the dataset during data preparation and analysis.
4. **NumPy:** Used to support numerical calculations and selected feature engineering operations.
5. **Seaborn:** Used to visualise numerical data distributions and identify outliers through boxplots.
6. **Matplotlib:** Used to visualise sales and profit performance, trends, and patterns across different business dimensions.
7. **Microsoft Excel:** Used to inspect and review the sales transaction dataset in spreadsheet format.
8. **Looker Studio:** Used to develop an interactive dashboard presenting sales performance across geographic, customer, product, operational, and promotional dimensions.
9. **GitHub:** Used to document the project, organise its files, and publish the project as part of a data analytics portfolio.


## 🔄 E. Project Workflow
### 1. Data Collection
Obtaining the retail sales transaction dataset from Kaggle as the primary data source for the analysis.
### 2. Data Review
Reviewing the structure, variables, and characteristics of the data.
### 3. Data Cleaning
Preparing the dataset by removing duplicates, handling missing values, standardising data formats, and detecting outliers.
### 4. Feature Engineering
Creating additional variables to support a more comprehensive analysis.
### 5. Exploratory Data Analysis (EDA)
Exploring sales performance across five dimensions of analysis, such as geographic, customer, product, operational, and promotion, to identify trends, patterns, and business insights.
### 6. Dashboard Development
Building an interactive dashboard to present key performance indicators and analysis results.
### 7. Key Findings & Recommendation Reporting
Identifying main insights from the analysis and developing data-driven business strategy recommendations to highlight potential opportunities and support better decision-making.


## 🧹 F. Data Cleaning
### 1. Removing Duplicates
Duplicate records were identified and removed to prevent repeated entries from affecting the accuracy of the analysis.
### 2. Handling Missing Values
Missing values were handled according to the characteristics of each variable:
- **Median Imputation:** Missing values in `Customer_Age`, `Delivery_Days`, and `Inventory_Level` were replaced with their respective median values to minimise the influence of extreme values.
- **Unknown Categorisation:** Missing values in `Customer_Name`, `Customer_Gender`, and `Payment_Method` were replaced with "Unknown" to maintain transparency in the analysis.
- **Reference-Based Imputation:** Missing values in `Product_Name` were filled using the corresponding `Product_ID` as a reference from other completed records.
- **Retaining Blank Values:** Missing values in `Return_Reason`, `Customer_Rating`, and `Promotion_Code` were left blank because they could represent valid business conditions.
### 3. Standardising Data Formats
Formatting inconsistencies were corrected by standardising capitalisation, removing unnecessary whitespace, and fixing encoding errors. This ensured that identical values were not treated as separate categories during analysis.
### 4. Detecting Outliers
Invalid and extreme values were examined to improve data reliability:
- **Quantity:** Three negative values were identified as logically invalid. These values were corrected through back-calculation using the `Sales_Amount`, `Unit_Price`, and `Discount_Percentage` variables.
- **Customer Age:** Three extreme age values were identified. The age range was restricted to 15–75 years to exclude values considered unrealistic for individuals making transactions independently.


## ⚙️ G. Feature Engineering
Several additional variables were created from the existing dataset to enable more detailed analysis. Those variables are as follows:
1. **Customer Age Group:** Used to simplify the evaluation of sales performance based on customer age.
2. **Order Month and Order Day:** Used to enable time-based analysis and determine peak sales periods.
3. **Discount Amount:** Used to calculte the monetary value of discounts provided to customers.
4. **Profit Margin Percentage:** Used to evaluate profitability across transactions and product categories.


## 🌍 H. Geographic Analysis
### 1. Main Insights
- The US generated the highest revenue and profit among the other five countries, reaching around 3.5 million and 699.6 thousand, respectively.
- The high sales volume in the US was driven by its 4 high-performing stores, each generating over 700 thousand in sales. Meanwhile, other countries operate fewer stores than the US. The UK, Canada, and Germany have 2 active stores, while France and Australia operate 1 only.
- However, the profit margin percentage of the US was lower than that of the UK and Canada. The UK and Canada achieved margins of 20.75% and 20.06%, respectively, while the US achieved roughly 19.98%.
- Paris Central generated approximately 725.7 thousand in sales, comparable to several stores operating in the US. Its profit was even higher than that of Chicago Loop, reaching around 144.6 thousand.
- The single store in France demonstrates better performance compared to each store operating in Canada and Germany, where sales and profits did not exceed 700 thousand and 140 thousand, respectively.
### 2. Business Recommendations
- **Total Cost Efficiency Evaluation:** The store branches operating in the US need to conduct a comprehensive review of their production, operational, and promotional strategies. This aims to identify cost components that can be minimised, ensuring that the high sales volume is accompanied by a higher profit margin, at least comparable to the percentage achieved by store branches in the UK and Canada, which is more than 20%.
- **Measured Company Expansion:** The company should prioritise France for its next expansion plan, as this country shows high potential to open a new store branch beyond Paris. However, this expansion must be implemented by considering customer needs in the targeted city to ensure that sales are not centralised in Paris. The company needs an in-depth investigation into why 63% of the UK revenue and profit were generated solely from London.
- **Underperforming Store Optimisation:** The store branches located in Australia and Germany require a more structured business research regarding customer satisfaction analysis and product development reassessment. The company needs to collect customer feedback to identify the root causes of low sales performance, allowing teams to implement adjustments in their production and operations to meet local customer expectations.﻿
