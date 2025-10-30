### 🗓️ Day 4 — October 29, 2025 (12:30 pm - 8:30 pm)

**Focus:**  
LIMITS + ALIASING  
JOINS in MySQL  
UNIONS in MySQL   

**Number of Videos Watched:** 3

**Total Learning Time:** 3 hr

**Today's Mood:** A little tensed, but I'm alright

---

#### 🧠 What I Learned

* **LIMIT clause** → Literally SQL’s way of saying “give me this number of rows.”
  Example: `LIMIT 5` means “show only five rows.”

* **LIMIT with comma** → When you write `LIMIT 2, 2`, SQL reads it as:
  → Skip (or count) the first 2 rows
  → Then display the next 2 rows after the skipped ones

* **Aliasing** → Just changing the *name* of a column or table.
  You can use the **AS** keyword (e.g., `SELECT name AS employee_name`) —
  but **AS** is totally optional. SQL still understands the alias even if you skip it.

* **INNER JOIN** → Pulls *matching rows* from both tables and displays them.
  If a row doesn’t exist in both tables, it’s skipped.
  If it exists but one side has missing data, SQL fills that part with **NULL**.

* **Types of Joins** → There are **three main types**:
  1️⃣ **INNER JOIN** → Only shows matching data between both tables.
  2️⃣ **LEFT JOIN (LEFT OUTER JOIN)** → Displays *all rows* from the left table and matches from the right.
  If there’s no match, SQL still keeps the left data and fills the missing right side with **NULL**.
  3️⃣ **RIGHT JOIN (RIGHT OUTER JOIN)** → The reverse. It displays *all rows* from the right table and matches from the left.
  If there’s no match, SQL fills the unmatched left side with **NULL**.

* **SELF JOIN** → Joining a table *to itself.*
  It exists because sometimes your data is **recursive or relational within itself** —
  meaning the relationships you want to analyze live *inside one table,* not between two separate ones.

* **Joining Multiple Tables** → You can join more than two tables together —
  even when not all of them share a common column.
  Example: You have **Employee Demographics** and **Employee Salary** already joined,
  and now you want to bring in **Parks and Recreation**, which only shares a column with the **Employee Salary** table.
  You simply **build the bridge through that second table** —
  SQL doesn’t need every table to directly connect, just a chain of relationships that link them.

* **UNION** → Used for **combining rows**, not columns.
  It combines the results of multiple **SELECT** statements into one.
  Why? To view data from multiple criteria or segments in one place.
  Example: You can use UNION to combine results of employees who are older,
  highly paid, or belong to a specific department — and label them all in one unified result view.

**Discoveries:**

* **UNION = row stacking.** It performs its process **vertically** — stacking results one on top of another.
* **JOIN = column joining.** It performs its process **horizontally** — connecting related columns side by side.

---

#### 🤯 My Struggle Moment
- JOINS are crazyyyyyyyyyyyyyyyyyyyyyyyy!

#### ⚡ Aha! Moment
- Finally understanding that UNIONS are used for row-stacking (performed vertically) while JOINS used for column-joining (performed horizon.)
- made my day!

#### 🧰 Tools & Commands I Used
- LIMIT  
- AS
- JOIN (INNER, JOIN LEFT JOIN, RIGHT JOIN)
- UNION (UNION DISTINCT, UNION ALL)

#### 🎨 Mini Project / Practice Task

