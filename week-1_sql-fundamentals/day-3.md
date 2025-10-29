### 🗓️ Day 3 — October 28, 2025 (time)

**Focus:** ORDER BY, WHERE, and HAVING in SQL

**Number of Videos Watched:** 4

**Total Learning Time:** 3 hr

**Today's Mood:** Tired but had to show up 🙂


---

#### 🧠 What I Learned

* **ORDER BY prioritization:** When sorting by multiple columns, SQL works by *priority*. The first column is the main one it sorts by.

* **Secondary sorting:** Once the first column is sorted, SQL only uses the second column if there are duplicates in the first.

* **Unique second columns:** If the second column has all unique values, there’s nothing left to rearrange — SQL leaves it as is.

* **Why it matters:** Forcing an unnecessary sort can literally mess up your data order — like swapping people’s ages just to make the table “look” organized.

* **WHERE vs HAVING:**

  * `WHERE` filters data **before grouping** — it only works on existing values (like `occupation`, `age`, or `gender`).
  * `HAVING` filters data **after grouping** — it works on aggregate results like `AVG(salary)` or `COUNT(id)`.

* **SQL’s internal logic order:**
  SQL doesn’t read queries the way you write them — it has its own internal workflow:
  1️⃣ **FROM** → Gather the data (tables, joins, etc.)
  2️⃣ **WHERE** → Filter rows
  3️⃣ **GROUP BY** → Form groups
  4️⃣ **HAVING** → Filter groups
  5️⃣ **SELECT** → Pick what to display
  6️⃣ **ORDER BY** → Arrange the output

* **Why WHERE can’t come after GROUP BY:**
  By the time SQL reaches `GROUP BY`, the rows have already been bundled into groups.
  So, if you try to add a `WHERE` after grouping, SQL gets confused — it’s like asking it to “filter rows” that no longer exist.
  That’s like trying to remove ingredients after the soup’s already been cooked 🍲😅

* **HAVING vs WHERE analogy:**
  Think of SQL like a factory line:
  1️⃣ Workers pick raw materials (**FROM**)
  2️⃣ They remove unwanted ones (**WHERE**)
  3️⃣ They bundle them into boxes (**GROUP BY**)
  4️⃣ They reject boxes that don’t meet standards (**HAVING**)
  Trying to use `WHERE` after grouping is like saying, “Remove that bad item after you’ve already sealed the box.”
  You can’t — the only options are to filter *before* boxing (WHERE) or *after* boxing (HAVING).

**💡 Discoveries:**

* **HAVING** is used for filtering *aggregated function–level data*.
* **WHERE** is used for filtering *row-level data*.
* **HAVING ≠ WHERE.**
* **HAVING** is what *saves the day* when **WHERE** cannot be used to perform aggregate calculations.

---

#### 🤯 My Struggle Moment
- Understanding the SQL logic of processing queries (FWGHSO)

#### ⚡ Aha! Moment
- I finally understood HAVING & WHERE with the factory worker and soup analogy.

#### 🧰 Tools & Commands I Used
- ORDER BY
- WHERE
- HAVING

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















