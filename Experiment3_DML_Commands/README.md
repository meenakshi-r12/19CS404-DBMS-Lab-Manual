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
<img width="1116" height="301" alt="438712363-aa005081-072e-4412-8adb-6f500afeb345" src="https://github.com/user-attachments/assets/ee6012f6-145b-4df0-a49a-570052ea81da" />

## SQL Code:
```
UPDATE sales
SET total_sell_price = quantity * sell_price
WHERE product_id = 10;
```

**Output:**

<img width="1163" height="333" alt="438712563-a8ddecbd-e86a-480f-b302-3c8e0bdec3a5" src="https://github.com/user-attachments/assets/379460fe-40e9-4c61-b8e7-e843df5e1824" />


**Question 5**
---
<img width="1116" height="406" alt="438712671-4851b1e3-8122-4449-85f2-a87cf346ca0a" src="https://github.com/user-attachments/assets/340a97d8-4336-4abc-97eb-78ca5c907a21" />

## SQL Code:
```
UPDATE employees
SET email = 'Unavailable';
```

**Output:**

<img width="742" height="369" alt="438712973-61fe882b-be3b-4d18-9d74-055e18806cbe" src="https://github.com/user-attachments/assets/b74dbb2c-e602-494e-b3e2-fa74774a4fe6" />



**Question 6**

<img width="1258" height="286" alt="438713138-cf249de4-51d1-4571-b684-3cbcabf18f1e" src="https://github.com/user-attachments/assets/e2c6e149-a491-4327-b269-67d7c93c1854" />

## SQL Code:
```
DELETE FROM customer
WHERE GRADE = 2;
```
**Output:**

<img width="627" height="466" alt="438713353-b3b16aa3-a2d2-4974-9955-ed1a57cd9156" src="https://github.com/user-attachments/assets/85e7c686-f9f6-4f56-aec5-efd91f56fa94" />


**Question 7**

<img width="1242" height="262" alt="438713445-4065dd95-30d9-43f4-a790-ff72adce9e33" src="https://github.com/user-attachments/assets/dd91f0c8-75a1-4725-a001-5701b75d9bc9" />

## SQL Code:
```
DELETE FROM customer
WHERE CUST_COUNTRY NOT IN ('India', 'USA');
```

**Output:**

<img width="971" height="306" alt="438713966-f4560ca2-1fbc-476d-b647-33d71db7d372" src="https://github.com/user-attachments/assets/0bd0267c-7183-4717-80ca-5f872653a4cd" />


**Question 8**

<img width="1283" height="236" alt="438714211-7f7a74a1-870f-4a1f-8b31-df3bc457e045" src="https://github.com/user-attachments/assets/f6d707b8-3690-4830-95f1-fd369d99da1a" />

## SQL Code:
```
DELETE FROM customer
WHERE GRADE >= 2;
```

**Output:**

<img width="606" height="395" alt="438714450-1e0da64d-81c1-4493-aed7-9e30ea6eef28" src="https://github.com/user-attachments/assets/573f0d9d-6ec5-44ac-aee7-9eb854816eb2" />


**Question 9**

<img width="1226" height="175" alt="438714567-6582b276-3672-4426-b317-7549c9b32a9d" src="https://github.com/user-attachments/assets/a2925056-9dac-4d3e-ae00-5a490e10c6ce" />

## SQL Code:
```
DELETE FROM Doctors
WHERE specialization = 'Pediatrics'
  AND first_name = 'Michael';
```
**Output:**

<img width="983" height="299" alt="438714705-2d9ca326-978a-42e2-a707-7b52de0a1324" src="https://github.com/user-attachments/assets/1042bbba-a5fd-4aa7-becf-dae61bf682e1" />

**Question 10**

<img width="1261" height="235" alt="438714835-5cdc5453-a0c6-4290-b442-dffb772c27e9" src="https://github.com/user-attachments/assets/9d3fd810-c2c9-430d-a8e7-90257a873e57" />

## SQL Code:
```
DELETE FROM customer
WHERE AGENT_CODE IN ('A003', 'A008');
```
**Output:**

<img width="798" height="709" alt="438715046-46f39bd1-21b8-4724-b47b-53099e272de6" src="https://github.com/user-attachments/assets/0e25e3f9-b1a4-4450-a889-a7f816abcec0" />

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
