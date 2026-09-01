#What is SQL\
SQL (Structured Query Language) is a structured language used to query, manipulate, and transform data from relational databases

A relational database is a collection of related (2D) tables of named columns and numbers of rows of data

##Learning SQL \
This markdown file is be where I note down things that I have learned, acting as a diary and summary of commands/queries
To begin with, SQLBolt (https://sqlbolt.com/) will be the primary starting off point. 

#Complete SELECT query

SELECT DISTINCT column, AGG_FUNC(column_or_expression), …
FROM mytable
    JOIN another_table
      ON mytable.column = another_table.column
    WHERE constraint_expression
    GROUP BY column
    HAVING constraint_expression
    ORDER BY column ASC/DESC
    LIMIT count OFFSET COUNT;

#Day 1 - 29 Aug 2026\
Finished Lessons 1-5 on SQLBolt

What I have learnt:
1. What SQL is
2. Select queries and its constraints

#Day 2 - 31 Aug 2026
Aim: At least get to Lesson 9: Queries with Expressions

##Lesson 6: Multi-table queries with JOIN
Data normalisation:
Real-life data is broken into pieces and distributed among orthogonal tables
Allows data to grow independently of each other
Tables that share information about entries have to have a primary key that identifies the entity uniquely across tables 
Auto-incrementing integer is most common, but can be hashed value, string, as long as its unique
After joining the tables then apply conditions

##Lesson 7: Outer Join
Resulting table from inner join will only have entries that is in both tables
For assymetric data you need to use a LEFT JOIN, RIGHT JOIN or FULL JOIN
For two tables Table A and B:
LEFT JOIN includes all rows from A regardless if a match is found in B 
RIGHT JOIN is the opposite
FULL JOIN means rows from both tables are kept

##Lesson 8: NULLs
Always best to reduce NULL values as they need special attention when constraining
Alternatively can create data-type appropriate default values such as 0 for numerical data or empty strings
Can select for or not in where using

WHERE column IS/IS NOT NULL

##Lesson 9: Expressions
You can use expressions to write more complex column values in a query
Modulo operator works in SQL

##Lesson 10&11: Aggregates
SQL also supports aggregate expressions or functions 
COUNT(*)/COUNT(column)
MIN()
MAX()
AVG()
SUM()

Also supports 
GROUP BY column
- Group by is set after where, so to filter after group by HAVING is used
HAVING another_condition;

#Day 3 - 1 Sep 2026
Aim: To Finish the Beginners Lessons on SQL Bolt

##Order of Execution
Each part of a query is executed sequentially:
1. FROM and JOIN
2. WHERE
3. GROUP BY
4. HAVING
5. SELECT
6. DISTINCT
7. ORBER BY
8. LIMIT/OFFSET

##Inserting/Updating Rows

A database Schema describes the structure of the table and the datatypes that it contains

INSERT INTO mytable
(column, another_column, …)
VALUES (value_or_expr, another_value_or_expr, …),
      (value_or_expr_2, another_value_or_expr_2, …),

UPDATE mytable
SET column = value_or_expr, 
    other_column = another_value_or_expr, 
    …
WHERE condition;

It is recommended that a SELECT query is run first (to constrain which row to update) before actually running UPDATE

##Deleting Rows
DELETE FROM mytable
WHERE condition;

the WHERE condition dictates which row to delete, if left out ALL rows are removed

##Creating tables
CREATE TABLE IF NOT EXISTS mytable (
    column DataType TableConstraint DEFAULT default_value,
    another_column DataType TableConstraint DEFAULT default_value,
    …
);

IF NOT EXISTS clause supresses an error if that table doesn't exist

##Altering and Dropping Tables

ALTER TABLE mytable
ADD column DataType OptionalTableConstraint
	DEFAULT default_value;
	
DROP column_to_be_deleted;

RENAME TO new_table_name;
	
DROP TABLE IF EXISTS mytable;
Drop table is not the same as delete as dropping also removes the table schema too

#SQLBolt Completed
Next steps to learning SQL: 
1. Read Up on some Intermediate SQL on ToughSpot, start on SQL Analytics training on ToughSpot
2. Install PostgreSQL
