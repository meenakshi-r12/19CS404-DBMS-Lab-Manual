# Experiment 6: PL/SQL – Variables, Control Structures and Loops

## AIM
To write and execute simple PL/SQL programs using variables, loops, and conditional statements.


## THEORY

PL/SQL, which stands for Procedural Language extensions to the Structured Query Language (SQL). It is a combination of SQL along with the procedural features of programming languages.

**Syntax:**
```sql
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

### Basic Components of PL/SQL Block:
- DECLARE: Section to declare variables and constants.
- BEGIN: The execution section that contains PL/SQL statements.
- EXCEPTION: Handles errors or exceptions that occur in the program.
- END: Marks the end of the PL/SQL block.

# PL/SQL Programs – Steps and Expected Output

## 1. Write a PL/SQL program to find the Greatest of Two Numbers

### Steps:
- Declare two numeric variables and initialize them.
- Use an `IF` statement to compare the values.
- Display the greater number using `DBMS_OUTPUT.PUT_LINE`.

- Program:
 ```
DECLARE
    -- Declare variables
    num1 NUMBER := 15;      -- First number (you can change this value)
    num2 NUMBER := 10;      -- Second number (you can change this value)
    result NUMBER;          -- Variable to store the result
    
BEGIN
    -- Compare the two numbers
    IF num1 > num2 THEN
        result := num1;
    ELSE
        result := num2;
    END IF;
    
    -- Display the result
    DBMS_OUTPUT.PUT_LINE('The greatest of ' || num1 || ' and ' || num2 || ' is: ' || result);
    
EXCEPTION
    WHEN OTHERS THEN
        DBMS_OUTPUT.PUT_LINE('An error occurred: ' || SQLERRM);
END;
/
```

**Expected Output:**  
![image](https://github.com/user-attachments/assets/b95c1305-5316-457c-99c0-dab5052d03f3)


---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.

- program:
```
DECLARE
    N NUMBER;          -- Input: how many natural numbers to sum
    i NUMBER := 1;     -- Counter
    sum NUMBER := 0;   -- Variable to store the sum
BEGIN
    -- Assign value to N (you can modify this or get input dynamically if needed)
    N := 10;

    -- Loop to calculate the sum
    WHILE i <= N LOOP
        sum := sum + i;
        i := i + 1;
    END LOOP;

    -- Output the result
    DBMS_OUTPUT.PUT_LINE('Sum of first ' || N || ' natural numbers is: ' || sum);
END;
/
```

**Expected Output:**  
![image](https://github.com/user-attachments/assets/1f8b4961-9c18-4c8c-b913-ec1ec9b5d0e4)


---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.
- Program:
 ```
DECLARE
    -- Variables to store Fibonacci sequence values
    n1 NUMBER := 0;         -- First Fibonacci number
    n2 NUMBER := 1;         -- Second Fibonacci number
    next_term NUMBER;       -- Next term in the sequence
    terms NUMBER := 10;      -- Number of terms to generate (you can change this)
    i NUMBER;               -- Loop counter
    
BEGIN
    -- Enable DBMS_OUTPUT to display results
    DBMS_OUTPUT.PUT_LINE('Fibonacci Series up to ' || terms || ' terms:');
    DBMS_OUTPUT.PUT_LINE(n1);  -- Print first term
    DBMS_OUTPUT.PUT_LINE(n2);  -- Print second term
    
    -- Generate Fibonacci series using a loop
    FOR i IN 3..terms LOOP
        next_term := n1 + n2;
        DBMS_OUTPUT.PUT_LINE(next_term);
        
        -- Update values for next iteration
        n1 := n2;
        n2 := next_term;
    END LOOP;
    
EXCEPTION
    WHEN OTHERS THEN
        DBMS_OUTPUT.PUT_LINE('An error occurred: ' || SQLERRM);
END;
/
```
**Expected Output:**  
![image](https://github.com/user-attachments/assets/2b0371dd-5ba1-441e-98bc-57c4e88e0655)



---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.

Program:
```
DECLARE
    original_num NUMBER := 12345;  -- Number to reverse (can be changed)
    reversed_num NUMBER := 0;
    remainder NUMBER;
    temp_num NUMBER;
    
BEGIN
    -- Display original number
    DBMS_OUTPUT.PUT_LINE('Original Number: ' || original_num);
    
    -- Store original number in temporary variable
    temp_num := original_num;
    
    -- Reverse the number using arithmetic operations
    WHILE temp_num > 0 LOOP
        remainder := MOD(temp_num, 10);  -- Get last digit
        reversed_num := reversed_num * 10 + remainder;
        temp_num := FLOOR(temp_num / 10);  -- Remove last digit
    END LOOP;
    
    -- Display reversed number
    DBMS_OUTPUT.PUT_LINE('Reversed Number: ' || reversed_num);
    
EXCEPTION
    WHEN OTHERS THEN
        DBMS_OUTPUT.PUT_LINE('An error occurred: ' || SQLERRM);
END;
/
```
**Expected Output:**  

![image](https://github.com/user-attachments/assets/221fd624-59c6-46b8-900e-65c61f244791)



---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.
Program:
```
DECLARE
    num1 NUMBER := 15;      -- First number
    num2 NUMBER := 25;      -- Second number
    num3 NUMBER := 10;      -- Third number
    largest NUMBER;         -- Variable to store result
    
BEGIN
    -- Compare all three numbers
    IF num1 >= num2 AND num1 >= num3 THEN
        largest := num1;
    ELSIF num2 >= num1 AND num2 >= num3 THEN
        largest := num2;
    ELSE
        largest := num3;
    END IF;
    
    -- Display the result
    DBMS_OUTPUT.PUT_LINE('The largest of ' || num1 || ', ' || num2 || 
                         ', and ' || num3 || ' is: ' || largest);
    
EXCEPTION
    WHEN OTHERS THEN
        DBMS_OUTPUT.PUT_LINE('An error occurred: ' || SQLERRM);
END;
/
```

**Expected Output:**  

![image](https://github.com/user-attachments/assets/db9440a5-543d-4d17-9d6e-42166d025abe)



## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.
