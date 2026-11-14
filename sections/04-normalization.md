
# 4. Normalization

## 1. Have Own

### UNF
Have own (dept_id, dept_name, course_id, course_name, prerequisite_course)

### 1NF
There is no multivalued attribute. Relation already in 1NF.

1. dept_id, dept_name, course_id, course_name, prerequisite_course

### 2NF
1. dept_id, dept_name
2. course_id, course_name, prerequisite_course

### 3NF
There is no transitive dependency. Relation already in 3NF.

1. dept_id, dept_name
2. course_id, course_name, prerequisite_course

### Table Creation
1. dept_id, dept_name
2. course_id, course_name, prerequisite_course, dept_id

---

## 2. Has a (Faculty and Department)

### UNF
Has a (faculty_id, faculty_name, dept_id, dept_name)

### 1NF
There is no multivalued attribute. Relation already in 1NF.

1. faculty_id, faculty_name, dept_id, dept_name

### 2NF
1. faculty_id, faculty_name
2. dept_id, dept_name

### 3NF
There is no transitive dependency. Relation already in 3NF.

1. faculty_id, faculty_name
2. dept_id, dept_name

### Table Creation
1. dept_id, dept_name
2. faculty_id, faculty_name, dept_id

---

## 3. Has a (Student and Department)

### UNF
Has a (dept_id, dept_name, student_id, student_name_cradit_complete, cgpa)

### 1NF
There is no multivalued attribute. Relation already in 1NF.

1. dept_id, dept_name, student_id, student_name_cradit_complete, cgpa

### 2NF
1. dept_id, dept_name
2. student_id, student_name_cradit_complete, cgpa

### 3NF
There is no transitive dependency. Relation already in 3NF.

1. dept_id, dept_name
2. student_id, student_name_cradit_complete, cgpa

### Table Creation
1. dept_id, dept_name
2. student_id, student_name_cradit_complete, cgpa, dept_id

---

## 4. FORM

### UNF
FORM (student_id, student_name_cradit_complete, cgpa, dept_id, dept_id, dept_name, faculty_id, faculty_name, dept_id, course_id, course_name, prerequisite_course, dept_id, section_id, section_name, class_time, class_rom, a_d_id, student_id, action, course_id, section_id, faculty_id, dept_id)

### 1NF
There is no multivalued attribute. Relation already in 1NF.

### 2NF
1. dept_id, dept_name
2. student_id, student_name_cradit_complete, cgpa, dept_id, faculty_id, faculty_name, course_id, course_name, prerequisite_course, section_id, section_name, class_time, class_rom, a_d_id, student_id, action, course_id, section_id, faculty_id, dept_id

### 3NF
1. section_id, section_name, class_time, class_rom
2. student_id, action, course_id, section_id, faculty_id, dept_id
3. student_id, dept_id, course_id, section_id, faculty_id

### Table Creation
1. section_id, section_name, class_time, class_rom
2. a_d_id, student_id, action, course_id, section_id, faculty_id, dept_id
3. reg_id, student_id, dept_id, course_id, section_id, faculty_id
4. course_name, prerequisite_course, dept_id, section_id, section_name, class_time, class

---

## 5. CAN

### UNF
can (a_d_id, student_id, action, course_id, section_id, faculty_id, dept_id, student_id, student_name_cradit_complete, cgpa, dept_id)

### 1NF
There is no multivalued attribute. Relation already in 1NF.

1. a_d_id, student_id, action, course_id, section_id, faculty_id, dept_id, dept_name, student_id, student_name_cradit_complete, cgpa

### 2NF
1. a_d_id, student_id, action, course_id, section_id, faculty_id, dept_id
2. student_id, student_name, cradit_complete, cgpa, dept_id

### 3NF
1. student_id, student_name, cradit_complete, cgpa
2. dept_id, dept_name
3. course_id, section_id, faculty_id, dept_id

### Table Creation
1. dept_id, dept_name, student_id
2. course_id, course_name, dept_id

---

## 6. Temporary Tables

1. dept_id, dept_name, student_id
2. dept_id, dept_name
3. course_id, course_name, dept_id
4. course_id, course_name, prerequisite_course, dept_id
5. student_id, student_name, cradit_complete, cgpa, dept_id
6. faculty_id, faculty_name, dept_id
7. section_id, section_name, class_time, class_rom
8. student_id, student_name_cradit_complete, cgpa, dept_id
9. a_d_id, student_id, action, course_id, section_id, faculty_id, dept_id
10. section_id, section_name, class_time, class_rom
11. reg_id, student_id, dept_id, course_id, section_id, faculty_id
12. dept_id, dept_name
13. course_name, prerequisite_course, dept_id, section_id, section_name, class_time, class
14. reg_id, student_id, dept_id, course_id, section_id, faculty_id
15. dept_id, dept_name
16. a_d_id, student_id, action, course_id, section_id, faculty_id, dept_id

---

## 7. Final Tables

1. dept_id, dept_name

2. course_id, course_name, prerequisite_course, dept_id

3. faculty_id, faculty_name, dept_id

4. student_id, student_name_cradit_complete, cgpa, dept_id

5. section_id, section_name, class_time, class_rom

6. a_d_id, student_id, action, course_id, section_id, faculty_id, dept_id

7. reg_id, student_id, dept_id, course_id, section_id, faculty_id

---

[Back to Table of Contents](../README.md)
