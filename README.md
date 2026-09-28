DBMS Learning – Complete Notes, Definitions & Formulas

📚 Overview

This README contains comprehensive DBMS (Database Management System) notes covering database fundamentals, relational concepts, keys, constraints, ER modeling, relational algebra, SQL, normalization, transactions, concurrency control, indexing, recovery, and important formulas.

📑 Table of Contents
DBMS Basics
Important Database Terms
DBMS Architecture
Types of DBMS
Keys
Constraints
ER Model
Relationships
Relational Algebra
SQL
SQL Operators
SQL Aggregate Functions
SQL Clauses
Joins
Functional Dependency
Normalization
Database Anomalies
Transactions
ACID Properties
Concurrency Control
Locks
Deadlock
Indexing
B-Tree and B+ Tree
Hashing
Database Recovery
Views, Procedures and Triggers
Data Integrity
OLTP and OLAP
ETL and ELT
Important DBMS Formulas
DBMS Acronyms
1. DBMS Basics
Database

A database is an organized collection of related data that can be stored, accessed, managed, and updated efficiently.

DBMS

Database Management System (DBMS) is software used to create, store, retrieve, update, and manage databases.

RDBMS

Relational Database Management System (RDBMS) stores data in tables consisting of rows and columns.

Examples
MySQL
Oracle
PostgreSQL
Microsoft SQL Server
SQLite
2. Important Database Terms
Data

Raw facts and figures.

Information

Processed data that has meaningful context.

Relation

A table in a relational database.

Tuple

A row in a table.

Attribute

A column in a table.

Domain

The set of valid values that an attribute can contain.

Cardinality

The number of rows/tuples in a relation.

Cardinality = Number of Rows
Degree

The number of columns/attributes in a relation.

Degree = Number of Columns
Schema

The structure/design of a database.

EMP(EmpNo, Name, Salary, DeptNo)
Instance

The actual data stored in the database at a particular time.

Schema = Structure
Instance = Actual Data
3. DBMS Architecture
Three-Schema Architecture
1. External Level

User's view of the database.

2. Conceptual Level

Overall logical structure of the database.

3. Internal Level

Physical storage of the database.

External Level
      ↓
Conceptual Level
      ↓
Internal Level
      ↓
Physical Storage
Data Independence
Physical Data Independence

Changing physical storage without changing the conceptual schema.

Logical Data Independence

Changing the conceptual schema without changing external views.

4. Types of DBMS
Type	Description
Hierarchical DBMS	Tree-based structure
Network DBMS	Graph-like structure
Relational DBMS	Table-based structure
Object-Oriented DBMS	Object-based structure
NoSQL DBMS	Non-relational/flexible data models
5. Keys
Super Key

A set of one or more attributes that uniquely identifies a record.

Candidate Key

A minimal super key.

Primary Key

The candidate key selected to uniquely identify records.

Properties
Unique
Cannot contain NULL
One primary key per table
Can contain multiple columns
Alternate Key

Candidate keys that are not selected as the primary key.

Foreign Key

An attribute that references a key in another table and is used to establish relationships.

Composite Key

A key consisting of two or more attributes.

(Student_ID, Course_ID)
Surrogate Key

An artificially generated key.

Customer_ID = 1001
Key Relationship
Super Key
    ↓
Candidate Key
    ↓
Primary Key
6. Constraints

Constraints are rules that maintain data accuracy and integrity.

Constraint	Purpose
NOT NULL	Prevents NULL values
UNIQUE	Prevents duplicate values
PRIMARY KEY	Uniquely identifies records
FOREIGN KEY	Maintains relationships
CHECK	Restricts values
DEFAULT	Provides a default value
Example
CREATE TABLE Employee (
    EmpID INT PRIMARY KEY,
    Name VARCHAR(50) NOT NULL,
    Salary INT CHECK (Salary > 0),
    City VARCHAR(30) DEFAULT 'Bangalore'
);
7. ER Model

ER = Entity Relationship

An ER model is used to design the structure of a database.

Entity

A real-world object.

Examples:

Student
Employee
Customer
Product
Entity Set

