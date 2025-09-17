# Unit 1 


## **Data vs Information**
| **Aspect** | **Data** | **Information** |
| --- | --- | --- |
| Definition | Raw, unprocessed facts and figures. | Processed, organized, and meaningful data. |
| Nature | Unstructured or structured values. | Structured and contextually relevant. |
| Example | A list of numbers: 23, 45, 67, 89 (without context). | The average test score of students is 56%. |
| Processing | Requires processing to be useful. | Already processed and meaningful. |
| Storage in DBMS | Stored as tables, records, and fields. | Retrieved as reports, summaries, or insights. |
| Usage | Used as input for processing. | Used for decision-making. |

## **Database and DBMS**

- A database is an organized collection of structured information, or data, typically stored electronically in a computer system
- It is the collection of interrelated data that is organised in a way that data can be easily accessed, managed and updated.
- It is designed to handle large amounts of structured information and supports various operations like querying, updating, and deleting data.
- Databases are managed using Database Management Systems (DBMS), which provide an interface to interact with the data.
- The DBMS also handles tasks like backup, recovery, and query optimization to maintain the database’s performance.
- Examples of databases include MySQL, PostgreSQL, MongoDB, and Oracle Database.
- Databases can store data in the form of tables depending upon the type of database.

### **Types of Databases**

- **Relational Databases (RDBMS)** – Use tables with rows and columns (e.g: MySQL, PostgreSQL).
- **NoSQL Databases** – Store data in flexible formats like key-value pairs, documents, or graphs (e.g: MongoDB, Redis).
- **Cloud Databases** – Hosted on cloud platforms for scalability (e.g: Google BigQuery, Amazon RDS).
- **Distributed Databases** – Spread across multiple locations for high availability (e.g: Apache Cassandra).

### **Applications**

1. **Railway and Airline Reservation Systems:**
    - Manages ticket bookings, schedules, and delays.
2. **Library Management System:**
    - Tracks books, issue dates, authors, and availability.
3. **Banking:**
    - Handles transactions, account details, and fund transfers.
4. **Educational Institutions:**
    - Stores student records, results, and course details.
5. **Credit Card Transactions:**
    - Secures transaction history and cardholder data.
6. **Social Media Platforms:**
    - Stores user data, posts, and interactions.
7. **Finance and Business:**
    - Manages sales, investments, and financial statements.
8. **Military:**
    - Maintains highly secure defense-related data.
9. **Online Shopping:**
    - Stores product inventory, customer orders, and payments.
10. **Human Resource Management:**
    - Keeps track of employee details, salaries, and taxes.
11. **Manufacturing and Supply Chain:**
    - Manages production, inventory, and sales.

### **Characteristics & Features**

1. **Data Stored in Tables**
    - Data is stored in tables with relationships between them, making it structured and meaningful.
2. **Data Abstraction:**
    - Hides complexity and provides a simplified view of data storage.
3. **Data Independence**
    - Schema changes do not affect applications accessing the data.
4. **Reduced Redundancy**
    - Uses **Normalization** to minimize data repetition, reducing storage costs and improving consistency.
5. **Efficient Data Access**
    - Database systems structure data using **predefined schemas and data models**, allowing efficient **storage and retrieval**.
    - They **eliminate redundancy and anomalies** by enforcing constraints and rules, maintaining **data accuracy and reliability**.
6. **Support for Multiple Users and Concurrent Access** 
    - **Multiple users** can **access and manipulate** data **simultaneously** while ensuring **data consistency** across applications.
    - Supports **collaborative data sharing** without conflicts, making it easier for teams to work on shared datasets.
7. **Query Language**
    - Provides a simple query language like **SQL** for data retrieval, insertion, deletion, and updates.
8. **Security** 
    - Database systems implement **strong security measures** to prevent **unauthorized access** and **protect sensitive data**.
    - Security mechanisms like **authentication, authorization, and encryption** help preserve **data confidentiality and privacy**.
9. **Data Integrity and Consistency** 
    - Ensures correctness and completeness using constraints like **primary keys, foreign keys, and unique constraints**.
    - Enforces **ACID (Atomicity, Consistency, Isolation, Durability)** properties to ensure **reliable transactions**.
    - Prevents inconsistencies by maintaining **referential integrity** and enforcing **business rules** through constraints.
10. **Backup and Recovery** 
    - Provides **automatic data backups** and **transaction management** to safeguard data from **system crashes or failures**.
    - Ensures **data durability**, meaning no data is lost even if a system failure occurs.
11. **Data Sharing** 
    - Enables authorized users to access shared data as needed.
12. **Scalability & Performance Optimization**
    - Database systems are designed to handle **large volumes of data** efficiently, supporting **business growth and expansion**.
    - Indexing, query optimization, and caching improve **performance and speed** in retrieving information

