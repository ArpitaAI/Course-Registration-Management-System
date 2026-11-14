
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

### Query 2: Calculate Total Credits Completed

Calculate the total credits completed by the student with STUDENT_ID 4 from the STUDENT table.

```sql
SELECT SUM(CREDIT_COMPLETE) AS Total_Credits_Completed
FROM STUDENT
WHERE STUDENT_ID = 4;
```

---

## 2. Group Function

### Query 1: Calculate Average CGPA

Calculate the average CGPA of all students in the STUDENT table.

```sql
SELECT AVG(CGPA) AS Average_CGPA
FROM STUDENT;
```

### Query 2: Count Students in Each Department

```sql
SELECT DEPT_ID, COUNT(*) AS Student_Count
FROM STUDENT
GROUP BY DEPT_ID;
```

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

---

## 4. Joining

### Query 1: Retrieve Course Name, Section Name and Class Time

```sql
SELECT C.COURSE_NAME, S.SECTION_NAME, S.CLASS_TIME
FROM COURSE C
JOIN SECTION S
ON C.COURSE_ID = S.SECTION_ID;
```

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

---

[Back to Table of Contents](../README.md)
