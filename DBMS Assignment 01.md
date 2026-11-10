# Database Management System - Assignment 01 (Example 01)

## Part 1: Table Creation and Data Insertion

### 1. `student` Table
Create a `student` table having the fields `roll`, `name`, `dept`, `year`, and `semester` by setting `roll` as a primary key, and insert the following values into the table:

| Roll | Name | Dept. | Year | Semester |
| :--- | :--- | :--- | :--- | :--- |
| 06543201 | Rahim | BBA | 2nd | 1st |
| 06543202 | Karim | ICE | 2nd | 1st |
| 06543203 | Motin | CSE | 1st | 2nd |
| 05654456 | Swadhin | CSE | 1st | 2nd |
| 05654457 | Hena | BBA | 4th | 2nd |
| 05654458 | Sohag | CSE | 3rd | 1st |

#### SQL Implementation:
```sql
CREATE TABLE student (
    roll VARCHAR(15) PRIMARY KEY,
    name VARCHAR(50),
    dept VARCHAR(20),
    year VARCHAR(10),
    semester VARCHAR(10)
);

INSERT INTO student (roll, name, dept, year, semester) VALUES
('06543201', 'Rahim', 'BBA', '2nd', '1st'),
('06543202', 'Karim', 'ICE', '2nd', '1st'),
('06543203', 'Motin', 'CSE', '1st', '2nd'),
('05654456', 'Swadhin', 'CSE', '1st', '2nd'),
('05654457', 'Hena', 'BBA', '4th', '2nd'),
('05654458', 'Sohag', 'CSE', '3rd', '1st');
```

---

### 2. `studentInfo` Table
Create a `studentInfo` table having the fields `roll`, `name`, `fatherName`, `address`, and `mobile` by setting `roll` as a primary key, and insert the following values into the table:

| Roll | Name | Father Name | Address | Mobile |
| :--- | :--- | :--- | :--- | :--- |
| 06543201 | Rahim | Ataur | Rajshahi | 01719201233 |
| 06543202 | Karim | Tareq | Dhaka | 01719202020 |
| 06543203 | Motin | Rahman | Khulna | 01719202678 |
| 05654456 | Swadhin | Fazlu | Rajshahi | 01719204564 |
| 05654457 | Hena | Rahman | Rajshahi | 01119212020 |
| 05654458 | Sohag | Fazlul | Natore | 01719202222 |

#### SQL Implementation:
```sql
CREATE TABLE studentInfo (
    roll VARCHAR(15) PRIMARY KEY,
    name VARCHAR(50),
    fatherName VARCHAR(50),
    address VARCHAR(100),
    mobile VARCHAR(20)
);

INSERT INTO studentInfo (roll, name, fatherName, address, mobile) VALUES
('06543201', 'Rahim', 'Ataur', 'Rajshahi', '01719201233'),
('06543202', 'Karim', 'Tareq', 'Dhaka', '01719202020'),
('06543203', 'Motin', 'Rahman', 'Khulna', '01719202678'),
('05654456', 'Swadhin', 'Fazlu', 'Rajshahi', '01719204564'),
('05654457', 'Hena', 'Rahman', 'Rajshahi', '01119212020'),
('05654458', 'Sohag', 'Fazlul', 'Natore', '01719202222');
```

---

## Part 2: Queries & Solutions

### A. Find out the names of those students who:

**1. are in 1st semester.**
```sql
SELECT name FROM student WHERE semester = '1st';
```

**2. are in 2nd year.**
```sql
SELECT name FROM student WHERE year = '2nd';
```

**3. are in CSE.**
```sql
SELECT name FROM student WHERE dept = 'CSE';
```

**4. have the roll `06543201`.**
```sql
SELECT name FROM student WHERE roll = '06543201';
```

---

### B. Find out the names, address, and mobile for those students whose:

**1. father’s name is Rahman.**
```sql
SELECT name, address, mobile FROM studentInfo WHERE fatherName = 'Rahman';
```

**2. mobile is `01719202020`.**
```sql
SELECT name, address, mobile FROM studentInfo WHERE mobile = '01719202020';
```

**3. address is Rajshahi.**
```sql
SELECT name, address, mobile FROM studentInfo WHERE address = 'Rajshahi';
```

**4. address is Rajshahi and father’s name is Rahman.**
```sql
SELECT name, address, mobile FROM studentInfo WHERE address = 'Rajshahi' AND fatherName = 'Rahman';
```

**5. roll is `05654456`.**
```sql
SELECT name, address, mobile FROM studentInfo WHERE roll = '05654456';
```