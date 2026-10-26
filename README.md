# Pizza Sales Analysis using SQL

An end-to-end SQL analysis of a pizza restaurant's sales data in **MySQL**. The project answers 13 business questions about orders, revenue, best-selling products, peak hours and category performance, using joins, subqueries, aggregations and window functions.

📄 **Project deck (PDF):** [Pizza_Sales_SQL_Project.pdf](Pizza_Sales_SQL_Project.pdf)

---

## Objective

Understand how the business is performing by finding out:
- How many orders were placed and how much revenue was generated
- Which pizzas, sizes and categories sell the most
- When customers order the most
- Which products and categories drive revenue

---

## Dataset

The database `pizzahut` contains four tables:

| Table | Description |
|---|---|
| `orders` | One row per order: `order_id`, `order_date`, `order_time` |
| `order_details` | Line items of each order: `order_details_id`, `order_id`, `pizza_id`, `quantity` |
| `pizzas` | Each pizza with its size and price: `pizza_id`, `pizza_type_id`, `size`, `price` |
| `pizza_types` | Pizza names and details: `pizza_type_id`, `name`, `category`, `ingredients` |

**Relationships**
- `order_details.order_id` → `orders.order_id`
- `order_details.pizza_id` → `pizzas.pizza_id`
- `pizzas.pizza_type_id` → `pizza_types.pizza_type_id`

---

## Tools and Skills

- **Tool:** MySQL Workbench (MySQL 8.0)
- **SQL concepts used:**
  - `SELECT`, `WHERE`, `GROUP BY`, `ORDER BY`, `LIMIT`
  - Aggregate functions: `COUNT`, `SUM`, `AVG`, `ROUND`
  - `JOIN` across multiple tables
  - Subqueries (in `FROM` and `SELECT`)
  - Date and time functions: `HOUR()`
  - Window functions: `SUM() OVER`, `RANK() OVER (PARTITION BY ...)`

---

## Business Questions

### Basic
1. Retrieve the total number of orders placed.
2. Calculate the total revenue generated from pizza sales.
3. Identify the highest-priced pizza.
4. Identify the most common pizza size ordered.
5. List the top 5 most ordered pizza types along with their quantities.

### Intermediate
6. Find the total quantity of each pizza category ordered.
7. Determine the distribution of orders by hour of the day.
8. Find the category-wise distribution of pizzas.
9. Group the orders by date and calculate the average number of pizzas ordered per day.
10. Determine the top 3 most ordered pizza types based on revenue.

### Advanced
11. Calculate the percentage contribution of each pizza category to total revenue.
12. Analyze the cumulative revenue generated over time.
13. Determine the top 3 most ordered pizza types based on revenue for each pizza category.

---

## Key Findings

| Metric | Result |
|---|---|
| Total orders | 21,350 |
| Total revenue | about 817,860 |
| Highest-priced pizza | The Greek Pizza (35.95) |
| Most ordered size | Large (L), counted per order line |
| Most ordered pizza | The Classic Deluxe Pizza (2,453 pizzas) |
| Most ordered category | Classic (14,888 pizzas) |
| Average pizzas per day | about 138 |
| Top revenue pizza | The Thai Chicken Pizza (43,434.25) |
| Revenue share by category | Classic 26.91%, Supreme 25.46%, Chicken 23.96%, Veggie 23.68% |

**Insights**
- Orders peak around lunchtime (12:00 to 13:00).
- The top 5 most ordered pizzas are very close in volume, so demand is spread evenly across the menu.
- The top 3 revenue earners are all chicken pizzas, even though the Chicken category has the fewest pizza types.
- Revenue is balanced across categories, with each contributing about 24% to 27%.
- XL and XXL sizes are rarely ordered.

---

## Screenshots

> Replace the file names below with your own screenshots from the `screenshots` folder.

![Total orders](screenshots/01_total_orders.png)
![Top 5 pizzas](screenshots/05_top5_pizzas.png)
![Revenue by category](screenshots/11_revenue_percentage.png)
![Cumulative revenue](screenshots/12_cumulative_revenue.png)

---

## Repository Structure

```
pizza-sales-sql-analysis/
├── queries.sql                      # All 13 queries with questions as comments
├── Pizza_Sales_SQL_Project.pdf      # Presentation of queries, results and insights
├── results/                         # Query results exported as CSV
├── screenshots/                     # Screenshots of queries and outputs
└── README.md
```

---

## How to Run

1. Install MySQL and MySQL Workbench.
2. Create a database named `pizzahut` and import the four tables (`orders`, `order_details`, `pizzas`, `pizza_types`) from the source CSV files.
3. Open `queries.sql` in MySQL Workbench.
4. Run each query one at a time and compare with the results in the `results` folder.

---

## Author

**Gowhar**
🔗 LinkedIn: [add your profile link here]
