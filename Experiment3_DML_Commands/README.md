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
![Screenshot 2025-04-29 135844](https://github.com/user-attachments/assets/1307af9d-04f7-43d3-b416-a4264ee74a0b)


```sql
update products
set sell_price = sell_price * 1.15
where quantity < 50 and supplier_id = 10 ;
```

**Output:**
![Screenshot 2025-04-29 135901](https://github.com/user-attachments/assets/edebbe95-0c36-47ff-9433-10a01561d8c3)



**Question 2**
---
![Screenshot 2025-04-29 135912](https://github.com/user-attachments/assets/d54007ea-0787-46b7-b7dc-1cf0c702033e)


```sql
update employees
set email='Unavailable';
```

**Output:**
![Screenshot 2025-04-29 135923](https://github.com/user-attachments/assets/683cf5a8-d3e7-417e-a402-ff64af610853)



**Question 3**
---
![Screenshot 2025-04-29 135933](https://github.com/user-attachments/assets/3e8c51c3-6420-4b6b-ba75-b0fb6b2c28c5)


```sql
update products
set product_name='Grapefruit'
where product_id = 4 ;
```

**Output:**

![Screenshot 2025-04-29 135943](https://github.com/user-attachments/assets/19ab255a-d3ec-48a0-ac5b-e8e03ed2bf7a)


**Question 4**
---
![Screenshot 2025-04-29 135950](https://github.com/user-attachments/assets/c8c434ee-a54d-4e3f-8eb7-98013b84de44)


```sql
update Products
set quantity= quantity * 1.10;
```

**Output:**

![Screenshot 2025-04-29 140000](https://github.com/user-attachments/assets/b5fa65fd-4424-4f20-8d83-0fc3afee0d5b)


**Question 5**
---
![Screenshot 2025-04-29 140012](https://github.com/user-attachments/assets/1cf42c17-387c-40d9-b4bb-d9e3e5f3740a)


```sql
update sales
set total_sell_price = quantity * sell_price
where product_id = 10 ;
```

**Output:**

![Screenshot 2025-04-29 140021](https://github.com/user-attachments/assets/99acd3c1-a28a-4a4b-a4c6-ad7064ce7753)


**Question 6**
---
![Screenshot 2025-04-29 140031](https://github.com/user-attachments/assets/de6e504b-451a-4454-aaf1-f2f414d7bda1)


```sql
delete from customer
where CUST_NAME LIKE '%Holmes%';
```

**Output:**

![Screenshot 2025-04-29 140040](https://github.com/user-attachments/assets/6f7ea766-8c54-4f6f-be5c-c436fa4b382e)


**Question 7**
---
![Screenshot 2025-04-29 140052](https://github.com/user-attachments/assets/83710c53-82ea-49f2-82eb-0c02f0430c62)

```sql
delete from surgeries
where surgery_id = 3 or surgeon_id = 4 ;
```

**Output:**

![Screenshot 2025-04-29 140104](https://github.com/user-attachments/assets/927d4532-9f95-40c7-abb7-ef44fc5b548d)


**Question 8**
---
![Screenshot 2025-04-29 140116](https://github.com/user-attachments/assets/7daccb37-bf92-408f-934d-29d2c068465d)


```sql
delete from customer
where CUST_COUNTRY ='UK' AND WORKING_AREA = 'London' AND GRADE < 3 ;
```

**Output:**
![Screenshot 2025-04-29 140122](https://github.com/user-attachments/assets/87300c86-d674-4413-bc03-034ee96c920c)



**Question 9**
---
![Screenshot 2025-04-29 140134](https://github.com/user-attachments/assets/0d3d3414-becb-42c7-9db1-8f636c7f0177)


```sql
delete from customer
where GRADE >= 2;
```

**Output:**
![Screenshot 2025-04-29 140143](https://github.com/user-attachments/assets/f075da12-36b3-42f6-8966-d203fd2c8da9)


**Question 10**
---
![Screenshot 2025-04-29 140149](https://github.com/user-attachments/assets/fc143510-88d9-4793-a0e6-31a723d9743a)


```sql
delete from Doctors
where specialization = 'Pediatrics' and first_name = 'Michael' ;
```

**Output:**

![Screenshot 2025-04-29 140155](https://github.com/user-attachments/assets/4d2cea5f-95fb-4b65-a1ab-56895f397dad)


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
