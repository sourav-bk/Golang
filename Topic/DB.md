## ER Model (Entity-Relationship) 

The E-R model stands for the Entity-Relationship model,
E-R model is a high-level conceptual data model used in software engineering to visualize the structure of a database.
It represents real-world objects as entities and their associations as relationships, creating a, diagrammatic blueprint (ER Diagram) that facilitates database design and understanding about the Data.

This model represents the logical structure of a database, using entities, their attributes, and relationships between them.

- ***Entity:*** An object that is stored as data. E.g: Student, Course, or Company.
- ***Attribute:*** Properties that describe an entity. E.g: StudentID, CourseName, or EmployeeEmail.
- ***Relationship:*** A connection between entities. E.g: Student enrolls in a Course.

## Relational Model 

The relational model represents the database management approach that organizes or stored data into tables , columns and rows.
Relational Model real Implementation is Mysql, SQL server. 

Key Concepts of the Relational Model are --

- ***Relation (Table):*** Relational Model represents Data as a Collection of tables. A table is called Relation. 
- ***Tuple (Row/Record):*** Represents single instance or Each Row of data in a table. ( e.g., one customer Data )
- ***Attribute (Column/Field):*** Represents a specific characteristic or property of the entity or Column Header. ( e.g., customer name, ID ).
- ***Domain:*** The set of allowed values for an attribute. ( e.g., String Data type customer name  )
- ***Schema:*** The logical structure of a relation.
  
## Types of relationship in Rdbms
- One-to-One (1:1): A single record in Table A is related to only one record in Table B.
  - Example: A Person table and an AadharCard table, where one person has exactly one Aadhar card.
- One-to-Many (1:M) / Many-to-One (M:1): A record in Table A can be associated with multiple records in Table B, but a record in Table B relates to only one in Table A.
  - Example: A Department table (one) and an Employee table (many).
- Many-to-Many (M:N): Multiple records in Table A are related to multiple records in Table B, requiring a junction table to implement.
  - Example: A Student table and a Course table, where students take multiple courses and courses have multiple students
 
## Keys in Relational Model


- ***1. Super Key :***
  Its set of one or more attributes (columns) that can uniquely identify a each Tuple/Record/Row in a Relation/Table. 

- ***2. Candidate Key :***
  Its minimum set of one or more attributes (columns) that can uniquely identify a each Tuple/Record/Row in a Relation/Table. A table can have multiple candidate keys.

- ***3. Primary Key :***
  Its specific candidate key chosen to uniquely identify Tuple/Record/Row in a Relation/Table. It cannot contain NULL values and must be unique.

- ***4. Alternate Key :***
  Any candidate key that is not selected as the primary key.

- ***5. Unique Key :***

- ***6. Composite Key :***
  Its a combination of two or attributes (columns) that together uniquely identify a Tuple/Record/Row in a Relation/Table. Each attributes (columns) may contain duplicate values but cannot contain NULL values. And by combined its Behave like Primary Key.

- ***7. Foreign Key :***
  Foreign key is a attribute/column (or set of attributes/columns) in one Relation/Table that links to the primary key of another Relation/Table. It serves as a cross-reference between Relation/Table to establish a relationship and maintain referential integrity.

- ***8. Partial Key :***




## Normalization

Normalization in DBMS is the process of structuring a relational database to reduce data redundancy (repetition) and eliminate undesirable characteristics. It involves decomposing large, inefficient tables into smaller, related tables to improve data integrity, consistency, and storage efficiency.

It involves decomposing large, inefficient tables into smaller, related tables to improve data integrity, consistency, and storage efficiency.


- ***Key Objectives of Normalization:***

Minimizes duplicate data, saving storage space. Prevents issues where updating or deleting data causes inconsistency, or where data cannot be inserted due to missing information.


### Normal Forms (Levels of Normalization)

Normalization is achieved through a series of stages called normal forms. Each stage has specific rules
- ***1NF (First Normal Form):***
  
  Data is in a tabular format, and every cell contains atomic (indivisible) values.
  
- ***2NF (Second Normal Form):***

  Must be in 1NF, and all non-key attributes are fully functionally dependent on the primary key. It removes partial dependencies.
  
- ***3NF (Third Normal Form):***
  
  Must be in 2NF, and no transitive dependencies exist (i.e., non-key attributes must not depend on other non-key attributes).
  
- ***BCNF (Boyce-Codd Normal Form):***

  A stricter version of 3NF, sometimes called 3.5NF, which addresses, which addresses anomalies caused by multiple overlapping candidate keys.
  
- ***4NF & 5NF:***

  Address multi-valued dependencies and join dependencies, used in advanced database design.


### Advantages :

  - ***Improved Data Integrity:*** Ensures data accuracy and consistency across the database.
  - ***Better Organization:*** Data is organized logically, making it easier to maintain.Faster Maintenance: Smaller tables are easier to manage.
    
