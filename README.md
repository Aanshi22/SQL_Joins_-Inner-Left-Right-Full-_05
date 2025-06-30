# SQL_Joins_-Inner-Left-Right-Full-_05
# JOIN operations using a sample E-commerce dataset 

This project demonstrates the use of various SQL JOIN operations (`INNER`, `LEFT`, `RIGHT`, and `FULL OUTER`) using a simple yet realistic **Customer-Order** relationship within an E-commerce domain.

The project includes:
- SQL scripts for JOIN queries
- A relational schema (ER Diagram)
- Query outputs as CSVs
- A `.mwb` file to visualize/edit in MySQL Workbench

---

## Project Structure

| File Name                                           | Description |
|----------------------------------------------------|-------------|
| `Customer_and_order_for_SQL_JOIN_OPERTION.mwb`     | MySQL Workbench file (ER model) |
| `SQL_JOINS.sql`                                    | SQL code demonstrating all types of JOINs |
| `ER_Diagram.png`                                   | Visual representation of the ER model |
| `ER_Diagram_customer_and_order.png`                | Clean alternative ER diagram for documentation |
| `Result_inner_join.csv`                            | Output of `INNER JOIN` query |
| `Result_left_join.csv`                             | Output of `LEFT JOIN` query |
| `Result_right_join.csv`                            | Output of `RIGHT JOIN` query |
| `Result_FULL_OUTER_JOIN_(Simulated).csv`           | Simulated `FULL OUTER JOIN` output using `UNION` |

---

## SQL JOINs Covered

### INNER JOIN
Returns records that have matching values in both tables.

### LEFT JOIN
Returns all records from the left table (Customer), and the matched records from the right table (Order).

### RIGHT JOIN
Returns all records from the right table (Order), and the matched records from the left table (Customer).

### FULL OUTER JOIN (Simulated)
Returns all records when there is a match in either table using `UNION` of `LEFT JOIN` and `RIGHT JOIN`.

---

## Learning Outcomes

- Understand the structure of relational data
- Write effective SQL JOIN queries
- Interpret real-world E-commerce data
- Use ER diagrams for modeling relationships
- Analyze join results in `.csv` format

---

## Tools Used

- **MySQL Workbench** – For schema design and SQL execution
- **DB Fiddle / SQLiteStudio** – For quick testing
- **GitHub** – For version control and collaboration

---

## Sample SQL Snippet

sql
-- INNER JOIN between Customer and Order
`` 
SELECT c.customer_id, c.name, o.order_id, o.order_date
FROM CustomerLite c
INNER JOIN OrderLite o
ON c.customer_id = o.customer_id;``
-- LEFT JOIN between Customer and Order
`` 
SELECT 
    c.customer_id, 
    c.name, 
    o.order_id, 
    o.order_date
FROM CustomerLite c
LEFT JOIN OrderLite o
    ON c.customer_id = o.customer_id; ``
-- RIGHT JOIN between Customer and Order
`` 
SELECT 
    c.customer_id, 
    c.name, 
    o.order_id, 
    o.order_date
FROM CustomerLite c
RIGHT JOIN OrderLite o
    ON c.customer_id = o.customer_id; ``
-- FULL OUTER JOIN (simulated using UNION)
```
SELECT 
    c.customer_id, 
    c.name, 
    o.order_id, 
    o.order_date
FROM CustomerLite c
LEFT JOIN OrderLite o
    ON c.customer_id = o.customer_id

UNION

SELECT 
    c.customer_id, 
    c.name, 
    o.order_id, 
    o.order_date
FROM CustomerLite c
RIGHT JOIN OrderLite o
    ON c.customer_id = o.customer_id; ```
