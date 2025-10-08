# Database Management System (DBMS) Notes

## What is a DBMS?
A **DBMS (Database Management System)** is software used to create and manage databases: insert, modify, delete records and provide access control. A database is a collection of inter-related tables and objects.

- **DBMS = DB (Database) + MS (Management System)**
- **RDBMS (Relational Database Management System):** Organizes data in tables (relations).  
  _Examples:_ MySQL, Oracle, Sybase, DB2

***

## Key Terminology in RDBMS

| Term            | Meaning                                                                 |
| --------------- | ----------------------------------------------------------------------- |
| **Table / Relation**   | Collection of inter-related records                           |
| **Tuple / Row / Record** | Collection of attributes                                    |
| **Attribute / Column / Field** | Descriptive property of an entity                   |
| **Primary Key** | Attribute(s) that uniquely identify a record in a table               |
| **Candidate Key** | Attribute(s) that can be chosen as primary key                       |
| **Alternate Key** | Candidate key not chosen as primary key                              |
| **Foreign Key**  | Non-key attribute whose values come from the primary key of another table |

***

## Types of Keys
- **Primary Key:** Chosen attribute(s) uniquely identifying a record  
- **Candidate Key:** All possible attributes that could serve as a primary key  
- **Alternate Key:** Candidate keys that are not the primary  
- **Foreign Key:** Attribute in one table referencing the primary in another for referential integrity

***

## SQL (Structured Query Language)

- Open industry-standard language for querying, creating, and managing databases.
- MySQL is an open-source RDBMS created by Michael Widenius (Monty).

***

## Data Types in SQL

- Text: `CHAR(n)`, `VARCHAR(n)`
- Numbers: `INT(n)`, `INTEGER(n)`, `DECIMAL(n, d)`, `FLOAT(n)`
- Date: `DATE` (e.g., `'yyyy-mm-dd'`)
- Boolean: `TINYINT(1)` (0 for False, 1 for True)
- Example: `DECIMAL(7,2)` has 7 digits, 2 after decimal

***

## SQL Command Categories

| Type | Purpose | Examples |
|------|---------|----------|
| DDL  | Data Definition Language | `CREATE`, `ALTER`, `DROP` |
| DML  | Data Manipulation Language | `INSERT`, `UPDATE`, `SELECT`, `DELETE` |
| DCL  | Data Control Language | `GRANT`, `REVOKE` |
| TCL  | Transaction Control Language | `COMMIT`, `ROLLBACK`, `SAVEPOINT` |

***

## Common SQL Commands

```sql
-- Create a database and table
CREATE DATABASE mydb;
USE mydb;

CREATE TABLE pupil (
    admno INT(4) PRIMARY KEY,
    name VARCHAR(18) NOT NULL,
    dob DATE,
    gender CHAR(6) DEFAULT 'MALE',
    fees DECIMAL(7,2),
    avgmark DECIMAL(5,2)
);

-- Insert records
INSERT INTO pupil VALUES (114, 'ANITA MATHUR', '2002-06-20', 'FEMALE', 3150.0, 91.2);

-- Alter a table
ALTER TABLE pupil ADD grade CHAR(2);

-- Delete a table
DROP TABLE pupil;

-- Select queries
SELECT * FROM pupil;
SELECT admno, name, dob FROM pupil;
SELECT DISTINCT name FROM pupil;
SELECT * FROM pupil WHERE fees BETWEEN 3000 AND 3500;
SELECT * FROM pupil ORDER BY name DESC;
```

***

### SELECT Clause Extensions

- **WHERE**: Filter rows by condition  
- **BETWEEN**: Range query (`WHERE fees BETWEEN 3000 AND 3500`)
- **IN**: Match against a set/list  
- **LIKE**: Pattern matching (`LIKE 'A%'`)
- **ORDER BY**: Sort results  
- **GROUP BY**: Aggregate/group rows  
- **HAVING**: Condition on groups  
- **IS NULL / IS NOT NULL**: Check for missing values

***

## Aggregate Functions

- `SUM()`: Total of column values
- `MIN()`: Minimum value
- `MAX()`: Maximum value
- `AVG()`: Mean of column values
- `COUNT()`: Row count

***

## Working With Multiple Tables

- **CARTESIAN PRODUCT / CROSS JOIN:** All pairs of rows
- **EQUIJOIN:** Match rows from both tables on a common column
  ```sql
  SELECT * FROM books, issued WHERE books.book_id = issued.book_id;
  ```
- **NATURAL JOIN:** Like equijoin, but the common column appears only once
  ```sql
  SELECT * FROM books NATURAL JOIN issued;
  ```

***

## Python-MySQL Interface Summary

1. Install with pip:  
   ```bash
   pip install mysql-connector-python
   ```
2. Import & connect in Python
   ```python
   import mysql.connector
   mydb = mysql.connector.connect(host="localhost", user="root", passwd="tiger", database="school")
   cursor = mydb.cursor()
   cursor.execute("SELECT * FROM stud")
   data = cursor.fetchall()
   print(cursor.rowcount)  # Number of rows fetched
   ```

***

## Short Q&A Recap

- **Install MySQL library:** `pip install mysql-connector-python`
- **Connect to MySQL:** `connect()` method in `mysql.connector`
- **Fetch methods:**  
  - `fetchall()`: All records  
  - `fetchone()`: Single record  
  - `fetchmany(n)`: n records

***

These notes include all fundamental concepts, queries, and procedures from your Database Management System (DBMS) unit.[1]

[1](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/122445919/9d77493b-3e13-4e80-8e90-f2bcf315645f/12-CS-Last-Minute-Revision_240609_154654.pdf)
