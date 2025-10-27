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
- SELECT & WHERE

#### 🎨 Mini Project / Practice Task
```
Project Task on SELECT #1:
You’ve been asked to help management identify which occupation are paying the most on average. 
Use the company’s `employees` table to calculate the **average salary** for each department, 
then rank all departments from the **highest** to **lowest** average salary.

---

Step-by-Step Instructions:
1. Use the table named `employees`.
2. Select the `occupation` column.
3. Use the `AVG()` function on the `salary` column and give it an alias called `avg_salary`.
4. Group the results by `department` to calculate averages for each occupation.
5. Order the results by `avg_salary` in **descending** order so the highest averages appear first.

My Thought Process:
 -- Pseudo Query --
# occupation is a field/data column in a table
# calculate the average salary AVG(salary) and alias it AS avg_salary
# Use the employees table
# GROUP the calculation by occupation to get the average for each occupation
# ORDER the avg_salary in DESC order to get the salary from highest to lowest

-- SQL Query --
SELECT occupation,
AVG(salary) AS avg_salary
FROM employees
GROUP BY occupation
ORDER BY avg_salary DESC;


---

Project Task on SELECT #2:
You’re exploring the `parks_and_recreation` database to understand your employee data better.
First, review all the available fields in the `employee_demographics` table. 
Then, experiment with performing calculations on the `age` field to project an adjusted figure (for example, future or weighted age). 
Finally, find out how many **unique first names** and gender combinations exist in the organization.

---

Step-by-Step Instructions:
1. Retrieve all columns from the `employee_demographics` table to get a full view of the data.
2. Select specific fields such as `first_name`, `last_name`, `birth_date`, and `age`, and perform a calculation
on the `age` column where you add, multiply, and add values in sequence — to see how SQL handles arithmetic operations.
3. Extract only the **unique combinations** of `first_name` and `gender` using the `DISTINCT` keyword to identify duplicates
or repeated entries.

My Thought Process:
 -- Pseudo Query --
# SELECT all fields 
# Specify the table and from which db
# SELECT specific fields like first_name, last_name, birth_date, and age
# Perform calculation on age to see how SQL handles arithmetic operations.
# Start a new query and get DISTINCT firstname and gender FROM the table

-- SQL Query --
SELECT *
FROM parks_and_recreation.employee_demographics;

SELECT first_name,
last_name,
age,
(age + 10) * 10 + 10 AS future_age
FROM parks_and_recreation.employee_demographics;

SELECT DISTINCT gender
FROM parks_and_recreation.employee_demographics;


--

Project Task on WHERE Clause #1:
You’re analyzing employee data to spot salary trends, birth year patterns, and naming structures across departments. Your goal is to use **filtering and pattern-matching techniques** to answer specific questions about the workforce. Start by identifying employees who earn less than or equal to ₦50,000, then move on to finding younger employees born after a given date. Next, test logical operators like **AND**, **OR**, and **NOT** to combine conditions and filter data more precisely. Finally, use the **LIKE** operator to explore name patterns (e.g., names containing “er,” names starting with “A,” or those with a specific number of letters) and identify employees born in a particular year.

---

Step-by-Step Instructions:
1. Filter the `employee_salary` table to show only employees earning **₦50,000 or less**.
2. From the `employee_demographics` table, retrieve all employees **born after January 1, 1985**.
3. Combine filters using **logical operators** to explore how multiple conditions work together — for example, using `AND` and `OR` to narrow or widen search results, and testing how `NOT` changes what gets included or excluded.
4. Experiment with case sensitivity by checking how SQL interprets values like `'male'` vs `'Male'`.
5. Use the **LIKE** operator to search for name patterns:
   * Names that **contain** certain letters (e.g., “er”)
   * Names that **start with** a specific letter (e.g., “A”)
   * Names with a specific **length** using underscores `_`
6. Apply the **LIKE** operator to the `birth_date` field to filter all employees born in a specific **year** (e.g., 1989).

My Thought Process:
 -- Pseudo Query --

```

#### 💭 Reflection
> Weirdly, SELECT can do a lot more than picking data columns/fields.























