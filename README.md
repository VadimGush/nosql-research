# NoSQL Research

## Table of contents

 1. Introduction
 1. Structures
    1. Complexity
    1. SQL Model
    2. NoSQL Data Structures
 2. Operations on data
    1. SQL
    2. NoSQL
 2. Performance
    1. Column-oriented and Row-oriented
    2. X-oriented
 3. Infrastructure
    1. Introduction To The Problem
    2. SQL Solutions
    3. NoSQL Solutions
 4. Don't Say "NoSQL"
 
# Introduction

In this article I will try to compare two types of modern databases: SQL and NoSQL. I divived this article by chapters, one of which describes one particular characteristic of a database. There are 3 main chapters: structures, performance, infrastracture. In every chapter I will try to explain main advantages and drawbacks of each particular type of database without too much details. Database design is a very hard subject and due to the fact that we're just applicable software engineers, we'll look at different databases only in high-level.

For comparasion I choose PostgreSQL as a SQL database and MongoDB as a NoSQL databases. Of course, I will mention more NoSQL databases because they have so much variations of structures and architectures, that it will be biased to compare SQL with only one of them.

# Structures

## Complexity

Different structures have different advantages and drawbacks. And it's not just performance and memory layout. Let's use graph as an example. This data structure is very effective for different kinds of problems like maps or object dependencies. But most of the time these structures are created or handled primarily by machines. It's very hard for human to manage big graphs with hight amount of edges (which represent connection) and verticies (which represent nodes, objects and etc.). Therefore, when we are talking about database structures we also need to pay attention to their complexity (like code complexity).

When developer is making changes to database, he should understand overall structure in order to modify it quickly and without introducing additional complexity. For example: let's suppose that you have SQL database that stores paychecks. Your database contains 20+ tables. 10 tables for paychecks where every table contains set of paychecks of different type: `dev_division_paychecks`, `qa_division_paychecks`, `design_division_paychecks` and etc.. And 10+ additional tables for cases when some particular division have some unique payment position like `devlead_bonus` or `mentorship_bonus`. As a result you have the most horrible structure of your data which very hard to maintain because its complexity is very high. 

You may say that we should blame database administrator for this problem. And yes, we should. But there are some cases when your structure is very clear and scalable on paper. But when you start to implement it, you noticed that complexity goes up very rapidly. If your data structure is a graph with high amount of many-to-many relationships, your SQL database will force you to create one more additional table for storing connections. It may sound like a not a big deal, but with adding new models you will realizie that 30% of your tables is just linking data. And queries also will be affected by this and you will be forced to run a lot of `JOIN` across big amount of tables.

So, by now we have two types of complexity: **complexity introduced by user** and **complexity introduced by the database choice**. Second type will be a very big problem if structure of your data (mental model) differs from database structure. And this is what we want to prevent in the first place. If you're application treats data in terms of documents, then you should choose document-oriented DB. If your application needs just key-value storage, then you should choose key-value DB. And it doesn't matter what type of database (SQL or NoSQL) it will be. Just **use database that designed for your particular structure or model**.

## SQL model

 > What is SQL and how it used  
 > Why SQL so popular  
 > Why we shouldn't treat SQL as before
 

# References

 1. "Distributed Systems in One Lesson" by Tim Berglund [https://youtu.be/Y6Ev8GIlbxc]
 2. "CS50 Lecture" by Mark Zuckerberg [https://youtu.be/xFFs9UgOAlE]
 3. "SQL Queries For Mere Mortals" by John Viescas, Michael J. Hernandez [https://www.amazon.com/SQL-Queries-Mere-Mortals-Hands/dp/0321992474/]
