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
In the Products table, insert a record where some fields are NULL, another record where all fields are filled without any NULL values, and a third record where some fields are filled, and others are left as NULL.

ProductID Name Category Price Stock

106 Fitness Tracker Wearables 107 Laptop Electronics 999.99 50 108 Wireless Earbuds Accessories 100
```
insert into Products(ProductID,Name,Category,Price,Stock)
values(106,"Fitness Tracker","Wearables",NULL,NULL);
insert into Products(ProductID,Name,Category,Price,Stock) 
values(107,"Laptop","Electronic",999.99,50);
insert into Products(ProductID,Name,Category,Price,Stock) 
values(108,"Wireless Earbud","Accessorie",NULL,100); 
-- Paste your SQL code below for Question 1
```

**Output:**

<img width="1174" height="266" alt="image" src="https://github.com/user-attachments/assets/4367af72-6730-4f1f-bde1-16aa8637e805" />


**Question 2**
---
Write a SQL Query to add attribute ISBN as varchar(30) and domain_dept as varchar(30) in the table 'books'

```
alter table books add  ISBN varchar(30);
alter table books add domain_dept  varchar(30);

```

**Output:**

<img width="1178" height="378" alt="image" src="https://github.com/user-attachments/assets/68bd7ec9-57ec-4c1e-8d85-8695fe6d1b64" />


**Question 3**
---
Insert a customer with CustomerID 301, Name Michael Jordan, Address 123 Maple St, City Chicago, and ZipCode 60616 into the Customers table.

```
insert into Customers(CustomerID,Name,Address,City,ZipCode)
values(301,"Michael Jordan","123 Maple St","Chicago",60616);
```

**Output:**

<img width="1184" height="229" alt="image" src="https://github.com/user-attachments/assets/650bada8-65e7-4faa-8d2d-c9d1e546c724" />


**Question 4**
---
Create a new table named contacts with the following specifications: contact_id as INTEGER and primary key. first_name as TEXT and not NULL. last_name as TEXT and not NULL. email as TEXT. phone as TEXT and not NULL with a check constraint to ensure the length of phone is at least 10 characters.

```
create table contacts(
contact_id  INTEGER  primary key,
first_name  TEXT not NULL,
last_name  TEXT  not NULL,
email  TEXT,
phone  TEXT  not NULL  check(LENGTH(phone)>=10) 


);

```

**Output:**

<img width="1192" height="323" alt="image" src="https://github.com/user-attachments/assets/489ef3ed-ec0b-460c-8d7f-4b0437ae711c" />


**Question 5**
---
-- Paste Question 5 here

```sql
-- Paste your SQL code below for Question 5
```

**Output:**

![Output5](output.png)

**Question 6**
---
-- Paste Question 6 here

```sql
-- Paste your SQL code below for Question 6
```

**Output:**

![Output6](output.png)

**Question 7**
---
-- Paste Question 7 here

```sql
-- Paste your SQL code below for Question 7
```

**Output:**

![Output7](output.png)

**Question 8**
---
-- Paste Question 8 here

```sql
-- Paste your SQL code below for Question 8
```

**Output:**

![Output8](output.png)

**Question 9**
---
-- Paste Question 9 here

```sql
-- Paste your SQL code below for Question 9
```

**Output:**

![Output9](output.png)

**Question 10**
---
-- Paste Question 10 here

```sql
-- Paste your SQL code below for Question 10
```

**Output:**

![Output10](output.png)


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
