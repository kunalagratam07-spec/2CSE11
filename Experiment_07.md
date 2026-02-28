# 📘 Experiment 7 – Aggregate & Advanced Queries

## 🎯 Objective  
To perform aggregate functions, grouping, conditional queries, and date calculations on the `employee` table using MariaDB.

---

## 1️⃣ Compute the number of days remaining in this year.

```sql
SELECT DATEDIFF(
STR_TO_DATE(CONCAT(YEAR(CURDATE()), '-12-31'), '%Y-%m-%d'), CURDATE()
) AS days_remaining;
```

---

## 2️⃣ Find the highest and lowest salaries and the difference between them.

```sql
SELECT MAX(sal) AS highest_salary,
MIN(sal) AS lowest_salary,
(MAX(sal) - MIN(sal)) AS salary_difference
FROM employee;
```

---

## 3️⃣ List employees whose commission is greater than 25% of their salary.

```sql
SELECT *
FROM employee
WHERE comm > (sal * 0.25);
```

---

## 4️⃣ Display salary in dollar format.

```sql
SELECT ename,
CONCAT('$', FORMAT(sal, 2)) AS salary_in_dollars
FROM employee;
```

---

## 5️⃣ Create a matrix query to display job, salary based on department number, and total salary for that job.

```sql
SELECT job,
SUM(CASE WHEN deptno = 10 THEN sal ELSE 0 END) AS Dept_10,
SUM(CASE WHEN deptno = 20 THEN sal ELSE 0 END) AS Dept_20,
SUM(CASE WHEN deptno = 30 THEN sal ELSE 0 END) AS Dept_30,
SUM(sal) AS Total_Salary
FROM employee
GROUP BY job;
```

---

## 6️⃣ Display total number of employees and number hired in 1980, 1981, 1982, and 1983.

```sql
SELECT COUNT(*) AS total_employees,
SUM(YEAR(hiredate) = 1980) AS hired_1980,
SUM(YEAR(hiredate) = 1981) AS hired_1981,
SUM(YEAR(hiredate) = 1982) AS hired_1982,
SUM(YEAR(hiredate) = 1983) AS hired_1983
FROM employee;
```

---

## 7️⃣ Get the last Sunday of any month (example: current month).

```sql
SELECT DATE_SUB(
LAST_DAY(CURDATE()),
INTERVAL (DAYOFWEEK(LAST_DAY(CURDATE())) - 1) DAY
) AS last_sunday;
```

---

## 8️⃣ Display department numbers and total number of employees in each department.

```sql
SELECT deptno,
COUNT(*) AS total_employees
FROM employee
GROUP BY deptno;
```

---

## 9️⃣ Display various jobs and total number of employees in each job group.

```sql
SELECT job,
COUNT(*) AS total_employees
FROM employee
GROUP BY job;
```

---

## 🔟 Display department numbers and total salary for each department.

```sql
SELECT deptno,
SUM(sal) AS total_salary
FROM employee
GROUP BY deptno;