### **Advantages**

1. **Data Redundancy Control** – Minimizes data duplication using **Normalization**, ensuring efficient storage.
2. **Data Consistency** – Maintains data accuracy and prevents inconsistencies across multiple users.
3. **Improved Data Security** – Uses authentication, access control, and encryption to protect data.
4. **Data Integrity** – Enforces constraints like **primary keys and foreign keys** to maintain correctness.
5. **Concurrent Access & Multi-User Support** – Allows multiple users to access and modify data simultaneously while ensuring **ACID properties**.
6. **Backup & Recovery** – Provides mechanisms to recover data in case of system failures or crashes.
7. **Efficient Data Retrieval** – Uses indexing, query optimization, and caching for faster data access.
8. **Standardized Query Language** – Supports **SQL** for easy data manipulation and retrieval.
9. **Scalability** – Can handle growing amounts of data efficiently.
10. **Data Sharing & Centralized Management** – Enables multiple users to share data while maintaining control.

### **Disadvantages**

1. **High Initial Cost** – Requires investment in hardware, software, and skilled personnel.
2. **Complexity** – Requires expertise to design, manage, and maintain databases efficiently.
3. **Performance Overhead** – Extra processing for security, integrity checks, and concurrency control can slow down operations.
4. **Failure Impact** – A database crash or corruption can lead to significant data loss if backups are not properly managed.
5. **Frequent Updates & Maintenance** – Regular updates, tuning, and maintenance are necessary for smooth operation.
6. **Security Risks** – While DBMS provides security measures, improper configuration can make data vulnerable to attacks.
7. **Hardware & Storage Requirements** – Large-scale databases require significant storage and powerful hardware.

### **Tasks in DBMS**

- **Data Definition** – Defines database structures, including tables, fields, and relationships using **Data Definition Language (DDL)**.
- **Data Storage Management** – Efficiently stores and organizes data in tables.
- **Data Manipulation** – Supports inserting, updating, deleting, and retrieving data using **Data Manipulation Language (DML)**.
- **Data Retrieval** – Uses query languages like **SQL** to extract relevant information.
- **Query Processing & Optimization** – Executes and optimizes queries for faster data retrieval.
- **Transaction Management** – Ensures **ACID properties** (Atomicity, Consistency, Isolation, Durability) for reliable transactions.
- **Concurrency Control** – Manages multiple users accessing the database simultaneously without conflicts.
- **Data Security & Access Control** – Prevents unauthorized access through authentication, user permissions, and encryption.
- **Data Integrity Enforcement** – Ensures correctness using constraints like **primary keys, foreign keys, and unique constraints**.
- **Backup and Recovery** – Provides data recovery options in case of system failures or corruption.
- **Data Redundancy Control** – Minimizes duplicate data through **Normalization** techniques.
- **Indexing & Performance Tuning** – Uses indexing and optimization techniques for faster data retrieval.
- **Logging & Monitoring** – Keeps logs of database activities and monitors performance for maintenance.
- **Improved Data Sharing** – Enables multiple users to access and share data efficiently while maintaining security and consistency.

## File System Approach 

The **File System Approach** is a traditional method of storing and managing data in files on a storage device without a centralized database management system (**DBMS**). It relies on operating system file-handling mechanisms to store, retrieve, and manipulate data

### Characteristics

1. **Data is Stored in Files** – Each application has its own set of files, and data is stored in separate text or binary files.
2. **Manual Data Management** – Users and applications must manually handle data access, retrieval, and updates.
3. **Limited Data Sharing** – Data is difficult to share between applications due to lack of standardization.
4. **No Centralized Control** – Each file is managed separately without a common structure.
5. **Data Redundancy & Inconsistency** – The same data may be duplicated in multiple files, leading to inconsistencies

### Disadvantages

1. **Data Redundancy** – Duplicate data in multiple files wastes storage space.
2. **Data Inconsistency** – Changes in one file may not be reflected in others, leading to mismatches.
3. **Lack of Security** – No built-in authentication or access control mechanisms.
4. **Difficult Data Retrieval** – Searching for specific data requires manual or programmatic effort.
5. **Concurrency Issues** – Multiple users accessing the same file can cause conflicts and data corruption.
6. **No ACID Properties** – Transactions are not managed properly, leading to data integrity issues.
7. **Difficult Backup & Recovery** – Manual backups are required, and recovering lost data is complex.

### Advantages

