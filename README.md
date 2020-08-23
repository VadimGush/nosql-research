# NoSQL Research

## Table of contents

 1. Introduction
 1. Structures
    1. SQL tables
    2. NoSQL data structures
 2. Performance
    1. Column-oriented and row-oriented
    2. X-oriented
 3. Infrastructure
    1. Introduction to the problem
    2. SQL solutions
    3. No-SQL solutions
 
# Introduction

In this article I will try to compare two types of modern databases: SQL and NoSQL. I divived this article by chapters, one of which describes one particular characteristic of a database. There are 3 chapters: structures, performance, infrastracture. In every chapter I will try to explain main advantages and drawbacks of each particular type of database without too much details. Database design is a very hard subject and due to the fact that we're just applicable software engineers, we'll look at different databases only in high-level.

For comparasion I choose PostgreSQL as a SQL database and MongoDB as a NoSQL databases. Of course, I will mention more NoSQL databases because they have so much variations of structures and architectures, that it will be biased to compare SQL with only one of them.

# Structures

## Complexity

Different structures have different advantages and drawbacks. And it's not just performance and memory layout. Let's use graph as an example. This data structure is very effective for different kinds of problems like maps or object dependencies. But most of the time these structures are created or handled primarily by machines. It's very hard for human to manage big graphs with hight amount of edges (which represent connection) and verticies (which represent nodes, objects and etc.). Therefore, when we are talking about database structures we also need to pay attention to their complexity (like code complexity).

When developer is making changes to database, he should understand overall structure in order to modify it quickly and without introducing additional complexity. For example: let's suppose that you have SQL database that stores paychecks. Your database contains 20+ tables. 10 tables for paychecks where every table contains set of paychecks of different type: `dev_division_paychecks`, `qa_division_paychecks`, `design_division_paychecks` and etc.. And 10+ additional tables for cases when some particular division have some unique payment position like `devlead_bonus` or `mentorship_bonus`. As a result you have most horrible structure of your data 


# References

 1. "Distributed Systems in One Lesson" by Tim Berglund [https://youtu.be/Y6Ev8GIlbxc]
 2. "CS50 Lecture" by Mark Zuckerberg [https://youtu.be/xFFs9UgOAlE]
 3. "SQL Queries For Mere Mortals" by John Viescas, Michael J. Hernandez [https://www.amazon.com/SQL-Queries-Mere-Mortals-Hands/dp/0321992474/]
