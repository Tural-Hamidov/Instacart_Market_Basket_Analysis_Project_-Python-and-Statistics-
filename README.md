# Instacart Market Basket Analysis Project - Python and Statistics

Exploratory data analysis and statistical analysis project using the Instacart dataset to uncover customer shopping behavior, ordering patterns, reorder habits, product popularity, and key purchasing trends.

# 🛒 Instacart Customer Shopping Behavior Analysis

## 📌 Project Overview
This project explores customer shopping behavior using the Instacart dataset.  
The main goal was to clean the data, handle missing values, inspect duplicate records, and perform exploratory and statistical analysis to better understand how customers shop, reorder products, and build their carts.

The analysis focuses on:
- ⏰ customer ordering patterns  
- 🔁 reorder behavior  
- 🥑 product popularity  
- 🛒 cart-building habits  
- 📊 statistical insights from customer purchasing trends  

---

## 🗂️ Dataset Overview
This project uses the Instacart dataset, which consists of five related tables describing customer orders, products, and product categories. Together, these tables make it possible to analyze shopping behavior from multiple perspectives.

- **`orders`** — contains information about each order, including the customer, the day and hour of purchase, and the number of days since the previous order  
- **`products`** — contains product-level information such as product name and its related aisle and department  
- **`order_products`** — links products to orders and shows the order in which items were added to the cart, as well as whether the product had been purchased before  
- **`aisles`** — contains aisle category names  
- **`departments`** — contains department category names  

Using these five tables together makes it possible to explore customer purchasing habits, reorder patterns, popular products, and cart-building behavior.

---

## 🎯 Objectives
The main objectives of this project were:

- inspect and understand the structure of the datasets  
- clean the data by handling missing values and checking duplicate records  
- perform exploratory data analysis  
- apply basic statistical analysis to key numerical variables  
- visualize shopping and reorder behavior  
- generate business insights and recommendations  

---

## 🧹 Data Cleaning
Several preprocessing steps were performed before analysis:

- missing `product_name` values were identified and filled with `"Unknown"`
- missing `product_name` values were found to be concentrated in `department_id = 21`
- missing `days_since_prior_order` values were confirmed to belong only to first-time orders and kept as `NaN`
- missing `add_to_cart_order` values were found only in orders with 65+ items and replaced with `999` as a placeholder
- duplicate rows in the `orders` dataset were removed
- `product_id` values were checked and confirmed to be unique
- repeated `product_name` values were inspected case-insensitively, but not removed, because products with different `product_id` values may represent different items

These steps helped preserve the structure and reliability of the dataset for analysis.

---

## 🔍 Exploratory Data Analysis
The following questions were explored during the project:

### ⏰ Ordering Patterns
- What time of day do people shop for groceries?
- What day of the week do people shop the most?
- How long do people wait before placing another order?
- Is there a difference between order-hour distributions on Wednesdays and Saturdays?

### 👥 Customer Behavior
- What is the distribution of the number of orders per customer?
- How many items do people typically buy in one order?
- For each customer, what proportion of their products ordered are reorders?

### 🥬 Product Behavior
- What are the top 20 most popular products?
- What are the top 20 most frequently reordered products?
- For each product, what proportion of its orders are reorders?
- What are the top 20 items that people put in their carts first?

---

## 📈 Statistical Analysis
In addition to EDA, descriptive and statistical analysis was applied to key numerical columns.

This included:
- descriptive statistics using `.describe()`
- mean and variance of `order_hour_of_day`
- normality testing before correlation analysis
- Spearman correlation analysis between meaningful numerical variables
- exclusion of identifier columns such as `order_id` and `user_id` from correlation analysis
- boxplot analysis of reorder intervals
- histogram-based distribution analysis of order times

These statistical measures helped support and strengthen the findings from the visual analysis.

---

## 🛠️ Tools and Libraries
This project was completed in **Python** using:

- **pandas** — data cleaning and manipulation  
- **matplotlib** — visualizations  
- **seaborn** — statistical plots  
- **plotly.express** — interactive charts  
- **scipy** — statistical testing  

---

## 🔑 Key Findings
Some of the main findings from the analysis include:

- Orders are concentrated during the daytime, especially between **10 AM and 3 PM**
- Customers tend to shop more at the **beginning of the week**
- Many customers reorder products on a **weekly cycle**, with a strong peak at **7 days**
- The most popular and most reordered products are mostly **fresh produce, dairy, beverages, and everyday essentials**
- Most orders are relatively small, typically containing around **5–6 items**
- The products most often added to the cart first are also mostly **produce, dairy, beverages, and other essentials**
- Customer reorder behavior is generally moderate to high, suggesting repeated and routine shopping habits
- Correlation analysis showed mostly weak relationships between the selected numerical variables
- `order_id` and `user_id` were excluded from correlation analysis because they are identifier columns and do not represent meaningful measurable features
- Spearman correlation was used because the selected variables were not assumed to be normally distributed

---

## 💡 Business Recommendations
Based on the findings, several practical recommendations can be made for Instacart:

### 1. 🔁 Improve personalized reorder recommendations
Since many customers repeatedly purchase the same products, Instacart can strengthen its “Buy Again” features and personalized reorder suggestions.

### 2. ⏰ Use peak shopping hours for targeted promotions
Because most orders are placed between late morning and afternoon, promotions and push notifications should be scheduled around these high-activity hours.

### 3. 📅 Build strategies around weekly shopping cycles
The strong 7-day reorder pattern suggests that many users follow a weekly grocery routine. This creates opportunities for reminder notifications, weekly bundles, and subscription-style services.

### 4. 🥛 Prioritize staple products in the app interface
Fresh produce, dairy, beverages, and everyday essentials dominate the most popular, most reordered, and first-added cart items. These categories should be highlighted more prominently in the app.

### 5. 🛒 Optimize the platform for small and medium-sized orders
Since most orders contain around 5–6 items, the shopping experience can be improved with faster checkout, simplified cart-building, and one-click reorder options.

### 6. 👥 Segment customers by reorder behavior
Customers with high reorder rates may respond well to loyalty programs and subscription offers, while lower-reorder customers may benefit from discounts and personalized discovery recommendations.

### 7. 📍 Use first-added cart items to improve product placement
Products most commonly added first can be used to design smarter recommendation flows and improve the shopping experience from the start of the customer journey.

### 8. 📊 Use predictive analytics carefully
Because correlation analysis showed mostly weak relationships between the selected numerical variables, Instacart should not rely on correlation results alone. Instead, customer history, reorder behavior, product preferences, order timing, and basket-level features should be combined for more accurate customer targeting and predictive modeling.

---