### Disadvantages :

  - ***Increased Query Complexity:*** Breaking data into many tables may require complex JOIN operations, potentially slowing down read-heavy applications.
  - ***Performance Trade-off:*** Extremely high normalization (4NF/5NF) can decrease performance in some scenarios


## ACID properties in DB :
ACID properties in a Database Management System (DBMS) are a set of 4 core principles — **Atomicity**, **Consistency**, **Isolation**, and **Durability** — that ensure database transactions are processed reliably, maintaining data integrity and accuracy. They guarantee that even in the event of failures or concurrent access, data remains accurate and consistent.


- ***Atomicity ("All or Nothing"):***
  
  Transactions are indivisible units. Either the entire transaction succeeds, or if any part fails, the entire transaction is rolled back, leaving the database unchanged.
  
- ***Consistency (Valid State):***

  Ensures the database transforms from one valid state to another valid state, maintaining all predefined integrity constraints, rules, and triggers.
  
- ***Isolation (Independent Execution):***

   Multiple transactions occurring simultaneously do not interfere with each other. The intermediate state of a transaction is invisible to other concurrently running transactions.
  
- ***Durability (Permanent Changes):***

   Once a transaction is committed, its changes are permanently saved, even in the event of a system crash, power failure, or error.


## Type of sql commands:
SQL commands are categorized into 5 primary types based on their specific functionality in managing a database: DDL, DML, DQL, DCL, and TCL.

 1. ***Data Definition Language (DDL)***
    
    DDL commands are used to define or modify the structure (schema) of the database, such as tables, indexes, and views.
    - CREATE: Creates a new database object (e.g., table or view).
    - ALTER: Modifies the structure of an existing object, like adding or deleting columns.
    - DROP: Permanently deletes an object from the database.
    - TRUNCATE: Removes all records from a table while keeping its structure intact.
    - RENAME: Changes the name of a database object.
 2. ***Data Manipulation Language (DML)***
    
    DML commands are used to handle the actual data stored within the tables. Most everyday SQL operations fall under this category.
    - INSERT: Adds new rows of data to a table.
    - UPDATE: Modifies existing records based on specific conditions.
    - DELETE: Removes rows from a table.
    - LOCK: Controls concurrent access to data to ensure consistency.
 3. ***Data Query Language (DQL)***
    
    DQL is used specifically for retrieving and viewing data from the database.
    - SELECT: The primary command used to fetch data. It is often paired with clauses like WHERE, ORDER BY, and GROUP BY to filter and sort results.
 4. ***Data Control Language (DCL)***
    
    DCL commands manage user access, permissions, and security within the database system.
    - GRANT: Gives a user specific privileges to access or modify data.
    - REVOKE: Withdraws previously granted permissions.
 5. ***Transaction Control Language (TCL)***
     
    TCL commands manage database transactions to ensure data integrity and consistency, often used in conjunction with DML operations.
    - COMMIT: Permanently saves the changes made during the current transaction.
    - ROLLBACK: Undoes changes that have not yet been saved, returning the data to its previous state.
    - SAVEPOINT: Sets a temporary marker within a transaction to which you can later roll back.
    - SET TRANSACTION: Specifies characteristics for the transaction, such as isolation levels


## Joint and types of joins In RDBMS?

Join is an operation in DBMS that combines the rows of two or more tables based on related columns between them. The main purpose of join is to retrieve data from multiple tables, in other words Join is used to perform multi-table queries.

Types of Joins ---

- INNER JOIN:

  Returns records with matching values in both tables.
  - Eg = SELECT * FROM Orders INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID;.
    
- LEFT (OUTER) JOIN:

  Returns all records from the left table, and matched records from the right table.
  - Eg = SELECT * FROM Customers LEFT JOIN Orders ON Customers.CustomerID = Orders.CustomerID;.
    
- RIGHT (OUTER) JOIN:

  Returns all records from the right table, and matched records from the left table.
  - Eg = SELECT * FROM Orders RIGHT JOIN Customers ON Orders.CustomerID = Customers.CustomerID;.
    
- FULL (OUTER) JOIN:

  Returns all records when there is a match in either left or right table.
  - Eg = SELECT * FROM Customers FULL OUTER JOIN Orders ON Customers.CustomerID = Orders.CustomerID;.
 
## Index in DB
An index in SQL is a data structure used to speed up the retrieval of records, from a DB table. It acts like the index at the back of a textbook: instead of scanning every page to find topic, we look in to the index and jump straight to the correct page.

Common Types of Indexes---

- Clustered Index:

  Determines the physical order of data in the table. A table can have only one clustered index because data can only be physically stored in one order (often automatically created on the Primary Key).
  
- Non-Clustered Index:

  A separate structure from the data rows that contains pointers to the original data. You can have multiple non-clustered indexes on a single table.

- Unique Index:

  Ensures that all values in the indexed column are unique, preventing duplicate entries and maintaining data integrity.

