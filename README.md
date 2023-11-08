# Ecommerce_Olist-store-Analysis

## Presentation
Link to  [https://drive.google.com/file/d/17A8aRHBp_vnA2rq6GROMgPe8aJGUqnu4/view?usp=drive_web]

## Overview of Project:

The Olist Store Analysis project aims to analyze customer purchasing patterns and payment statistics on an E-commerce platform, Olist. This project covers several key performance indicators (KPIs) such as weekday vs weekend sales, payment statistics, delivery time, and customer behavior. The analysis is based on nine CSV files, which are cleaned and manipulated to extract valuable insights.
 
## Description of Our source Data:

We chose the Brazilian-eCommerce dataset from ExcelR Solutions for our analysis. This dataset contains approximately 100,000 customer orders, along with corresponding files on product information and English translations of product categories originally in Portuguese. Nine files from the original ExcelR dataset were chosen for further analysis: 
A] olist_geolocation_dataset  

B] olist_customers_dataset

C] olist_sellers_dataset

D] olist_product_dataset

E] olist_order_items_dataset 

F] olist_orders_dataset 

G] olist_order_payments_dataset

H] olist_order_reviews_dataset

I] product_category_name_translation.

## Questions we hope to answer with our data:

with this Data we hope to Answer 5 different KPI's

1] Weekdays and weekend payment statistics ?

2] Payment Type with review score 5 ?

3] Average numbers of delivery days taken for pet shop ?

4] Average price and payment value of sao paulo city ?

5] Average shipping days vs review scores ?
 
## Data Modelling
 We used joins to create relationship between data tables in Power bi.The Entity Relationship Diagram(ERD) below shows the connectivity between the 9 data tables used in our analysis.
 
![image](https://github.com/Nivedhitha1009/Ecommerce_Olist-store-Analysis/assets/148059737/09c5f971-050f-4f4f-aa6f-35aad671535f)

The description of these tables is as follows:

olist_orders_dataset: This table is connected to 4 other tables. It is used to connect all the details related to an order.

olist_order_items_dataset: It contains the details of an item that had been purchased such as freight value, price and so on.

olist_order_reviews_dataset: It contains details related to any reviews posted by the customer on a particular product that he had purchased.

olist_products_dataset: It contains related to a product such as the Product ID, Product category name and measurements.

olist_order_payments_dataset: The information contained in this table is related to the payment details associated with a particular order type.

olist_customers_dataset: Details the customer base information of this firm.

olist_geolocation_dataset: It contains geographical information related to both the sellers and customers.

olist_sellers_dataset: This table contains the information related to all the sellers who have registered with this firm.

olist_product_category_name_translation: This table is connected to products database.

Individual datasets were cleaned using Power Query in a Power bi  before importing the data tables to  powerbi.
SQL left  joins were used to connect relevant  data tables for our My Sql.

# Data Cleaning 
Data Cleaning in Power Query

![image](https://github.com/Nivedhitha1009/Ecommerce_Olist-store-Analysis/assets/148059737/f21e7fb1-d7f6-4d7b-850d-b19ca19f5360) 

## Step 1: Remove Blank And Null values 

1] I cleaned the data in Excel before importing it to PowerBI, I explored the data to find any inconsistencies, duplicates, incorrect format, or missing values. I’ll share some of the inconsistencies and incorrect format I found and how I corrected them, for example in the customer dataset city names were in lower case I used the proper formula and with the help of the helper column I replaced the values.  

2] In the orders dataset, there was some Null Values in order_purchase timestamp,order delivery customer date , and each order id is unique hence I removed those blank rows and remove duplicates . In this way, I cleaned the all 9 datasets and then imported the files into PowerBI.

3] In the product dataset, there was some empty product category name, and each product id is unique hence I removed those blank rows. In this way, I cleaned the dataset and then imported the files into PowerBI.

## Step 2:Merging Of Datasets

1] In order to get the KPI1 we need to merge the Olist_orders dataset and olist_Payments dataset 

2] merging of 3 datasets olist orders datase ,olist reviwe dataset and olist payments dataset to get Payment type of credit card  with review score of 5

3] merged 2 datasets Olist orders dataset and olist products dataset to get Average delivery days for pet Shop

4] merging of 3 datasets Customers dataset,Olist_Order_items ,and Olist Payment dataset in order to get Average Price and Average Payment of Sao_Paulo city

5]merging of 2 datasets Olist Orders dataset and olist_reviwes dataset to get Average Shipping Days vs review scores


## Step 3: Transform 

1] After Cleaned all the files, I created some extra columns while referencing the order purchase timestamp column to get insight into the day, month, and year of order like day of week, weekend/weekday in the order dataset.

2] For calculating Shipping days With reference of Order purchase time stamp and Order deliver customer date i created customn column renamed to Shipping days in power query applied a formula and there after converted that custom column to Days by rightclick on the column 

3] in order to calculate Average Days with reference to order delivery customer table.duplicate the order delivary customer date column ,renamed to Delivery Days and finally tranform to days by right click on the column 

# My SQL Queries

[Link to Olist store Schema](https://github.com/Nivedhitha1009/Olist-Database-_Schemas/blob/main/Ecommerce%20Olist%20Analysis%20Sql.sql)

## Creating Data Visualizations

## KPI1

Now to find the Payment values for weekend vs weekday ,Firstly duplicated the purchase timestamp transform to days of the week and  renamed to purchase days.Now I created a custom column for purchase days used if else formula . And to verify if it is working, I m represented this KPI in Donut chart of weekname and Payment values

  ![image](https://github.com/Nivedhitha1009/Ecommerce_Olist-store-Analysis/assets/148059737/0e46fa16-9c93-40db-a95c-499de9a3557e)

## KPI2

 There are 4 types of payment types, and since orders of review score of 5 are asked, I selected a Waterfall chart  for this KPI.

![image](https://github.com/Nivedhitha1009/Ecommerce_Olist-store-Analysis/assets/148059737/43ee5acf-7dec-47e2-b3a3-819d43f2676e)

## KPI3
To show this KPI I simply created a gauge chart, now to provide more insights for product category and Average days taken to deliver 

![image](https://github.com/Nivedhitha1009/Ecommerce_Olist-store-Analysis/assets/148059737/de34826e-bbd6-4025-b2c9-23af73312c2d)

## KPI4

Represented this KPI with the help of Stacked column bar chart and analysed that the  Average payment is high compared to Avg price for Sao paulo city 

![image](https://github.com/Nivedhitha1009/Ecommerce_Olist-store-Analysis/assets/148059737/75c77514-20ce-4dc5-a64d-2f3f4a76d701)

## KPI5

Represented this KPI with the help of Area chart with the visualization that shipping days is more for review score 1.
As the number of Shipping days to deliver the orders increases the review score decreases.

![image](https://github.com/Nivedhitha1009/Ecommerce_Olist-store-Analysis/assets/148059737/b55e167e-32b0-4563-acfc-a8e88d1e6535)

# Dashboard

[Link to Dashboard on Tableau ](https://public.tableau.com/views/Ecommercestoreanalysis_16984286588070/Dashboard1?:language=en-US&publish=yes&:display_count=n&:origin=viz_share_link)

[Link to Dashboard on Power Bi](https://www.novypro.com/project/ecommerceolist-store-analysis)
























