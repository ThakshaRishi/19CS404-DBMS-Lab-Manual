# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--
![image](https://github.com/user-attachments/assets/672dff9d-dc0d-47fb-bcf5-3c2b137b00d0)

```sql
SELECT * FROM CUSTOMERS WHERE AGE<30;
```

**Output:**

![image](https://github.com/user-attachments/assets/5561af8b-7549-48ac-8150-144d8c4fcab4)

**Question 2**
---
![image](https://github.com/user-attachments/assets/29aebadf-03f3-4e0e-b6d2-8c9496ff90b2)

```sql
SELECT * FROM ORDERS WHERE salesman_id in (SELECT salesman_id FROM SALESMAN WHERE city='New York');
```

**Output:**

![image](https://github.com/user-attachments/assets/cf1b1c1c-78de-40e1-88ba-02f7e15aee87)

**Question 3**
---
![image](https://github.com/user-attachments/assets/cb7ef18c-e9c6-4cd9-8079-3605a805b3b6)

```sql
SELECT salesman_id, name FROM salesman WHERE salesman_id IN (SELECT salesman_id FROM customer GROUP BY salesman_id HAVING COUNT(customer_id)>1);
```

**Output:**

![image](https://github.com/user-attachments/assets/bac95387-b1d7-45fb-9b3b-79b7eeb0a8de)

**Question 4**
---
![image](https://github.com/user-attachments/assets/1ae021bf-80fc-45ca-bd75-ae8129811048)

```sql
SELECT medication_id AS medic, medication_name, dosage FROM Medications WHERE dosage=(SELECT MAX(dosage) FROM Medications);
```

**Output:**

![image](https://github.com/user-attachments/assets/c7eb764f-6434-4b13-9941-ec3299991ca5)

**Question 5**
---
![image](https://github.com/user-attachments/assets/be29cded-1017-4c97-8ddf-b81bcba7ed8b)

```sql
SELECT * FROM orders WHERE salesman_id IN (SELECT salesman_id FROM salesman WHERE city='London');
```

**Output:**

![image](https://github.com/user-attachments/assets/b22a69a7-7633-4244-af07-a1994afb9562)

**Question 6**
---
![image](https://github.com/user-attachments/assets/d8eef286-4857-4085-a8e0-ef8d3f3fc2bc)

```sql
SELECT student_name, grade FROM GRADES WHERE (subject,grade) IN (SELECT subject,MIN(grade) FROM GRADES GROUP BY subject);
```

**Output:**

![image](https://github.com/user-attachments/assets/9b719dcc-9a86-416a-902c-e323bf86aae4)

**Question 7**
---
![image](https://github.com/user-attachments/assets/e1361fcd-0a51-46c7-a0c5-2721c806589b)

```sql
SELECT * FROM orders WHERE purch_amt>(SELECT AVG(purch_amt) FROM orders WHERE ord_date='2012-10-10');
```

**Output:**

![image](https://github.com/user-attachments/assets/07af850b-32fc-4704-a00d-9d9a54bc5ac5)

**Question 8**
---
![image](https://github.com/user-attachments/assets/9931e3e2-72a8-4060-9f0e-97769a4bda05)

```sql
SELECT * FROM GRADES WHERE (grade,subject) IN (SELECT MAX(grade),subject FROM GRADES GROUP BY subject);
```

**Output:**

![image](https://github.com/user-attachments/assets/a027b446-c9a4-4f31-b977-23be5ef4f89b)

**Question 9**
---
![image](https://github.com/user-attachments/assets/5f66c0b6-4de7-461e-91a5-624ba93c8ca2)

```sql
SELECT * FROM CUSTOMERS WHERE salary=1500;
```

**Output:**

![image](https://github.com/user-attachments/assets/eb3d9271-6f99-4360-b37f-d6e5e31d0cc4)

**Question 10**
---
![image](https://github.com/user-attachments/assets/5ee45e22-2439-4af0-99fd-0ab4bf1c0ca8)

```sql
SELECT * FROM employee WHERE age < (SELECT AVG(age) FROM employee WHERE income > 250000);
```

**Output:**

![image](https://github.com/user-attachments/assets/6d33da4d-0a37-4af4-bdc7-ab6740c4f3c0)

## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
