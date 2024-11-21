# **DBMS Questiion Paper Solution**

### **Q1: Differentiate Between Weak and Strong Entity Type**

| **Feature**        | **Weak Entity**                                                 | **Strong Entity**                                 |
| ------------------ | --------------------------------------------------------------- | ------------------------------------------------- |
| **Dependency**     | Depends on a strong entity for identification.                  | Exists independently and does not rely on others. |
| **Primary Key**    | Lacks a complete primary key; uses a foreign key + partial key. | Has a unique primary key.                         |
| **Representation** | Represented with a double rectangle in ER diagrams.             | Represented with a single rectangle.              |
| **Example**        | `Dependent` (relies on `Employee`)                              | `Employee` entity                                 |

---

### **Q2: What is a Multivalued Attribute? Give Example.**

- **Definition:** A multivalued attribute is one that can have multiple values for a single entity instance.
- **Example:**
  - Entity: `Student`
  - Multivalued Attribute: `Phone_Numbers` (A student can have multiple phone numbers like 1234567890 and 9876543210).

---

### **Q3: State Any 5 Properties of Relation**

1. **Rows Uniqueness (Tuples):**  
   No two rows in a relation can have identical values for all attributes.

2. **Atomicity of Attributes:**  
   Each attribute must hold atomic (indivisible) values; no composite or multivalued attributes allowed.

3. **Order Irrelevance:**  
   The order of rows and columns in a relation does not affect its data or meaning.

4. **Attribute Uniqueness:**  
   Each attribute must have a unique name within a relation.

5. **Domain Constraint:**  
   The values of each attribute must belong to a defined domain (e.g., integers, dates).

---

### **Q4: Explain Stored and Derived Attribute with Examples**

1. **Stored Attribute:**

   - **Definition:** An attribute physically stored in the database.
   - **Example:** `Date_Of_Birth` in a `Person` entity is a stored attribute.

2. **Derived Attribute:**
   - **Definition:** An attribute that can be derived from stored attributes but is not physically stored in the database.
   - **Example:** `Age` can be derived from `Date_Of_Birth` and the current date.

---

### **Q5: Explain Any 5 Aggregate Functions**

1. **SUM():**

   - Calculates the sum of a numeric column.
   - **Example:** `SELECT SUM(Salary) FROM Employees;`

2. **AVG():**

   - Computes the average of a numeric column.
   - **Example:** `SELECT AVG(Marks) FROM Students;`

3. **COUNT():**

   - Returns the number of rows that match a condition.
   - **Example:** `SELECT COUNT(*) FROM Orders;`

4. **MIN():**

   - Finds the smallest value in a column.
   - **Example:** `SELECT MIN(Salary) FROM Employees;`

5. **MAX():**
   - Finds the largest value in a column.
   - **Example:** `SELECT MAX(Salary) FROM Employees;`

---

### **Q6: Write Any 5 Disadvantages of DBMS**

1. **Cost:**

   - High initial and operational cost for hardware, software, and skilled personnel.

2. **Complexity:**

   - DBMS systems are complex to design, implement, and maintain.

3. **Performance Issues:**

   - For small datasets or simple tasks, DBMS may be slower than traditional file systems.

4. **Security Risks:**

   - Centralized storage increases vulnerability to data breaches and unauthorized access.

5. **Overhead:**
   - Requires additional resources (e.g., memory and processing power) to manage databases efficiently.

---

### **Q7: Write Any 5 DDL Commands**

1. **CREATE:**

   - Used to create database objects like tables, views, or schemas.
   - **Example:** `CREATE TABLE Students (ID INT, Name VARCHAR(50));`

2. **ALTER:**

   - Modifies the structure of existing database objects.
   - **Example:** `ALTER TABLE Students ADD Age INT;`

3. **DROP:**

   - Deletes a database object, such as a table or view.
   - **Example:** `DROP TABLE Students;`

4. **TRUNCATE:**

   - Removes all rows from a table without logging individual row deletions.
   - **Example:** `TRUNCATE TABLE Employees;`

5. **RENAME:**
   - Renames a database object like a table or column.
   - **Example:** `RENAME TABLE Old_Name TO New_Name;`

