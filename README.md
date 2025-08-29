# Lightweight-DBMS-Engine

#### A Relational database model, data storage based on B+ tree indexing

## QUERIES SUPPORTED BY SYSTEM

1. SHOW Tables
2. CREATE Table
3. INSERT INTO Table
4. DISPLAY Table contents
5. SEARCH INTO Table
6. DROP Table

## SYSTEM DESIGN

The Database System is designed using C++ programming language.
It stores the data on physical disk using files.

Features of system include:

#### 1. Custom Blocks for each table:

The data is stored in blocks.

Benefits of block storage: [here](<https://en.wikipedia.org/wiki/Block_(data_storage)>)

All the separate row data of a particular table is stored in different file creating blocks of data. System reads as well as writes data back to files in blocks.

#### 2. B+ Tree Indexing:

A separate multilevel B+ tree is created for each table. Each node contains maximum of 50 entries. Right now data storage is based only on primary key, primary key can be INTEGER or VARCHAR. By default, first column is choosen as primary key.

#### 3. Storing Meta Data of Tables:

Meta Data of the tables are stored separately which provides quick access to several information like current number of records, table name, etc.

#### 4. Search:

##### 1. B+ Indexed Search

For searching a record in file for particular table, B+ tree indexed search is implemented. B+ indexed search is based on primary key

##### 2. Brute Force Search

For searching records without providing primary key from table, brute force search algorithm is implemented. You can display selected number of columns and limit results based on where clause(see section In Development below).

Advantages of B+ Tree Indexing [here](https://www.tutorialcup.com/dbms/b-plus-tree.htm)

System also calculates the time taken by the search algorithm.

## IN DEVELOPMENT:

For displaying the table contents, you have to select option 5 from menu and the queries supported by it are, do care about syntax, since complete parser is not implemented.

select \* from table_name;

select id,name from table_name;

select id,name from table_name where id = 1;
