### 🗓️ Day 5 — October 30, 2025 

**Focus:**  
STRING Functions  
CASE Statements  
SUBQUERIES  

**Number of Videos Watched:** 3

**Total Learning Time:** 1 hr

**Today's Mood:** Cleaning up my carryover lessons on 1st Nov. Yeah, I know. 🙄

---

#### 🧠 What I Learned (Oct 30, 2025)

* **TRIM():** Removes **leading and trailing spaces** from a string.

  * `LTRIM()` → removes spaces **on the left** (leading).
  * `RTRIM()` → removes spaces **on the right** (trailing).

* **LEFT() & RIGHT():** Extracts characters from a string.

  * `LEFT(column, n)` → returns the **first n characters**.
  * `RIGHT(column, n)` → returns the **last n characters**.

* **SUBSTRING():** Returns a part of a string **based on position**.
  You specify:
  1️⃣ The column name,  
  2️⃣ The **starting position**, and  
  3️⃣ The **number of characters** to return.  

  > Important: The counting **starts at** the position you specify —
  > position 3 means it will include the 3rd character, not skip it.

* **REPLACE():** Substitutes specific text with something new.  
  Example: `REPLACE(column, 'old_value', 'new_value')`

* **LOCATE():** Finds the **position of a character or string** within another string.  
  Example:  
  `LOCATE('d', 'goodness') → 4` (because ‘d’ is the 4th letter).

* **CONCAT():** Joins multiple strings or columns together.
  Example:  
  `CONCAT(first_name, ' ', last_name)` → merges first and last names.  

**What I Learned / What Stood Out:** (Oct 31, 2025)

* The **alias** for a CASE statement **must come at the end** of the CASE expression.

  > Think of CASE like a **box** — you can’t label the box before it’s fully built.
  > The `END` keyword closes the box, and **only then** can you label (alias) it.

* The **CASE** expression can be used **inside a SELECT** statement.  
  Anything that comes before it (like another column) must be followed by a **comma** before writing the CASE.

* The **WHEN** clause in CASE works like **IF statements** in programming — it checks for a condition, and if it’s true, it returns a specific value.

* The **order of WHEN clauses matters.**
  Always put **specific conditions first** and **general ones later**, so the logic flows correctly and SQL doesn’t stop too early on a broader match.

**Discoveries:** (Nov 01, 2025)

* SQL runs **Subqueries first** before the **outer query**.

  > The inner query completes its execution and passes its result to the outer query for further processing.

* When you **alias a subquery**, you **don’t alias it inside the subquery itself**.

  > You alias it **after the closing parenthesis**, because the alias belongs to the **entire subquery result**, not what’s inside it.


#### 🤯 My Struggle Moment
- Understanding the syntax of a subquery and the relevance of subqueries.

#### ⚡ Aha! Moment
- Writing case statements was like IF/ELSE logic in Python

#### 🧰 Tools & Commands I Used
- ** String commands:** LENGTH(), UPPER(), LOWER(), TRIM(), LTRIM(), RTRIM(), LEFT(), RIGHT(), SUBSTRING(birth_date, 6, 2) AS birth_month,
REPLACE(first_name, 'Leslie', 'Goodness'), SELECT LOCATE('D', 'Goodness'), LOCATE('An', first_name), CONCAT(first_name, ' ', last_name) AS full_name
CONCAT(first_name, ' ', UPPER(last_name)) AS full_name
- **Case statements:**
  CASE  
    `WHEN conditions`  
    ...  
  END AS case_alias  
- **Subqueries:**  
  SELECT first_name, salary,  
    (SELECT AVG(salary)   
	  FROM employee_salary  
  ) AS avg_salary  
  FROM employee_salary  


#### 🎨 Mini Project / Practice Task


#### 💭 Reflection
> 1% progress also counts. Don't get worked up, Goodness. 👀






