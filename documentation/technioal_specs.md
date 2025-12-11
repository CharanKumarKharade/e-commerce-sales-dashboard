## Project Overview
Project Name: E-commerce Sales Performance Dashboard
Tools Used: Power BI, Excel, SQL (for analysis), GitHub
Data Source: Superstore Sales Dataset (9,994 transactions)
Time Period: 2015-2016
Development Time: 2 days (8 hours total)

### Simple Architecture

Superstore CSV → Power BI Import → Data Cleaning → Visualizations → Power BI Service
Data Structure
Single Table Setup (No complex relationships needed)


Orders Table (9,994 rows, 21 columns)
├─ Order Details: Order ID, Order Date, Ship Date
├─ Product Info: Product ID, Category, Sub-Category, Product Name
├─ Customer Info: Customer ID, Customer Name, Segment, Country, City, State, Postal Code, Region
├─ Sales Metrics: Sales, Quantity, Discount, Profit
└─ Shipping: Ship Mode

## Key DAX Measures Created
dax
-- Basic Calculations
Total Sales = SUM('Orders'[Sales])
Total Profit = SUM('Orders'[Profit])
Profit Margin = DIVIDE([Total Profit], [Total Sales])

-- Category Analysis
Category Sales = CALCULATE([Total Sales], ALLEXCEPT('Orders', 'Orders'[Category]))

-- Time Analysis (for line chart)
Yearly Sales = TOTALYTD([Total Sales], 'Date'[Year])
Visualizations Implemented
Page 1: Executive Summary
3 KPI Cards: Total Sales, Total Profit, Profit Margin

Bar Chart: Sales by Product Category

Line Chart: Yearly Sales Trend (2015-2016)

Interactive Features: Bookmarks, Cross-visual highlighting

Page 2: Product Analysis
Table: Top 10 Products by Sales

Bar Chart: Sales & Profit by Category

Donut Chart: Profit Distribution by Category

Treemap: Sales by Sub-Category

Page 3: Customer Insights
Table: Top 5 Customers by Sales

Donut Chart: Customer Segments (Consumer/Corporate/Home Office)

Cards: Total Customers, Average Order Value

Page 4: Regional Performance
Map: Sales by State (US Map visualization)

Bar Chart: Sales by Region comparison

Table: Top States by Sales

## #Interactive Features
Bookmarks: Created "Tech Focus" and "Reset View" bookmarks

Highlighting: Enabled cross-visual highlighting (click category → highlights trend)

Navigation: Back buttons on all pages for seamless navigation

Mobile Optimization: Separate mobile layouts for all pages

## Data Processing Steps
Data Import: CSV file imported directly into Power BI

Basic Cleaning: Verified data types, checked for missing values

Calculated Columns: Created Month-Year for time analysis

No Complex ETL: Simple transformation using Power Query

### Deployment
Published to: Power BI Service

Access: Public "Publish to web" link (no login required)

Mobile: Tested on Power BI mobile app