# CAPSTONE PROJECT DETAILS



## REPORT INCLUDES :



* Objective
* Dataset Overview
* Data Cleaning Process
* Data Model \& Relationships
* KPI Analysis
* Customer Analysis
* Product Analysis
* Store Analysis
* Dashboard
* Business Recommendations





#### OBJECTIVE  :



✅ Understand the dataset and relationships

✅ Clean the data

✅ Validate the data (check duplicates, blanks, invalid values)

✅ Create Pivot Tables

✅ Create Pivot Charts

✅ Build a Dashboard

✅ Write business insights and recommendations







#### DATASET OVERVIEW :



CUSTOMER\_DIM, PRODUCT\_DIM, STORE\_DIM, SLAES\_FACT



What Each Sheet Does



##### CUSTOMER\_DIM



Contains customer details:



Customer\_ID

Name

Age

Gender

Loyalty\_Level





##### PRODUCT\_DIM



Contains product details:



Product\_ID

Product\_Name

Category

Brand

Cost





##### STORE\_DIM



Contains store information:



Store\_ID

Region

Store\_Type





##### SALES\_FACT



This is the main transaction table.



Contains:



Sales\_ID

Order\_Date

Customer\_ID

Product\_ID

Store\_ID

Quantity

Total\_Amount (TOTAL AMT = (1 - DISCOUNT = DISCOUNT VALUE ) UNIT PRICE \* QUANTITY \* DISCOUNT VALUE





#### DATA CLEANING PROCESS :



* Checked all worksheets for duplicate records, while no duplicates were found in Sheets 1, 2, 3 and 4.
* Applied the RIGHT function to extract the numerical portion of the Customer ID field.
* Split the Customer Name column into First Name and Last Name using the delimiter feature.
* Utilized the PROPER, TRIM, and CLEAN functions to standardize text formatting, remove extra spaces, eliminate non-printable characters, and ensure data consistency.
* Used the Find and Replace feature to correct misspelled words and improve data accuracy.
* Applied the IF function to replace missing values with "UNKNOWN" or "N/A", depending on the context of the data.
* Converted the Order Date column to the DD-MM-YYYY format using the TEXT() function to ensure consistency in date representation across the dataset.

Applied the IF(ISBLANK()) function to identify missing values in the Sales Fact table and replaced them with "UNKNOWN" where the required information was unavailable.



&#x20;

#### DATA MODEL \& RELATIONSHIP:



###### RELATIONSHIP STRUCTURE



Customer\_Dim

&#x20;     |

&#x20;     | Customer\_ID

&#x20;     |

Sales\_Fact

&#x20;     |

&#x20;     | Product\_ID

&#x20;     |

Product\_Dim



&#x20;     |

&#x20;     | Store\_ID

&#x20;     |

Store\_Dim





###### TABLES IN MODEL



1. Table
2. Type
3. Purpose



**Sales\_Fact**



Fact Table



Stores sales transactions and numeric measures



**Customer\_Dim**



Dimension Table



Stores customer details



**Product\_Dim**



Dimension Table



Stores product details



**Store\_Dim**



Dimension Table



Stores store and region details



**KEYS USED FOR RELATIONSHIPS TABLE**

&#x20;

1. Primary Key
2. Foreign Keys in Sales\_Fact



**WHY THIS MODEL IS USED**



Reduces duplicate data



Customer, product, and store details are stored only once in their dimension tables.



Improves analysis performance



Sales\_Fact contains only transaction data, making calculations faster.



Makes reporting easier



You can analyze sales by customer, product, category, region, loyalty level, and more.





**SUMMARY**



* &#x20;Sales\_Fact is the central fact table.
* &#x20;Customer\_Dim, Product\_Dim, and Store\_Dim are dimension tables.
* &#x20;Relationships are built using Customer\_ID, Product\_ID, and Store\_ID.





**Sales Analysis :**

* Total Revenue
* Total Orders
* Monthly Sales Trend
* Best-Selling Month



Question answered: What happened?



**Customer Analysis :**

* Revenue by Loyalty Level
* Revenue by Gender
* Revenue by State



Question answered: Who contributed most to sales?



**Product Analysis :**

* Top 10 Products
* Revenue by Category
* Best-Selling Category



Question answered: Which products performed best?



**Store Analysis :**

* Revenue by Region
* Revenue by Store Type



Question answered: Which stores and regions performed best?





**DESCRIPTIVE ANALYSIS :** 





1. What are the monthly sales trends?
2. Who are the top customers?
3. Which products generate the highest profit?
4. Which payment method used most?



**DIAGNOSTIC ANALYSIS :**



1. Why do some categories have high sales but low profit?
2. Why are some regions underperforming?



**PRESCRIPTIVE ANALYSIS :**



1. Reduce discounts on low-margin products.
2. Review pricing strategies for top-selling products.
3. Focus promotions on products with higher profit margins.
4. Increase marketing for underperforming products.
5. Bundle low-selling products with popular items.
6. If a payment method generates most revenue:
7. Offer incentives for preferred payment methods.
8. If certain months have low sales:
9. Launch seasonal promotions during slow periods. 





**KPI ANALYSIS :**



1. Total Sales
2. Total Profit
3. Total Customers
4. Total Quantity Sold
5. Top Category
6. Top Customer





1\. Total Sales



KPI: Total Revenue Generated



Formula:



=SUM(Sales\_Amount)



Insight:

Measures the overall business performance and revenue generated during the analysis period.



2\. Total Profit



KPI: Total Profit Earned



Formula:



=SUM(Profit)



Insight:

Shows the actual earnings after accounting for costs and discounts.



3\. Total Orders



KPI: Number of Orders



Formula:



=COUNTA(Order\_ID)



Insight:

Indicates overall business activity and customer demand.



4\. Total Quantity Sold



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



