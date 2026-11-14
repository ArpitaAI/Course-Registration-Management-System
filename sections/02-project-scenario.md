
# 2. Project Scenario



In a course registration management system, one student have many sections and many student have one section.

A student is identified by a Student_ID. The system also stores Student_Name, Student_ID, Department_ID, CGPA, and Credits_Completed.

Section is identified by Section_ID and the system also stores Class_Room, Section_Name and Class_Time. From one section many students can take the form of Student_Reg.

Student can take Form from Student_Reg. A student can register only once but registration is done for many students. Here, Student_Reg is identified by Reg-ID. Also, Student_ID, Dept-ID (Foreign key), Course-ID, Section-ID, Faculty-ID AND Reg-ID are also stored in this system. Many student can register in one department.

A student has one department and one department can be taken by many students. Department is identified by department-id and it also stores dept name. A department has many faculty but one faculty can take only one department. To identify Faculty the system stores faculty id along with faculty name and dept id (Foreign key). A faculty member is identified by a faculty ID. The system also stores faculty name and department ID (Foreign Key). Many faculty can provide the Form of Adding/Dropping to many students.

One department have own many courses but one courses have own only one department. Course is identified by Course_ID and it also stores Course_Name, Dept_ID (Foreign Key) and Prerequisite_Course. Also many student can take the Form of Adding/Dropping from many courses.

A section can provide many Form of Adding/Dropping and one Adding/Dropping Form is provided to many section. Adding/Dropping is identified by AD_ID and it also stores Student_ID, Dept_ID (Foreign key), Action, Course_ID, Section_ID and Faculty_ID. Also, one student can add or drop many subject and one subject can add or drop by many students.

---

[Back to Table of Contents](../README.md)