- Composite Index:

  An index created on two or more columns together, useful for queries that filter by multiple criteria



## What is RDBMS and Nosql?

- ***RDBMS(Mysql)***
  
  RDBMS: A Relational Database Management System (RDBMS) is software that manages data organized into tables with rows and columns.

  SQL: SQL (Structured Query Language) is the standard programming language designed for managing, manipulating, and retrieving data from RDBMS.
 
- ***Nosql***

  NoSQL databases are non-relational data management systems designed for high scalability, flexibility, and performance, handling large volumes of unstructured, semi-structured, or rapidly changing data. They use flexible, schemaless data models—including document, key-value, graph, or wide-column stores—and scale horizontally across distributed servers, making them ideal for modern, data-intensive web applications.


  
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Q. What is the difference between DDL and DML?'
Q. What is a primary key in a database, and how is it used to uniquely identify records?
Q. Can you explain basic database concepts and your experience with databases?
Q. What is a query?
Q. What are functions in databases, and how do they differ from stored procedures?
Q. What is an index in a database? Describe the di…dexes and discuss their advantages and drawbacks.', 'Database Developer Jobs
Q. What is database migration?
Q. How do you handle data migration in SQL?
Q. What are file groups?
Q. What strategies can a Product Manager use to ma…e and resolve conflicts within engineering teams?
Q. Describe a challenging situation at work
Q. What are the different types of database normalization, and why is it important?
Q. Explain the ACID properties.
Q. Can you describe the MERGE statement and provid…amples of its application in database operations?
Q. Please demonstrate your proficiency in SQL by writing queries to solve common database problems.
Q. Describe your salary structure expectations.
Q. Briefly describe your past experience relevant to this role.
Q. Please provide a general introduction about you…lf and answer any initial questions I might have.', 'Interview Questions of Similar Designations'
Q. Write a procedure using bulk collect.
Q. What is the difference between the DROP TABLE command and the DELETE command in MySQL?
Q. What is a database cluster?
Q. What is a data structure?
Q. Given a 10-digit number, how would you format it as 4-3-3?
Q. What are output parameters?', 'Database Developer Jobs
Q. What are Magic Tables in SQL Server?
Q. Explain joins in SQL in detail
Q. Explain the concept of normalization in RDBMS and its different levels.
Q. What is performance optimization?
Q. What is a recursive CTE?
Q. Explain joins and all types of joins.
Q. Explain Database Architecture
Q. Is Java the primary language you use?
Q. What is the difference between a left join and a right join in SQL?
Q. What is index fragmentation?
Q. Give me a query to solve.
Q. Explain your approach to delegating tasks and responsibilities within a team.
Q. What is a query in Join?
Q. What are temporary tables in SQL Server? Descri… of temporary tables and their typical use cases.
Q. What is a primary key?
Q. Explain the use of abstraction.
Q. How does inheritance work?
Q. What is a materialized view?
Q. What are the advantages of PostgreSQL over Oracle?
Q. Can you elaborate on your day-to-day activities?
Q. What are the different types of joins and their potential problems?
Q. How do you perform JOIN operations in SQL? Please explain with examples.
Q. What are the differences between deleting and truncating a table in a database?
Q. What is collation?', 'Interview Questions of Similar Designations
Q. What makes you unique?
Q. Write an SQL query to remove duplicate rows from a table named tab1.
Q. L?
Q. Why is indexing used in software engineering, and what are its advantages?
Q. What are the best practices for writing queries that cover all possible cases?
Q. How can you find people from the same city in a database table?', 'Database Developer Jobs
Q. Can you tell me about a difficult work situation and how you overcame it?
Q. What is the difference between INNER JOIN and LEFT JOIN in SQL?
Q. What is heap memory and what is stack memory?
Q. What are the advantages of using transactions?
Q. Explain the different normalization forms and their significance.
Q. What reasons would you give us to hire you?
Q. Write a query that will give a combination of matches.
Q. Write a query to find the employees who joined recently.
Q. Can you discuss your experience with Linux, inc…s and scenarios relevant to platform development?
Q. How do you run parallel queries for multiple databases?
Q. What are the different types of normal forms in…tabase normalization, and why are they important?
Q. What types of indexes have you used in previous organizations?
Q. What is database normalization and why is it important?', 
Q. Let's discuss your experience with Oracle SQL analytical and aggregate queries 
Q. Do you know how to work with Hadoop?
Q. What does a Stored Procedure do?
Q. How would you optimize a slow-running SQL query?
Q. Explain how you would optimize a slow-running query using indexing and other techniques.
Q. What is a Rank Function? Explain with an example.
Q. What is the difference between the WHERE and HAVING clauses?
Q. Describe the differences between Stored Procedu…hat are the advantages and disadvantages of each?
Q. How does the COALESCE function work?
Q. What is SQL, and how have you applied it in your development work?
Q. What is a global variable in Oracle?', 
Q. Interview Questions of Similar Designations
