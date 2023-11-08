# Ecommerce_Olist-store-Analysis

## Presentation
Link to [Google slides](https://docs.google.com/presentation/d/1v0Peu1mknfhY74Vh4-TtTokyAE6-vQw2/edit#slide=id.p2)

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

# My SQL Queries

[Link to Olist store Schema](`olist_store`)



