---

### **Q8: State Referential Integrity Constraint**

- **Definition:**  
  A referential integrity constraint ensures that a foreign key in one table corresponds to a valid primary key in another table.

- **Example:**
  - **Parent Table:** `Departments` with `Department_ID` as the primary key.
  - **Child Table:** `Employees` with `Department_ID` as a foreign key.
  - The constraint ensures that every `Department_ID` in `Employees` must exist in `Departments`.






### Q3a) Four of Codd's Rules:

Codd's 12 rules are a set of guidelines proposed by Dr. Edgar F. Codd to define what constitutes a relational database management system (RDBMS). Below are four of them:

1. **Rule 1 - Information Rule:**
   All information in a relational database is represented explicitly as values in tables (also known as relations). This includes both data and metadata (e.g., column names, table names). Everything must be stored in a tabular format.

2. **Rule 2 - Guaranteed Access Rule:**
   Every piece of data in a relational database should be accessible by using a combination of table name, primary key, and attribute name. This ensures that the data is not hidden in any other way and can be retrieved with certainty.

3. **Rule 3 - Systematic Treatment of Null Values:**
   Null values (representing missing or unknown information) should be treated systematically in the database. Null should not be confused with zero or empty strings. All operations on the database should recognize and correctly handle null values.

4. **Rule 5 - Data Independence:**
   The data in a relational database should be logically independent from the application programs that use the data. Changes to the database's structure should not require changes to application programs, thus supporting data independence.

---

### Q3b) Types of Database Users and Role of Database Administrator (DBA):

**Types of Database Users:**

1. **End Users:**
   These are the people who directly interact with the database through applications. They can be classified into:
   - **Naive users**: These users interact with the database using pre-designed applications, often through user interfaces (e.g., query forms).
   - **Parametric users**: These users interact with the database through a set of queries and commands (e.g., SQL users).
   - **Sophisticated users**: These users have expertise in the database system and might develop complex queries, reports, or use programming interfaces.

2. **Application Programmers:**
   These users write application programs that interact with the database using languages like SQL, Java, or Python. They create software that manipulates the data stored in the database.

3. **Database Administrators (DBAs):**
   DBAs are responsible for the overall management and maintenance of the database system. Their tasks include:
   - Database design and implementation.
   - Ensuring data security, integrity, and availability.
   - Performing regular backups and recovery operations.
   - Managing database performance and optimization.
   - Creating user access controls and permissions.
   - Handling data migration, patching, and upgrades.

---

### Q4a) What is Normalization? Why Do We Normalize a Database? Explain the Second Normal Form (2NF) with an Example:

**Normalization:**
Normalization is the process of organizing the data in a database to reduce redundancy and improve data integrity. This process involves dividing large tables into smaller, related tables and ensuring that relationships among the data are well-structured.

**Why Normalize a Database:**
- **Reduce Data Redundancy:** It avoids the unnecessary duplication of data.
- **Improve Data Integrity:** Normalization ensures that the data is consistent and follows rules that help maintain its accuracy.
- **Simplify Data Structure:** It makes querying and updating the data easier and more efficient.
- **Improve Storage Efficiency:** By eliminating duplicate data, normalization can reduce the overall storage requirements.

**Second Normal Form (2NF):**
A table is in 2NF if it is in **First Normal Form (1NF)** and if all non-key attributes are fully functionally dependent on the primary key (no partial dependencies).

- **1NF**: The table must have a primary key and all attributes must contain atomic values (no repeating groups).
- **2NF**: The table must not have any partial dependency. This means that if a table has a composite primary key, all non-key attributes must depend on the entire primary key, not just part of it.

**Example of 2NF:**

Consider a table that stores information about students and their enrolled courses:

| StudentID | CourseID | StudentName | Instructor |
|-----------|----------|-------------|------------|
| 1         | CS101    | Alice       | Prof. A    |
| 2         | CS101    | Bob         | Prof. A    |
| 3         | MATH101  | Charlie     | Prof. B    |

This table is in **1NF** but violates **2NF** because `StudentName` is partially dependent on `StudentID` and `Instructor` is partially dependent on `CourseID`. To convert it into 2NF, we split the table into two:

