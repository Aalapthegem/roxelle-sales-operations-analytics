# Roxelle Sales & Operations Analytics | Power BI Project

## Project Overview

This project was developed as part of a Power BI Final Assignment for Roxelle Nigeria Ltd., a mid-sized FMCG retail company operating across Lagos and Abuja.

The objective of the project was to design and develop a professional interactive Power BI dashboard capable of helping executives monitor sales performance, customer behaviour, product performance, inventory health, and discount effectiveness across all branches.

The solution was built using Microsoft Power BI Desktop and includes:

* Data cleaning and transformation using Power Query
* Star schema data modelling
* DAX measures and calculated columns
* Interactive dashboards with slicers and KPI cards
* Business insight generation for executive decision-making

## Business Problem Statement

Roxelle Nigeria Ltd. faced several business challenges including:

* Poor visibility into branch-level profitability
* Uncontrolled discount and promotion spending
* High return rates across some product categories
* Weak understanding of customer purchasing behaviour
* Lack of inventory and reorder-level monitoring

This project was developed to transform raw transactional data into actionable business intelligence insights.

## Dataset Description

The project utilised five CSV datasets provided by the organisation:

| Dataset                | Description                                              |
| ---------------------- | -------------------------------------------------------- |
| branches.csv           | Branch information including location and branch details |
| customers.csv          | Customer demographic and segmentation data               |
| products.csv           | Product details, categories, prices, and reorder levels  |
| sales_transactions.csv | Transactional sales records across branches              |
| date.csv               | Calendar and date dimension table                        |

## Tools & Technologies Used

* Microsoft Power BI Desktop
* Power Query Editor
* DAX (Data Analysis Expressions)
* GitHub
* Power BI Service
## Data Cleaning & Transformation

The datasets were loaded into Power BI using Power Query Editor for transformation and cleaning.

The following cleaning operations were performed:

* Renamed columns to improve readability and consistency
* Corrected all column data types (Date, Decimal, Whole Number, Text)
* Removed duplicate rows from the sales transaction dataset
* Checked and handled blank/null values appropriately
* Created a custom Revenue After Discount column using:

```DAX
Revenue After Discount = Quantity × UnitPrice × (1 - DiscountPercent / 100)

### Null & Blank Value Handling

| Column          | Action Taken                                                                              |
| --------------- | ----------------------------------------------------------------------------------------- |
| CustomerID      | Blank values retained because some transactions may not be linked to registered customers |
| DiscountPercent | Blank values treated as 0 where necessary                                                 |
| LoyaltyCard     | Blank values retained for analysis purposes                                               |
| Other fields    | Validated and corrected where required                                                    |

## Data Modelling

A star schema model was implemented to ensure efficient filtering, reporting, and DAX calculations.

### Fact Table

* sales_transactions

### Dimension Tables

* customers
* products
* branches
* date

### Relationship Design

* One-to-many relationships were created between dimension tables and the sales_transactions table
* Single-direction cross-filtering was used to improve model performance and avoid ambiguity
* No many-to-many relationships exist in the model

### Star Schema Screenshot

Model view screenshot is available in the `/screenshots` folder.

## DAX Measures Created

The following DAX measures were implemented:

| Measure               | Purpose                                 |
| --------------------- | --------------------------------------- |
| Total Revenue         | Calculates total revenue after discount |
| Total Cost            | Calculates total transaction cost       |
| Total Profit          | Revenue minus cost                      |
| Profit Margin %       | Profitability percentage                |
| Total Transactions    | Counts distinct transactions            |
| Return Rate %         | Percentage of returned transactions     |
| Avg Basket Size       | Average revenue per transaction         |
| MoM Revenue %         | Month-over-month revenue growth         |
| Discount Revenue Loss | Revenue sacrificed through discounting  |
## Dashboard Pages

The Power BI report was structured into four major analytical dashboards:

### 1. Sales Performance Dashboard

This dashboard provides visibility into:

* Total revenue, profit, and profit margin
* Branch-level revenue performance
* Revenue trends over time
* Revenue contribution by category
* Profitability across branches

### 2. Customer Behaviour Analysis

This dashboard focuses on customer insights including:

* Customer segmentation analysis
* Average basket size
* Loyalty card performance
* Customer age distribution
* Gender analysis
* Top customers by revenue

### 3. Product & Inventory Analysis

This dashboard provides insights into:

* Top and bottom performing products
* Product return rate analysis
* Revenue contribution by product category
* Inventory reorder-level monitoring
* Product profitability trends

### 4. Discount & Promotions Audit

This dashboard evaluates discount effectiveness by analysing:

* Revenue lost through discounting
* Discount impact by payment method
* Relationship between discounts and returns
* Branch revenue versus discount performance

## Key Business Insights

The analysis generated several important business insights:

* Some branches generated high revenue but also applied excessive discounting, reducing overall profitability
* Loyalty card customers demonstrated stronger purchasing behaviour compared to non-holders
* Certain product categories contributed significantly more to revenue and profit
* Multiple products showed elevated return rates above acceptable business thresholds
* Discount-heavy transactions did not always correlate with higher revenue performance
* Inventory monitoring revealed products approaching reorder-level risk

## Screenshots

Dashboard screenshots and model view screenshots are available in the `/screenshots` folder of this repository.

## Power BI Service Link

Published Power BI Service Report:
https://app.powerbi.com/groups/me/reports/5a859b0d-7c6c-4bc2-a8c5-4492c0bcf930/152bad589e51cc42d818?experience=power-bi

## Repository Contents

| Folder/File                  | Description                           |
| ---------------------------- | ------------------------------------- |
| /datasets                    | Source CSV datasets                   |
| /screenshots                 | Dashboard and model screenshots       |
| /docs                        | Project documentation and summary PDF |
| Roxelle_Sales_Analytics.pbix | Power BI project file                 |
| README.md                    | Project documentation                 |

## Conclusion

This project demonstrates the use of Microsoft Power BI for transforming raw business data into actionable executive-level insights.

The final solution combines:

* data cleaning,
* data modelling,
* DAX calculations,
* interactive visualisation,
* and business storytelling

to support data-driven decision-making for retail operations management.


