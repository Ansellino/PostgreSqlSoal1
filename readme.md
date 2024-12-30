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
# 3. Practicing Where Statements
We are once again working with the phones table.

Write a query that will print the name and price of all phones that sold greater than 5000 units.

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
SELECT name, price
FROM phones
WHERE units_sold > 5000;
```

# 4. A More Challenging 'Where'
We are once again working with the phones table.

Write a query that will select the name and manufacturer for all phones created by Apple or Samsung

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
SELECT name, manufacturer
FROM phones
WHERE manufacturer = 'Apple' OR manufacturer = 'Samsung';
```

# 5. Trying Calculations in Where Clauses
We are once again working with the phones table.

Write a query that will print the name and total_revenue of all phones with a total_revenue greater than 1,000,000

Hints

Remember that total_revenue can be found by multiplying price and units_sold columns!

Don't forget to rename the column produced by price X units_sold to total_revenue using the AS operator

Only the calculation in the SELECT clause needs to be renamed, not the one in the WHERE clause.

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
SELECT name, price * units_sold AS total_revenue
FROM phones
WHERE price * units_sold > 1000000
```

# 6. Try Updating Records In a Table!
We are once again working with the phones table.

You are going to write two separate queries

The first query should update the units_sold of the phone with name N8 to 8543

The second query should select all rows and columns of the phones table

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
-- Write query here to update the 'units_sold' of the phone with name 'N8' to 8543
UPDATE phones
SET units_sold = 8543
WHERE name = "N8";


-- Write query here to select all rows and columns of the 'phones' table
SELECT * FROM phones;
```

# 7. Practice Deleting Records
We are once again working with the phones table.

You are going to write two separate queries

The first query should delete all phones that were created by Samsung

The second query should select all rows and columns of the phones table

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
-- Write your delete SQL here
DELETE FROM phones
WHERE manufacturer = "Samsung";

-- Write query here to select all rows and columns from phones
SELECT * FROM phones;
```

# 8. Creating and Using Foreign Keys
You are building a database for a naval shipping company.  You need to store a list of boats and the crew members who work on each, so you create a table called boats and a table called crew_members.  From the perspective of a boat, this is a one-to-many relationship.

To complete this design, you need to do two things:

Add a column to the crew_members table definition that will relate crew_members to boats.  You should call this foreign key column boat_id

Write a query that will fetch all columns for all crew_members associated with the boat that has an ID of 1.

**Answer**:
```bash
-- Create table called 'boats'
CREATE TABLE boats (
    -- Note that this environment doesn't support 'SERIAL' keyword
    -- so 'AUTOINCREMENT' is used instead. Postgres always uses 'SERIAL'
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name VARCHAR
);


-- Insert two boats 
INSERT INTO boats (name)
VALUES ('Rogue Wave'), ('Harbor Master');


-- Create table called 'crew_members'
CREATE TABLE crew_members (
    -- Note that this environment doenst support 'SERIAL' keyword
    -- so 'AUTOINCREMENT' is used instead. Postgres always uses 'SERIAL'
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    first_name VARCHAR,
    -- >>>>>>>> TODO #1 HERE!!!
    boat_id INTEGER REFERENCES boats(id)
);

-- Insert three crew members
INSERT INTO crew_members (first_name, boat_id)
VALUES ('Alex', 1), ('Lucia', 1), ('Ari', 2);


