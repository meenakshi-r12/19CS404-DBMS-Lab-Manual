# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
<img width="1252" height="448" alt="438871864-5b936da4-b778-408b-adc2-c850f00f7a04" src="https://github.com/user-attachments/assets/5adcee9f-d601-4ee9-8a0c-c53f5097b3fb" />

**SQL Code:**
```
SELECT s.name
FROM salesman s
LEFT JOIN customer c ON s.salesman_id = c.salesman_id
WHERE c.city = 'New York';
```
**Output:**

<img width="460" height="342" alt="438872109-020a1685-7857-4485-977b-c29f11a32294" src="https://github.com/user-attachments/assets/2b2acd68-ea78-4639-b2cf-154e128c28c3" />

**Question 2**
<img width="1290" height="416" alt="438872394-b9369423-4fb8-4265-981e-59dfc0c6fead" src="https://github.com/user-attachments/assets/ab7dd23e-3b92-4b05-9ec3-06c9a8fcc1ba" />
**SQL Code:**
```
SELECT c.cust_name
FROM customer c
LEFT JOIN orders o ON c.customer_id = o.customer_id;
```
**Output:**

<img width="710" height="770" alt="438872642-dec393d5-5ce6-4b59-b3d6-4b486bf4436b" src="https://github.com/user-attachments/assets/8c6bfdc6-6000-40cb-b2b7-72f2c8c52579" />

**Question 3**
<img width="1277" height="631" alt="438872778-1953161d-5b0b-4777-aa72-062dfa523c00" src="https://github.com/user-attachments/assets/fc672435-2843-4c37-9228-f3f6594fb78f" />
**SQL Code:**
```
SELECT 
    c.cust_name ,
    c.city ,
    c.grade,
    s.name as  Salesman  ,
    s.city 
FROM 
    customer c
JOIN 
    salesman s ON c.salesman_id = s.salesman_id
ORDER BY 
    c.customer_id ASC;
```
**Output:**
<img width="1246" height="579" alt="438872973-929856d3-1320-4f5d-acc8-81b4bd345d21" src="https://github.com/user-attachments/assets/19eb1741-7d7d-4c3e-b8d6-82e76bf6b8ed" />

**Question 4**
<img width="1322" height="836" alt="438873212-9e9520f2-2a1d-425a-96ad-9ad5630d0d9f" src="https://github.com/user-attachments/assets/e9b1508c-7c3a-40f8-98b8-4360db6e4e89" />
**SQL Code:**
```
SELECT 
    c.cust_name, 
    c.city, 
    o.ord_no, 
    o.ord_date, 
    o.purch_amt AS "Order Amount", 
    s.name, 
    s.commission
FROM 
    customer c
LEFT JOIN 
    orders o ON c.customer_id = o.customer_id
LEFT JOIN 
    salesman s ON c.salesman_id = s.salesman_id;
```
**Output:**

<img width="1339" height="766" alt="438873461-1cd006c1-6e32-46d0-bded-839a10001c00" src="https://github.com/user-attachments/assets/f7381fc5-8f94-4e9b-a26a-a68ae2deb523" />

**Question 5**
<img width="1278" height="626" alt="438873649-46160731-9ae6-40c3-9098-a00720a77665" src="https://github.com/user-attachments/assets/c3a1bab0-c023-47ae-b658-7f23dad04619" />

**SQL Code:**
```
SELECT 
    c.cust_name AS "Customer Name", 
    c.city, 
    s.name AS "Salesman", 
    s.city , 
    s.commission 
FROM 
    customer c
JOIN 
    salesman s
ON 
    c.salesman_id = s.salesman_id
WHERE 
    c.city != s.city
    AND s.commission > 0.12;
```
**Output:**

<img width="1251" height="452" alt="438873832-8e54b1d5-a030-4188-ae18-c26772a6f9d6" src="https://github.com/user-attachments/assets/39bcfc9c-acfd-4c48-a1bc-13ac845f7190" />

**Question 6**
<img width="1043" height="592" alt="438873927-034231f4-ee51-496f-a199-bf24841b1ced" src="https://github.com/user-attachments/assets/7068e639-0c92-4bb9-bb59-504eb55f8eed" />
**SQL Code:**
```
SELECT
    s.name AS Salesman,
    c.cust_name,
    s.city
FROM
    salesman s
JOIN
    customer c ON s.city = c.city;
```
**Output:**

<img width="1142" height="646" alt="438874098-a49a153a-b6db-48ce-918b-f8cd964980d2" src="https://github.com/user-attachments/assets/6ea3e0e4-7855-40a5-ad72-4f0880c0de27" />

**Question 7**
<img width="1290" height="504" alt="438874231-fdc430cd-ed67-4f59-b0f0-b9b385bf300f" src="https://github.com/user-attachments/assets/5996936d-5db1-48b0-8ffd-0f9b36df204b" />
**SQL Code:**
```
SELECT 
    p.first_name AS patient_name,
    t.*
FROM 
    patients p
INNER JOIN 
    test_results t ON p.patient_id = t.patient_id;
```
**Output:**

<img width="1308" height="355" alt="438875002-7cc3f79a-faa1-462c-a812-f9ab79c41f78" src="https://github.com/user-attachments/assets/5ca6856d-b274-42a9-8ca5-c14879ee75d5" />

**Question 8**
<img width="1298" height="756" alt="438875122-8ace6368-acde-4f4c-8941-f2dbed4b3272" src="https://github.com/user-attachments/assets/d90f7e65-6508-42ae-8574-a6e1cfd1a89f" />
**SQL Code:**
```
SELECT 
    c.cust_name,
    c.city,
    o.ord_no,
    o.ord_date,
    o.purch_amt AS "Order Amount"
FROM 
    customer c
LEFT JOIN 
    orders o ON c.customer_id = o.customer_id
ORDER BY 
    o.ord_date ASC;
```
**Output:**

<img width="1294" height="617" alt="438875348-e2a4306d-a29c-41d0-8ae5-316d9b1182c8" src="https://github.com/user-attachments/assets/72dceebf-f294-4a3f-b7f6-323831345c87" />

**Question 9**
<img width="1196" height="583" alt="438875440-ede04ca3-83ba-4003-bc3a-10c5e908afa8" src="https://github.com/user-attachments/assets/c6af2d40-86e2-47c0-92dd-6d293ce23a79" />

**SQL Code:**
```
SELECT 
    p.*,
    d.first_name AS doctor_name
FROM 
    patients p
INNER JOIN 
    doctors d ON p.doctor_id = d.doctor_id;
```
**Output:**

<img width="1885" height="384" alt="438875687-58625dd1-9765-4df0-bb15-bf8ef978ebf3" src="https://github.com/user-attachments/assets/691dd8db-237d-479a-969a-d7a59bc767bb" />

**Question 10**
<img width="1247" height="523" alt="438875832-4eeb3953-9f2e-454a-a2dd-67e6c5bc49f8" src="https://github.com/user-attachments/assets/3b282fd0-6f3a-4074-b00e-c84d4be0f679" />

**SQL Code:**
```
SELECT 
    p.*
FROM 
    patients p
INNER JOIN 
    appointments a ON p.patient_id = a.patient_id
WHERE 
    a.appointment_date BETWEEN '2024-01-01' AND '2024-01-31';
```
**Output:**

<img width="1869" height="338" alt="438876090-62897191-9dbe-4f00-bdcc-8617914f9ec5" src="https://github.com/user-attachments/assets/e8db03cc-7339-48e6-923e-5e4d97bd08b1" />

## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