1. **Simple & Easy to Use** – Requires no complex setup; files can be created and managed easily.
2. **Low Cost** – No need for expensive database software; works with basic operating system tools.
3. **Faster for Small-Scale Applications** – Works well for small tasks where a full **DBMS** is unnecessary.
4. **No Overhead** – No extra processing for security, transaction management, or query optimization.
5. **Efficient for Specific Tasks** – Useful for storing logs, configuration files, or temporary data.
6. **Less Hardware Requirement** – Does not require high-end hardware or large storage capacity.
7. **Customizable** – Developers can structure and manage files according to specific application needs.
    
    
    | FILE SYSTEM INTERFACE | DBMS INTERFACE |
    | --- | --- |
    | End User  | End User  |
    | Application Programs  | Application Programs  |
    | Interface through high lvl language | Interface through Query |
    | OS | DBMS |
    | Disk Storage (FS) | OS  |
    |  | Disk Storage (DB) |

| Feature | **FSA** | **DBMS**  |
| --- | --- | --- |
| **Data Storage** | Data is stored in separate files manually. | Data is stored in a structured format using tables. |
| **Data Redundancy** | High redundancy due to duplicate data in multiple files. | Minimizes redundancy through **Normalization**. |
| **Data Consistency** | Low consistency as changes in one file may not reflect in others. | Ensures consistency with constraints and **ACID properties**. |
| **Data Integrity** | No built-in integrity constraints. | Uses **primary keys, foreign keys**, and constraints for data accuracy. |
| **Security** | No authentication or access control. | Provides **user authentication, permissions, and encryption**. |
| **Data Sharing** | Difficult to share data across applications. | Multiple users and applications can easily share data. |
| **Concurrency Control** | No mechanism to handle multiple users accessing the same file. | Uses **locking, transactions**, and **ACID properties** for safe concurrent access. |
| **Data Retrieval** | Requires manual searching or custom programming. | Supports **SQL** for fast and efficient data retrieval. |
| **Backup & Recovery** | Manual backup; data recovery is complex. | Automated **backup and recovery** mechanisms available. |
| **Scalability** | Limited scalability; performance degrades with data growth. | Highly scalable; efficiently handles large amounts of data. |
| **Cost** | Low initial cost; does not require additional software. | High setup cost due to software, hardware, and management. |
| **Complexity** | Simple and easy to use. | More complex but provides advanced features. |


## View of Data 
**Schema:** The overall design of the database is called schema

For example - In a program we do variable declaration and assignment of values to the variable. The variable declaration is called schema and the value assigned to the variable is called instance. The schema for the student record can be

| Roll No | Name | Marks |
| --- | --- | --- |

**Instances:** When information is inserted or deleted from the database then the database gets changed. The collection of information at particular moment is called instances. For example - following is an instance of student database

| Roll No | Name | Marks |
| --- | --- | --- |
| 10 | AAA | 43 |
| 20 | BBB | 67 |

**Types of Schema:** The database has several schema based on the levels of abstraction.

**(1) Physical Schema:** The physical schema is a database design described at the physical level of abstraction.

**(2) Logical Schema:** The logical schema is a database design at the logical level of abstraction.

**(3) Subschema:**A database may have several views at the view level which are called subschemas.

## Data Abstraction 

Data abstraction in DBMS refers to the process of hiding unnecessary details from end users while providing only the relevant data. Database systems involve complex data structures and relationships, but data abstraction ensures that users interact with data without needing to understand these complexities.

### **Levels of Data Abstraction**

![image.png](attachment:60af6bd4-afcc-4d09-9593-a603752dd0f4:image.png)

1. **Physical Level (Internal Level)**
- Lowest level of abstraction.
- Defines how data is stored using data structures, indexing, and access methods.
- Concerned with database performance, optimization, and storage mechanisms.
- **Example:**
    - A customer’s information is stored in tables, but at the physical level, it is managed as data blocks.
    - Indexed file organization allows record retrieval using indexes, while sequential file organization stores records in a continuous manner.
1. **Logical Level (Conceptual Level)**
- Middle level of abstraction.
- Defines what data is stored and the relationships between them.
- Represents entities, attributes, and relationships among tables.
- Less complex than the physical level but still requires knowledge of the database schema.
- **Example:**
    - A table **"Students"** with attributes **student_name, roll_no, student_ID, and marks**.
    - A table **"Teachers"** containing teacher_ID, address, and linked student_IDs (foreign key).
1. **View Level (External Level)**
- Highest level of abstraction.
- Provides different views of the database for different users, showing only relevant data.
- Facilitates interaction with the database using Graphical User Interfaces (GUIs).
- **Example:**
    - A teacher’s view of a student database may show **student names and marks**, while an admin may access **fees and attendance records**.

---

### **Features of Data Abstraction**

**1. Multiple Levels of Abstraction**

DBMS provides three levels of abstraction:

- **External Level (View Level):** Users see only the relevant part of the database without needing to know its internal structure.
- **Conceptual Level (Logical Level):** Defines the structure and relationships of data without focusing on physical storage.
- **Internal Level (Physical Level):** Deals with the actual storage of data in memory and databases.

