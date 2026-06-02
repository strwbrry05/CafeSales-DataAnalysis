# Cafe Sales - Data Analysis (EDA) & Visualization
## Executive Summary
The Dirty Cafe Sales dataset contains 10,000 rows of synthetic data representing sales transactions in a cafe.

Analysis reveals that Coffee, Juice, Cake are the top three performers in quantities sold, but not in revenue generated. [(3766, $7532),(3681, $11043),(3655, $10965)]. Cookie and Tea are the worst performing items [(3427, $3427 ),(3441, $5161)]. Data shows that June was the Cafe's best preforming month generating revenue up to $7353.0 and item revenue is highly dependent on Month.

**Key Findings**
- June Insights
- Total Quantities Sold vs Revenue Generated (Grouped by Item/Month/WeekDay)

## Business Task
Extract insights and highlight emerging patterns in Cafe data. Find trends based on items sold including: quantity of items sold and revenue generated from each item. Delve into revenue generated per day/week/month.

**Questions**
1. Which items sold the best/worst?
2. How much revenue did they generate?
3. Best preforming month? Insights?
4. How much revenue was generated per month? In Total?

## Data Sources
Dataset From Kaggle: [Kaggle Dataset](https://www.kaggle.com/datasets/ahmedmohamed2003/cafe-sales-dirty-data-for-cleaning-training/data)
**Source:** Public data from Kaggle
**File Name:** dirty_cafe_sales.csv

| Column Name  | Description | Data Type |
| ------------- | ------------- | ------------- |
| Transaction ID  | unique transaction identifier  | string |
| Item  | name of menu item  | string |
| Quantity  | number of items purchased  | float |
| Price Per Unit  | cost of individual item  | float |
| Total Spent  | total amount spent on transaction  | float |
| Payment Method  | customer payment method  | string |
| Location  | takeout or dine in  | string |
| Transaction Date  | date of transaction  | datetime |

## Methodology
### Cleaning
**Initial shape: (10000, 8)**
1. Quantity, Price Per Unit, Total Spent, Item are Interconnected
2. Replace any 'Unknown' or 'Error' values with NaN values
3. Fill in missing data with variations of this equation:
   - df ['Quantity'] = df ['Quantity'].fillna ( df ['Total Spent'] / df ['Price Per Unit'])
5. Drop rows where values cannot be identified or calculated
6. Remove duplicate rows (none in this case)
7. Remove Transaction ID, as it will always be unique and is not needed here
8. Generate three new columns for Day, Month, Year, generated from Transaction Date
**Final shape: (9514, 10)**

### Manipulation
1. Total quantity of Items sold and total revenue generated per item
2. Breakdown of revenue generated each month and quantity of items sold each month
3. Created a subset of all transactions in the highest performing month (June)
  - Revenue generated daily
  - Highest performing day
  - Quantities of items sold on highest performing day (June 16)
4. Average customer expenditure per month
5. Most popular days of the week
6. Sales of Items affected by Month (Line plot)
7. Customer preferences of Location and Payment Method

Cleaned Dataset Overview
| Column Name  | Description | Data Type |
| ------------- | ------------- | ------------- |
| Item  | name of menu item  | string |
| Quantity  | number of items purchased  | float |
| Price Per Unit  | cost of individual item  | float |
| Total Spent  | total amount spent on transaction  | float |
| Payment Method  | customer payment method  | string |
| Location  | takeout or dine in  | string |
| Transaction Date  | date of transaction  | datetime |
| Day  | day of transaction  | datetime |
| Month  | month of transaction  | datetime |
| Year  | year of transaction  | datetime |

## Visualizations
Google Data Studio/Looker: [Google Public View Link](https://datastudio.google.com/u/0/reporting/242db653-f9e1-421c-b8df-e7b3645222cd/page/rLszF?s=nwwOKvqqcec)

Tableau: [Tableau Public View Link](https://public.tableau.com/views/Cafe_VizTableu/JuneStats?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link )

## Summary of Key Findings
**Top 3 Quantities Sold:** Coffee, Cake, Juice

**Top 3 Revenue Generated:** Salad, Sandwich, Smoothie
<br></br>

- June, October, January generated the most revenue
- October, March, June sold the most quantities of items
<br></br>

- Different Items had different months for popualrity (quantities sold)
<br></br>

**Best performing (revenue) day** was June 16, 2023

**Worst performing (revenue) day** was June 7, 2023
<br></br>

- Salad was always the most consistent in generating the most revenue, Cookie was always the worst
<br></br>

- Friday, Thursday, and Tuesday were the most popular days of the week in June
- Smoothies sold the best in June
- Tea sold the worst in June

## Recommendations & Next Steps
1. **Reduce Menu Items**
- Remove the worst performing items from the menu (Cookie/Tea) to prevent loss of profit **or** create a seasonal menu that introduces items based on past data month popularity
2. **Promotions & Marketing**
- Increase item prices during popular months and decrease in less popular months. Introduce promotions to encourage customers to buy less popular items by offering a 2-for-1 deal bundled with a popular item (e.g. Coffee & Cookie). Provide discounts or promotions on popular days of the week such as Thursdays
3. **Routine Maintenance**
- Assure all systems are in working order. The majority of customers prefer to pay through digital means. Having no access to technology results in loss of revenue.

