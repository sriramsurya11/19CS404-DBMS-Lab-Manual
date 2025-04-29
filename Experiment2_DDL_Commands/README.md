# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

*Syntax:*
sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);

### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
sql
ALTER TABLE std ADD (Address CHAR(10));

(b) MODIFY
sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));

(c) DROP
sql
ALTER TABLE relation_name DROP COLUMN field_name;

(d) RENAME
sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;

### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
sql
DROP TABLE relation_name;

### 4. RENAME
Used to rename an existing database object.
sql
RENAME TABLE old_relation_name TO new_relation_name;

### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);

### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);

### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);

### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);

### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);

### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);


*Question 1*
--
![image](https://github.com/user-attachments/assets/1a29aec7-9e1e-45e1-96c0-35f1551f020b)


sql
--
INSERT INTO Employee(EmployeeID,Name,Position)
values(5,           'George Clark',  'Consultant');

INSERT INTO Employee(EmployeeID,Name,Position,Department,Salary)
values(7,           'Noah Davis',    'Manager',     'HR',          60000);

INSERT INTO Employee(EmployeeID,Name,Position,Department)
values(8,           'Ava Miller',    'Consultant',  'IT');


*Output:*

![image](https://github.com/user-attachments/assets/4f08e69d-3696-41cc-93a1-14c259564577)


*Question 2*
---
![image](https://github.com/user-attachments/assets/bad81a8b-bad3-4abe-9bb9-a78f3df20d50)


sql
-- 
CREATE TABLE Attendance (  
    AttendanceID INTEGER PRIMARY KEY,  
    EmployeeID INTEGER,  
    AttendanceDate DATE,  
    Status TEXT CHECK (Status IN ('Present', 'Absent', 'Leave')),  
    FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID)  
);


*Output:*

![image](https://github.com/user-attachments/assets/5546b497-d1e5-4ee9-94c0-ef0b46aff8f6)


*Question 3*
---
![image](https://github.com/user-attachments/assets/a828529f-6fff-42fe-a4cb-c291422cf102)


sql
--
ALTER TABLE Employees
ADD COLUMN Date_of_joining Date;

ALTER TABLE Employees
RENAME COLUMN job_title To Designation;




*Output:*

![image](https://github.com/user-attachments/assets/6f02c1a7-886d-4a24-ba4d-0b77706185ef)


*Question 4*
---
![image](https://github.com/user-attachments/assets/104c3a88-8e14-4894-b4c9-220a25c1fd28)


sql
--
 CREATE TABLE jobs (  
    job_id INTEGER PRIMARY KEY,  
    job_title TEXT NOT NULL DEFAULT '',  
    min_salary INTEGER NOT NULL DEFAULT 8000,  
    max_salary INTEGER DEFAULT NULL  
);


*Output:*

![image](https://github.com/user-attachments/assets/6e389b67-8bea-4e99-9c42-d343c6846f92)


*Question 5*
---
![image](https://github.com/user-attachments/assets/f8c8b4ea-860d-4533-86e7-39c30c74949b)


sql
--
CREATE TABLE Departments(
DepartmentID INTEGER,
DepartmentName TEXT
);


*Output:*

![image](https://github.com/user-attachments/assets/6c5603b9-1821-4380-af56-37b95985a8f2)


*Question 6*
---
![image](https://github.com/user-attachments/assets/1fe189da-4710-4d78-9281-ce6512cb7527)


sql
select *from Out_of_print_books
union all
select *from Books


*Output:*

![image](https://github.com/user-attachments/assets/b018af7c-4b61-43a2-a2d6-0e423b24c199)


*Question 7*
---
![image](https://github.com/user-attachments/assets/b142f374-c419-49fe-a6a4-3d29df06724a)


sql
CREATE TABLE item (  
    item_id TEXT PRIMARY KEY,  
    item_desc TEXT NOT NULL,  
    rate INTEGER NOT NULL,  
    icom_id TEXT CHECK(4),  
    FOREIGN KEY (icom_id) REFERENCES company(com_id)  
    ON UPDATE CASCADE  
    ON DELETE CASCADE  
);


*Output:*

![image](https://github.com/user-attachments/assets/00332d1c-fea8-44a2-b3a4-a4360ed466c7)


*Question 8*
---
![image](https://github.com/user-attachments/assets/a3e803e3-1d80-4bd0-b776-1ce935991e42)


sql
ALTER TABLE employee
ADD COLUMN designation varchar(50);


*Output:*

![image](https://github.com/user-attachments/assets/fa3632ac-9982-4457-987d-f79549324b50)


*Question 9*
---
![image](https://github.com/user-attachments/assets/bd937a5c-ea14-4ea7-964b-2263a2bfbad1)


sql
INSERT INTO Products (ProductID, Name, Category)  
VALUES (104, 'Tablet', 'Electronics');


*Output:*

![image](https://github.com/user-attachments/assets/c9dc4337-0bd5-46cd-83f5-f12606f2d7df)


*Question 10*
---
![image](https://github.com/user-attachments/assets/fa338148-c01f-4a4d-bd65-c892da104f02)


sql
CREATE TABLE Employees(
EmployeeID INTEGER primary key,
FirstName INTEGER NOT NULL,
LastName INTEGER NOT NULL,
Email VARCHAR(50) unique,
Salary CHECK (Salary>0),
DepartmentID INTEGER,
foreign key(DepartmentID) references Departments(DepartmentID)
);


*Output:*

![image](https://github.com/user-attachments/assets/e104b259-c68a-4b5a-bfbb-8167d5ce4981)


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
