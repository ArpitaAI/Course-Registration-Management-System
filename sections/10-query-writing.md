
# 10. Query Writing

This section contains the SQL queries used in the Course Registration Management System.

## 1. Single Row Function

### Query 1: Retrieve the Full Name of a Student

Retrieve the full name of the student with STUDENT_ID 3 from the STUDENT table.

```sql
SELECT STUDENT_NAME
FROM STUDENT
WHERE STUDENT_ID = 3;
```
<img width="1008" height="538" alt="image" src="https://github.com/user-attachments/assets/0338ef3d-1311-497f-9599-553dd2a535ba" />


### Query 2: Calculate Total Credits Completed

Calculate the total credits completed by the student with STUDENT_ID 4 from the STUDENT table.

```sql
SELECT SUM(CREDIT_COMPLETE) AS Total_Credits_Completed
FROM STUDENT
WHERE STUDENT_ID = 4;
```
<img width="1008" height="536" alt="image" src="https://github.com/user-attachments/assets/fd27bcdf-2398-4274-a436-09d442e29f44" />


---

## 2. Group Function

### Query 1: Calculate Average CGPA

Calculate the average CGPA of all students in the STUDENT table.

```sql
SELECT AVG(CGPA) AS Average_CGPA
FROM STUDENT;
```
<img width="1008" height="538" alt="image" src="https://github.com/user-attachments/assets/58b35480-0f5c-4b1b-a5b5-052f8fbaa5e8" />


### Query 2: Count Students in Each Department

```sql
SELECT DEPT_ID, COUNT(*) AS Student_Count
FROM STUDENT
GROUP BY DEPT_ID;
```
<img width="1008" height="538" alt="image" src="https://github.com/user-attachments/assets/5ff8d68b-8d0e-4882-a6e7-1ccb3fd9290b" />


---

## 3. Subquery

### Query 1: Students with More Than Average Credits

Retrieve the names of students who have completed more credits than the average credits completed by all students.

```sql
SELECT STUDENT_NAME
FROM STUDENT
WHERE CREDIT_COMPLETE > (
    SELECT AVG(CREDIT_COMPLETE)
    FROM STUDENT
);
```
<img width="1008" height="511" alt="image" src="https://github.com/user-attachments/assets/e2ece2db-9c55-4ab7-a197-d5ffd34ffefe" />


### Query 2: Students with CGPA Greater Than Department Average

Retrieve the names of students who have a CGPA greater than the average CGPA of students in their department.

```sql
SELECT STUDENT_NAME
FROM STUDENT
WHERE CGPA > (
    SELECT AVG(CGPA)
    FROM STUDENT s2
    WHERE s2.DEPT_ID = STUDENT.DEPT_ID
);
```
<img width="1008" height="539" alt="image" src="https://github.com/user-attachments/assets/990bcdfe-c05b-4b66-9690-cc4e6b314485" />


---

## 4. Joining

### Query 1: Retrieve Course Name, Section Name and Class Time

```sql
SELECT C.COURSE_NAME, S.SECTION_NAME, S.CLASS_TIME
FROM COURSE C
JOIN SECTION S
ON C.COURSE_ID = S.SECTION_ID;
```
<img width="1008" height="533" alt="image" src="https://github.com/user-attachments/assets/e6785507-19c3-42eb-85c8-095f4ce5038b" />


### Query 2: Retrieve Student Registration Information

Retrieve student registration information along with course name, department name, faculty name, class time, and room number.

```sql
SELECT
    SR.STUDENT_ID,
    S.STUDENT_NAME,
    C.COURSE_NAME,
    D.DEPT_NAME,
    F.FACULTY_NAME,
    SEC.CLASS_TIME,
    SEC.CLASS_ROOM
FROM STUDENT_REG SR
JOIN STUDENT S
    ON SR.STUDENT_ID = S.STUDENT_ID
JOIN COURSE C
    ON SR.COURSE_ID = C.COURSE_ID
JOIN DEPARTMENT D
    ON C.DEPT_ID = D.DEPT_ID
JOIN FACULTY F
    ON SR.FACULTY_ID = F.FACULTY_ID
JOIN SECTION SEC
    ON SR.SECTION_ID = SEC.SECTION_ID;
```
<img width="1008" height="539" alt="image" src="https://github.com/user-attachments/assets/b5e7fba8-746b-4e52-9d12-5a834fc647b0" />


---

## 5. Views

### View 1: Course Enrollment

This view provides a summary of student enrollment, showing the number of students enrolled in each course.

```sql
CREATE VIEW Course_Enrollment AS
SELECT
    C.COURSE_ID,
    C.COURSE_NAME,
    COUNT(SR.STUDENT_ID) AS Enrollment_Count
FROM STUDENT_REG SR
JOIN COURSE C
    ON SR.COURSE_ID = C.COURSE_ID
GROUP BY C.COURSE_ID, C.COURSE_NAME;

SELECT * FROM Course_Enrollment;
```
<img width="1008" height="517" alt="image" src="https://github.com/user-attachments/assets/c827e84d-bc1f-4632-8a02-4ed0394a7003" />


### View 2: Student Enrollment Information

Create a view that includes information about students' course enrollment and any actions related to adding or dropping courses.

```sql
CREATE VIEW Student_Enrollment_Info AS
SELECT
    SR.STUDENT_ID,
    S.STUDENT_NAME,
    C.COURSE_NAME,
    D.DEPT_NAME,
    F.FACULTY_NAME,
    SEC.CLASS_TIME,
    SEC.CLASS_ROOM,
    AD.ACTION
FROM STUDENT_REG SR
JOIN STUDENT S
    ON SR.STUDENT_ID = S.STUDENT_ID
JOIN COURSE C
    ON SR.COURSE_ID = C.COURSE_ID
JOIN DEPARTMENT D
    ON C.DEPT_ID = D.DEPT_ID
JOIN FACULTY F
    ON SR.FACULTY_ID = F.FACULTY_ID
JOIN SECTION SEC
    ON SR.SECTION_ID = SEC.SECTION_ID
LEFT JOIN ADDING_DROPING AD
    ON SR.STUDENT_ID = AD.STUDENT_ID
    AND SR.COURSE_ID = AD.COURSE_ID
    AND SR.SECTION_ID = AD.SECTION_ID;

SELECT * FROM Student_Enrollment_Info;
```
<img width="1008" height="534" alt="image" src="https://github.com/user-attachments/assets/3a18babb-0046-4eb4-b99f-f99e00eda0c2" />


---

[Back to Table of Contents](../README.md)