A collection of similar entities.

Attribute

Property of an entity.

Types of Attributes
Simple Attribute

Cannot be divided further.

Age
Composite Attribute

Can be divided into smaller attributes.

Name
 ├── First Name
 └── Last Name
Single-Valued Attribute

Has one value.

Date of Birth
Multi-Valued Attribute

Can have multiple values.

Phone Numbers
Derived Attribute

Calculated from another attribute.

Date of Birth → Age
8. Relationships
One-to-One
1 : 1

Example:

Person ↔ Passport
One-to-Many
1 : N

Example:

Department → Employees
Many-to-One
N : 1

Example:

Employees → Department
Many-to-Many
M : N

Example:

Students ↔ Courses

An M:N relationship is normally implemented using a separate junction/associative table.

Strong Entity

An entity having its own primary key.

Weak Entity

An entity that depends on another entity for identification.

Total Participation

Every entity must participate in the relationship.

Partial Participation

Only some entities participate.

9. Relational Algebra

Relational algebra is a procedural query language used to manipulate relations.

Selection — σ

Selects rows based on a condition.

σ Salary > 50000 (Employee)
Projection — π

Selects columns.

π Name, Salary (Employee)
Union — ∪

Combines tuples from compatible relations.

R ∪ S
Requirements
Same number of attributes
Compatible domains
Difference — −

Returns tuples in R but not S.

R − S
Intersection — ∩

Returns common tuples.

R ∩ S
Cartesian Product — ×

Combines every row of R with every row of S.

R × S
Rename — ρ

Renames a relation.

ρ NewName(R)
Join — ⋈

Combines related tuples from two relations.

R ⋈ condition S
10. SQL

SQL stands for Structured Query Language.

SQL is used to:

Create databases
Create tables
Insert data
Retrieve data
Update data
Delete data
Control access
Manage transactions
SQL Categories
DDL — Data Definition Language

Used to define database structure.

CREATE
ALTER
DROP
TRUNCATE
RENAME
DML — Data Manipulation Language

Used to manipulate data.

INSERT
UPDATE
DELETE
DQL — Data Query Language

Used to retrieve data.

SELECT
DCL — Data Control Language

Used for permissions.

GRANT
REVOKE
TCL — Transaction Control Language

Used to control transactions.

COMMIT
ROLLBACK
SAVEPOINT
11. SQL Operators
Arithmetic Operators
Operator	Meaning
+	Addition
-	Subtraction
*	Multiplication
/	Division
%	Modulus
Comparison Operators
=
<>
!=
>
<
>=
<=
Logical Operators
AND
OR
NOT
Special Operators
BETWEEN
IN
LIKE
IS NULL
IS NOT NULL
EXISTS
12. SQL Aggregate Functions
COUNT()

Counts rows/values.

SELECT COUNT(*) FROM Employee;
SUM()

Calculates the total.

SELECT SUM(Salary) FROM Employee;
AVG()

Calculates the average.

AVG = SUM / COUNT
MAX()

Returns the maximum value.

MIN()

Returns the minimum value.

13. SQL Clauses
WHERE

Filters rows.

SELECT *
FROM Employee
WHERE Salary > 50000;
GROUP BY

Groups records with the same values.

HAVING

Filters groups.

ORDER BY

Sorts results.

ASC  → Ascending
DESC → Descending
DISTINCT

Removes duplicate values.

LIMIT

Restricts the number of returned records.

14. Joins
INNER JOIN

Returns matching records from both tables.

LEFT JOIN

Returns all records from the left table and matching records from the right table.

RIGHT JOIN

Returns all records from the right table and matching records from the left table.

FULL OUTER JOIN

Returns records from both tables, including unmatched records.

SELF JOIN

A table is joined with itself.

CROSS JOIN

Produces a Cartesian product.

Number of rows = Rows in R × Rows in S
15. Functional Dependency

Functional dependency describes a relationship between attributes.

A → B

This means:

If A is known, B can be uniquely determined.

Example:

Student_ID → Student_Name
Types of Functional Dependency
Trivial Functional Dependency
A → B

