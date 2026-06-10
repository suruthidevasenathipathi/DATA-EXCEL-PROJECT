# DATA-EXCEL-PROJECT
CAPSTONE PROJECT DETAILS

REPORT INCLUDES :

Objective
Dataset Overview
Data Cleaning Process
Data Model & Relationships
KPI Analysis
Customer Analysis
Product Analysis
Store Analysis
Dashboard
Business Recommendations


OBJECTIVE  :

✅ Understand the dataset and relationships
✅ Clean the data
✅ Validate the data (check duplicates, blanks, invalid values)
✅ Create Pivot Tables
✅ Create Pivot Charts
✅ Build a Dashboard
✅ Write business insights and recommendations



DATASET OVERVIEW :

CUSTOMER_DIM, PRODUCT_DIM, STORE_DIM, SLAES_FACT

What Each Sheet Does

CUSTOMER_DIM

Contains customer details:

Customer_ID
Name
Age
Gender
Loyalty_Level


PRODUCT_DIM

Contains product details:

Product_ID
Product_Name
Category
Brand
Cost


STORE_DIM

Contains store information:

Store_ID
Region
Store_Type


SALES_FACT

This is the main transaction table.

Contains:

Sales_ID
Order_Date
Customer_ID
Product_ID
Store_ID
Quantity
Total_Amount (TOTAL AMT = (1 - DISCOUNT = DISCOUNT VALUE ) UNIT PRICE * QUANTITY * DISCOUNT VALUE


DATA CLEANING PROCESS :

Checked all worksheets for duplicate records, while no duplicates were found in Sheets 1, 2, 3 and 4.
Applied the RIGHT function to extract the numerical portion of the Customer ID field.
Split the Customer Name column into First Name and Last Name using the delimiter feature.
Utilized the PROPER, TRIM, and CLEAN functions to standardize text formatting, remove extra spaces, eliminate non-printable characters, and ensure data consistency.
Used the Find and Replace feature to correct misspelled words and improve data accuracy.
Applied the IF function to replace missing values with "UNKNOWN" or "N/A", depending on the context of the data.
Converted the Order Date column to the DD-MM-YYYY format using the TEXT() function to ensure consistency in date representation across the dataset.
Applied the IF(ISBLANK()) function to identify missing values in the Sales Fact table and replaced them with "UNKNOWN" where the required information was unavailable.

 
DATA MODEL & RELATIONSHIP:

RELATIONSHIP STRUCTURE

Customer_Dim
      |
      | Customer_ID
      |
Sales_Fact
      |
      | Product_ID
      |
Product_Dim

      |
      | Store_ID
      |
Store_Dim


TABLES IN MODEL

Table
Type
Purpose

Sales_Fact

Fact Table

Stores sales transactions and numeric measures

Customer_Dim

Dimension Table

Stores customer details

Product_Dim

Dimension Table

Stores product details

Store_Dim

Dimension Table

Stores store and region details

KEYS USED FOR RELATIONSHIPS TABLE
 
Primary Key
Foreign Keys in Sales_Fact

WHY THIS MODEL IS USED

Reduces duplicate data

Customer, product, and store details are stored only once in their dimension tables.

Improves analysis performance

Sales_Fact contains only transaction data, making calculations faster.

Makes reporting easier

You can analyze sales by customer, product, category, region, loyalty level, and more.


SUMMARY

 Sales_Fact is the central fact table.
 Customer_Dim, Product_Dim, and Store_Dim are dimension tables.
 Relationships are built using Customer_ID, Product_ID, and Store_ID.


Sales Analysis :
Total Revenue
Total Orders
Monthly Sales Trend
Best-Selling Month

Question answered: What happened?

Customer Analysis :
Revenue by Loyalty Level
Revenue by Gender
Revenue by State

Question answered: Who contributed most to sales?

Product Analysis :
Top 10 Products
Revenue by Category
Best-Selling Category

Question answered: Which products performed best?

Store Analysis :
Revenue by Region
Revenue by Store Type

Question answered: Which stores and regions performed best?


DESCRIPTIVE ANALYSIS : 


What are the monthly sales trends?
Who are the top customers?
Which products generate the highest profit?
Which payment method used most?

DIAGNOSTIC ANALYSIS :

Why do some categories have high sales but low profit?
Why are some regions underperforming?

PRESCRIPTIVE ANALYSIS :

Reduce discounts on low-margin products.
Review pricing strategies for top-selling products.
Focus promotions on products with higher profit margins.
Increase marketing for underperforming products.
Bundle low-selling products with popular items.
If a payment method generates most revenue:
Offer incentives for preferred payment methods.
If certain months have low sales:
Launch seasonal promotions during slow periods. 


KPI ANALYSIS :

Total Sales
Total Profit
Total Customers
Total Quantity Sold
Top Category
Top Customer


1. Total Sales

KPI: Total Revenue Generated

Formula:

=SUM(Sales_Amount)

Insight:
Measures the overall business performance and revenue generated during the analysis period.

2. Total Profit

KPI: Total Profit Earned

Formula:

=SUM(Profit)

Insight:
Shows the actual earnings after accounting for costs and discounts.

3. Total Orders

KPI: Number of Orders

Formula:

=COUNTA(Order_ID)

Insight:
Indicates overall business activity and customer demand.

4. Total Quantity Sold

KPI: Units Sold

Formula:

=SUM(Quantity)

Insight:
Measures the volume of products sold.

Top-Selling Category

KPI: Category with Highest Sales

Method:
Pivot Table → Category in Rows → Sum of Sales in Values

Insight:
Identifies the most important product category.

Top Customer

KPI: Customer with Highest Sales

Method:
Pivot Table → Customer Name in Rows → Sum of Sales in Values

Insight:
Identifies the most valuable customer.