**2. Separation of Concerns**

- Different users (end users, database designers, and administrators) can interact with the database at different abstraction levels.
- Ensures that logical design and physical storage are independent, simplifying database management.

**3. Mapping Between Levels**

- Provides a structured way to link different abstraction levels, ensuring changes at one level do not affect others.
- Example: A change in storage structure at the physical level does not affect the conceptual or external levels.

**4. Data Independence**

- **Logical Data Independence:** Changes in the logical structure do not impact external views.
- **Physical Data Independence:** Changes in storage methods do not affect logical schema.

**5. Transparency** 

- Hides complex implementation details, providing a simplified and consistent view of data to users.
- Users can retrieve and manipulate data without knowing its actual storage or retrieval mechanisms.

**6. Security and Controlled Access**

- Restricts access to sensitive data by defining different views for different users.
- Ensures that unauthorized users cannot see or modify restricted information.

**7. Enhanced Maintainability & Flexibility**

- Simplifies updates, modifications, and scaling of the database.
- Reduces the impact of structural changes on users and applications.

---

### Advantages of Data Abstraction

**Simplifies User Interaction**

– Users do not need to understand storage complexities.

**Improves Security**

– Sensitive data is hidden, ensuring restricted access.

**Reduces Complexity**

– Users work with simplified views, while DBMS handles complex operations.

**Increases Flexibility**

– Structural changes in the database do not affect user experience.

**Enhances Data Integrity**

– Ensures consistent and correct data storage.

---


## Data Independance 

**Data Independence** refers to the ability to modify a database schema at one level without affecting the schema at the next higher level. It ensures that changes in storage, structure, or organization do not impact the way users interact with data. This is one of the key characteristics of a **(DBMS)** as it helps in managing large amounts of data efficiently and ensures adaptability over time.

![image.png](attachment:731adf55-0723-41d6-b52f-7656f0a670d0:image.png)

**Importance of Data Independence:**

- A database contains vast amounts of data that must be frequently updated to meet changing requirements.
- A **multi-layer architecture** is used in DBMS to ensure that modifications at one level do not affect other levels.
- The **three levels of abstraction**—Physical Level, Logical Level, and View Level—help achieve data independence.
- Data independence improves maintainability, flexibility, security, and cost-effectiveness in database management.

### Physical Data Independence

Physical data independence is the ability to modify the **physical schema** (how and where data is stored) without affecting the **logical schema** (conceptual structure) or the **view level** (user interactions).

**Key Aspects:**

- Changes in storage structure, indexing methods, or hardware do not require changes in the database schema or applications.
- Helps in optimizing storage and improving performance without impacting user accessibility.

**Examples:**

1. Changing from one data structure to another (e.g., switching from B-trees to hash indexes).
2. Using a new storage technology, such as moving from HDDs to SSDs or cloud storage.
3. Changing the location of database files from one drive to another.
4. Modifying the database file organization (e.g., partitioning tables for faster queries).

---

### **Logical Data Independence**

Logical data independence is the ability to modify the **logical schema** (organization, structure, or relationships of data) without affecting the **external schema** (user views and application programs).

**Key Aspects:**

- Ensures that applications remain unaffected by changes in data structure.
- Compared to physical data independence, **logical data independence is harder to achieve** because changes in relationships or attributes might require modifications in queries and reports.

**Examples:**

1. Adding, modifying, or deleting an attribute, entity, or relationship without rewriting existing application programs.
2. Merging two tables into one or splitting an existing table into multiple tables.
3. Changing constraints or data types of existing attributes without affecting user interactions

| **Feature** | **PDI** | **LDI** |
| --- | --- | --- |
| **Definition** | Changes in physical storage do not affect logical structure. | Changes in logical structure do not affect user views or applications. |
| **Affects** | Storage structures, file organization, indexing. | Database schema, tables, attributes, relationships. |
| **Ease of Implementation** | Easier to achieve. | Harder to achieve. |
| **Ease of Retrieving** | we can retrieve it easily  | retrieving is very difficult because the data mainly depends on its logical structure not its physical location |
| **Types of Schema** | the internal schema is the primary concern | the conceptual schema is the primary concern  |
| **Examples** | Changing storage devices, file locations. | Adding new attributes, splitting tables. |

## EF Codd Rules 
Dr. **Edgar F. Codd**, a computer scientist, proposed a set of **12 rules** (plus Rule 0) to define what qualifies as a **Relational Database Management System (RDBMS)**. These rules ensure **data integrity, consistency, usability, and independence** in database management

 - **Rule 0: The Foundation Rule**
    - A database must be structured in a **relational manner**, and its management should be entirely based on **relational capabilities** to be considered an RDBMS.
    
