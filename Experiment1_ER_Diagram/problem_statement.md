# Experiment 1: Entity-Relationship (ER) Diagram

## 🎯 Objective:
To understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application.

## 📚 Purpose:
The purpose of this workshop is to gain hands-on experience in designing ER diagrams that visually represent the structure of a database including entities, relationships, attributes, and constraints.

---

## 🧪 Choose One Scenario:

### 🔹 Scenario 1: University Database
Design a database to manage students, instructors, programs, courses, and student enrollments. Include prerequisites for courses.

**User Requirements:**
- Academic programs grouped under departments.
- Students have admission number, name, DOB, contact info.
- Instructors with staff number, contact info, etc.
- Courses have number, name, credits.
- Track course enrollments by students and enrollment date.
- Add support for prerequisites (some courses require others).

---

### 🔹 Scenario 2: Hospital Database
Design a database for patient management, appointments, medical records, and billing.

**User Requirements:**
- Patient details including contact and insurance.
- Doctors and their departments, contact info, specialization.
- Appointments with reason, time, patient-doctor link.
- Medical records with treatments, diagnosis, test results.
- Billing and payment details for each appointment.

---

## 📝 Tasks:
1. Identify entities, relationships, and attributes.
2. Draw the ER diagram using any tool (draw.io, dbdiagram.io, hand-drawn and scanned).
3. Include:
   - Cardinality & participation constraints
   - Prerequisites for University OR Billing for Hospital
4. Explain:
   - Why you chose the entities and relationships.
   - How you modeled prerequisites or billing.

# ER Diagram Submission - Student Name

## Scenario Chosen:
University / Hospital (choose one)

## ER Diagram:
![image](https://github.com/user-attachments/assets/4b0b0f45-9a8e-4821-abcb-81aa103907a7)
![image](https://github.com/user-attachments/assets/28f9582c-14b2-43cc-97a4-d99d7b20824f)



## Entities and Attributes:
...
- Department - Dept id, Dept name, Head of Department
- Program - Program id, Program name
- Student - Student id, Date of birth, Email, Name, Phone number
- Course - Credits, Department, Course id, Course name, Course description
- Instructor - Name, Department, Mobile number, Office location, Email, Instructor id


...

## Relationships and Constraints:
Relationship 1: Department - Program
Cardinality: 1 Department → many Programs (1:N)

Participation:

Department: Total

Program: Total

Relationship 2: Program - Student
Cardinality: 1 Program → many Students (1:N)

Participation:

Program: Total

Student: Total

Relationship 3: Student - Course (Enrolled in)
Cardinality: Many Students → Many Courses (M:N)

Participation:

Student: Partial

Course: Partial

Relationship 4: Course - Instructor (Taught by)
Cardinality: 1 Instructor → many Courses (1:N)


Participation:

Instructor: Partial

Course: Partial
...

## Extension (Prerequisite / Billing):
-Extension (Prerequisite / Billing):
1. Prerequisite Modeling:
Idea: Some courses may require students to complete other courses first.

Modeling:

Add a "Prerequisite" relationship between Course and Course itself.

It will be a binary relationship like:

One Course (prerequisite) → another Course (dependent).

Cardinality:

0 or 1 prerequisite for a course (Optional, 0:1).

2. Billing Modeling:
Idea: Students pay based on enrolled courses (credits or fixed fees).

Modeling:

Add a Billing entity.

Connect Student ↔ Billing and Course ↔ Billing.

Billing will store:

Billing ID

Amount

Payment Date

Payment Status

Cardinality:

1 Student → Many Billing Records (1:N)

1 Course → Many Billing Records (1:N)


## Design Choices:
Design Choices:
Entities like Department, Program, Student, Course, and Instructor were chosen because they represent real-world objects we need to track separately, each with their own properties (attributes).

Relationships like offers, enrolled by, enrolled in, and taught by were used to properly connect the entities:

Department offers Program: Logical because programs are under departments.

Program enrolled by Student: Students must belong to a program.

Student enrolled in Course: Students register for multiple courses.

Course taught by Instructor: Instructors are responsible for teaching courses.

Assumptions:

Every Program must belong to exactly one Department.

A Student must be enrolled in one Program but can enroll in multiple Courses.

Each Course must belong to a Department.

Instructors are assigned based on department expertise but can teach multiple courses.

Billing and Prerequisites (if added) are optional extensions for real-world system needs.


## RESULT
Hence, the concepts of ER modeling is understood and applied by creating an ER diagram for a real-world application.
