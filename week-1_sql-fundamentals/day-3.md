### 🗓️ Day 3 — October 28, 2025 (time)

**Focus:** 

**Number of Videos Watched:** 4

**Total Learning Time:** 1 hr

**Today's Mood:** 

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
-- Project Task on HAVING vs WHERE #1:
You’re working on refining employee and salary reports for management. The goal is to understand how to filter data effectively  
— both **before** and **after** aggregation.  
Start by analyzing the average age of employees by gender, and notice why filtering with `WHERE`  
on an aggregated function (like `AVG(age)`) causes an error. Then, apply the correct approach using  
the **HAVING** clause to filter aggregated results (e.g., genders with an average age above 40).  
Next, analyze average salaries by occupation to identify which managerial roles earn more than ₦75,000 on average.  
While doing this, use **WHERE** to filter data at the **row level** (like selecting occupations ending with “manager”)  
and **HAVING** to filter at the **aggregate level** based on computed averages.

---

Step-by-Step Instructions:

1. Try filtering gender groups by their **average age** using `WHERE`, and observe why it produces an error —  
it’s because `WHERE` filters individual rows, not grouped results.  
2. Fix the query using the **HAVING** clause to filter gender groups whose **average age** is greater than 40.  
3. Move to the `employee_salary` table and use `WHERE` to filter records that match a certain text pattern —  
for example, occupations that **end with “manager.”**  
4. After grouping by **occupation**, use the **HAVING** clause to filter only those occupations whose **average salary** exceeds ₦75,000.  
5. Compare how **WHERE** and **HAVING** operate at different stages of query execution —  
`WHERE` filters **rows before grouping**, while `HAVING` filters **groups after aggregation**.  

--

-- SQL Query
SELECT occupation, AVG(salary) as avg_salary
FROM employee_salary
WHERE occupation LIKE '%manager%' 
GROUP BY occupation
HAVING AVG(salary) > 75000
;

```



#### 💭 Reflection
> tbd














