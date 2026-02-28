# Experiment 2 – Retrieving Data from Employee Table

## 🎯 Objective
To perform various SELECT queries on the `employee` table to retrieve specific information.

---

## 1️⃣ List all distinct jobs in Employee.

```sql
SELECT DISTINCT job
FROM employee;
```

---

## 2️⃣ List all information about employees in Department Number 30.

```sql
SELECT *
FROM employee
WHERE deptno = 30;
```

---

## 3️⃣ Find all department numbers with department names greater than 20.

```sql
SELECT deptno
FROM department
WHERE deptno > 20;
```

---

## 4️⃣ Find all information about managers as well as clerks in department 30.

```sql
SELECT *
FROM employee
WHERE deptno = 30
AND job IN ('MANAGER', 'CLERK');
```

---

## 5️⃣ List employee name, employee number, and department of all clerks.

```sql
SELECT ename, empno, deptno
FROM employee
WHERE job = 'CLERK';
```

---

## 6️⃣ Find all managers not in department 30.

```sql
SELECT *
FROM employee
WHERE job = 'MANAGER'
AND deptno <> 30;
```

---

## 7️⃣ List information about employees in department 10 who are not managers or clerks.

```sql
SELECT *
FROM employee
WHERE deptno = 10
AND job NOT IN ('MANAGER', 'CLERK');
```

---

## 8️⃣ Find employees and jobs earning between 1200 and 1400.

```sql
SELECT ename, job, sal
FROM employee
WHERE sal BETWEEN 1200 AND 1400;
```

---

## 9️⃣ List name and department number of employees who are clerks, analysts, or salesmen.

```sql
SELECT ename, deptno
FROM employee
WHERE job IN ('CLERK', 'ANALYST', 'SALESMAN');
```

---

## 🔟 List name and department number of employees whose names begin with M.

```sql
SELECT ename, deptno
FROM employee
WHERE ename LIKE 'M%';