where B is a subset of A.

Example:

(Student_ID, Name) → Name
Non-Trivial Functional Dependency

B is not a subset of A.

Student_ID → Name
Full Functional Dependency

An attribute depends on the complete composite key.

Partial Dependency

An attribute depends only on part of a composite key.

Transitive Dependency

If:

A → B
B → C

then:

A → C
16. Normalization

Normalization is the process of organizing data to:

Reduce redundancy
Avoid anomalies
Improve data integrity
1NF — First Normal Form

Requirements:

Atomic values
No repeating groups
One value per cell
Example

❌ Not 1NF:

Student | Phone
Ramya   | 9876, 8765

✅ 1NF:

Student | Phone
Ramya   | 9876
Ramya   | 8765
2NF — Second Normal Form

A relation must:

Be in 1NF
Have no partial dependency
3NF — Third Normal Form

A relation must:

Be in 2NF
Have no transitive dependency
Easy Rule
Non-key attributes must depend on:
the key,
the whole key,
and nothing but the key.
BCNF

Boyce-Codd Normal Form

For every non-trivial functional dependency:

X → Y

X must be a super key.

4NF

Deals with multivalued dependencies.

5NF

Deals with join dependencies.

17. Database Anomalies
Insertion Anomaly

Cannot insert information without unrelated information.

Update Anomaly

The same information must be updated in multiple places.

Deletion Anomaly

Deleting one record unintentionally removes other useful information.

18. Transactions

A transaction is a logical unit of database operations.

Example:

Bank Transfer


Debit ₹1000
      ↓
Credit ₹1000

Both operations should be treated as one transaction.

19. ACID Properties
A — Atomicity

Transaction is completed completely or not at all.

All or Nothing
C — Consistency

Database moves from one valid state to another valid state.

I — Isolation

Concurrent transactions should not interfere incorrectly.

D — Durability

Committed changes remain permanently even after failures.

Easy Memory Trick
A → All
C → Correct
I → Independent
D → Durable
20. Transaction States

A transaction can have the following states:

Active
  ↓
Partially Committed
  ↓
Committed

If a failure occurs:

Active
  ↓
Failed
  ↓
Aborted

Finally:

Terminated
21. Concurrency Control

Concurrency means multiple transactions execute at the same time.

Purpose
Maintain consistency
Prevent conflicts
Improve performance
Common Concurrency Problems
Lost Update

One transaction overwrites another transaction's update.

Dirty Read

A transaction reads uncommitted data from another transaction.

Non-Repeatable Read

The same query returns different values because another transaction modified the data.

Phantom Read

A repeated query returns a different set of rows because another transaction inserted/deleted matching rows.

22. Serializability

A schedule is serializable if its result is equivalent to some serial execution of the transactions.

Types
Conflict Serializability
View Serializability
23. Locks

Locks control simultaneous access to database items.

Shared Lock — S

Used for reading.

S = Read

Multiple transactions can generally hold shared locks simultaneously.

Exclusive Lock — X

Used for writing.

X = Write

An exclusive lock prevents conflicting access by other transactions.

24. Two-Phase Locking

2PL = Two-Phase Locking

Growing Phase

Transaction can acquire locks but cannot release them.

Shrinking Phase

Transaction can release locks but cannot acquire new locks.

Growing Phase → Shrinking Phase
25. Deadlock

Deadlock occurs when transactions wait for each other indefinitely.

Example:

T1 → Waiting for T2
T2 → Waiting for T1

Neither transaction can continue.

Deadlock Handling
Prevention
Avoidance
Detection
Recovery
26. Indexing

An index is a data structure that improves the speed of data retrieval.

It is similar to the index of a textbook.

Types
Primary Index
Secondary Index
Clustered Index
Non-Clustered Index
Dense Index
Sparse Index
Dense Index

Contains an index entry for every search-key value/record, depending on the indexing scheme.

Sparse Index

Contains index entries for only some search-key values, typically requiring ordered data.

27. B-Tree and B+ Tree
B-Tree

A balanced tree used for database indexing.

Properties:

Balanced
Efficient searching
Supports insertion
Supports deletion
B+ Tree

