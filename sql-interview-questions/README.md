# SQL Interview Practice Dataset

A small online-store dataset for practicing SQL interview questions. It's used in the post
[SQL and Data Science Interview Questions: A Practical Guide to Practice and Preparation](https://victorhugosolis.com/posts/sql-data-science-interview-questions-practice-guide/).

## Tables

| Table | Rows | Description |
|---|---|---|
| `customers` | 25 | Customers, their city, and when they signed up |
| `products` | 16 | Products with a category and price |
| `orders` | 60 | Orders placed by customers, with a status (`completed`, `cancelled`, `pending`) |
| `order_items` | 99 | The products and quantities in each order |

Relationships:

- `orders.customer_id` → `customers.customer_id`
- `order_items.order_id` → `orders.order_id`
- `order_items.product_id` → `products.product_id`

## Files

- `customers.csv`, `products.csv`, `orders.csv`, `order_items.csv` — the data as CSV files
- `setup.sql` — creates the four tables and inserts all the data (SQLite, PostgreSQL, MySQL 8+)
- `store.db` — a ready-to-use SQLite database

## Quick start

SQLite (no server needed):

```bash
sqlite3 store.db
```

Or build the database from scratch:

```bash
sqlite3 store.db < setup.sql        # SQLite
psql -d mydb -f setup.sql           # PostgreSQL
mysql mydb < setup.sql              # MySQL 8+
```
