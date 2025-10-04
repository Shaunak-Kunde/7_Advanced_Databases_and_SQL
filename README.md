# 🧠 Advanced Databases and SQL – Final Project

This project showcases a wide range of advanced SQL and relational database concepts using MySQL-like syntax. It includes real-world database operations such as writing stored functions and procedures, implementing triggers for data validation and automation, and working with recursive common table expressions (CTEs).

## 📁 File

- `project_10_advanced_databases_and_sql.sql`: A complete SQL script containing all tasks, queries, and object definitions.


## 📌 Project Objectives

### ✅ Task 1: Customer Order Report
- Join multiple tables (`customer`, `customer_order`, `merchandise_item`) to display:
  - Customer name
  - Ordered items
  - Quantity, Unit Price, and Line Total
- Sort data by customer and order.

### ✅ Task 2: Server Functions
- Use built-in aggregate functions like `SUM()` and `AVG()`.
- Format monetary values for Indian locale using rupee (₹) symbol.

### ✅ Task 3: Stored Functions
- Create:
  - `check_credit()` to verify a customer’s credit limit.
  - `get_qoh_ftn()` to fetch quantity on hand for an item.
- Use these in logical decision-making operations.

### ✅ Task 4: Stored Procedures
- Create procedures such as:
  - `customer_roster_stp()` to list all customers sorted by name.
  - `get_qoh_stp()` to retrieve quantity on hand using OUT parameters.

### ✅ Task 5: Triggers
- Implement triggers to:
  - Decrease inventory after a new line item is inserted.
  - Validate stock levels before allowing order inserts (using signal handling).
- Demonstrates both direct logic and calling stored procedures from triggers.

### ✅ Task 6: Common Table Expressions (CTEs)
- Write and query:
  - CTEs to simplify complex joins
  - Example: `order_line_item_cte` for summarizing sales

### ✅ Task 7: Recursive CTEs
- Construct hierarchical item bundles using:
  - Self-referencing recursive CTEs
  - Depth-level tracking
  - Pretty-printed indented output for nested items

![Advanced_SQL_Project_Shaunak](https://github.com/user-attachments/assets/b57adcfc-68a0-456a-a952-674a9c07dc42)


## 🧰 SQL Concepts Demonstrated

- Joins and Calculations
- Aggregate and Scalar Functions
- Stored Functions & Procedures
- Triggers with Conditions and Signals
- Common Table Expressions (CTEs)
- Recursive Queries with Depth Tracking
- Error Handling and Logic Branching

---

## 🌐 Environment

- SQL dialect: MySQL / MariaDB-compatible syntax
- Assumes database: `world_peace`
- Objects: `customer`, `merchandise_item`, `customer_order`, `customer_order_line_item`

---

## 📌 How to Use

1. Ensure your SQL server is compatible (e.g., MySQL 8.x).
2. Load schema and data into your database.
3. Run `project_10_advanced_databases_and_sql.sql` in your SQL IDE.
4. Test stored procedures, functions, and triggers with sample inputs.

---

## ✅ Example Queries

```sql
-- Call procedure to get customer list
CALL customer_roster_stp();

-- Use function to validate credit limit
SET @approved = check_credit('C000000001', 4000000);
SELECT @approved;

-- Insert a new line item and auto-trigger inventory validation
INSERT INTO customer_order_line_item
(customer_order_id, merchandise_item_id, quantity)
VALUES ("D000000003", "ITALYPASTA", 20);