A variation of B-tree commonly used for database indexing.

Important features:

Internal nodes store search keys
Leaf nodes contain record pointers/entries
Leaf nodes are linked
Efficient range queries
28. Hashing

Hashing maps a key to a bucket/location.

h(key) → bucket

Example:

h(25) = 25 % 10
     = 5

Therefore, key 25 is mapped to bucket 5.

Collision

When two different keys map to the same bucket.

h(25) = 5
h(35) = 5

Both keys produce the same bucket.

29. Database Recovery

Recovery restores the database to a consistent state after a failure.

Types of Failure
Transaction failure
System crash
Power failure
Disk failure
Log-Based Recovery

A log stores database operations.

Example:

<T1, START>
<T1, A, Old_Value, New_Value>
<T1, COMMIT>
UNDO

Reverses changes made by an incomplete or failed transaction.

REDO

Reapplies changes of committed transactions when required.

Checkpoint

A checkpoint creates a known recovery point and reduces recovery work.

30. Views, Procedures and Triggers
View

A virtual table based on a query.

Advantages
Security
Simplicity
Data abstraction
Customized access
Stored Procedure

A stored collection of SQL/procedural statements that can be executed as a unit.

Trigger

A trigger automatically executes when a specified database event occurs.

Common events:

INSERT
UPDATE
DELETE
Cursor

A cursor allows row-by-row processing of query results in procedural database programming.

31. Data Integrity
Entity Integrity

Primary key cannot be NULL.

Referential Integrity

Foreign key values must properly reference existing values in the referenced table, subject to the configured referential actions.

Domain Integrity

Values must belong to the allowed domain.

32. NULL

NULL represents missing, unknown, or not-applicable information.

NULL is not:

0
''
FALSE
SPACE
Correct NULL Checking
WHERE column IS NULL;
WHERE column IS NOT NULL;
33. SQL Pattern Matching
%

Represents zero or more characters.

'A%'

Starts with A.

'%A'

Ends with A.

'%A%'

Contains A.

_

Represents exactly one character.

'A__'

Starts with A and contains exactly 3 characters.

34. Important SQL Functions
String Functions
UPPER()
LOWER()
LENGTH()
SUBSTRING()
CONCAT()
TRIM()
REPLACE()
Numeric Functions
ABS()
ROUND()
CEIL()
FLOOR()
MOD()
Aggregate Functions
COUNT()
SUM()
AVG()
MAX()
MIN()

Date/time functions vary by DBMS, but commonly support current date/time, date differences, and extracting date parts.

35. SQL Logical Execution Order

The logical processing order is generally:

FROM
  ↓
WHERE
  ↓
GROUP BY
  ↓
HAVING
  ↓
SELECT
  ↓
DISTINCT
  ↓
ORDER BY
  ↓
LIMIT
Easy Memory
F → W → G → H → S → D → O → L
36. Important DBMS Formulas
Cardinality
Cardinality = Number of Rows
Degree
Degree = Number of Columns
Average
Average = SUM / COUNT
Percentage
Percentage = (Part / Total) × 100
Salary Increment
New Salary = Old Salary × (1 + Rate/100)
Salary Deduction
Final Salary = Salary × (1 - Rate/100)
Total
Total = Σ Values
37. Relational Algebra Formulas
Cartesian Product

If:

R = m rows
S = n rows

then:

|R × S| = m × n
Union
|R ∪ S| = |R| + |S| - |R ∩ S|

If R and S have no common tuples:

|R ∪ S| = |R| + |S|
Intersection
|R ∩ S| ≤ min(|R|, |S|)
Difference
|R - S| ≤ |R|
38. Hashing Formula

A common simple hash function is:

h(key) = key MOD number_of_buckets

Example:

key = 47
buckets = 10


h(47) = 47 MOD 10
      = 7
39. OLTP and OLAP
OLTP

Online Transaction Processing

Used for daily transactions.

Examples:

Banking
ATM
Online shopping
Railway booking

Characteristics:

Many small transactions
Fast inserts/updates
High concurrency
OLAP

