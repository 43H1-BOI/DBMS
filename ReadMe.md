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