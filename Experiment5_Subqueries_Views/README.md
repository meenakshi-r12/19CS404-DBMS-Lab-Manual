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

<img width="1053" height="377" alt="438780616-bc4ca765-6c12-453c-af56-f0a8198394fe" src="https://github.com/user-attachments/assets/38471de8-7aab-4838-9eb8-8a75a6b711d2" />

**SQL Code:**
```
SELECT *
FROM CUSTOMERS
WHERE ADDRESS = 'Delhi' AND AGE < 30
ORDER BY ID;
```
**Output:**

<img width="1200" height="291" alt="438780858-164afd13-3206-4254-9deb-93d55cd8b88b" src="https://github.com/user-attachments/assets/f7904998-db3d-4ec2-b34a-d6bdb1391fc8" />

**Question 2**

<img width="1258" height="412" alt="438780988-dec2ba69-7bfa-4b17-ba3d-0cd831375398" src="https://github.com/user-attachments/assets/2321fcbc-0f73-4c6a-a370-4cbf4c06e24c" />

**SQL Code:**
```
SELECT g.student_name, g.grade
FROM GRADES g
JOIN (
    SELECT subject, MIN(grade) AS min_grade
    FROM GRADES
    GROUP BY subject
) AS min_grades ON g.subject = min_grades.subject AND g.grade = min_grades.min_grade;
```
**Output:**

<img width="754" height="371" alt="438781174-7ee610bf-6fc4-4082-a633-127d9c910ca2" src="https://github.com/user-attachments/assets/191dd110-cce2-463a-92d4-bfd32feb6da0" />

**Question 3**

<img width="1244" height="387" alt="438781270-5e256c61-584c-4a7b-967c-026c40be5020" src="https://github.com/user-attachments/assets/e869a3dd-f0e8-4eef-a4d6-22dc9cfa088f" />

**SQL Code:**
```
SELECT g.*
FROM GRADES g
JOIN (
    SELECT subject, MAX(grade) AS max_grade
    FROM GRADES
    GROUP BY subject
) AS max_grades ON g.subject = max_grades.subject AND g.grade = max_grades.max_grade;
```
**Output:**

<img width="1220" height="328" alt="438781793-befdcf19-4e1d-4428-b484-846c0c8a9135" src="https://github.com/user-attachments/assets/b86a46ad-8833-4779-a56f-6db89ad65804" />

**Question 4**

<img width="985" height="242" alt="438782079-e28348cd-68d4-4a59-8f37-e8eaa5f232e1" src="https://github.com/user-attachments/assets/f6ae212f-c265-4f06-aee8-44f129107470" />

**SQL Code:**
```
SELECT name, city
FROM customer
WHERE city IN (
    SELECT city
    FROM customer
    WHERE id IN (3, 7)
);
```
**Output:**

<img width="596" height="396" alt="438782291-7d82ab61-0500-4b66-8b46-bd3e6d53c1d3" src="https://github.com/user-attachments/assets/1ab0f732-b0cb-4ccb-9cf2-202e316784f7" />

**Question 5**

<img width="1008" height="359" alt="438782448-807faebf-2a81-4c43-bed0-c8c0e5b8f66a" src="https://github.com/user-attachments/assets/654bb81b-4249-4503-9170-67cd33a4c657" />

**SQL Code:**
```
SELECT *
FROM CUSTOMERS
WHERE SALARY > 4500;
```
**Output:**

<img width="1194" height="368" alt="438783183-cfa4590b-c9cf-43bf-ad22-2af2cee2aeba" src="https://github.com/user-attachments/assets/51ace65e-0414-407d-8a84-566d95a81748" />

**Question 6**

<img width="1208" height="503" alt="438783443-f2d8fbcc-acc2-4e5c-9445-e22e68ffbad5" src="https://github.com/user-attachments/assets/52e290ff-86c3-46b0-b409-6a601fb7986c" />

**SQL Code:**
```
SELECT * FROM orders WHERE salesman_id IN (select salesman_id FROM salesman WHERE city ='London');
```
**Output:**

<img width="1227" height="348" alt="438783699-27a3e527-0a65-4509-98e2-3988bf6a79b3" src="https://github.com/user-attachments/assets/d8aff8c5-8885-49ce-a19a-226906167bc5" />

**Question 7**

<img width="1217" height="281" alt="438783844-bb7dbeaa-5a09-49d9-92da-0918d002c1c5" src="https://github.com/user-attachments/assets/f7f2e1e9-9dc2-4853-a004-9d03495d70a1" />

**SQL Code:**
```
SELECT * FROM orders WHERE salesman_id IN (select salesman_id FROM salesman WHERE city ='New York');
```
**Output:**

<img width="1233" height="397" alt="438784090-82c8dc38-b695-4793-a71e-830d8f480fe6" src="https://github.com/user-attachments/assets/ccde81de-7f2a-4813-90cd-e63af5d58751" />

**Question 8**

<img width="1031" height="276" alt="438784179-e916ed3d-47ea-4d5d-b855-3aa44329965e" src="https://github.com/user-attachments/assets/cbfebbc5-a485-4bcb-a189-5c91b8916470" />

**SQL Code:**
```
SELECT *
FROM customer
WHERE city <> (
    SELECT city
    FROM customer
    WHERE id = (SELECT MAX(id) FROM customer)
);
```
**Output:**

<img width="1248" height="383" alt="438784377-f039ef9a-3a37-4ddd-a98d-89e78ef6626b" src="https://github.com/user-attachments/assets/81d30643-3e6e-481b-97ed-83c1c025d206" />

**Question 9**
<img width="1013" height="369" alt="438784521-90d07760-06b4-4ee4-9965-dd6c1d9a5128" src="https://github.com/user-attachments/assets/6a92e7e2-8e57-4453-a7fb-e116607f97ea" />
**SQL Code:**
```
SELECT *
FROM CUSTOMERS
WHERE SALARY > 1500;
```
**Output:**

<img width="1192" height="540" alt="438784644-ddc741c3-ef05-4b06-8d11-a09d8874e583" src="https://github.com/user-attachments/assets/e0d61221-897b-4247-8c18-8bc2bfb61ecc" />

**Question 10**

<img width="1260" height="388" alt="438784778-4667dcda-5d8e-4d32-ab12-73fdaa67a927" src="https://github.com/user-attachments/assets/65ffd5ce-d2b9-4b9b-bbc6-93ac4a5e89de" />

**SQL Code:**
```
SELECT g.*
FROM GRADES g
JOIN (
    SELECT subject, MIN(grade) AS min_grade
    FROM GRADES
    GROUP BY subject
) AS min_grades ON g.subject = min_grades.subject AND g.grade = min_grades.min_grade;
```
**Output:**

<img width="1242" height="332" alt="438784938-6e44fe4a-6677-4d8b-a026-f713de5f75e2" src="https://github.com/user-attachments/assets/b9fc69f5-cb15-4672-9259-e9f667168713" />

## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
