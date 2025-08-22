---
title: "Database Concepts Part I"
date: 2020-06-08T06:00:23+06:00
hero: /images/posts/writing-posts/analytics.svg
description: Database Concepts
theme: Toha
menu:
  sidebar:
    name: Database Concepts Part I
    identifier: database-concepts-1
    parent: oracle-database
    weight: 500
---

An overview of the basic Database Concepts is what I could think of as a fitting initial post. as the post will be long even if it is just an overview, hence i have decided to split the post into two. This is the part I and I will publish the [Part II](https://sandeepnarayankv.github.io/Database_Concepts_2.html) soon.

When we talk about Database Concepte the best place to start is Data.

### **What is Data?**

According to Oxford Dictionary Data could be defined as "**_facts and statistics collected together for reference or analysis_**"

In the digital world, we can mention data as "**_distinct pieces of information, usually formatted and stored in a way that is concordant with a specific purpose_**".

### **What is Database?**

Oracle defines Database as "**_an organized
collection of information treated as a unit_**" whose purpose is to **_collect, store and retrive information_**.

I prefer a slightly more elaborate definition especially from a tech prespective, I would define Database as an **Information System, used to Store, Access, Retrive & Manipulate data**.

### **Database Management Systems (DBMS)**

A database application is software program that inteacts with the database to access & manipulate data stored in it.

A DBMS is a database application that controls the **storage, organization and processing (Retrieval & Manipulation)** of the data.

There are multiple types of DBMS Systems, the major ones are,

1. **Hierarchical DBMS** - resembles a tree structure, each parent has one or more childs. An Operting system file structure is a good example. Follows One to Many relationships (1 Parent, Multiple Childs. 1 Child, 1 Parent)

2. **Network DBMS** - Similar to Hierarchical DBMS, but follows Many to Many relationships (1 Parent, Multiple Childs. 1 Child, Multiple Parents).

3. **Object Oriented DBMS** - Information is represented as Objects with relationships between Objects. Similar to Object Oriented Program Languages.

4. **NO-SQL** - A popular alternative to relational databases, NoSQL databases take a variety of forms and allow you to store and manipulate large amounts of unstructured and semi-structured data. Popular example is MongoDB.

5. **Relational DBMS** - The most popular DBMS System, based on relational model, generally includes an SQL Engine. This will be discussed in detail below.

### **Relational Model**

First Described by Edgar F. Codd in 1969, the relational model for databases is an approach for managing data using **Structure** (Well-defined objects store or access the data of a database), **Operations** (Clearly defined actions enable applications to manipulate the data and structures of a database) and **Integrity Rules** (govern operations on the data and structures of a database) consistant with [**_first-order predicate logic_**](https://en.wikipedia.org/wiki/First-order_logic) (a collection of formal systems used in mathematics, philosophy, linguistics, and computer science) where all data is represented in terms of tuples, grouped into relations.

### **Relational Databases**

A database organized as per the Relational model is a relational database. a relational database stores data in a set of relations (Tables)

**Table** is a two diamentional representation of rows (tuples) & columns (Attributes).

**Relations** are stored in Relational databases as Tables. Relations are a collection of Tables.

**Tuple** is an unordered set of Attributes and represents a row of a table and a single record in a relation.

**Attribute** is defined to store only one type of value. eazch row/tuple will have multiple attribute. Attribute is also know as Column.

### **Relational DBMS (RDBMS)**

**R**elational **D**ata**B**ase **M**anagement **S**ystems is a program that allows us to create, fetch, delete, and update a relational database. The guiding principle for RDBMS system is that he values of each table are related to others and can handle huge volumes of data.

Relational Database Management Systems maintains data integrity by simulating the following features:

- Entity Integrity: Two records of the database table can never be completely duplicate.
- Referential Integrity: Only the rows of those tables can be deleted which are not used by other tables as it will lead to data inconsistency.
- User-defined Integrity: Rules defined by the users based on confidentiality and access.
- Domain integrity: The columns of the database tables are enclosed within some structured limits, based on default values, type of data or ranges.

Major Characteristics of RDBMS systems are:

- Data should be represented in tables, with values in columns within rows.
- Unique data in a row/tuple. No duplicate rows.
- Tables are related using foreign keys
- Data within a column must be accessible by specifying the table name, the column name, and the value of the primary key of the row.
- The DBMS must support missing and inapplicable information in a systematic way, distinct from regular values and independent of data type.
- The DBMS must support an active on-line catalogue.
- The DBMS must support at least one language that can be used independently and from within programs, and supports data definition operations, data manipulation, constraints, and transaction management.
- Views must be updatable by the system.
- The DBMS must support insert, update, and delete operations on sets.
- The DBMS must support logical data independence.
- The DBMS must support physical data independence.
- Integrity constraints must be stored within the catalogue, separate from the application.
- The DBMS must support distribution independence. The existing application should run when the existing data is redistributed or when the DBMS is redistributed.
- If the DBMS provides a low level interface (row at a time), that interface cannot bypass the integrity constraints.

#### **Advantages of RDBMS**

- Managablity: tables can be independently manipulated.
- Secure: multiple levels of security hence more secure also Access data can be controlled.
- Flexible: Single point updation. Extendable & scalable. Easy data access using SQL queries.
  Users: multiple users access.
- Can handle large amount of data.
- Easy Data Handling:
  - Faster Data Access.
  - Data redundancy or duplicity is avoided (Keys, Indexes & normalization)
- Higher Data consistency because to Atomicity Consistency Isolation Durability (ACID) properties.
- Higher Fault Tolerance due simultaneous access and helps system recovery as a result od replication.

#### **Disdvantages of RDBMS**

- High Cost
- Scalability requires additional power, and memory are required.
- High Volume of Data causes complexity and can impact performance.
- The fields or columns has set limits which could lead to loss of data

Two further terms of Note are,

**Arity** of a relation is the number of objects involved in any instance of that relation.

**Cardinality** has two different meanings depending on the context of it’s usage – one for data modeling and the other for SQL statements.
In the context of _data modeling_, it simply refers to the relationship that one table has with another table (One to Many, One to One, Many to Many etc.).
In _SQL_, the cardinality of a column in a given table refers to the number of unique values that appear in the table for that column. So, remember that the cardinality is a number.This impacts performance a lot, because it influences the query execution plan.

Regards,<br>
Sandeep