- **Rule 1: The Information Rule**
    - All **data and metadata** (information about the database) must be stored in tables as values within cells.
    - The entire database should follow a **tabular format** to maintain consistency.
- **Rule 2: The Guaranteed Access Rule**
    - Each data item must be accessible using a **combination of table name, primary key (row identifier), and attribute name (column identifier)**.
    - This ensures that no data is left inaccessible.
- **Rule 3: Systematic Treatment of NULL Values**
    - **NULL values** (representing missing or unknown data) should be handled uniformly across the system.
    - NULL should be **distinct** from blank spaces or zero values.
- **Rule 4: Active Online Catalog Rule**
    - Metadata (information about database structure) should be **stored within the database itself** as tables.
    - Users should be able to query this catalog using the same language (e.g., SQL) used for regular data queries.
- **Rule 5: The Comprehensive Data Sublanguage Rule**
    
    The database should support a **single, well-defined language** (such as SQL) for:
    
    - **Data Definition (DDL)** – Creating and modifying tables.
    - **Data Manipulation (DML)** – Querying, inserting, updating, and deleting records.
    - **Access Control** – Managing security and authorization.

- **Rule 6: The View Updating Rule**
    - A **view** (a virtual table based on query results) should be updatable if it is **theoretically possible** to do so.
    - This ensures **data consistency** when using views.
- **Rule 7: High-level Insert, Update, and Delete**
    - The system should allow **set-level operations**, meaning users can **insert, update, or delete multiple rows** at once using a single query.
    - This improves **efficiency and usability**.
- **Rule 8: Physical Data Independence**
    - Changes in **physical storage structures** (e.g., moving data to different disks) **should not affect applications** that access the database.
    - This ensures **hardware flexibility** without disrupting the system.
- **Rule 9: Logical Data Independence**
    - Changes in the **logical schema** (e.g., adding/modifying tables or columns) **should not require changes in application programs**.
    - This makes the system more **adaptable** to future modifications.
- **Rule 10: Integrity Independence**
    - **Integrity constraints** (such as **primary keys, foreign keys, and unique constraints**) must be **defined separately from applications** and stored within the database catalog.
    - These constraints should be **enforced automatically** by the system.
- **Rule 11: Distribution Independence**
    - Whether the database is **centralized or distributed across multiple locations**, it should behave the **same way** for users.
    - Distribution should be **transparent**, meaning users don’t need to know where the data is physically stored.
- **Rule 12: Non-Subversion Rule**
    - The system should prevent users from **bypassing security and integrity constraints** through low-level access methods (e.g., file handling).
    - Even if a system provides direct access to records, **security measures must not be compromised**.

## DB: Languages 
Database languages are used to create, manipulate, retrieve, and manage data in a **Database Management System (DBMS)**. The main types of database languages are:

**1. Data Definition Language (DDL)**

- Used to **define and modify** the database structure.
- Includes commands for **creating, altering, and deleting** tables and schemas.
    
    
    | Command | Description |
    | --- | --- |
    | `CREATE` | Creates a new database, table, or view |
    | `ALTER` | Modifies an existing database structure |
    | `DROP` | Deletes a database, table, or column |
    | `TRUNCATE` | Removes all records from a table without deleting its structure |
    
    ```sql
    CREATE TABLE Employees (
        EmployeeID INT PRIMARY KEY,
        Name VARCHAR(50),
        Age INT,
        Department VARCHAR(50)
    );
    
    ALTER TABLE Employees ADD Salary DECIMAL(10,2);
    
    DROP TABLE Employees;
    
    TRUNCATE TABLE Employees;
    ```
    

**2. Data Manipulation Language (DML)**

- Used to **retrieve and manipulate** data stored in the database.
- Allows **insertion, deletion, modification, and retrieval** of data.

| Command | Description |
| --- | --- |
| `SELECT` | Retrieves data from a database |
| `INSERT` | Adds new data to a table |
| `UPDATE` | Modifies existing records in a table |
| `DELETE` | Removes records from a table |

**Types of DML:**

- **Procedural DML** – Requires the user to specify **how** to retrieve data.
- **Non-Procedural DML** – Requires the user to specify **what** data to retrieve, letting the system handle retrieval (e.g., SQL).
    
    ```sql
    SELECT Name, Age FROM Employees WHERE Department = 'HR';
    
    INSERT INTO Employees (EmployeeID, Name, Age, Department, Salary) 
    VALUES (101, 'Alice', 30, 'IT', 50000.00);
    
    UPDATE Employees SET Salary = 55000.00 WHERE EmployeeID = 101;
    ```
    

**3. Data Control Language (DCL)**

