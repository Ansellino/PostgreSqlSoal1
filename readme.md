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