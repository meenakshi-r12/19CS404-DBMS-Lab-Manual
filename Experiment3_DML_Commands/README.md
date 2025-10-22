# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
<img width="979" height="232" alt="438711302-3fb5b196-fd57-4e9c-8d03-4e445dacb453" src="https://github.com/user-attachments/assets/1020ae83-5961-4709-8f60-627465d5f8a1" />


## SQL Code:
```
UPDATE products
SET product_name = 'Grapefruit'
WHERE product_id = 4;
```
**Output:**

<img width="1002" height="148" alt="438711533-450e752a-8c92-4174-94ef-f60a21dce154" src="https://github.com/user-attachments/assets/6fc2804a-c842-4462-9382-128751db4a83" />



**Question 2**
---

<img width="1032" height="389" alt="438711662-58478acf-17ff-41bf-805b-a990e525e4a8" src="https://github.com/user-attachments/assets/fd680f6e-14e4-4e55-84d0-a71445992e7c" />

## sql
```
update employees
set salary= salary * 2
where department_id = 20
and job_id LIKE '%MAN';
```
**Output:**

<img width="1151" height="274" alt="438711841-cd7d0fc7-ea44-4d43-aae0-0d8f5c592dde" src="https://github.com/user-attachments/assets/f3f79bdf-1a84-496f-94b2-b1094f31dc1c" />

**Question 3**
---
<img width="949" height="614" alt="438711968-a5cc9cd3-1df5-443d-b76b-55953b47d747" src="https://github.com/user-attachments/assets/1c71294b-97de-497a-987e-754812338a79" />

## SQL Code:
```
UPDATE SALES
SET sell_price = sell_price + 3
WHERE product_id IN (
    SELECT product_id 
    FROM PRODUCTS 
    WHERE supplier_id = 4
);
```

**Output:**

<img width="1161" height="230" alt="438712243-4154d858-e973-4537-aa69-9f77dcad49e9" src="https://github.com/user-attachments/assets/2d3c70eb-47e7-4bea-8dbc-a2fc7106684a" />

**Question 4**
---
-- Paste Question 4 here

```sql
-- Paste your SQL code below for Question 4
```

**Output:**

![Output4](output.png)

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
Thus, the SQL queries to implement DML commands have been executed successfully.
