# Pizza-Sales-Report
This project analyzes a year of sales data from a fictional pizza store using Microsoft Excel. The dataset includes variables such as pizza type, size, quantity sold, price, and ingredients. The analysis focuses on identifying sales trends, top performing products, and key business insights that can support better decision-making and operational optimization.

## Table of content 

## Project overview 
This project analyzes a year's worth of sales data from a fictional pizza company to uncover key business insights. The dataset includes information on orders, pizza types, sizes, prices, and ingredients.

The goal of the analysis is to identify revenue drivers, understand customer ordering behavior, and provide actionable insights that can help improve business performance and decision-making.

## Project Scope 
This project involves a comprehensive analysis of pizza sales data spanning one year. The analysis integrates multiple related tables, orders, order details, pizzas, and pizza types, to evaluate operational performance, identify sales trends, and assess product-level performance across the business.

## Project Objective 
The primary objectives of this analysis are:
- **Sales Analysis**: Examine sales patterns across the year to identify peak order periods, daily and hourly demand trends, and overall revenue performance.
- **Product Performance**: Assess which pizza categories, types, and sizes contribute the most to total sales and revenue, and identify both top-performing and underperforming menu items.
- **Customer Ordering Behavior**: Examine how customers place orders by identifying purchasing trends that reveal common buying behavior.
- **Operational Insights**: Generate insights that can help improve operational planning, including staffing during peak hours, targeted promotions for popular items, and potential adjustments to the menu to enhance overall business performance.

## Expected Outcome 
The analysis aims to provide actionable insights, including:
- Total number of orders placed during the year.
- Identification of peak sales periods by hour, day, and month.
- Average number of pizzas purchased per order.
- Identification of top-performing pizzas based on sales and revenue.
- Revenue analysis across pizza categories and sizes.
- Detection of sales patterns and trends over time.
- Recommendations for improving menu offerings, promotional strategies, and operational planning.

