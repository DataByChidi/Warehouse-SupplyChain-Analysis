Warehouse Supply-Chain Analysis
Written by Ozuzu Chidiebere
Project Overview

I conducted this project to transform a raw supply chain inventory dataset into a structured, analysis ready dataset and use it to uncover patterns in inventory distribution, warehouse performance, product categories, supplier exposure, and stock availability.
The dataset contained product level inventory records covering Product ID, Product Name, Category, Warehouse, Location, Quantity, Price, Supplier, Status, Last Restocked, and Inventory Value.

At the beginning of the project, the dataset contained missing numerical values and other data-quality issues that could affect inventory calculations and business reporting. Hence, I approached the project as a complete data analytics workflow: data inspection – cleaning- missing-value treatment - validation - exploratory analysis - dashboard development - business recommendations.

The final objective was not simply to clean the dataset, but to turn the raw inventory records into information that could help management understand where inventory is concentrated, what products and warehouses require attention, and where potential stock management risks exist.

The Business Problem
The central business question I investigated was:
"Where is our inventory concentrated, which products and warehouses require attention, and how can inventory efficiency and stock availability be improved?"
During the analysis, I focused on several areas:

Warehouse Performance
I examined inventory quantities and inventory values across warehouses to identify locations carrying disproportionately high or low levels of stock.

Product & Category Performance
I analyzed product categories and individual products to determine which areas represented the largest inventory volumes and financial exposure.

Stock Availability
I investigated the distribution of products across In Stock, Low Stock, and Out of Stock statuses to identify potential inventory risks.

Supplier Exposure
I analyzed inventory associated with different suppliers to understand supplier concentration and its potential implications for replenishment and inventory management.

Data Quality
This part, I assessed the quality of the raw dataset because missing Quantity, Price, and Inventory Value values could distort the results if they were not handled appropriately.

Project Objectives
As part of my analysis, I structured the project around the following objectives:

•	Clean and standardize the raw inventory dataset.
•	Identify and handle missing values in Quantity, Price, and Inventory Value.
•	Validate the relationship between Quantity, Price, and Inventory Value.
•	Analyze inventory distribution across warehouses and locations.
•	Identify the highest-value and highest-volume product categories.
•	Analyze stock availability across inventory-status classifications.
•	Examine inventory concentration across suppliers.
•	Identify potential inventory-management risks.
•	Build an interactive Excel dashboard to communicate the findings.
•	Translate the analysis into practical business recommendations.

About the Dataset
Dataset: Supply Chain Inventory Dataset

The dataset contains inventory records covering products, categories, warehouses, storage locations, suppliers, pricing, stock status, and restocking information.

Data Dictionary:

•	Product ID Identifier: associated with the product record
•	Product Name: name of the product
•	Category: category to which the product belongs
•	Warehouse: warehouse where the product is stored
•	Location: specific warehouse location/aisle
•	Quantity: number of units recorded in inventory
•	Price Unit: price of the product
•	Supplier: supplier associated with the inventory record
•	Status: current stock status
•	Last Restocked: date the product was last restocked
•	Inventory Value: monetary value associated with the inventory record

The primary numerical variables I worked with were Quantity, Price, and Inventory Value.

Data Cleaning Journey
One of the first stages of the project was assessing the raw dataset before performing any analysis. Rather than immediately replacing missing values or modifying the original columns, I first examined the structure of the dataset and identified where data quality issues could affect the analysis. Thus, I created separate cleaned fields to preserve the original observations:
Quantity_Clean
Price_Clean
Inventory_Value_Clean

This allowed me to distinguish between original values and values generated during the cleaning process.

Missing Quantity
I found that some Quantity records were missing.
Instead of replacing every missing value with the overall average Quantity, I used a context-based imputation approach.
The hierarchy I applied was:
Category + Warehouse + Location

Category + Warehouse

Category

Overall Quantity Average

This allowed the estimated quantity to be based on records that were as similar as possible to the missing observation.
Because Quantity represents physical inventory units, I rounded the imputed values to whole numbers.
For example, an estimated average of:
202.73
was recorded as:
203 units
The key principle was that the imputed value represented an estimate, rather than an assertion that the original missing quantity was exactly that amount.