- Used to **control user access** to the database.
- Ensures **security and authorization** for database operations.
    
    
    | Command | Description |
    | --- | --- |
    | `GRANT` | Gives users permissions to perform database operations |
    | `REVOKE` | Removes permissions from a user |
    
    ```sql
    GRANT SELECT, INSERT ON Employees TO user1;
    
    REVOKE INSERT ON Employees FROM user1;
    ```
    

**4. Transaction Control Language (TCL)**

- Used to **manage transactions** in a database to ensure **consistency and integrity**.
- Helps in **rollback, commit, and savepoint** operations.
    
    
    | Command | Description |
    | --- | --- |
    | `COMMIT` | Saves all changes made by the transaction permanently |
    | `ROLLBACK` | Reverts all changes made in the current transaction |
    | `SAVEPOINT` | Creates a checkpoint in a transaction, allowing partial rollbacks |
    
    ```sql
    BEGIN TRANSACTION;
    UPDATE Employees SET Salary = 60000 WHERE EmployeeID = 101;
    COMMIT;
    
    BEGIN TRANSACTION;
    UPDATE Employees SET Salary = 65000 WHERE EmployeeID = 101;
    ROLLBACK;
    
    BEGIN TRANSACTION;
    UPDATE Employees SET Salary = 60000 WHERE EmployeeID = 101;
    SAVEPOINT BeforeRaise;
    UPDATE Employees SET Salary = 65000 WHERE EmployeeID = 101;
    ROLLBACK TO BeforeRaise;
    
    ```

## DB: Design Process 
- The **database design process** is a structured approach to developing a **Database Management System (DBMS)** that ensures **efficient data storage, retrieval, integrity, and security**.
- A well-designed database meets user requirements while maintaining **scalability, performance, and reliability**.
- The database design process consists of several **phases**, each playing a crucial role in ensuring the success of the database application.By following these phases:
1. **Requirement Collection & Analysis** – Gather user needs.
2. **Conceptual Design** – Create ER models.
3. **Logical Design** – Convert to relational schema.
4. **Physical Design** – Optimize storage and indexing.
5. **Implementation & Data Loading** – Create and populate the database.
6. **Testing & Evaluation** – Ensure functionality and performance.
7. **Maintenance & Optimization** – Continuously monitor and improve.

---

**1. Requirement Collection and Analysis Phase**

This phase involves gathering detailed **user and functional requirements** for the database.

**Key Activities:**

- Conduct **interviews** and **meetings** with prospective users to understand their needs.
- Identify **data flow, user operations, transaction frequency, and security requirements**.
- Document requirements using **diagrams** such as:
    - **Sequence Diagrams** (User interactions)
    - **Data Flow Diagrams (DFDs)** (Data movement)
    - **Use Case Scenarios** (Real-world use cases)

**Outcome:**

- A **comprehensive requirements document** that serves as the foundation for database design.
- Defines the **functional scope** of the database.
- This phase plays a **vital role** in the success of the database and ensures that **all stakeholder needs** are accounted for.

---

**2. Conceptual Design Phase**

In this phase, a **conceptual schema** is developed to represent the **overall structure of the database** without focusing on technical implementation details.

**Key Activities:**

- Select an appropriate **data model** (e.g., **Entity-Relationship (ER) Model**).
- Identify **entities, attributes, relationships, and constraints**.
- Represent the data using an **ER diagram**.

**Outcome:**

- A **high-level conceptual schema** that ensures all user requirements are met without conflicts.
- The design remains **independent of any specific RDBMS** (e.g., MySQL, PostgreSQL).
- Acts as a **communication tool** between designers and end users.

---

**3. Logical Design Phase**

This phase translates the **conceptual schema** into a **relational schema** that can be implemented in an RDBMS.

**Key Activities:**

- Convert **ER diagrams** into **tables, attributes, primary keys (PK), and foreign keys (FK)**.
- Define **constraints** (e.g., `NOT NULL`, `UNIQUE`, `CHECK`) to ensure data integrity.
- Normalize data to remove redundancy and improve consistency.

**Outcome:**

- A **relational schema** that is **structured and optimized** for efficient data operations.
- Provides a **detailed framework** for physical database implementation.

**Example:**

| **Student Table** | **Course Table** | **Enrollment Table** |
| --- | --- | --- |
| Student_ID (PK) | Course_ID (PK) | Student_ID (FK) |
| Name | Course_Name | Course_ID (FK) |
| Age |  |  |

---

**4. Physical Design Phase**

In this phase, technical **decisions about storage and performance optimization** are made.

**Key Activities:**

- Define **storage structures, indexing, partitioning, and file organization**.
- Optimize for **performance, scalability, and security**.
- Choose **appropriate database servers and application environments**.

**Outcome:**

- A **physical design specification** that includes:
    - Database **storage architecture**.
    - Indexing strategies to **improve query performance**.
    - Security configurations and **access control policies**.

---

