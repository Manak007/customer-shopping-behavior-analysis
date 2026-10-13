# 🛍️ Customer Shopping Behavior Analysis | Python · SQL · Power BI

An end-to-end data analytics project that analyzes **3,900 retail transactions** to uncover how customers shop, what drives their spending, and how the business can grow revenue and loyalty. The workflow covers data cleaning and feature engineering in Python, business analysis in SQL, an interactive Power BI dashboard, and a written report with recommendations.

## 📌 Business Problem
A retail company wants to understand its customers' purchasing patterns across demographics, product categories and sales channels. The key question:

> **How can the company use customer shopping data to identify trends, improve engagement and optimize marketing and product strategies?**

The full problem statement is in `Business Problem  Document.pdf`.

## 🗂️ Dataset
| Item | Detail |
|---|---|
| Rows | 3,900 transactions |
| Columns | 18 |
| Demographics | Age, Gender, Location, Subscription Status |
| Purchase details | Item, Category, Purchase Amount (USD), Season, Size, Color |
| Behavior | Discount Applied, Promo Code Used, Previous Purchases, Purchase Frequency, Review Rating, Shipping Type, Payment Method |
| Missing data | 37 values in Review Rating |

## 🛠️ Tech Stack
- **Python** (Pandas, NumPy, Matplotlib, Seaborn, SQLAlchemy): data cleaning, EDA, feature engineering, database loading
- **SQL** (PostgreSQL): business analysis with aggregations, CASE, CTEs and window functions
- **Power BI**: interactive dashboard
- **Report & presentation**: PDF report and PowerPoint deck

## 🔄 Project Workflow
1. **Data preparation (Python)**
   - Explored the structure with `df.info()` and `df.describe()`
   - Imputed the 37 missing review ratings with the **median rating of each product category**
   - Standardized column names to snake_case
   - Engineered `age_group` (quartile bins: Young Adult, Adult, Middle-aged, Senior) and `purchase_frequency_days`
   - Found `promo_code_used` was redundant with `discount_applied` and dropped it
   - Loaded the cleaned data into PostgreSQL
2. **Business analysis (SQL)**: answered 10 business questions (see below)
3. **Dashboard (Power BI)**: built KPI cards and visuals for revenue, customer segments, categories, subscriptions and shipping
4. **Reporting**: summarized the insights and recommendations in a report and stakeholder presentation

## ❓ Business Questions Answered in SQL
1. Total revenue by gender
2. Customers who used a discount but still spent above the average purchase amount
3. Top 5 products by average review rating
4. Average purchase amount for Standard vs. Express shipping
5. Average spend and total revenue of subscribers vs. non-subscribers
6. Top 5 products with the highest share of discounted purchases
7. Customer segmentation into New, Returning and Loyal
8. Top 3 most purchased products in each category (`ROW_NUMBER()` window function)
9. Whether repeat buyers (more than 5 previous purchases) are more likely to subscribe
10. Revenue contribution of each age group

## 📊 Key Insights
- **Total revenue:** $233,081 across 3,900 orders (average order value **$59.76**)
- **Gender:** male customers generated **$157,890 (~68%)** of revenue vs. $75,191 from female customers
- **Category:** **Clothing** leads with $104,264 (~45% of revenue), followed by Accessories ($74,200)
- **Subscriptions:** only **27%** of customers (1,053) are subscribers, and their average spend ($59.49) is about the same as non-subscribers ($59.87), so the subscription program is not yet increasing basket size
- **Repeat buyers:** of 3,476 customers with more than 5 previous purchases, only **958 (~28%)** subscribe, a clear upsell opportunity
- **Loyalty:** **80%** of customers (3,116) fall in the Loyal segment (more than 10 previous purchases)
- **Discounts:** **43%** of all orders used a discount; Hats, Sneakers and Coats are the most discount-dependent products (about 49–50% of their orders)
- **Shipping:** Express shipping orders average **$60.48** vs. **$58.46** for Standard
- **Age:** Young Adults contribute the most revenue ($62,143), but revenue is fairly balanced across all four age groups

## 💡 Business Recommendations
- **Boost subscriptions:** target the ~2,500 frequent buyers who don't subscribe with exclusive subscriber benefits
- **Reward loyalty:** run loyalty programs that move Returning customers into the Loyal segment
- **Review the discount policy:** reduce reliance on discounts for products like Hats and Sneakers to protect margins
- **Product positioning:** feature top-rated and best-selling products in campaigns
- **Targeted marketing:** focus on high-revenue age groups and Express shipping users

## 📁 Repository Structure
| File | Description |
|---|---|
| `customer_shopping_behavior.csv` | Raw dataset (3,900 rows) |
| `Customer_Shopping_Behavior_Analysis.ipynb` | Python notebook: cleaning, EDA, feature engineering, loading to PostgreSQL |
| `customer_behavior_sql_queries.sql` | SQL queries answering the 10 business questions |
| `customer_behavior_dashboard.pbix` | Power BI dashboard |
| `Customer Shopping Behavior Analysis.pdf` | Project report |
| `Customer-Shopping-Behavior-Analysis.pptx` | Stakeholder presentation |
| `Business Problem  Document.pdf` | Business problem statement |


## 👤 Author
**Manak Singh**
[LinkedIn](https://linkedin.com/in/manak-singh) · [GitHub](https://github.com/Manak007)
