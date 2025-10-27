### 🗓️ Day 2 — October 27, 2025 (9:30 am - 10:30 am)

**Focus:** SELECT Statements in MySQL  
WHERE Clause in MySQL

**Number of Videos Watched:** 4

**Total Learning Time:** 1 hr

**Today's Mood:** Charged up. I feel like I can conquer the world!

---

#### 🧠 What I Learned
- 

#### 🤯 My Struggle Moment
- 

#### ⚡ Aha! Moment
- 

#### 🧰 Tools & Commands I Used
- 

#### 🎨 Mini Project / Practice Task
```
**Project Task:**
You’ve been asked to help management identify which departments are paying the most on average. Use the company’s `employees` table to calculate the **average salary** for each department, then rank all departments from the **highest** to **lowest** average salary.

---

**Step-by-Step Instructions:**

1. Use the table named `employees`.
2. Select the `department` column.
3. Use the `AVG()` function on the `salary` column and give it an alias called `avg_salary`.
4. Group the results by `department` to calculate averages for each department.
5. Order the results by `avg_salary` in **descending** order so the highest averages appear first.

My thought process:
 -- Pseudo Query --
# occupation is a field/data column
# calculation to do in SELECT: AVG(salary) aliased AS avg_salary
# table to use - employees
# GROUP the calculation to get the average for each occupation
# ORDER the avg_salary in DESC order to get the salary from highest to lowest

SQL Query
SELECT occupation,
AVG(salary) AS avg_salary
FROM employees
GROUP BY occupation
ORDER BY avg_salary DESC;

```

#### 💭 Reflection
> 