## Data Source
The dataset for this project is sourced from [Maven Analytics](https://app.mavenanalytics.io/datasets?dataStructure=Multiple+tables&accessType=open) website, designed specifically for practice purposes. It is presented in an Excel file with four tables (Order Details, Orders, Pizza Types, and Pizzas) comprising 48,620, 21,350, 32, and 96 rows respectively, and 4, 3, 4, and 4 columns respectively. The dataset includes key attributes essential for a comprehensive analysis, such as:

-	Order_id: Unique identifier for each order.
-	Date: Date the order was placed.
-	Time: Time the order was placed.
-	Order_details_id: Unique identifier for each pizza within each order.
-	Pizza_id: Foreign key linking to pizza details (size and price).
-	Quantity: Number of each type and size of pizza ordered.
-	Pizza_type_id: Foreign key linking to pizza type.
-	Size: Size of the pizza. 
-	Price: Price of the pizza in USD.
-	Name: Name of the pizza as shown in the menu.
-	Category: Category of the pizza in the menu.
-	Ingredients: Ingredients used in the pizza, as shown in the menu.
  
Each of these variables contributes crucial insights, collectively painting a vivid portrayal of Pizza Sales Place.

## Data Cleaning and Processing 
The dataset was cleaned and prepared using Excel and Power Query to ensure accuracy, consistency, and proper data modeling before conducting the analysis.

**Data Import:**

The dataset files were imported into Excel using Power Query, allowing for efficient data transformation and management.

**Header Correction:**

The Pizza Types sheet contained formatting issues where the first row needed to be promoted as column headers. Power Query was used to correctly promote the row to headers to ensure proper column labeling.

**Data Validation:**

The datasets were reviewed to check for missing values, inconsistencies, and formatting errors to ensure the data was suitable for analysis.

**Data Transformation:**

Additional columns were created to enhance time-based analysis, including:
- Weekday
- Month
- Quarter
These fields enabled a deeper analysis of sales patterns across different time periods

**Data Modeling:**

A relational data model was created to connect the different tables in the dataset. Relationships were established between:
- orders and order_details
- order_details and pizzas
- pizzas and pizza_types
This structure allowed for accurate aggregation and analysis across the different tables.

Data Preparation for Analysis:
The cleaned and structured data was then loaded into the data model, enabling the creation of measures and calculations used in the analysis and dashboard development.

## Data Model 
The dataset consists of four related tables that were structured into a relational data model to enable accurate analysis. Establishing relationships between these tables allows data from different sources to be combined efficiently for reporting and calculations.

**Tables Used**

**Orders**: Contains information about each order placed, including the order ID, date, and time.

**Order Details**: Contains transaction-level information, including the specific pizzas included in each order and the quantity purchased.

**Pizzas**: Contains details about each pizza variation, including its size and price.

**Pizza Types**: Contains descriptive information about the pizzas, including the name, category, and ingredients.

**Relationships**

The tables were connected using the following relationships:

- **Orders → Order Details**
  
orders.order_id → order_details.order_id

This relationship links each order to the items included in that order.

- **Pizzas → Order Details**

pizzas.pizza_id → order_details.pizza_id

This relationship connects each ordered item to its corresponding pizza details, such as size and price.

- **Pizza Types → Pizzas**

pizza_types.pizza_type_id → pizzas.pizza_type_id

This relationship provides descriptive information about each pizza, including its name and category.

**Data Model Structure**

The data model follows a **relational structure**, where the Order Details table serves as the central transactional table connecting orders to pizza information.

This structure enables accurate aggregation of metrics such as total sales, order counts, and product performance across different dimensions such as time, category, and pizza size.

## Data Analysis and Insight 
The primary aim of this analysis is to extract meaningful insights from the Pizza Sales Place dataset by examining sales performance, product contribution, and demand patterns over a one-year period.

The analysis begins with a **monthly sales trend analysis** to understand how revenue fluctuates throughout the year and to identify any potential seasonal patterns in sales performance. This helps provide a clearer view of how the business performs across different months.

Next, the analysis focuses on **product performance** by identifying the top revenue-generating pizzas as well as the least performing pizzas. This helps determine which products drive the majority of revenue and which menu items may require promotional support or potential reconsideration.

The analysis also examines **sales distribution by hour** to identify peak ordering periods during the day. Understanding these peak hours provides valuable insights into customer demand patterns and informs staffing and operational planning.

Through these analyses, the project aims to uncover patterns in sales performance, highlight key revenue drivers, and identify opportunities for improving business strategy and operational efficiency.

### 1. How much money did we make this year? Can we identify any seasonality in the sales? 
The aim of this analysis is to evaluate the total annual revenue and identify sales patterns that change over time. Understanding these patterns helps assess the overall financial performance of the pizza business and reveals potential seasonal trends that influence sales throughout the year.

To achieve this, **monthly and quarterly sales trends** were analyzed using pivot tables and visualized with a line chart to clearly illustrate how revenue fluctuates across different periods. The **total revenue** was calculated using a **DAX measure**, which multiplies the quantity of pizzas ordered by their corresponding prices to accurately determine total sales.

These visualizations provide a clear overview of sales performance throughout the year, helping to highlight trends, fluctuations, and any unusual patterns that may require further attention.

**Total Revenue** 
**(image of Dax and Revenue)** 

**Seasonality in Sales**
**(Image of Montly data)**

From the analysis above;
- July has the highest revenue at $72,558, followed by May, March, and November at $71,403, $70,397 and $70,395, respectively.
- October, September, and December have the least revenue at $64,026, $61,180, and $64,701, respectively.

**(image of quarterly sales)**
From the analysis above;
- The second quarter has the highest revenue, followed by the first quarter at $208,370 and $205,350, respectively, with the fourth quarter having the least revenue at $199,124.

### 2. Do we have any best-selling pizzas? Are there underperforming pizzas that may need to be removed from the menu or supported with promotions?
This analysis aims to evaluate the popularity and revenue contribution of different pizzas offered by the business. By identifying both the best-performing and least-performing pizzas, the business can better understand which products drive customer demand and which items may require strategic adjustments. These insights can support decisions related to menu optimization, inventory planning, and targeted promotional campaigns.

To conduct this analysis, sales data was examined to determine which pizzas were purchased most frequently and which were ordered the least.
To highlight the most significant findings, filters were applied to display the **top five best-selling pizzas** and the **bottom five least-performing pizzas** based on total quantity sold. This visualization provides a clear comparison of product demand, helping to identify key revenue drivers and potential areas for menu improvement.

**(Image of top 5 revenue generating pizza)**
- The **Thai Chicken Pizza generates the highest revenue**, totaling **$43,434**, making it the top revenue-contributing pizza. Its strong performance suggests that it is a customer favorite and serves as a major driver of overall sales for the business.
- Other pizzas such as **Barbecue Chicken Pizza, California Chicken Pizza, Classic Deluxe Pizza, and Spicy Italian Pizza** also contribute significantly to revenue. Although they do not generate as much revenue as the top performer, their strong sales indicate steady demand and consistent popularity among customers, making them important contributors to the overall performance of the menu.

**(image of least performing Pizza)**
- With total revenue of **$11,588**, the** Brie Carre Pizza** emerges as the least performing pizza in terms of sales. Its low revenue contribution suggests that it experiences significantly lower customer demand compared to other menu items.
- Other pizzas such as **Green Garden Pizza, Spinach Supreme Pizza, Mediterranean Pizza, and Spinach Pesto Pizza** also record relatively lower revenue figures. This indicates weaker demand for these items compared to the more popular pizzas on the menu.

### 3. Is there a peak hour for customer orders?
The objective of this analysis is to identify the specific times of the day when Pizza Sales Place receives the highest number of customer orders. Understanding peak ordering hours is important as it helps the business better manage staffing levels, improve service efficiency, and ensure adequate preparation during high-demand periods.

To conduct this analysis, a **pivot table** was created where the **time column** was placed in the rows section and grouped by hour, while **order_id** was placed in the values section to count the total number of orders. The results were then visualized using a **column chart**, which clearly illustrates the distribution of customer orders across different hours of the day and highlights the peak ordering periods.

**(image of customer order by hour)**
Peak Hours Analysis:
- 12 PM: Customer traffic peaks at 12 PM with 2,520 orders, making lunchtime the busiest period of the day.
- 1 PM: Close behind, 1 PM records 2,455 customers, confirming the lunchtime rush.
- 5 PM: The early evening period begins to pick up at 5 PM with 2,336 customers.
- 6 PM: Evening traffic reaches 2,399 customers, marking the start of the dinner rush.

Overall, **Pizza Sales Place experiences its busiest periods during lunch (12 PM – 1 PM) and evening (5 PM – 7 PM)**. Early afternoon and late evening see moderate activity, while late night and early morning hours have minimal customer flow.

### 4. How many customers do we have each day?
