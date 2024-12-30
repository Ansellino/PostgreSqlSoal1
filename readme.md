# 1. Create, Insert, and Select!
Let's practice creating a table and inserting data into it.

The SQL you see below creates a new table called movies and inserts two rows into it.

Goal

Write a SELECT statement to retrieve both rows inserted into the movies table.  Select both the title column and the box_office column.

**Answer**:
```bash
-- You don't need to change these lines
CREATE TABLE movies (
    title VARCHAR(60),
    box_office INTEGER
);

INSERT INTO movies (title, box_office)
VALUES 
    ('The Avengers', 1500000000),
    ('Batman v Superman', 873000000);
    
-- WRITE YOUR SOLUTION BELOW THIS LINE!
SELECT * FROM movies;
```

# 2. Using Calculated Columns
Take a look at the following table called phones. This table has already been inserted into the database for you.

Write a query that will select the name of each phone and calculate the total revenue for each phone (price X units_sold)

Rename this calculated column to revenue

+-------------+--------------+-------+------------+
| name        | manufacturer | price | units_sold |
+-------------+--------------+-------+------------+
| N1280       | Nokia        | 199   | 1925       |
+-------------+--------------+-------+------------+
| Iphone 4    | Apple        | 399   | 9436       |
+-------------+--------------+-------+------------+
| Galaxy S    | Samsung      | 299   | 2359       |
+-------------+--------------+-------+------------+
| S5620 Monte | Samsung      | 250   | 2385       |
+-------------+--------------+-------+------------+
| N8          | Nokia        | 150   | 7543       |
+-------------+--------------+-------+------------+
| Droid       | Motorola     | 150   | 8395       |
+-------------+--------------+-------+------------+
| Wave S8500  | Samsung      | 175   | 9259       |
+-------------+--------------+-------+------------+

**Answer**:
```bash
-- Write your SQL here to find the name and revenue for each phone
SELECT name, price * units_sold AS revenue
FROM phones
```
