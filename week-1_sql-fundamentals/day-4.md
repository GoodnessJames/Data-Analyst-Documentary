### 🗓️ Day 4 — October 29, 2025 (12:30 pm - 8:30 pm)

**Focus:** 

**Number of Videos Watched:** 2

**Total Learning Time:** 3 hr

**Today's Mood:** A little tensed but I'm alright

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
-- Project Task on LIMIT & ALIASING:

You’re working on cleaning and summarizing HR data to make your reports more efficient and readable.  
Begin by exploring how the **LIMIT** clause helps you control how many records are displayed at a time.  
Use it to skip a certain number of rows and then return a specific number of results — for example,  
showing only a few employees after skipping the first set of records.
Next, focus on **aliasing**, which allows you to rename columns or calculated fields to make your queries easier to read and maintain.  
Practice renaming your aggregated column for **average age** by gender and see how using an alias simplifies your `HAVING` clause,  
especially when filtering based on aggregate results.

**Step-by-Step Instructions:**
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

```

#### 💭 Reflection
> tbd














