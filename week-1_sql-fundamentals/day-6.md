### 🗓️ Day 6 — Nov 08, 2025 

**Focus:**  
Window Functions vs GROUP BY in SQL   

**Number of Videos Watched:** 1

**Total Learning Time:** 1 hr

**Today's Mood:** Feels good to be back and wrap up with my intermediate series

---

#### 🧠 What I Learned

* **Window functions** almost work like **GROUP BY**, but with one key difference —
  they perform calculations **per row**, not per group.

* Unlike GROUP BY, **window functions don’t collapse rows** into a single summary.

  > Each row keeps its identity while still showing the aggregated result beside it.

* A big **advantage** of using window functions:**
  You can **add more columns** to your `SELECT` statement without breaking your calculations.

  > The results stay clean and consistent — no data “roll-up” or grouping issues.

* **ORDER BY** is what makes a total “roll.”

  > Without it, it’s not rolling — it’s just a static sum.

* **ROW_NUMBER()** does exactly what it sounds like —
  it **assigns numbers to rows** in your result set, one by one, in the order you specify.

* **RANK()** and **ROW_NUMBER()** both assign numbers to rows —
  but **RANK()** treats duplicates differently.

* When **RANK()** encounters duplicate values, it **repeats the rank** for those duplicates
  and then **skips the next number** before continuing.

  > Example: `1, 2, 2, 4` (notice it skips 3).

* **DENSE_RANK()**, on the other hand, also **repeats ranks** for duplicates
  but **doesn’t skip numbers**.

  > Example: `1, 2, 2, 3` (no gaps).

* **ROW_NUMBER()** simply assigns a **unique sequential number** to every row —
  no duplicates, no skips.

---

#### 🤯 My Struggle Moment
- Understanding rank() is for positional order and dense_rank for top N filtering.

#### ⚡ Aha! Moment
- Learning the difference between row_number, rank(), and dense_rank()

#### 🧰 Tools & Commands I Used
- ROW_NUMBER()
- RANK()
- DENSE_RANK()

#### 🎨 Mini Project / Practice Task  
*Loading...*

#### 💭 Reflection
> I took a little pause for my Canva externship. Now I'm back with fresh energy!
> And I'm so excited to finish my intermediate series.



