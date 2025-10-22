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

<img width="1234" height="155" alt="438549337-219bf5e2-9208-4c6f-8229-e1a9c0b2d545" src="https://github.com/user-attachments/assets/e1d90847-4e43-4aa9-bca8-11cd97475789" />

## SQL Code:
```
CREATE TABLE Orders(
 OrderID INTEGER PRIMARY KEY,
 OrderDate DATE NOT NULL,
 CustomerID INTEGER,
 FOREIGN KEY(CustomerID) REFERENCES CustomerS(CustomerID)
 );
```

**Output:**

<img width="1324" height="232" alt="438549584-6709e358-ded9-4297-b80c-2dd36c2d62dc" src="https://github.com/user-attachments/assets/3082046a-e9b4-4e0d-9d91-49fff64c15ec" />


**Question 2**

<img width="621" height="232" alt="438704848-dcc48243-a82c-41c8-9b34-b26f240bf572" src="https://github.com/user-attachments/assets/25860989-06e3-4a89-a80e-9376bb4acb7b" />

## SQL Code:
```
CREATE TABLE item(
 item_id TEXT PRIMARY KEY,
 item_desc TEXT NOT NULL,
 rate INTEGER NOT NULL,
 icom_id TEXT CHECK (length(icom_id = 4)),
 FOREIGN KEY (icom_id) REFERENCES company(com_id)
 ON UPDATE CASCADE
 ON DELETE CASCADE
 );
```
**Output:**

<img width="1250" height="256" alt="438705074-a2122bb7-2821-40b5-bba7-3a4f365aada3" src="https://github.com/user-attachments/assets/2aacd684-6375-4138-850a-347160a0ce21" />


**Question 3**

<img width="478" height="139" alt="438705229-17220573-306d-44a6-bab5-f2a1b50c420f" src="https://github.com/user-attachments/assets/973bb99a-baac-4b0a-8d32-137bb733a6af" />

## SQL Code:
```
INSERT INTO Customers (CustomerID, Name,Address,City,ZipCode)
VALUES (302, 'Laura Croft', '456 Elm St','Seattle', 98101);

INSERT INTO Customers (CustomerID, Name,Address,City,ZipCode)
VALUES (303, 'Bruce Wayne', '789 Oak St ','Gotham ', 10001);
```
**Output:**

<img width="1253" height="278" alt="438705480-c9f8889e-0893-46ef-95e8-50fa91250ed6" src="https://github.com/user-attachments/assets/56292045-f973-4e22-885f-f5a2a40daddf" />

**Question 4**

<img width="506" height="149" alt="438705605-f23ccb5d-4675-4b45-a582-732fe6cfc116" src="https://github.com/user-attachments/assets/d38e17b3-6f8a-4c45-8205-8c4c750b3c54" />

## SQL Code:
```
CREATE TABLE  Reviews(
    ReviewID  INTEGER,
    ProductID  INTEGER,
    Rating REAL,
    ReviewText TEXT
);
```
**Output:**

<img width="1082" height="251" alt="438706007-7365cb07-a963-4b90-bd7e-5e7cea3cdec9" src="https://github.com/user-attachments/assets/55ad3bbb-3957-445c-a1b4-e2523bc66462" />


**Question 5**

<img width="1237" height="166" alt="438706759-e3b31a9f-99c4-469f-8c95-cc4b85ce6ae4" src="https://github.com/user-attachments/assets/0a499e03-605d-451c-a4eb-71f419bae1bb" />

## SQL Code:
```
ALTER TABLE employee
ADD COLUMN department_id INTEGER;

ALTER TABLE employee
ADD COLUMN manager_id INTEGER DEFAULT NULL;
```
**Output:**

<img width="1219" height="209" alt="438706996-ab3f86bd-0580-4a79-b5ab-4f9f28a483da" src="https://github.com/user-attachments/assets/d251d0d2-fb0a-4ff0-ba1d-10f53bf842cc" />


**Question 6**

<img width="559" height="89" alt="438707134-7bd765ab-79f8-4d55-8869-195293bc88f4" src="https://github.com/user-attachments/assets/f9c62b4e-0ecc-4057-be69-8b72877e51ac" />

## SQL Code:
```
INSERT INTO Products( ProductID, ProductName, Price, Stock)
SELECT ProductID, ProductName, Price, Stock
FROM Discontinued_products;
```
**Output:**

<img width="1140" height="184" alt="438707471-c6a8d724-84fa-404b-a372-345634603889" src="https://github.com/user-attachments/assets/d3d37478-0711-46fd-9a41-8a65fbe59a35" />

**Question 7**

<img width="705" height="299" alt="438707588-0535afec-4e16-4ac3-b3b0-fae3d06529e3" src="https://github.com/user-attachments/assets/ca8573a0-4324-4c09-94b7-ac786872a5a6" />

## SQL Code:
```
CREATE TABLE products (
    product_id INTEGER PRIMARY KEY,
    product_name TEXT NOT NULL,
    list_price DECIMAL(10, 2) NOT NULL,
    discount DECIMAL(10, 2) NOT NULL DEFAULT 0,
    CHECK (list_price >= discount),
    CHECK (discount >= 0),
    CHECK (list_price >= 0)
);
```
**Output:**

<img width="763" height="150" alt="438707774-01b7b738-3e54-4288-8373-d864b6fa6cb2" src="https://github.com/user-attachments/assets/78f93527-4a55-4487-b313-5da5a9941d3e" />


**Question 8**

<img width="1229" height="97" alt="438707881-67b2ca3e-6486-472f-97f2-d5f24a91f944" src="https://github.com/user-attachments/assets/4dd83131-2e78-4309-a106-8ef7df9b86a1" />

## SQL Code:
```
ALTER TABLE Companies
ADD COLUMN designation varchar(50);

ALTER TABLE Companies
ADD COLUMN net_salary number;
```
**Output:**

<img width="1223" height="333" alt="438708131-88d6a2ed-1baf-4599-8ae6-f11e435e12bd" src="https://github.com/user-attachments/assets/17d67f7a-c7cb-4500-9135-3c3396940069" />


**Question 9**

<img width="660" height="237" alt="438708249-2182ae38-63f6-4014-815f-9b8ae9632a5a" src="https://github.com/user-attachments/assets/264814be-d78b-4e01-87f6-da370206d1ba" />

## SQL Code:
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

<img width="1015" height="210" alt="438708402-d1092dbf-8484-48a2-b805-9dd8982bc67c" src="https://github.com/user-attachments/assets/8a12d162-5c45-4d53-8b52-bcd57fa6fad7" />


**Question 10**

<img width="924" height="162" alt="438708502-4333c8c6-f8a5-495a-af25-bafd3a25e27b" src="https://github.com/user-attachments/assets/6fe69bf9-6416-49e3-be04-0a5f17dd78dd" />

## SQL Code:
```
INSERT INTO Employee (EmployeeID, Name, Position)
VALUES (4, 'Emily White', 'Analyst');
```
**Output:**

<img width="1019" height="265" alt="438708739-01e7b248-9972-4263-b5e4-4754d0327def" src="https://github.com/user-attachments/assets/038a13d1-75f1-4125-be9a-a6251e35a6b3" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