**5. Implementation and Data Loading Phase**

This phase involves the **creation of the database** and **loading of data**.

**Key Activities:**

- Implement the database using **SQL DDL (Data Definition Language) commands**.
- Populate tables manually or automatically by **migrating data from an existing system**.
- Configure **database security and user roles**.

**Outcome:**

- A **fully operational database** with initial data loaded.
- Ready for **testing and validation**.

**Example:**

```sql
sql
CopyEdit
CREATE TABLE Student (
    Student_ID INT PRIMARY KEY,
    Name VARCHAR(50),
    Age INT
);

INSERT INTO Student VALUES (1, 'Alice', 20);

```

---

**6. Testing and Evaluation Phase**

This phase ensures that the database performs correctly and meets **functional and non-functional requirements**.

**Key Activities:**

- Test **data integrity, concurrency, security, and performance**.
- Optimize database queries for **efficiency**.
- Identify issues and apply **modifications if needed** (e.g., improving indexing, adjusting constraints).

**Outcome:**

- A **fully optimized** and **functional** database system.
- Any performance issues or security risks are addressed before deployment.

**Example:**

- Testing whether a user can register for a **non-existent course**:

```sql

SELECT * FROM Enrollment WHERE Course_ID NOT IN (SELECT Course_ID FROM Course);
```

---

**7. Maintenance and Optimization Phase**

This phase ensures the database remains **efficient, secure, and up to date** over time.

**Key Activities:**

- Regular **monitoring and performance tuning**.
- Implement **backup and recovery plans** to prevent data loss.
- Modify the schema if **business requirements change**.

**Outcome:**

- A **reliable and well-maintained database** that continues to perform efficiently.
- Security vulnerabilities and performance bottlenecks are periodically addressed.

---

## DB: Architecture 
- The DBMS design depends upon its architecture. The basic client/server architecture is used to deal with a large number of PCs, web servers, database servers and other components that are connected with networks.
- The client/server architecture consists of many PCs and a workstation which are connected via the network.
- DBMS architecture depends upon how users are connected to the database to get their request done.

### **1 Tier**

In **1-Tier Architecture**, the database, client, and server are all located on the same machine. This architecture allows the user to directly interact with the database, making it suitable for personal or standalone applications.

![Screenshot 2025-03-24 at 8.36.31 AM.png](attachment:f8b1d1d1-2af6-4233-b341-52028d8b4ec5:Screenshot_2025-03-24_at_8.36.31_AM.png)

- **Example: Microsoft Excel** is a one-tier system where data is stored and processed on the same computer.

Features

- **All-in-One System**: The user interface (UI), application logic, and data are all managed on the same machine.
- **No External Network or Server Connection**: Everything is self-contained, requiring no external connections.

Advantages

✔ **Simple Setup** – Only one machine is needed.

✔ **Cost-Effective** – No need for additional hardware or network infrastructure.

✔ **Easy Deployment** – Ideal for small projects with minimal setup requirements

---

### **2 Tier**

The 2-Tier Architecture follows a client-server model, where the client directly communicates with the database server using APIs like ODBC/JDBC. The server handles query processing and transaction management, while the client runs the user interface and application logic.

![Screenshot 2025-03-24 at 8.34.59 AM.png](attachment:269e38f1-c347-45fb-85b9-7e48225816ab:Screenshot_2025-03-24_at_8.34.59_AM.png)

- **Example**: Library Management System
    
    1. Client Layer (Tier 1) – A desktop application used to search books, issue them, and check due dates.
    
    2. Database Layer (Tier 2) – Stores all book records, user information, and transaction logs.
    
    When a user searches for a book, the client sends a request to the database, which processes the query and returns the result.
    

**Advantages**

✔ Faster Access – Direct communication speeds up query execution.

✔ Scalability – Easy to add clients or upgrade hardware.

✔ Low Cost – More affordable than 3-tier and multi-tier architectures.

✔ Easy Deployment – Simple to set up compared to 3-tier systems.

---

### **3 Tier**

In 3-Tier Architecture, an additional application server sits between the client and database, acting as an intermediary. The client does not directly communicate with the database, improving security and scalability.

![Screenshot 2025-03-24 at 8.34.25 AM.png](attachment:8eb5cac6-0417-4d9d-b446-3918f04ad8d0:Screenshot_2025-03-24_at_8.34.25_AM.png)

**Example**: E-Commerce Store

1. Client (User) – Searches for a product and adds it to the cart.

2. Application Server (Processing) – Checks product availability, applies discounts, and calculates the total price.

3. Database Server – Stores product details, order history, and user information.

**Advantages**

✔ Enhanced Scalability – Distributes workload, reducing direct database connections.

✔ Data Integrity – The middle layer prevents data corruption and enhances consistency.

