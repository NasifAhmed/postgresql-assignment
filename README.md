## What is PostgreSQL?

PostgreSQL is an open source relational databse management system. It was developed by Michael Stonebraker and his team at the University of California, Berkeley and was sponsored by DARPA. It was a follow-up development to the Ingres database system. It supports standard SQL with minor differneces with other relational databases like Microsoft's SQL server or MySQL. It is currently the most widely used RDMBS because of its open source nature, rich and advaced features and scalability

## What is the purpose of a database schema in PostgreSQL?

Schemes are very useful in postgresql. It helps us divide all our tables into groups that hold its own tables, functions and views. It helps us to organize, manage and structure out database so we can better understand and manage all out tables. It makes our database modular and isolate meaningful tables in its own group or scheme. It also helps us do better access and permission controls.

## What is the difference between the VARCHAR and CHAR data types?

VARCHAR and CHAR both are data types of postgresql that stores strings. The difference between them is that when we delcare a CHAR type with its size, postgresql fills up the empty bytes of the data with white spaces. So many bytes can be wasted here if we don't fill up the CHAR type's size. On the contrary VARCHAR is varialbe character meaning the ununsed bytes are not wasted with white spaces rather postgresql shifts the next data in the empty spaces so no space is wasted. VARCHAR is compact while CHAR is not.

## Explain the purpose of the WHERE clause in a SELECT statement.

WHERE clause in postgresql is used to filter table based on condition and filter which records to include in the result set. Its a very useful and powerful function to filter out queries based on any condition.
Basic Syntax :

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

Examples of filtering using WHERE

```sql
-- Get users older than 25
SELECT name, age FROM users WHERE age > 25;

-- Get orders from a specific date
SELECT * FROM orders WHERE order_date = '2025-05-26';

-- Get products in a price range
SELECT name, price FROM products WHERE price BETWEEN 10.00 AND 50.00;
```

## What are the LIMIT and OFFSET clauses used for?

LIMIT and OFFSET clauses in postgresql are used to select portions of the table we want to see after selecting. LIMIT limits the rows in result set to its given number. For example LIMIT 10 will only show first 10 records. On the other hand OFFSET skips the number of records we give it. For example OFFSET 10 will skip the first 10 records and show the rest of the records.

Examples of LIMIT :

```sql
-- Get only the first 10 users
SELECT * FROM users LIMIT 10;

-- Get top 5 highest-priced products
SELECT name, price FROM products
ORDER BY price DESC
LIMIT 5;

-- Get 3 most recent orders
SELECT * FROM orders
ORDER BY order_date DESC
LIMIT 3;
```

Examples of OFFSET :

```sql
-- Skip first 20 rows, return the rest
SELECT * FROM products OFFSET 20;

-- Skip first 5 users
SELECT * FROM users
ORDER BY username
OFFSET 5;
```