-- Write query here to fetch all columns for all crew_members associated with the boat that has an ID of 1
-- >>>>>>>> TODO #2 HERE!!!
SELECT *
FROM crew_members
WHERE boat_id = 1;
```

# 9. Practice Joining Data
You are designing a database for a book publishing company.  The database needs to store a table of authors and books. An author has many books.  This means that books should have a foreign key column that references an author.

Write a query that will join together these two tables.  For each book, print the title of the book and the name of the author.

Table definitions of authors

+----+-----------------+
| id | name            |
+----+-----------------+
| 1  | JK Rowling      |
+----+-----------------+
| 2  | Stephen King    |
+----+-----------------+
| 3  | Agatha Christie |
+----+-----------------+
| 4  | Dr Seuss        |
+----+-----------------+
Table definition of books

+----+--------------------+-----------+
| id | title              | author_id |
+----+--------------------+-----------+
| 1  | It                 | 2         |
+----+--------------------+-----------+
| 2  | Chamber of Secrets | 1         |
+----+--------------------+-----------+
| 3  | Cat and the Hat    | 4         |
+----+--------------------+-----------+
| 4  | Affair at Styles   | 3         |
+----+--------------------+-----------+

**Answer**:
```bash
SELECT title, authors.name
FROM books
JOIN authors ON authors.id = books.author_id;
```

# 10. Joins, Joins, Join!
You are still authoring a database for a book publisher.  The database has a table of authors and a table of books .

Write a query that will return the title of each book, along with the name of the author.  All authors should be included, even if they do not have a book associated with them.

Table of authors

+----+-----------------+
| id | name            |
+----+-----------------+
| 1  | Stephen King    |
+----+-----------------+
| 2  | Agatha Christie |
+----+-----------------+
| 3  | JK Rowling      |
+----+-----------------+
Table of books

+----+---------------------+-----------+
| id | title               | author_id |
+----+---------------------+-----------+
| 1  | The Dark Tower      | 1         |
+----+---------------------+-----------+
| 2  | Affair At Styles    | 2         |
+----+---------------------+-----------+
| 3  | Murder at the Links | 2         |
+----+---------------------+-----------+

**Answer**:
```bash
SELECT title, authors.name
FROM authors
LEFT JOIN books ON books.author_id = authors.id;
```

# 11. Three Way Exercise
Hmmm...I wonder if any authors are writing their own reviews for books! You are working with a database of books, authors, and reviews

Write a query that will return the title of each book, along with the name of the author, and the rating of a review.  Only show rows where the author of the book is also the author of the review.

Table of authors

+----+-----------------+
| id | name            |
+----+-----------------+
| 1  | Stephen King    |
+----+-----------------+
| 2  | Agatha Christie |
+----+-----------------+
| 3  | JK Rowling      |
+----+-----------------+
Table of books

+----+---------------------+-----------+
| id | title               | author_id |
+----+---------------------+-----------+
| 1  | The Dark Tower      | 1         |
+----+---------------------+-----------+
| 2  | Affair At Styles    | 2         |
+----+---------------------+-----------+
| 3  | Chamber of Secrets  | 3         |
+----+---------------------+-----------+
Table of reviews

+----+--------+-------------+---------+
| id | rating | reviewer_id | book_id |
+----+--------+-------------+---------+
| 1  | 3      | 1           | 2       |
+----+--------+-------------+---------+
| 2  | 4      | 2           | 1       |
+----+--------+-------------+---------+
| 3  | 5      | 3           | 3       |
+----+--------+-------------+---------+

**Answer**:
```bash
SELECT title, name, rating
FROM reviews
JOIN books ON books.id = reviews.book_id
JOIN authors ON authors.id = books.author_id AND authors.id = reviews.reviewer_id
```

# 12. Practice For Grouping and Aggregating
Back to books and authors!

Write a query that will print an author's id and the number of books they have authored.

Hint: all the information that you need for this is present on the books table.

An example of the authors table

+----+-----------------+
| id | name            |
+----+-----------------+
| 1  | JK Rowling      |
+----+-----------------+
| 2  | Stephen King    |
+----+-----------------+
| 3  | Agatha Christie |
+----+-----------------+
| 4  | Dr Seuss        |
+----+-----------------+
An example of the books table

+----+---------------------+-----------+
| id | title               | author_id |
+----+---------------------+-----------+
| 1  | Chamber of Secrets  | 1         |
+----+---------------------+-----------+
| 2  | Prisoner of Azkaban | 1         |
+----+---------------------+-----------+
| 3  | The Dark Tower      | 2         |
+----+---------------------+-----------+
| 4  | Murder At the Links | 3         |
+----+---------------------+-----------+
| 5  | Affair at Styles    | 3         |
+----+---------------------+-----------+
| 6  | Cat in the Hat      | 4         |
+----+---------------------+-----------+

**Answer**:
```bash
SELECT author_id, count(*)
FROM books
GROUP BY author_id;
```

# 13. Grouping With a Join!
This is the same exercise as the last one, but this time we want to print out some information from both tables!

Write a query that will print an author's name and the number of books they have authored.

Hint: all the information that you need for this is present on the books table.

An example of the authors table

+----+-----------------+
| id | name            |
+----+-----------------+
| 1  | JK Rowling      |
+----+-----------------+
| 2  | Stephen King    |
+----+-----------------+
| 3  | Agatha Christie |
+----+-----------------+
| 4  | Dr Seuss        |
+----+-----------------+
An example of the books table

+----+---------------------+-----------+
| id | title               | author_id |
+----+---------------------+-----------+
| 1  | Chamber of Secrets  | 1         |
+----+---------------------+-----------+
| 2  | Prisoner of Azkaban | 1         |
+----+---------------------+-----------+
| 3  | The Dark Tower      | 2         |
+----+---------------------+-----------+
| 4  | Murder At the Links | 3         |
+----+---------------------+-----------+
| 5  | Affair at Styles    | 3         |
+----+---------------------+-----------+
| 6  | Cat in the Hat      | 4         |
+----+---------------------+-----------+

**Answer**:
```bash
SELECT authors.name, COUNT(*)
FROM books
JOIN authors ON authors.id = books.author_id
GROUP BY authors.name;
```

# 14. Practice Yourself Some Having
You are trying to find the phone manufacturers with the greatest revenue from selling phones.

Given a table of phones, print the names of manufacturers and total revenue (price * units_sold) for all phones.  Only print the manufacturers who have revenue greater than 2,000,000 for all the phones they sold.

Hints:

From the problem statement, it looks like you don't need to filter down any of the initial rows. That means you probably won't have to use the WHERE keyword!

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
SELECT manufacturer, SUM(price * units_sold) 
FROM phones
GROUP BY manufacturer
HAVING SUM(price * units_sold) > 2000000;
```