✔ Improved Security – Restricts direct access to the database, reducing unauthorized data access.

**Disadvantages**

✖ Increased Complexity – More components mean higher setup and maintenance costs.

✖ Slower Interaction – Additional layers increase processing time.


## DBS: Architure 

![image.png](attachment:6a477819-4252-4f9b-bcbd-5d9ad72a00bd:image.png)

### System Users

A database system has four primary types of users:

**1. Naive Users**

- Unsophisticated users who interact with the system through pre-written application programs.
- Example: A ticket booking clerk using a reservation system.

**2. Application Developers**

- Responsible for creating software applications that interact with the database.
- Develop APIs to facilitate communication between applications and the database.

**3. Sophisticated Users**

- Interact with the database without writing programs.
- Use database query languages to form requests.
- Their queries are processed by the query processor, which translates high-level DML statements into instructions understood by the storage manager.

**4. Database Administrator (DBA)**

- The DBA is responsible for managing and maintaining the database system.Key Role of DMA
    1. Database Installation & Configuration
    2. Set up database software, parameters, file structures, and security settings.
    3. Backup & Recovery
    4. Ensure regular backups and implement a disaster recovery plan.
    5. Security Management
    6. Set up user accounts, define access permissions, and encrypt sensitive data.
    7. Performance Tuning
    8. Optimize database schema, tune queries, and manage system resources (memory, CPU, storage).
    9. Maintenance & Upgrades
    10. Perform tasks like index optimization, defragmentation, and database migrations.

---

The functional components of a DBMS can be broadly divided into:

1. Query Processor

2. Storage Manager

### Query Processor

- The query processor is responsible for interpreting and executing user queries.
- It transforms high-level queries (SQL) into low-level operations that the database engine can execute.

**Functions of the Query Processor**

- Simplifies data access for users.
- Users do not need to understand the system’s physical implementation.
- Ensures quick query processing and updates.

**Query Processor Components**

**1. DDL Interpreter**

- Processes Data Definition Language (DDL) statements.
- Handles commands for creating, modifying, and deleting database structures (tables, indexes, views, constraints).

**2. DML Compiler & Organizer**

- Processes Data Manipulation Language (DML) statements such as INSERT, UPDATE, DELETE, and SELECT.
- Converts high-level DML queries into low-level database operations.
- DML Compiler: Translates DML queries into executable instructions.
- DML Organizer: Executes the compiled query plan.

**3. Application Program Object Code (APOC)**

- Compiled version of an application program that interacts with the database.
- Converts source code into machine-readable form.

**4. Compiler & Linker**

- Application programmers write source code.
- The compiler and linker process this code, linking it to DML queries before execution.

**5. Query Evaluation Engine**

- Executes user queries and retrieves the requested data.**Key Functions:**
- Query Parsing & Validation: Ensures correct syntax.
- Query Optimization: Determines the most efficient way to execute a query.
- Query Plan Generation: Creates an execution plan based on optimization.
- Data Retrieval & Manipulation: Interacts with the storage manager to fetch data efficiently.
- Concurrency Control & Transaction Management: Ensures data consistency in a multi-user environment.
- Result Formatting & Delivery: Formats query results for the user.

---

### Data Storage Manager

- Data Storage Manager also known as “Database Control System”, is generally a program that provides an interface between the data/information stored and the queries received.
- It is responsible for storing, retrieving, and updating database records.
- It helps us to maintain the integrity and consistency of the database by applying the constraints.
- It is a highly flexible and scalable product that provides us with the capability of fully managed storage.

**Functions of the Storage Manager**

- Converts DML statements into low-level file system commands.
- Handles large storage requirements (hundreds of gigabytes to terabytes).
- Moves data between disk storage and main memory as needed.

**Components of the Storage Manager**

**1. Authorization & Integrity Manager**

- Enforces integrity constraints and verifies user access rights.

**2. Transaction Manager**

- Ensures database consistency despite system failures.
- Handles concurrent transactions without conflicts.

**3. File Manager**

- Allocates storage space and manages data structures on disk.

**4. Buffer Manager**

- Fetches data from disk storage to main memory.
- Manages memory caching of frequently accessed data.
- Enabling the database to handle data sizes that are much larger than the size of the main memory.

---

### Disk Storage in DBMS

The storage manager implements several data structures as part of the physical system implementation:

**1. Data Files**

- Store actual database records.

**2. Data Dictionary**

- Stores metadata about the database structure, including:
- Table names, attributes, data types, and constraints.
- Indexes, views, and authorized users.
- Storage methods and optimization details.

**3. Indices**

- Provide fast access to data using pointers.
- Example: Hashing can be used for quicker lookups in some cases.

**4. Statistical Data**

- Stores statistical metadata, such as record count and block distribution.
- Helps optimize query execution.

---