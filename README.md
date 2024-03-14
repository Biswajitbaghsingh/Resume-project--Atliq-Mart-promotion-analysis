INTRODUCTION:
Atliq Mart is a retail giant with over 50 supermarkets in the southern region of India. All their 50 stores ran a massive promotion during the Diwali 2023 and Sankranti 2024 (festive time in India) on their Atliq branded products.

DOMAIN: FMCG

PROBLEM STATEMENT:
Analyse promotions and provide tangible insights to sales director in order to make more informed decisions over the next promotional period.

TOOLS USED:
MySQL Workbench: Creating SQL queries for ad-hoc business requests.

PowerBI: For Data cleaning, modelling, creating metrics using DAX and data visualization.

DATA SOURCE -
The 4 datasets provided are in the CSV file format.
There are 3 dimension tables namely, dim_campaigns, dim_products and dim_stores and 1 fact_table which is fact_events.

The dim_campaigns table contains information regarding the two festive period, i.e., Diwali 2023 and Sankranti 2024 with the starting and ending date of the festive offers, where campaign_id is the primary key of the table.

The dim_products table contains information regarding product_code, product_name and the category to which the product belongs, where product_code serves as the primary key for the table.

The dim_stores table contains information regarding the store_id and the city where the store is present, where store_id serves as the primary key for the table.

The fact_events tables consist about all the quantitative data which contains information about campaign_id, product_code, store_id, promo_type, base price of the product, quantity sold before the offer and quantity sold after the offer.


ADHOC BUSINESS REQUESTS:
There are 5 adhoc business requests and the subsequent information is extracted using MySQL.

PROBLEM 1: Provide a list of products with a base price greater than 500 and that are featured in promo type of ‘BOGOF’ (Buy One Get One Free). This information will help us identify high-value products that are currently being heavily discounted, which can be useful for evaluating our pricing and promotion strategies.

PROBLEM 2: Generate a report that provides an overview of the number of stores in each city. The results will be sorted in descending order of store counts, allowing us to identify the cities with the highest store presence. The report includes two essential fields: city and store count, which will assist in optimizing our retail operations.

PROBLEM 3: Generate a report that displays each campaign along with the total revenue generated before and after the campaign? The report includes three key fields: campaign_name, totaI_revenue(before_promotion), totaI_revenue(after_promotion). This report should help in evaluating the financial impact of our promotional campaigns. (Display the values in millions).

PROBLEM 4: Produce a report that calculates the Incremental Sold Quantity (ISU%) for each category during the Diwali campaign. Additionally, provide rankings for the categories based on their ISU%. The report will include three key fields: category, isu%, and rank order. This information will assist in assessing the category-wise success and impact of the Diwali campaign on incremental sales.

PROBLEM 5: Create a report featuring the Top 5 products, ranked by Incremental Revenue Percentage (IR%), across all campaigns. The report will provide essential information including product name, category, and ir%. This analysis helps identify the most successful products in terms of incremental revenue across our campaigns, assisting in product optimization.