Missing Price
I did apply a similar but more product focused approach to missing Price values.
The hierarchy was:
Product Name + Category + Location

Category + Location

Category

Over-all Price Average

This was important because product prices can vary significantly between categories and locations. I also checked the Product ID field rather than automatically assuming that every Product ID represented a unique product. This prevented Product ID from being used as the sole basis for price imputation where the underlying data did not support that assumption.
Price estimates were rounded to two decimal places.

Inventory Value
After Quantity and Price had been cleaned, I calculated Inventory Value.
The relationship used was:
Inventory Value = Quantity × Price
For example:
=Quantity_Clean*Price_Clean
This meant that when both Quantity and Price were available or successfully imputed, Inventory Value could be calculated consistently rather than independently estimated.
I also used records with complete Quantity, Price, and Inventory Value values to validate whether this relationship was consistent within the dataset.

Analytical Approach
After completing the cleaning stage, I moved into exploratory analysis. I used Excel PivotTables and calculated metrics to examine inventory from several perspectives.

Warehouse Analysis
I compared warehouses based on:

Total Quantity
Total Inventory Value
Stock Status
Product concentration
This helped identify where physical inventory and financial exposure were concentrated.

Category Analysis
I analyzed:
Quantity by Category
Inventory Value by Category
Average Price by Category

This allowed me to distinguish between categories with high physical volumes and categories with high financial value.

Product Analysis
I examined individual products to identify:
Highest-value products
Highest-quantity products
Products with Low Stock status
Products with Out-of-Stock status

Supplier Analysis
I analyzed inventory exposure by supplier to understand which suppliers were associated with the largest quantities and inventory values.

Stock Status Analysis
I examined the distribution of:
In Stock
Low Stock
Out of Stock
This provided a high-level view of inventory availability.

Dashboard Development
After completing the analysis, I translated the findings into an interactive Excel dashboard.
The dashboard was designed around the business questions rather than simply displaying every available variable.

Key Performance Indicators
The dashboard highlights:
Total Inventory Value
Total Quantity
Total Products
Total Warehouses

Dashboard Visuals/Charts
Inventory Value by Warehouse
I used a sorted bar chart to show which warehouses held the highest inventory value.
This provides management with a quick view of where the greatest financial inventory exposure exists.

Quantity by Warehouse
I compared physical inventory volume across warehouses.
Comparing this with Inventory Value helped distinguish between warehouses holding large quantities of lower-value products and warehouses holding smaller quantities of higher-value products.

Inventory Value by Category
This visualization shows which product categories account for the greatest proportion of inventory value.

Stock Status Distribution
I visualized the distribution of:
In Stock
Low Stock
Out of Stock
to provide a quick indication of inventory availability.

Supplier Inventory Value
I compared inventory value across suppliers to identify supplier concentration.

Key Findings
Total Inventory Value: $4.8 million
Highest-Value Category: Clothing - $1.148 million
Highest-Value Warehouse: Warehouse 1 — $1.5 million

Finding 1: Clothing had the highest inventory value at $1.148 million.

What it revealed: The company’s inventory investment was heavily concentrated in clothing, making this category particularly important when assessing overall inventory exposure.

Business Implication: Changes in demand, excess stock, or stock shortages within clothing could have a meaningful effect on the company’s overall inventory position.

Project Impact
This project demonstrates how I transformed a raw supply chain inventory dataset into a structured analytical resource.
Through the cleaning and analysis process, I was able to move from raw inventory records to a clearer view of:

Inventory value
Stock availability
Warehouse distribution
Product categories
Supplier exposure
Inventory concentration
Data quality

The resulting dashboard provides management with a more accessible way to monitor inventory performance and identify areas requiring further investigation.

Tools & Skills Demonstrated
Tools
Microsoft Excel
Excel PivotTables
Excel formulas
Data Cleaning
Missing-Value Imputation
Data Validation
Descriptive Statistics
Exploratory Data Analysis
Inventory Analytics
Supply Chain Analytics
Dashboard Development
Business Analysis
Data Storytelling
Technical Documentation


