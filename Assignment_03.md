# Assignment 3 – Advanced Retrieval Queries

## 🎯 Objective
To perform advanced filtering, pattern matching, ordering, and salary calculations using the `employee` table.

---

## 1️⃣ List all employees and jobs in Department 30 in descending order by salary.

```sql
SELECT ename, job, sal
FROM employee
WHERE deptno = 30
ORDER BY sal DESC;
```

---

## 2️⃣ List job and department number of employees whose name are five letters long beginning with 'A' and ending with 'N'.

```sql
SELECT job, deptno
FROM employee
WHERE ename LIKE 'A___N';
```

---

## 3️⃣ Display the name of employees whose name starts with alphabet S.

```sql
SELECT ename
FROM employee
WHERE ename LIKE 'S%';
```

---

## 4️⃣ Display the names of employees whose name ends with alphabet S.

```sql
SELECT ename
FROM employee
WHERE ename LIKE '%S';
```

---

## 5️⃣ Display the names of employees working in department 10 or 20 or 40 or working as clerk, salesman or analyst.

```sql
SELECT ename
FROM employee
WHERE deptno IN (10, 20, 40)
OR job IN ('CLERK', 'SALESMAN', 'ANALYST');
```

---

## 6️⃣ Display employee number and names for employees who earn commission.

```sql
SELECT empno, ename
FROM employee
WHERE comm IS NOT NULL
AND comm > 0;
```

---

## 7️⃣ Display employee number and total salary for each employee.

```sql
SELECT empno, (sal + IFNULL(comm,0)) AS total_salary
FROM employee;
```

---

## 8️⃣ Display employee number and annual salary for each employee.

```sql
SELECT empno, sal * 12 AS annual_salary
FROM employee;
```

---

## 9️⃣ Display the names of all employees working as clerks and drawing a salary more than 3000.

```sql
SELECT ename
FROM employee
WHERE job = 'CLERK'
AND sal > 3000;
```

---

## 🔟 Display the names of employees who are working as clerk, salesman or analyst and drawing a salary more than 3000.

```sql
SELECT ename
FROM employee
WHERE job IN ('CLERK', 'SALESMAN', 'ANALYST')
AND sal > 3000;
```

---

## ✅ Conclusion
Successfully executed advanced SQL queries involving filtering, pattern matching, sorting, and salary calculations on the `employee` table.