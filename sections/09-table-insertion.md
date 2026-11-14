
# 9. Table Insertion

## 1. Department

```sql
INSERT INTO department VALUES (dept_id.NEXTVAL, 'Computer Science');
INSERT INTO department VALUES (dept_id.NEXTVAL, ' English Literature');
INSERT INTO department VALUES (dept_id.NEXTVAL, 'Electrical Engineering');
INSERT INTO department VALUES (dept_id.NEXTVAL, 'Business Administration');
INSERT INTO department VALUES (dept_id.NEXTVAL, 'Psychology');
INSERT INTO department VALUES (dept_id.NEXTVAL, 'Chemistry');
INSERT INTO department VALUES (dept_id.NEXTVAL, 'Marketing');

SELECT * FROM department;
```

## 2. Course

```sql
INSERT INTO course VALUES (course_id.NEXTVAL, 'introduction to database','INTEGRALCALCULUS & ORDINARY DIFFERENTIAL EQUATIONS',1);

INSERT INTO course VALUES (course_id.NEXTVAL, ' ALGORITHMS','DATA STRUCTURE',1);

INSERT INTO course VALUES (course_id.NEXTVAL, 'OBJECT ORIENTED PROGRAMMING 2','DATA STRUCTURE,INTRODUCTION TO DATABASE',1);

INSERT INTO course VALUES (course_id.NEXTVAL, 'MATRICES, VECTORS, FOURIER ANALYSIS','COMPLEX VARIABLE,LAPLACE & Z-TRANSFORMATION',1);

INSERT INTO course VALUES (course_id.NEXTVAL, 'DIGITAL LOGIC AND CIRCUITS','ELECTRONIC DEVICES LAB',1);

INSERT INTO course VALUES (course_id.NEXTVAL, 'BANGLADESH STUDIES','INTRODUCTION TO COMPUTER STUDIES',1);

INSERT INTO course VALUES (course_id.NEXTVAL, 'CHEMISTRY','PHYSICS 2',1);

SELECT * FROM course;
```

## 3. Section

```sql
INSERT INTO section VALUES (section_id.NEXTVAL, 'A','sunday 8am to 10am,thuesday 8am to 10am','6107');

INSERT INTO section VALUES (section_id.NEXTVAL, 'B','monday 8am to 10am,Wednesday 8am to 10am','6108');

INSERT INTO section VALUES (section_id.NEXTVAL, 'C','sunday 10am to 12pm,thuesday 10am to 12pm','6109');

INSERT INTO section VALUES (section_id.NEXTVAL, 'D','monday 10am to 12pm,Wednesday 10am to 12pm','6110');

INSERT INTO section VALUES (section_id.NEXTVAL, 'E','sunday 12pm to 2pm,thuesday 12am to 2pm','5107');

INSERT INTO section VALUES (section_id.NEXTVAL, 'F','monday 1pm to 3pm,Wednesday 1pm to 3am','5108');

INSERT INTO section VALUES (section_id.NEXTVAL, 'G','sunday 2pm to 4pm,thuesday 8am to 10am','5107');

SELECT * FROM section;
```

## 4. Student

```sql
INSERT INTO student VALUES (student_id.NEXTVAL, 'MEHJABIN MOSTAFA','40','3.50',1);

INSERT INTO student VALUES (student_id.NEXTVAL, 'ESTIAK AHNED AL NAHIAN','66','3.50',1);

INSERT INTO student VALUES (student_id.NEXTVAL, 'MD NAHIDUR RAHMAN','50','3.60',1);

INSERT INTO student VALUES (student_id.NEXTVAL, 'ARPITA ISLAM','60','3.70',1);

INSERT INTO student VALUES (student_id.NEXTVAL, 'MD AKRAM HOSSAIN','40','3.50',1);

INSERT INTO student VALUES (student_id.NEXTVAL, 'Md fahim','70','3.50',3);

INSERT INTO student VALUES (student_id.NEXTVAL, 'Md maruf','77','3.50',4);

SELECT * FROM student;
```

## 5. Faculty

```sql
INSERT INTO faculty VALUES (faculty_id.NEXTVAL, 'JUENA AHMED NOSHIN',1);

INSERT INTO faculty VALUES (faculty_id.NEXTVAL, 'VICTOR STANY ROZARIO',1);

INSERT INTO faculty VALUES (faculty_id.NEXTVAL, 'SAZZAD HOSSAIN',1);

INSERT INTO faculty VALUES (faculty_id.NEXTVAL, 'KAWSER IROM RUSHEE',1);

INSERT INTO faculty VALUES (faculty_id.NEXTVAL, 'TOHEDUL ISLAM',3);

INSERT INTO faculty VALUES (faculty_id.NEXTVAL, 'MD HASIBUL HASAN',3);

INSERT INTO faculty VALUES (faculty_id.NEXTVAL, 'REZWAN AHMED',1);

SELECT * FROM faculty;
```

## 6. Student Registration

```sql
INSERT INTO student_reg VALUES (reg_id.NEXTVAL, 1,1,1,1,1);

INSERT INTO student_reg VALUES (reg_id.NEXTVAL, 4,1,2,4,5);

INSERT INTO student_reg VALUES (reg_id.NEXTVAL, 2,1,1,2,1);

INSERT INTO student_reg VALUES (reg_id.NEXTVAL, 3,1,3,2,3);

INSERT INTO student_reg VALUES (reg_id.NEXTVAL, 5,1,6,1,1);

INSERT INTO student_reg VALUES (reg_id.NEXTVAL, 6,3,5,5,5);

SELECT * FROM STUDENT_REG;
```

## 7. Adding/Dropping

```sql
INSERT INTO adding_droping VALUES (A_D_ID.NEXTVAL, 1,'dropped', 1, 1, 1,1);

INSERT INTO adding_droping VALUES (A_D_ID.NEXTVAL, 1,'ADDED', 1, 3, 1,1);

INSERT INTO adding_droping VALUES (A_D_ID.NEXTVAL, 2,'dropped', 1, 2, 1,1);

INSERT INTO adding_droping VALUES (A_D_ID.NEXTVAL, 2,'dropped', 1, 2, 1,1);

SELECT * FROM adding_droping;
```

---

[Back to Table of Contents](../README.md)