# 15. Group By Review
Let's get more familiar with the E-Commerce dataset.

Write a query to print the number of paid and unpaid orders.

The result should look something like this:

+-------+-------+
| paid  | count |
+-------+-------+
| true  | 4     |
+-------+-------+
| false | 2     |
+-------+-------+
Hints:

You should only need to use the orders table

Maybe the GROUP BY and COUNT keywords would be useful!

For reference, here is an example of the orders table:

+----+---------+------------+-------+
| id | user_id | product_id | paid  |
+----+---------+------------+-------+
| 1  | 1       | 3          | true  |
+----+---------+------------+-------+
| 2  | 3       | 3          | false |
+----+---------+------------+-------+
| 3  | 5       | 5          | true  |
+----+---------+------------+-------+
| 4  | 1       | 4          | true  |
+----+---------+------------+-------+
| 5  | 4       | 2          | false |
+----+---------+------------+-------+
| 6  | 2       | 1          | true  |
+----+---------+------------+-------+

**Answer**:
```bash
SELECT paid, COUNT(*)
FROM orders
GROUP BY paid;
```

# 16. Inner Join Review
Join together the users and orders tables.  Print the first_name and last_name of each user, then whether or not they have paid for their order.

Hints:

Remember that to join two tables, we use something like JOIN orders ON orders.user_id = users.id

A user might have more than one order, so they might show up twice!  That is OK - we want to see each of their orders.

Reminder on the structure of the orders table:

+----+---------+------------+-------+
| id | user_id | product_id | paid  |
+----+---------+------------+-------+
| 1  | 1       | 3          | true  |
+----+---------+------------+-------+
| 2  | 3       | 3          | false |
+----+---------+------------+-------+
| 3  | 5       | 5          | true  |
+----+---------+------------+-------+
| 4  | 1       | 4          | true  |
+----+---------+------------+-------+
| 5  | 4       | 2          | false |
+----+---------+------------+-------+
| 6  | 2       | 1          | true  |
+----+---------+------------+-------+
Reminder on the structure of the users table:

+----+------------+-----------+
| id | first_name | last_name |
+----+------------+-----------+
| 1  | Iva        | Lindgren  |
+----+------------+-----------+
| 2  | Ignatius   | Johns     |
+----+------------+-----------+
| 3  | Jannie     | Boehm     |
+----+------------+-----------+
| 4  | Neal       | Wehner    |
+----+------------+-----------+
| 5  | Mikayla    | Casper    |
+----+------------+-----------+
| 6  | Patience   | Stracke   |
+----+------------+-----------+

**Answer**:
```bash
SELECT first_name, last_name, paid
FROM users
JOIN orders ON orders.user_id = users.id
```

# 17. Sorting, Offsetting, and Limiting
Write a query that shows the names of only the second and third most expensive phones.

For reference, here is the phones table:

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
SELECT name
FROM phones
ORDER BY price DESC
LIMIT 2
OFFSET 1;
```

# 18. Merging Results with Union
Write a query that will print the manufacturer of phones where the phone's price is less than 170.  Also print all manufacturer that have created more than two phones.

IMPORTANT: You don't need to wrap each query with parenthesis! Your solution should not have any parens in it.

Hint:

To find the manufacturers who have created more than two phones, you can group by manufacturer then apply a 'HAVING' filter to only consider groups with a COUNT(*) > 2

For reference, here is the phones table:

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
SELECT manufacturer
FROM phones
WHERE price < 170
UNION 
SELECT manufacturer
FROM phones
GROUP BY manufacturer
HAVING COUNT(*) > 2;
```

# 19. Embedding in Select
Write a query that prints the name and price for each phone.  In addition, print out the ratio of the phones price against max price of all phones (so price / max price).  Rename this third column to price_ratio

The result should look something like this. (Only one row is shown, there should be one row for each phone)

+-------+-------+-------------+
| name  | price | price_ratio |
+-------+-------+-------------+
| N1280 | 199   | .498        |
+-------+-------+-------------+
For reference, here is the phones table:

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
SELECT name, price, price / (SELECT max(price) FROM phones) AS price_ratio
FROM phones;
```

# 20. Subquery From's
Calculate the average price of phones for each manufacturer.  Then print the highest average price. Rename this value to max_average_price

For reference, here is the phones table:

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
SELECT MAX(p.avg_price) AS max_average_price
FROM (
    SELECT AVG(price) AS avg_price
    FROM phones
    GROUP BY manufacturer
) AS p;
```

# 21. Subquery Where's
Write a query that prints out the name and price of phones that have a price greater than the Samsung S5620 Monte.

For reference, here is the phones table:

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
SELECT name, price
FROM phones
WHERE price > ( SELECT price FROM phones WHERE name = 'S5620 Monte');
```

# 22. Practice Your Subqueries!
Write a query that prints the name of all phones that have a price greater than all phones made by Samsung.

For reference, here is the phones table:

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
SELECT name
FROM phones
WHERE price > ALL (
    SELECT price
    FROM phones
    WHERE manufacturer = 'Samsung'
);
```

# 23. From-less Selects
Using only subqueries, print the max price, min price, and average price of all phones.  Rename each column to max_price, min_price, avg_price

The result should look something like this:

+-----------+-----------+-----------+
| max_price | min_price | avg_price |
+-----------+-----------+-----------+
| ...       | ...       | ...       |
+-----------+-----------+-----------+
For reference, here is the phones table:

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
SELECT (
    SELECT MAX(price)
    FROM phones
) AS max_price,( SELECT MIN(price)
    FROM phones
) AS min_price,( SELECT AVG(price)
    FROM phones
) AS avg_price;
```

# 24. Some Practice with Distinct
Write a query that will print the number of unique phone manufacturers.

For reference, here is the phones table:

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
SELECT COUNT(DISTINCT manufacturer)
FROM phones;
```

