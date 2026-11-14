
# 11. Relational Algebra

Relational Algebra is used to perform operations on relations (tables) in a database.

## 1. Projecting Student Names and CGPA

**Expression:**

```text
Π STUDENT_NAME, CGPA (STUDENT)
```

## 2. Selecting Courses Offered by Computer Science Department

**Expression:**

```text
σ DEPT_ID = 1 (COURSE)
```

## 3. Selecting Student Name with CGPA 3.5 from Student Table

**Expression:**

```text
σ CGPA = 3.5 (STUDENT)
```

## 4. Union of Computer Science and Electrical Engineering Courses

**Expression:**

```text
(σ DEPT_ID = 1 (COURSE)) ∪ (σ DEPT_ID = 3 (COURSE))
```

## 5. Projecting Student Names and Their CGPA

**Expression:**

```text
Π STUDENT.STUDENT_NAME, STUDENT.CGPA (STUDENT)
```

---

[Back to Table of Contents](../README.md)
