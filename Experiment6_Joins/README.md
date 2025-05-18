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
--
-- ![image](https://github.com/user-attachments/assets/000080f9-cd11-4234-a57b-a86f87e32228)


```sql
-- 

SELECT p.first_name AS patient_name, d.first_name AS doctor_name
FROM patients p
JOIN doctors d
ON p.doctor_id = d.doctor_id
WHERE p.date_of_birth > '1990-01-01';

```

**Output:**

![image](https://github.com/user-attachments/assets/ff0dfc55-5880-4c54-87e7-28e4e7ea5a64)


**Question 2**
---
-- 
![image](https://github.com/user-attachments/assets/09ab4a1d-b257-4b33-9484-5009abed3f0f)

```sql
--

SELECT o.ord_no, o.ord_date, o.purch_amt, 
       c.cust_name AS "Customer Name", c.grade, 
       s.name AS Salesman, s.commission
FROM orders o
JOIN customer c ON o.customer_id = c.customer_id
JOIN salesman s ON o.salesman_id = s.salesman_id;

```

**Output:**

![image](https://github.com/user-attachments/assets/df86b7e0-f557-426a-8e70-cf77bed5d5b9)


**Question 3**
---
-- ![image](https://github.com/user-attachments/assets/63c47968-1927-48b7-bbef-97edbc9176b2)


```sql
--

SELECT p.*
FROM patients p
JOIN test_results t
ON p.patient_id = t.patient_id
WHERE t.test_name IN ('Blood Test', 'Blood Pressure')
AND t.result NOT LIKE '%Normal%';

```

**Output:**

![image](https://github.com/user-attachments/assets/a3863076-2546-4d37-b510-a1f19dc321d1)


**Question 4**
---
-- 
![image](https://github.com/user-attachments/assets/e1072c90-f6a7-481c-be4f-dd80d59ea4f5)


```sql
--

SELECT c.cust_name AS "Customer Name", c.city, s.name AS Salesman, s.commission
FROM customer c
JOIN salesman s
ON c.salesman_id = s.salesman_id
WHERE s.commission > 0.12;

```

**Output:**

![image](https://github.com/user-attachments/assets/effbf57a-35fa-4698-949b-46fee40c9971)

**Question 5**
---
-- 
![image](https://github.com/user-attachments/assets/204a7910-7e9c-438c-99c5-931b17568f8f)


```sql
--

SELECT c.cust_name, o.ord_no, o.ord_date, o.purch_amt
FROM customer c
LEFT JOIN orders o
ON c.customer_id = o.customer_id
WHERE o.purch_amt > 1000;

```

**Output:**

![image](https://github.com/user-attachments/assets/dddaf9bf-b767-4972-b810-4ba06271519f)


**Question 6**
---
-- ![image](https://github.com/user-attachments/assets/a1b7011f-7c14-41c0-b089-510afaca0794)

```sql
-- 


SELECT c.cust_name, c.city, o.ord_no, o.ord_date, o.purch_amt AS "Order Amount"
FROM customer c
LEFT JOIN orders o
ON c.customer_id = o.customer_id
ORDER BY o.ord_date ASC;

```

**Output:**

![image](https://github.com/user-attachments/assets/6feab0ac-fbb0-4502-8488-9124c55fe06c)

**Question 7**
---
-- 
![image](https://github.com/user-attachments/assets/d138cafb-0ff3-4afc-a5fb-c91032700ef7)

```sql
--

SELECT p.first_name AS patient_name, d.first_name AS doctor_name
FROM patients p
JOIN doctors d
ON p.doctor_id = d.doctor_id
WHERE p.discharge_date IS NULL;

```

**Output:**

![image](https://github.com/user-attachments/assets/69ff3fe1-d127-4030-ae80-dfab76208aa2)

**Question 8**
---
-- 
![image](https://github.com/user-attachments/assets/a85aa5f1-ad80-4ae4-9527-e7ffe2a65f8d)


```sql
--

SELECT c.cust_name AS "Customer Name", c.city, s.name AS Salesman, s.commission
FROM customer c
JOIN salesman s
ON c.salesman_id = s.salesman_id;

```

**Output:**

![image](https://github.com/user-attachments/assets/f87bef97-95f1-4ff3-a308-5d7ada681f54)

**Question 9**
---
-- 
![image](https://github.com/user-attachments/assets/3949ac6f-0ea7-475e-8509-ddff96ac3b98)


```sql
--

SELECT s.name
FROM salesman s
JOIN customer c
ON s.salesman_id = c.salesman_id
WHERE c.city = 'New York';

```

**Output:**

![image](https://github.com/user-attachments/assets/926f0492-3514-4fc1-85fe-adcc164c1c80)

**Question 10**
---
-- ![image](https://github.com/user-attachments/assets/7f4ccd80-80d8-46ea-a7ea-52122d41f0a4)

```sql
--

SELECT c.cust_name, c.city, c.grade, s.name AS Salesman, s.city
FROM customer c
JOIN salesman s
ON c.salesman_id = s.salesman_id
ORDER BY c.customer_id ASC;

```

**Output:**
![image](https://github.com/user-attachments/assets/23a2842f-2197-4bcf-a759-0828c9b9e447)

## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