Online Analytical Processing

Used for analysis and reporting.

Examples:

Business intelligence
Sales analysis
Data warehouses

Characteristics:

Complex queries
Large datasets
Aggregation
Reporting
40. ETL and ELT
ETL
Extract → Transform → Load

Data is transformed before loading into the target system.

ELT
Extract → Load → Transform

Data is loaded first and transformed afterward.

41. CRUD

CRUD represents the four basic database operations.

C → Create
R → Read
U → Update
D → Delete

Common SQL mapping:

Create → INSERT
Read   → SELECT
Update → UPDATE
Delete → DELETE
42. Database Backup
Full Backup

Copies the entire database.

Incremental Backup

Copies changes since the previous backup.

Differential Backup

Copies changes since the last full backup.

43. DBMS Acronyms
Acronym	Full Form
DB	Database
DBMS	Database Management System
RDBMS	Relational Database Management System
SQL	Structured Query Language
DDL	Data Definition Language
DML	Data Manipulation Language
DQL	Data Query Language
DCL	Data Control Language
TCL	Transaction Control Language
DBA	Database Administrator
ER	Entity Relationship
ERD	Entity Relationship Diagram
ACID	Atomicity, Consistency, Isolation, Durability
1NF	First Normal Form
2NF	Second Normal Form
3NF	Third Normal Form
BCNF	Boyce-Codd Normal Form
4NF	Fourth Normal Form
5NF	Fifth Normal Form
OLTP	Online Transaction Processing
OLAP	Online Analytical Processing
CRUD	Create, Read, Update, Delete
JDBC	Java Database Connectivity
ODBC	Open Database Connectivity
ETL	Extract, Transform, Load
ELT	Extract, Load, Transform
DDL	Data Definition Language
DML	Data Manipulation Language
TCL	Transaction Control Language
DCL	Data Control Language
⭐ Quick Revision Sheet
DATABASE
KEYS
Super Key
    ↓
Candidate Key
    ↓
Primary Key


Other Keys:
Foreign Key
Alternate Key
Composite Key
Surrogate Key


NORMALIZATION
1NF  → Atomic Values
2NF  → No Partial Dependency
3NF  → No Transitive Dependency
BCNF → Every Determinant is a Super Key
4NF  → Multivalued Dependencies
5NF  → Join Dependencies


TRANSACTION
      ↓
     ACID
 ┌────┼────┐
 A    C    I    D
 ↓    ↓    ↓    ↓
All Correct Independent Durable


RELATIONAL ALGEBRA
σ → Selection
π → Projection
∪ → Union
− → Difference
∩ → Intersection
× → Cartesian Product
⋈ → Join
ρ → Rename


SQL
DDL → CREATE, ALTER, DROP, TRUNCATE
DML → INSERT, UPDATE, DELETE
DQL → SELECT
DCL → GRANT, REVOKE
TCL → COMMIT, ROLLBACK, SAVEPOINT


CONCURRENCY
Shared Lock    → Read
Exclusive Lock → Write


2PL
Growing → Shrinking


RECOVERY
UNDO → Reverse changes
REDO → Reapply changes
🎯 Most Important Topics to Study First

If this is for your DBMS learning/SQL coursework, focus especially on:

 DBMS vs RDBMS
 Schema vs Instance
 Three-Schema Architecture
 Data Independence
 Keys
 Constraints
 ER Model
 Cardinality
 Relational Algebra
 SQL Commands
 SQL Operators
 Aggregate Functions
 GROUP BY and HAVING
 Joins
 Functional Dependencies
 1NF, 2NF, 3NF and BCNF
 Anomalies
 Transactions
 ACID Properties
 Concurrency Problems
 Serializability
 Locks and 2PL
 Deadlocks
 Indexing
 B-Tree and B+ Tree
 Hashing
 Recovery
 Views
 Triggers
 Stored Procedures
 OLTP vs OLAP
 ETL vs ELT

Tip: For DBMS exams, don't study SQL alone. The strongest preparation combines DBMS theory + ER diagrams + relational algebra + normalization + SQL + transactions + indexing + recovery.
