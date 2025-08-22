---
title: "Database Concepts Part II"
date: 2020-06-08T06:00:23+06:00
hero: /images/posts/writing-posts/analytics.svg
description: Database Concepts
theme: Toha
menu:
  sidebar:
    name: Database Concepts Part II
    identifier: database-concepts-2
    parent: oracle-database
    weight: 500
---

As a continuation for the previous post, [Database Concepts Part I](https://sandeepnarayankv.github.io/Database_Concepts_1.html), we are going to discuss further on the database concepts.

### **Schema Objects**

Independence of physical storeage from logical data structures is a characteristic of RDBMS. Database Schema is a collection of logical data structures or Schema objects & is owned by DB User. Schema objects are user created structures which refer to the data in the database,

Few of the schema objects are

1. Tables - Stores data in rows, the most important schema object.
2. Indexes - Schema object that helps fast access of rows. It maintains an entry for each indexed table or table cluster.
3. Partitions - Pieces of large tables or indexes.
4. Views - Stored queries or custom presentation of data in one or more tables. Stores no Data.
5. Sequences - Used to generate integers, typically for Primary Keys.
6. Dimensions - Defines parent child relations between pairs of column sets where all the columns of a column set come from same table.
7. Synonyms - alias for another schema object. it requires no storage other than definition in data dictionary.
8. PL/SQL Subprograms & Packages - PL/SQL objects which can be stored on a schema. eg.: Packages, Procedures, Functions, Triggers etc.
9. DB Links - enables you to access schema objects on another Database.

### **Non Schema Objects**

Objects which are not stored in a DB Schema. eg.: Directories, Roles, Table Spaces, Users etc.

### **Structured Query Language (SQL)**

A set based **_declarative non procedural language_** providing interface to RDBMS used to describe **_what should be done_** unlike procedural languages which describe how it is done.

SQL helps to,

- Query data (DQL Commands)
- insert, update & delete Data (DML Commands)
- Create, replace, alter, drop Database objects (DDL Commands)
- Control access to Database objects (DCL Commands)
- Maintains/guarantees data consistency and integrity

### **Data Definition Language (DDL)**

Used to define database schema. used to create, modify or delete structure of schema objects. These commands are auto committed and will save to database permanently.
The main commands are

- **CREATE** - used to create schema objects

eg.:

```
 CREATE TABLE employee
  (
     name  VARCHAR2(20),
     email VARCHAR2(100),
     dob   DATE
  );
```

- **DROP** - used to delete schema objects

eg.:

```
 DROP TABLE employee;
```

- **ALTER** - used to alter the structure of schema objects

eg.:

```
 ALTER TABLE employee
  ADD (address VARCHAR2(20));

 ALTER TABLE employee
  MODIFY (name VARCHAR2(40));
```

- **TRUNCATE** - used to remove all records from a table.

eg.:

```
 TRUNCATE TABLE employee;
```

- **COMMENT** - used to add comment to data dictionary.

eg.:

```
-- Single Line Comment
/*
This is a
Multi Line Comment
*/
 TRUNCATE TABLE employee;
```

- **RENAME** - used to rename a schema object.

eg.:

```
 ALTER TABLE employee
  RENAME COLUMN name TO full_name;
```

### **Data Query Language (DQL)**

Used to fetch/query data from the database. Only one command **SELECT** is used. Conditions are defined by **WHERE**

eg.:

```
 SELECT origin,
       dest,
       time_dep
FROM   passengers
WHERE  origin = 'pa';
```

### **Data Manipulation Language (DML)**

SQL Commands used for manipulation of data present in database.DML is not auto committed and cannot save the changes permanently. This can be rolledback.

- **INSERT** - used to insert data into a table.

eg.:

```
INSERT INTO employee
            (full_name,
             email,
             dob,
             address)
VALUES      ('Sonoo',
             'abc@me.com',
             '06-APR-2010',
             '11, Newyork');
```

- **UPDATE** - used to update data in a table.

eg.:

```
UPDATE employee
SET    full_name = 'Sandeep'
WHERE  full_name = 'Sonoo';
```

- **DELETE** - used to delete data from table.

eg.:

```
DELETE FROM employee
WHERE  full_name = 'Sonoo';
```

### **Data Control Language (DCL)**

SQL Commands used for grant & revoke rights & permissions to database systems & objects.

- **GRANT** - used to give users privilages to database systems & objects.

eg.:

```
 GRANT SELECT, UPDATE ON employee TO sandeep, raj;
```

- **REVOKE** - used to revoke or takeback privilages to database systems & objects from an user.

eg.:

```
 REVOKE SELECT, UPDATE ON employee TO sandeep, raj;
```

### **Transaction Control Language (TCL)**

SQL Commands used to deal with Transactions within a database. These commands are used with DML commands to automatically commit or rollback transactions. They auto commit and cannot be reverted.

- **COMMIT** - used to save/commit transactions.

eg.:

```
 COMMIT;
```

- **ROLLBACK** - used to revert/rollback a transaction in case of failures or errors.

eg.:

```
 ROLLBACK;
```

- **SAVEPOINT** - used to set savepoint within a transaction.

eg.:

```
 SAVEPOINT SAVEPOINT_NAME;
```

- **SET TRANSACTION** - used to specify charecteristics of a transaction. Used to establish the current transaction as read-only or read/write, establish its isolation level, assign it to a specified rollback segment, or assign a name to the transaction.

eg.:

```
 SET TRANSACTION READ ONLY name 'Bangalore';
```

### **PL/SQL & Java**

PL/SQL is a procedural extention of SQL helping to control the flow of SQL Statements, use variables & error handling. It helps to store Application logic in Database.

A stored procedure can be created using Java which can be called from PL/SQL & vice versa.

Regards,<br>
Sandeep
