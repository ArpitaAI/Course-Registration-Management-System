
# 7. Table Creation

The following SQL statements are used to create the tables of the Course Registration Management System.

## 1. Department Table

```sql
CREATE TABLE department (
    dept_id INT PRIMARY KEY,
    dept_name VARCHAR2(50) NOT NULL
);

DESCRIBE student;
```

## 2. Faculty Table

```sql
CREATE TABLE faculty (
    faculty_id INT PRIMARY KEY,
    faculty_name VARCHAR2(50) NOT NULL,
    dept_id INT
    FOREIGN KEY (dept_id) REFERENCES department(dept_id)
);

DESCRIBE faculty;
```

## 3. Course Table

```sql
CREATE TABLE course (
    course_id INT PRIMARY KEY,
    course_name VARCHAR2(50) NOT NULL
    Prerequisite_course VARCHAR2(100) NOT NULL
    dept_id INT
    FOREIGN KEY (dept_id) REFERENCES department(dept_id)
);

DESCRIBE course;
```

## 4. Section Table

```sql
CREATE TABLE section (
    section_id INT PRIMARY KEY,
    section_name VARCHAR2(50) NOT NULL,
    class_time VARCHAR2(50) NOT NULL,
    class_room VARCHAR2(50) NOT NULL
);

DESCRIBE section;
```

## 5. Student Table

```sql
CREATE TABLE student (
    student_id INT PRIMARY KEY,
    student_name VARCHAR2(50) NOT NULL,
    credit_complete FLOAT NOT NULL,
    cgpa FLOAT NOT NULL,
    dept_id INT,
    FOREIGN KEY (dept_id) REFERENCES department(dept_id)
);

DESCRIBE STUDENT;
```

## 6. Student Registration Table

```sql
CREATE TABLE student_reg (
    reg_id INT PRIMARY KEY,
    student_id INT,
    FOREIGN KEY (student_id) REFERENCES student(student_id),
    dept_id INT,
    FOREIGN KEY (dept_id) REFERENCES department(dept_id),
    course_id INT,
    FOREIGN KEY (course_id) REFERENCES course(course_id),
    section_id INT,
    FOREIGN KEY (section_id) REFERENCES section(section_id),
    faculty_id INT,
    FOREIGN KEY (faculty_id) REFERENCES faculty(faculty_id)
);
```

## 7. Adding and Dropping Table

```sql
CREATE TABLE adding_droping (
    a_d_id INT PRIMARY KEY,
    student_id INT,
    FOREIGN KEY (student_id) REFERENCES student(student_id),
    action VARCHAR2(50) NOT NULL,
    course_id INT,
    FOREIGN KEY (course_id) REFERENCES course(course_id),
    section_id INT,
    FOREIGN KEY (section_id) REFERENCES section(section_id),
    faculty_id INT,
    FOREIGN KEY (faculty_id) REFERENCES faculty(faculty_id)
    dept_id INT,
    FOREIGN KEY (dept_id) REFERENCES department(dept_id),
);
```

---

[Back to Table of Contents](../README.md)