- **Student Table**:
  | StudentID | StudentName |
  |-----------|-------------|
  | 1         | Alice       |
  | 2         | Bob         |
  | 3         | Charlie     |

- **Course Enrollment Table**:
  | StudentID | CourseID | Instructor |
  |-----------|----------|------------|
  | 1         | CS101    | Prof. A    |
  | 2         | CS101    | Prof. A    |
  | 3         | MATH101  | Prof. B    |

Now, both tables are in 2NF, as all non-key attributes are fully functionally dependent on the entire primary key.

---

### Q4b) Three Basic Relational Algebra Operators:

Relational algebra provides a set of operations that can be used to query and manipulate data in relational databases. The basic operators are:

1. **Select (σ):**
   The select operator is used to filter rows based on a given condition (predicate). It returns a subset of rows from a table.
   - Example: `σ(condition)(Table)`
   - Query: Select all students who scored above 90 in a table of student scores.
   
   ``` 
   σ(Score > 90)(Students)
   ```

2. **Project (π):**
   The project operator is used to select specific columns from a table. It helps in eliminating unwanted attributes and focusing on the relevant ones.
   - Example: `π(column1, column2, ...)(Table)`
   - Query: Retrieve the names and ages of all employees from an employees table.

   ``` 
   π(Name, Age)(Employees)
   ```

3. **Join (⨝):**
   The join operator is used to combine related tuples from two relations based on a common attribute. There are various types of joins, but the most basic is the **natural join**.
   - Example: `R ⨝ S` where `R` and `S` are tables that share one or more common attributes.
   - Query: Retrieve all details of students and their respective courses by joining the Students and Courses tables on `StudentID`.
   
   ``` 
   Students ⨝ Courses
   ```

These operators are fundamental in manipulating relational data and forming complex queries for retrieving useful information from a database.


### Q5a) Definitions:

**i) Candidate Key:**
A *candidate key* is a set of one or more attributes (columns) that can uniquely identify a record in a database table. It is a minimal superkey, meaning no subset of the candidate key can uniquely identify the record. A table can have multiple candidate keys, but one will be chosen as the primary key.

**ii) Primary Key:**
A *primary key* is a special candidate key chosen to uniquely identify each record in a database table. It must have the following properties:
- Uniqueness: No two rows can have the same value for the primary key.
- Non-nullability: Every record must have a value for the primary key (cannot be NULL).

A table can only have one primary key.

**iii) Alternate Key:**
An *alternate key* refers to any candidate key that is not selected as the primary key. These are essentially secondary options that could uniquely identify records, but are not used as the primary key.

---

### Q5b) What is Mapping Cardinality? Explain ALTER and UPDATE command:

**Mapping Cardinality:**
Mapping cardinality refers to the relationship between two sets or tables in a database. It defines how many instances of one entity are related to instances of another entity. In relational databases, it is typically represented by the cardinality of relationships between tables. The types of cardinalities are:
- **One-to-One (1:1):** One record in a table is related to exactly one record in another table.
- **One-to-Many (1:M):** One record in a table is related to multiple records in another table.
- **Many-to-Many (M:N):** Multiple records in one table are related to multiple records in another table.

**ALTER Command:**
The `ALTER` command is used to modify the structure of an existing database object (like a table). It can perform operations such as adding, deleting, or modifying columns, or even renaming a table. Example:
- `ALTER TABLE table_name ADD column_name data_type;`
- `ALTER TABLE table_name DROP COLUMN column_name;`

**UPDATE Command:**
The `UPDATE` command is used to modify the data within a table. It allows you to change existing records based on specific conditions. Example:
- `UPDATE table_name SET column_name = new_value WHERE condition;`

---

### Q5c) What is Null?

**Null:**
In database terminology, *NULL* represents the absence of a value or the lack of data in a field. It is not the same as an empty string or zero; it simply means that the value is unknown, undefined, or missing. A field containing a NULL value does not hold any actual data, and special handling is required when querying or performing operations involving NULL values (e.g., `IS NULL` or `IS NOT NULL`).