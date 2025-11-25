# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--
<img width="1031" height="345" alt="image" src="https://github.com/user-attachments/assets/fbb1b984-1831-4c85-95ad-780571fe2605" />

```
CREATE TABLE Departments (
    DepartmentID INTEGER,
    DepartmentName TEXT
);
```

**Output:**

<img width="1231" height="440" alt="image" src="https://github.com/user-attachments/assets/d0b54f9c-ed3f-4d79-a1ec-9e20aa715ba5" />


**Question 2**
---
<img width="1236" height="460" alt="image" src="https://github.com/user-attachments/assets/3f036a41-9671-455f-a420-e75c7abb5ea7" />


```
CREATE TABLE orders (
    ord_id TEXT NOT NULL CHECK (LENGTH(ord_id) = 4),
    item_id TEXT NOT NULL,
    ord_date DATE,
    ord_qty INTEGER,
    cost INTEGER,
    PRIMARY KEY (item_id, ord_date)
);
```

**Output:**

<img width="1222" height="415" alt="image" src="https://github.com/user-attachments/assets/36e4a95a-ab0f-4168-b46f-4e3b7daeb9bb" />


**Question 3**
---
<img width="1222" height="368" alt="image" src="https://github.com/user-attachments/assets/876d0008-8e98-4b31-a34c-40e8765bcd3a" />

```
ALTER TABLE employee
ADD COLUMN first_name varchar(50);

ALTER TABLE employee
ADD COLUMN last_name varchar(50);
```

**Output:**

<img width="1247" height="387" alt="image" src="https://github.com/user-attachments/assets/66486081-f7cd-4c12-8cd6-5779e8a12837" />


**Question 4**
---
<img width="1010" height="435" alt="image" src="https://github.com/user-attachments/assets/827c77b4-9226-47cb-960b-f17f00d7272b" />

```
INSERT INTO Customers (CustomerID, Name, Address)
VALUES (304, 'Peter Parker', 'Spider St');
```

**Output:**

<img width="1232" height="383" alt="image" src="https://github.com/user-attachments/assets/1dc2ce4d-7cf8-485f-931e-698562c427cf" />

**Question 5**
---
<img width="1058" height="492" alt="image" src="https://github.com/user-attachments/assets/b0ca5142-c864-477c-aba2-f341c5451811" />

```
INSERT INTO Student_details (RollNo, Name, Gender, Subject, MARKS)
SELECT RollNo, Name, Gender, Subject, MARKS
FROM Archived_students;
```

**Output:**

<img width="1232" height="385" alt="image" src="https://github.com/user-attachments/assets/7e58f7ad-2133-4b5b-8fb2-03988037a2d0" />

**Question 6**
---
<img width="1227" height="312" alt="image" src="https://github.com/user-attachments/assets/de580c24-3199-4f5b-b7a2-f69532362f29" />

```
CREATE TABLE ProjectAssignments (
    AssignmentID INTEGER PRIMARY KEY,
    EmployeeID INTEGER,
    ProjectID INTEGER,
    AssignmentDate DATE NOT NULL,
    FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID),
    FOREIGN KEY (ProjectID) REFERENCES Projects(ProjectID)
);
```

**Output:**

<img width="1225" height="357" alt="image" src="https://github.com/user-attachments/assets/c90c00cf-a1fd-4cbe-b319-c5498bc0057a" />

**Question 7**
---
<img width="1218" height="521" alt="image" src="https://github.com/user-attachments/assets/5c3fa030-2baf-4984-a84c-276b144c08b4" />

```
INSERT INTO Products (ProductID, Name, Category)
VALUES (106, 'Fitness Tracker', 'Wearables');

INSERT INTO Products (ProductID, Name, Category, Price, Stock)
VALUES (107, 'Laptop', 'Electronics', 999.99, 50);

INSERT INTO Products (ProductID, Name, Category, Stock)
VALUES (108, 'Wireless Earbuds', 'Accessories', 100);
```

 **Output:**

<img width="1232" height="376" alt="image" src="https://github.com/user-attachments/assets/5a5b945f-6973-4549-9c83-de2bb4f12c3a" />

**Question 8**
---
<img width="1125" height="435" alt="image" src="https://github.com/user-attachments/assets/975b3b27-afa5-4de6-95fa-64a7a49e1808" />

```
CREATE TABLE item (
    item_id TEXT PRIMARY KEY,
    item_desc TEXT NOT NULL,
    rate INTEGER NOT NULL,
    icom_id TEXT(4),
    FOREIGN KEY (icom_id)
        REFERENCES company(com_id)
        ON UPDATE SET NULL
        ON DELETE SET NULL
);
```

**Output:**

<img width="1217" height="425" alt="image" src="https://github.com/user-attachments/assets/1b3a6482-90a7-447c-b070-3294c71d0735" />

**Question 9**
---
<img width="896" height="361" alt="image" src="https://github.com/user-attachments/assets/64f227be-8c6e-4c78-b27a-4633a9e7efbc" />

```
CREATE TABLE Products (
    ProductID INTEGER PRIMARY KEY,
    ProductName TEXT NOT NULL,
    Price REAL CHECK (Price > 0),
    Stock INTEGER CHECK (Stock >= 0)
);
```

**Output:**

<img width="1237" height="356" alt="image" src="https://github.com/user-attachments/assets/eb2218ad-9a20-49b8-8963-4252825e86e9" />

**Question 10**
---
<img width="1152" height="617" alt="image" src="https://github.com/user-attachments/assets/cc9b8c51-fdf4-4460-be6c-e8b7f3ba9bc1" />

```
ALTER TABLE Student_details
ADD COLUMN State TEXT;
```

**Output:**

<img width="1220" height="326" alt="image" src="https://github.com/user-attachments/assets/e3c22f7c-fa66-4292-967a-998cd828cddd" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
