
# 8. Table Sequences

The following sequences are created to automatically generate unique IDs for the tables in the Course Registration Management System.

## 1. Department ID Sequence

```sql
CREATE SEQUENCE dept_id
INCREMENT BY 1
START WITH 1
MAXVALUE 1000
NOCACHE
NOCYCLE;
```

## 2. Course ID Sequence

```sql
CREATE SEQUENCE course_id
INCREMENT BY 1
START WITH 1
MAXVALUE 1000
NOCACHE
NOCYCLE;
```

## 3. Section ID Sequence

```sql
CREATE SEQUENCE section_id
INCREMENT BY 1
START WITH 1
MAXVALUE 1000
NOCACHE
NOCYCLE;
```

## 4. Student ID Sequence

```sql
CREATE SEQUENCE student_id
INCREMENT BY 1
START WITH 1
MAXVALUE 1000
NOCACHE
NOCYCLE;
```

## 5. Faculty ID Sequence

```sql
CREATE SEQUENCE faculty_id
INCREMENT BY 1
START WITH 1
MAXVALUE 1000
NOCACHE
NOCYCLE;
```

## 6. Registration ID Sequence

```sql
CREATE SEQUENCE reg_id
INCREMENT BY 1
START WITH 1
MAXVALUE 1000
NOCACHE
NOCYCLE;
```

## 7. Adding/Dropping ID Sequence

```sql
CREATE SEQUENCE a_d_id
INCREMENT BY 1
START WITH 1
MAXVALUE 1000
NOCACHE
NOCYCLE;
```

---

[Back to Table of Contents](../README.md)
