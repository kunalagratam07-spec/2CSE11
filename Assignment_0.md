# Assignment 0 – Database Creation 

## Objective
To create database `KUNAL` and `department` & `employee` tables with inserted values.

---

## 1️⃣ Create Database

```sql
CREATE DATABASE KUNAL;
SHOW DATABASES;
```
---

### ✅ Select Database

```sql
USE KUNAL;
```

---

### 2️⃣ Create `Department` Table

```sql
CREATE TABLE department(
    deptno INT(2) PRIMARY KEY,
    dname VARCHAR(15) NOT NULL
);
```

---

### Describe Table

```sql
DESC department;
```

---

### 3️⃣ Insert Values into `Department`

```sql
INSERT INTO department VALUES
(10, 'RESEARCH'),
(20, 'ACCOUNTING'),
(30, 'SALES'),
(40, 'OPERATIONS');
```

---

### Verify Data

```sql
SELECT * FROM department;
```

---

## 4️⃣ Create `Employee` Table

```sql
CREATE TABLE employee(
    empno INT(4) PRIMARY KEY,
    ename VARCHAR(20) NOT NULL,
    job VARCHAR(20),
    mgr INT(4),
    hiredate DATE,
    sal INT(10),
    comm INT(7),
    deptno INT(2),
    FOREIGN KEY (deptno) REFERENCES department(deptno)
);
```

---

### Describe Table

```sql
DESC employee;
```

---

## 5️⃣ Insert Values into `Employee`

```sql
INSERT INTO employee VALUES
(7369, 'SMITH', 'CLERK', 7902, '1980-12-17', 800, NULL, 20),
(7499, 'ALLEN', 'SALESMAN', 7698, '1981-02-20', 1600, 300, 30),
(7521, 'WARD', 'SALESMAN', 7698, '1981-02-22', 1250, 300, 30),
(7566, 'JONES', 'MANAGER', 7839, '1981-04-02', 2975, NULL, 20),
(7654, 'MARTIN', 'SALESMAN', 7698, '1981-09-28', 1250, 1400, 30),
(7698, 'BLAKE', 'MANAGER', 7839, '1981-05-01', 2850, NULL, 30),
(7782, 'CLARK', 'MANAGER', 7839, '1981-06-09', 2450, NULL, 20),
(7788, 'SCOTT', 'ANALYST', 7566, '1982-12-09', 3000, NULL, 20),
(7839, 'KING', 'PRESIDENT', NULL, '1981-11-17', 5000, NULL, 20),
(7844, 'TURNER', 'SALESMAN', 7698, '1981-09-08', 1500, 0, 30),
(7876, 'ADAMS', 'CLERK', 7788, '1983-01-12', 1100, NULL, 20),
(7900, 'JAMES', 'CLERK', 7698, '1981-12-03', 950, NULL, 30),
(7902, 'FORD', 'ANALYST', 7566, '1981-12-03', 3000, NULL, 20),
(7934, 'MILLER', 'CLERK', 7782, '1982-01-23', 1300, NULL, 10);
```

---

### Verify Data

```sql
SELECT * FROM employee;
```

---

## ✅ Conclusion
Successfully created database `KUNAL` and tables `department` and `employee` with inserted records.