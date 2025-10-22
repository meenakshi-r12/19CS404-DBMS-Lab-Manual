# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**

<img width="1029" height="242" alt="438775375-6d478a1e-f402-4d9b-b1b4-82acd1ca3b6a" src="https://github.com/user-attachments/assets/4db49a5c-5680-4af5-9359-4eede6c0b863" />

**SQL Code:**
```
SELECT Diagnosis, COUNT(*) AS DiagnosisCount
FROM MedicalRecords
GROUP BY Diagnosis
ORDER BY DiagnosisCount DESC
LIMIT 1;
```
**Output:**

<img width="837" height="295" alt="438775624-21e78e1e-a092-4e23-a4f1-df3f6255446b" src="https://github.com/user-attachments/assets/08a2991f-1336-4654-ae58-eaa53e614bd3" />


**Question 2**

<img width="1018" height="247" alt="438775805-ead773fb-d4d6-4f4b-9c02-a9cb011f8e9b" src="https://github.com/user-attachments/assets/2857fa83-66f6-4f6e-964b-2521fffc6f65" />

**SQL Code:**
```
SELECT 
  Specialty,
  Gender,
  COUNT(*) AS TotalDoctors
FROM Doctors
GROUP BY Specialty, Gender
ORDER BY Specialty, Gender;
```
**Output:**

<img width="949" height="587" alt="438776041-0df250ba-82ff-4b1d-8010-0c289f6e6a6d" src="https://github.com/user-attachments/assets/db62609b-5953-445c-8624-7c6491d06725" />


**Question 3**

<img width="1005" height="238" alt="438776168-f37d5384-c40e-4888-be9d-067a2dfd521f" src="https://github.com/user-attachments/assets/faeba210-4bf1-4c5e-a696-3dede1d12f66" />

**SQL Code:**
```
SELECT 
  Address,
  COUNT(*) AS TotalPatients
FROM Patients
GROUP BY Address
ORDER BY Address;
```
**Output:**

<img width="614" height="344" alt="438776440-a780c5d8-c7e8-4f6e-a618-4f9842285403" src="https://github.com/user-attachments/assets/1b646c86-11de-4da7-a5c7-a5bbf031eca1" />

**Question 4**

<img width="903" height="268" alt="438776520-99fbc0ee-4eab-4951-8329-b893fb6899d6" src="https://github.com/user-attachments/assets/035091d5-03e7-4028-9da1-771c6c09fe05" />

**SQL Code:**
```
SELECT 
  SUM(purch_amt) AS TOTAL
FROM orders;
```
**Output:**

<img width="356" height="252" alt="438776885-42323470-da2a-480d-ada5-7696509c260c" src="https://github.com/user-attachments/assets/426bd029-2eb6-4530-bb7c-8cc3eddfe9e0" />

**Question 5**

<img width="855" height="269" alt="438777032-cf422229-bf29-4df5-a8ba-42c28e84fe93" src="https://github.com/user-attachments/assets/364f6734-2261-4ca3-9286-acea2bbd9112" />

**SQL Code:**
```
SELECT 
  COUNT(*) AS COUNT
FROM employee
WHERE age > 32;
```
**Output:**

<img width="346" height="250" alt="438777207-5f6bcb0e-eaa3-4c0d-98b8-c49faaeefc45" src="https://github.com/user-attachments/assets/48f1a030-7e66-4b52-8fb3-a7999566d6a4" />

**Question 6**

<img width="1053" height="249" alt="438777309-ddb513e9-d0dd-4ccc-a25a-2ca4b7aa5079" src="https://github.com/user-attachments/assets/d6be2206-73e7-4f8d-8377-31243dff01e6" />

**SQL Code:**
```
SELECT 
  COUNT(DISTINCT age) AS COUNT
FROM employee;
```
**Output:**

<img width="344" height="249" alt="438777497-a21d4163-6297-456f-9546-8b006ce9f684" src="https://github.com/user-attachments/assets/c092e033-4483-4bea-808f-d8758301cc9a" />

**Question 7**

<img width="987" height="287" alt="438778730-ff99991a-9ebf-46b3-99da-ad81d2fb0648" src="https://github.com/user-attachments/assets/5ac23704-ef69-42b8-901d-e1574fd0f9bd" />

**SQL Code:**
```
SELECT 
  COUNT(*) AS COUNT
FROM customer
WHERE city != 'Noida';
```
**Output:**

<img width="375" height="253" alt="438778955-ac49ab6c-2e9e-40a5-8688-04cca6a4495c" src="https://github.com/user-attachments/assets/1a414637-4e37-4280-9496-2ad8e7116b26" />


**Question 8**

<img width="1169" height="259" alt="438779124-59e5c8ba-5690-4600-9923-98e88c8c701a" src="https://github.com/user-attachments/assets/34c1bbea-78ea-4c19-9347-36cf81292df6" />

**SQL Code:**
```
SELECT 
  address, 
  SUM(salary)
FROM customer1
GROUP BY address
HAVING SUM(salary) > 2000;
```
**Output:**

<img width="601" height="416" alt="438779425-07c6142c-3c22-471f-bdcd-437e145239ac" src="https://github.com/user-attachments/assets/72accbcd-ecde-49a6-a407-2517aea876fc" />


**Question 9**

<img width="1189" height="289" alt="438779522-31ce49c3-a895-4667-92a6-163adf798228" src="https://github.com/user-attachments/assets/77adb0cf-669c-40a7-ad03-e9d6e99b5d47" />

**SQL Code:**
```
SELECT 
  category_id, 
  AVG(Price) 
FROM products
GROUP BY category_id
HAVING AVG(price) BETWEEN 10 AND 15;
```
**Output:**

<img width="581" height="278" alt="438779784-5515b5eb-9b08-4a5b-bae1-eac3e29bc439" src="https://github.com/user-attachments/assets/cf601ed5-f5ad-4487-adfa-ae7b9dc38d2c" />


**Question 10**

<img width="1202" height="288" alt="438779949-b4b8da44-8deb-4c7b-8b8a-f8a763339bef" src="https://github.com/user-attachments/assets/8284ddcb-c917-4d88-a047-8e3b8f3c6fdb" />

**SQL Code:**
```
SELECT 
  age, 
  AVG(income)
FROM employee
GROUP BY age
HAVING AVG(income) BETWEEN 300000 AND 500000;
```
**Output:**

<img width="574" height="262" alt="438780108-8689ff22-a9cd-4034-99a4-fbf98f2662aa" src="https://github.com/user-attachments/assets/a2e0a0a3-da66-4402-bf55-afba03f0c2e9" />

## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