```
-- Project Task on LIMIT & ALIASING:

You’re working on cleaning and summarizing HR data to make your reports more efficient and readable.  
Begin by exploring how the **LIMIT** clause helps you control how many records are displayed at a time.  
Use it to skip a certain number of rows and then return a specific number of results — for example,  
showing only a few employees after skipping the first set of records.
Next, focus on **aliasing**, which allows you to rename columns or calculated fields to make your queries easier to read and maintain.  
Practice renaming your aggregated column for **average age** by gender and see how using an alias simplifies your `HAVING` clause,  
especially when filtering based on aggregate results.

Step-by-Step Instructions:
1. Use the **LIMIT** clause to display only a specific set of results — for example, skip a few top records and show the next few.
2. Observe how using two numbers in `LIMIT` works — the first number represents how many rows to skip, and the second represents how many rows to return.
3. In the `employee_demographics` table, calculate the **average age** for each gender.
4. Create an **alias** for the calculated column (e.g., rename `AVG(age)` as `avg_age`) to make the result easier to read.
5. Apply a **HAVING** clause to filter only those gender groups whose average age is greater than 40.
6. Notice how aliasing allows you to reuse the alias name (`avg_age`) in the `HAVING` clause instead of repeating the full function `AVG(age)`.


-- SQL Query (LIMIT)

SELECT *
FROM employee_demographics
ORDER BY age DESC
LIMIT 2, 1
;

-- SQL Query (ALIASING)

SELECT gender, AVG(age) AS avg_age # The AS keyword is optional, query can run without it
FROM employee_demographics
GROUP BY gender
HAVING AVG(age) > 40	# Aliasing comes in handy here. avg_age can used instead of always typing AVG(age)
						# Better syntax: HAVING avg_age > 40
;

--

-- Project Task on JOINS #1:

You’ve been assigned to combine and analyze employee data from multiple tables in the HR database to understand how records  
connect across departments and salary structures. Begin by reviewing the contents of both `employee_demographics` and `employee_salary`  
to see what fields are available. Then, practice different **types of joins** to merge data meaningfully: 

Start with an **INNER JOIN** to return only employees who appear in both tables, based on a shared column (`employee_id`).
Then move to **OUTER JOINS** — using **LEFT JOIN** to see all employees from the demographics table (even if they don’t have salary data)
and **RIGHT JOIN** to capture the reverse scenario.

Next, experiment with a **SELF JOIN** on the same table to find relationships between rows — for instance, pairing employees whose IDs differ by 1.
Finally, practice joining **multiple tables** together to combine demographic, salary, and departmental details in a single, unified dataset.


Step-by-Step Instructions:

1. Explore both `employee_demographics` and `employee_salary` tables separately to understand their structure and shared columns.
2. Perform an **INNER JOIN** to display only the records that exist in both tables — matching them using the `employee_id` column.
3. Alias both tables (e.g., `dem` for demographics and `sal` for salary) to make your query more readable.
4. Experiment with **LEFT JOIN** to return all rows from the left table (`employee_demographics`) and any matching records from the right table (`employee_salary`).
5. Use **RIGHT JOIN** to do the opposite — returning all rows from the salary table and matching data from demographics where possible.
6. Perform a **SELF JOIN** on the `employee_salary` table to compare records within the same table — for example, matching employees whose `employee_id` differs by 1.
7. Select specific columns from both aliases (like first and last names) to better understand how self joins relate data.
8. Finally, practice **joining multiple tables** — combining demographics, salary, and department data — to produce a complete view of each employee’s profile.

-- SQL Query --
# INNER  JOIN

SELECT *
FROM employee_demographics AS dem
INNER JOIN employee_salary AS sal	# By default JOIN represents an inner join but you can explicitly write out INNER JOIN
	ON dem.employee_id = sal.employee_id	# ->> Is the ON keyword compulsory & why? Yes, if you're joining, you need to tie on soemthing :)
;

SELECT dem.employee_id, age, occupation
FROM employee_demographics AS dem
INNER JOIN employee_salary AS sal	
	#ON dem.employee_id = sal.employee_id	
;


# OUTER JOIN (LEFT JOIN & RIGHT JOIN)

SELECT dem.employee_id, age, occupation
FROM employee_demographics AS dem # LEFT table
LEFT JOIN employee_salary AS sal # RIGHT table 
	ON dem.employee_id = sal.employee_id
;

SELECT *
FROM employee_demographics AS dem # Notice that the join doesnt bother with reorganizing the table by displaying the RIGHT table first even if it's pulling data from the RIGHT table.
RIGHT JOIN employee_salary AS sal 
	ON dem.employee_id = sal.employee_id
;


# SELF JOIN #1
SELECT *
FROM employee_salary emp1
JOIN employee_salary emp2
	ON emp1.employee_id + 1 = emp2.employee_id
;

# SELF JOIN #2 - Picking specific columns
SELECT emp1.employee_id as emp_id1,
emp1.first_name AS first_name_santa,
emp1.last_name AS last_name_santa,
emp2.employee_id as emp_id2,
emp2.first_name AS first_name_emp,
emp2.last_name AS last_name_emp
FROM employee_salary emp1
JOIN employee_salary emp2
	ON emp1.employee_id + 1 = emp2.employee_id 
;


# Joining multiple tables
SELECT *
FROM employee_demographics AS dem
INNER JOIN employee_salary AS sal
	ON dem.employee_id = sal.employee_id
INNER JOIN parks_departments pd
	ON sal.dept_id = pd.department_id
;

--

-- Project Task on UNION #1:

You’re building a combined employee report that merges data from multiple sources. Unlike `JOIN`,  
which connects tables side-by-side (by columns), `UNION` stacks results **vertically**, combining rows from different tables into a single dataset.  

Start by merging the records from the `employee_demographics` and `employee_salary` tables to observe how `UNION` automatically removes duplicates —  
since it runs as `UNION DISTINCT` by default. Then, try `UNION ALL` to keep duplicates and understand the difference in output.  

Next, create a categorized report that labels employees based on their characteristics — for example, identifying older male and female employees,  
as well as those who are highly paid — and merge all these filtered results into one table using multiple `UNION` statements.  
Finally, observe what happens if you misspell or reference a non-existent table to understand SQL’s behavior and error handling in such cases.  


Step-by-Step Instructions:

1. Combine all rows from the `employee_demographics` and `employee_salary` tables using `UNION` to see how it merges records while removing duplicates.  
2. Repeat the combination using `UNION ALL` to view every record — including duplicates — for comparison.  
3. Create separate filtered queries for:  

   * Male employees over 40 labeled as “Old Man”  
   * Female employees over 40 labeled as “Old Lady”  
   * Employees earning above ₦70,000 labeled as “Highly Paid”  
     Then, merge these three filtered datasets using multiple `UNION` clauses into one unified report.  
4. Order the final results by first and last names for better readability.  
5. Finally, intentionally reference a misspelled table name to observe the type of error SQL returns —  
this helps reinforce how table validation works before query execution.  


-- SQL Query

SELECT * 
FROM employee_demographics
UNION # Shows distinct values only
SELECT * 
FROM employee_salary
;

SELECT first_name, last_name
FROM employee_demographics
UNION ALL # Shows all results without removing the duplicates
SELECT first_name, last_name
FROM employee_salary
;

SELECT first_name, last_name, 'Old Man' AS label
FROM employee_demographics
WHERE age > 40 AND gender = 'male'
UNION
SELECT first_name, last_name, 'Old Lady' AS label
FROM employee_demographics
WHERE age > 40 AND gender = 'female'
UNION
SELECT first_name, last_name, 'Highly Paid' AS label
FROM employee_salary
WHERE salary > 70000
ORDER BY first_name, last_name
;


```

#### 💭 Reflection
> Today was quite the day! I don't have anything else to say.




















