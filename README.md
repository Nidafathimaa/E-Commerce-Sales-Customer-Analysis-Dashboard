# E-Commerce-Sales-Customer-Analysis-Dashboard
This project is an interactive Power BI dashboard developed using the Superstore E-commerce Dataset to analyze sales performance, customer behavior, product performance, profitability, and business trends. The dashboard helps in identifying key revenue drivers, high-performing categories, customer purchasing patterns, and loss-making products through dynamic visualizations and data-driven insights.

The project was designed using a Star Schema data model with fact and dimension tables to improve report performance, filtering, and analytical efficiency.

# Dataset Description
The dashboard uses the Superstore Dataset, which contains transactional e-commerce order data.

🔹 Dataset includes:
- Order details and transaction records
- Customer information
- Product categories and sub-categories
- Sales, Profit, and Quantity metrics
- Regional and segment-wise data
- Order and shipping dates
🔹 Important Columns
- Order Date
- Customer Name
- Product Name
- Category / Sub-Category
- Region
- Sales
- Profit
- Quantity
- Segment
# Data Cleaning & Modeling
- Performed data cleaning and transformation using Power Query
- Removed unnecessary columns and handled null values
- Corrected data types for dates and numeric columns
- Created a Date Table for time-based analysis
- Built a Star Schema Data Model
   - Fact Table → Sales Transactions
   - Dimension Tables → Customers, Products, Date
- Established relationships between tables for efficient filtering and analysis

# Dashboard Pages & Features
1️⃣ Overview Dashboard

- Provides a high-level summary of:

- Total Sales
- Total Profit
- Total Orders
- Profit Margin
- Sales Trend Analysis
- Category & Region-wise Sales Distribution

- Features:
  - KPI Cards
  - Line Charts
  - Donut Charts
  - Interactive Filters & Slicers
    
2️⃣ Customer & Product Analysis

- Focuses on customer purchasing behavior and product performance.

Features:
- Top Customers Analysis
- Product Category Analysis
- Treemap Visualizations
- Sales by Customer & Product
- Interactive Tables

3️⃣ Profit Overview

- Analyzes overall profitability and growth.

- Features:
  - Profit Trend Analysis
  - Profit Margin Analysis
  - YoY Profit Growth %
  - Waterfall Chart for Profit Contribution
  
4️⃣ Loss & Performance Analysis

- Identifies low-performing and loss-making products.

- Features:
  - Scatter Plot (Sales vs Profit)
  - Top Loss-Making Products
  - Detailed Product Performance Table
  - Loss Product KPIs
 
# Main DAX Measures
🔹 Total Sales
   - Total Sales = SUM(Sales[Sales])

🔹 Total Profit
   - Total Profit = SUM(Sales[Profit])

🔹 Total Orders
   - Total Orders = DISTINCTCOUNT(Sales[Order ID])

🔹 Profit Margin
   - Profit Margin = DIVIDE([Total Profit], [Total Sales])

🔹 Avg Sales per Order
   - Avg Sales per Order = DIVIDE([Total Sales], [Total Orders])

🔹 YoY Growth %
   - YoY Growth % =
     DIVIDE(
            [Current Year Profit] - [Previous Year Profit],
            [Previous Year Profit]
         )
     
🔹 Loss Products
   - Loss Products =
              CALCULATE(
                       DISTINCTCOUNT(Products[Product Name]),
                       FILTER(
                             VALUES(Products[Product Name]),
                                    [Total Profit] < 0
                           )
                       )


# Power BI Features Used
- KPI Cards
- Slicers
- Drill-Down / Drill-Up
- Tooltips
- Interactive Filtering
- Dynamic Charts
- Conditional Formatting
- Top N Filtering
- Waterfall Chart
- Scatter Plot
- Treemap Visuals

# Tools & Technologies Used

- Power BI
- Power Query
- DAX (Data Analysis Expressions)
- Star Schema Data Modeling
- Data Visualization
- Excel / Superstore Dataset

# Key Insights
- Technology category generated the highest sales revenue
- A small group of customers contributed significantly to overall sales
- Certain products generated high sales but low profit margins
- Sales showed an overall positive growth trend over time
- Some products consistently generated losses and required business attention
- Regional sales performance varied significantly across categories

# Business Impact

- This dashboard helps businesses:

  - Monitor sales and profitability
  - Identify high-value customers
  - Detect loss-making products
  - Improve pricing and product strategies
  - Make data-driven business decisions
# Conclusion

The E-Commerce Sales & Customer Analysis Dashboard provides a complete analytical view of business performance through interactive visualizations, advanced DAX calculations, and structured data modeling. The project demonstrates practical skills in Power BI, DAX, data transformation, and business intelligence reporting.
