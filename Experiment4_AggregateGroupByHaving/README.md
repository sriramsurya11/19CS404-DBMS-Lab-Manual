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
--
![Screenshot 2025-04-29 173049](https://github.com/user-attachments/assets/53bcfb64-4be8-4ba0-81d3-7a475f0cc255)


```sql
select PatientID, count(*) as TotalAppointments
from Appointments
group by PatientID ;

```

**Output:**

![Screenshot 2025-04-29 173113](https://github.com/user-attachments/assets/4b46fcd2-6f06-4361-8840-30e74b2e1a7d)


**Question 2**
---
![Screenshot 2025-04-29 173125](https://github.com/user-attachments/assets/c214c29a-3696-4a1f-abcc-e30acc76bcbd)


```sql
select Specialty, avg(DATEDIFF(YEAR, DateOfBirth, GETDATE())) as AvgAge
from Doctors
group by Specialty;
```

**Output:**

![Screenshot 2025-04-29 173210](https://github.com/user-attachments/assets/6864e6c8-6721-4b74-bb22-d9c1b38597d1)


**Question 3**
---
![Screenshot 2025-04-29 173153](https://github.com/user-attachments/assets/a90426c1-e3a3-4c71-ae8c-8ec02fb98847)


```sql
select PatientID, sum(length(Medications) - length(replace(Medications, ',', '')) + 1 )::int as AvgMedications
from MedicalRecords
group by 
PatientID ;
```

**Output:**

![Screenshot 2025-04-29 173223](https://github.com/user-attachments/assets/7febec02-926d-4f35-8988-41f580b3b852)


**Question 4**
---
![Screenshot 2025-04-29 173204](https://github.com/user-attachments/assets/811d7d4e-ff2d-4ec6-b385-03d7cbdcd42a)


```sql
select avg(length(name)) as 
avg_name_length
from customer
where city = 'Chennai';
```

**Output:**

![Screenshot 2025-04-29 173210](https://github.com/user-attachments/assets/7c4f3089-e03c-4a2c-8e53-157ca92e1e95)


**Question 5**
---
![Screenshot 2025-04-29 173216](https://github.com/user-attachments/assets/82af1fe5-1353-4cc6-8535-bfcd2c290703)


```sql
select avg(income) as avg_income
from employee
where name like 'A%';
```

**Output:**
![Screenshot 2025-04-29 173223](https://github.com/user-attachments/assets/e75add66-1e8b-45c6-9f7e-21cdec34b501)



**Question 6**
---
![Screenshot 2025-04-29 173229](https://github.com/user-attachments/assets/ce7c1913-1a1a-4afc-ba93-8fb8e1254287)


```sql
select count(distinct salesman_id) as COUNT
from orders ;
```

**Output:**

![Screenshot 2025-04-29 173236](https://github.com/user-attachments/assets/3db650f2-dddf-493a-bf54-58f38be33bb7)


**Question 7**
---
![Screenshot 2025-04-29 173246](https://github.com/user-attachments/assets/d33eb8d6-fc0a-4cc7-8fc8-54f004430fbe)


```sql
select avg(length(email)) as avg_email_length_below_30
from customer
where city = 'Mumbai';
```

**Output:**

![Screenshot 2025-04-29 173252](https://github.com/user-attachments/assets/218a1813-966e-4ff0-9807-84ea1d4c3e1f)


**Question 8**
---
![Screenshot 2025-04-29 173300](https://github.com/user-attachments/assets/fd8fcac2-92d5-4b31-b98c-f155922f635f)


```sql
select age, SUM(income)
from employee
group by age
having SUM(income) > 1000000 ;
```

**Output:**
![Screenshot 2025-04-29 173308](https://github.com/user-attachments/assets/a6597985-53b5-429c-948a-f2d37c38dde5)


**Question 9**
---
![Screenshot 2025-04-29 173318](https://github.com/user-attachments/assets/5f417505-f0ac-443c-9554-5fb404f2cf44)


```sql
select category_id, SUM(price * category_id) as Revenue
from products
group by category_id
having SUM(price * category_id) > 25 ;l

```

**Output:**
![Screenshot 2025-04-29 173325](https://github.com/user-attachments/assets/08b6b6fb-e02f-4e11-b5f2-df710397cbec)



**Question 10**
---
![Screenshot 2025-04-29 173333](https://github.com/user-attachments/assets/ae2191d6-df9c-4649-a8aa-a3fb3152d6c4)


```sql
select category_id, SUM(price) as Total_Cost
from products
group by category_id
having SUM(price) > 50 ;
```

**Output:**

![Screenshot 2025-04-29 173340](https://github.com/user-attachments/assets/8c976ead-4dc6-4914-8659-98b3dc2242f6)

## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
