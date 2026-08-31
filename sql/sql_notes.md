#What is SQL\
SQL (Structured Query Language) is a structured language used to query, manipulate, and transform data from relational databases

A relational database is a collection of related (2D) tables of named columns and numbers of rows of data

##Learning SQL \
This markdown file is be where I note down things that I have learned, acting as a diary and summary of commands/queries
To begin with, SQLBolt (https://sqlbolt.com/) will be the primary starting off point. 

#Commands 

SELECT col1,col2 FROM table 
INNER JOIN another_table
	on table.id = another_table.id
WHERE condition1
	AND/OR condition2
ORDER BY col ASC/DESC
LIMIT num_limit OFFSET num_offset	

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
