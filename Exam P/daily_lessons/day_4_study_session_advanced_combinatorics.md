# Actuarial Exam P: Day 4 Study Session (Session 1B.2)
## Topic: Advanced Combinatorics Problem-Solving

---

## 1. Session Overview & Learning Objectives

This session focuses on **Advanced Combinatorics** for Actuarial Exam P (SOA Syllabus Objective 1B). Exam P counting problems often feature constrained committee selection, item arrangement rules (proximity constraints), identical item distribution, and rectangular lattice paths.

By the end of this session, you will be able to:
1. Solve **committee selection problems with complex constraints** (e.g., compulsory/excluded individuals, "cannot serve together" conditions).
2. Distinguish and apply the **Block Method** (items must sit together) vs. the **Gap / Separator Method** (no two items can be adjacent).
3. Apply the **Stars and Bars Principle** to distribute identical items among distinct bins under non-negative ($x_i \ge 0$) and positive ($x_i \ge 1$) integer constraints.
4. Count **Lattice / Grid Paths** across rectangular sample spaces with or without mandatory intermediate waypoints.

---

## 2. Theoretical Foundations & Key Methods

### A. Proximity Rules: Block Method vs. Gap Method

#### 1. The Block Method (Items MUST sit together)
When specific items are required to be placed adjacent to one another:
* **Strategy:** Group the $r$ restricted items into a single "super-item".
* **Total Objects:** If there are $n$ total items and $r$ items form a block, the effective number of items to arrange is $N = (n - r) + 1$.
* **Formula:**
  $$\text{Total Ways} = (\text{Arrangements of Super-Items}) \times (\text{Internal Arrangements inside Block})$$
  $$\text{Total Ways} = N! \times r! \quad \text{(if all items are distinct)}$$

#### 2. The Gap / Separator Method (NO TWO items can sit together)
When certain restricted items must **never** be placed adjacent to each other:
1. Arrange the $m$ **unrestricted items** first in $m!$ ways.
2. Identify the **gaps** created before, between, and after the unrestricted items. Placing $m$ items creates $m + 1$ available gaps.
3. Select $r$ gaps from the $m + 1$ available slots to place the $r$ restricted items ($\binom{m+1}{r}$), and multiply by their internal arrangements ($r!$).
* **Formula:**
  $$\text{Total Ways} = m! \times \binom{m + 1}{r} \times r! = m! \times P(m+1, r)$$

---

### B. Distribution Problems ("Stars and Bars")

Distributing $n$ indistinguishable (identical) items into $k$ distinguishable (distinct) bins:

#### Case 1: Bins CAN be empty ($x_i \ge 0$)
The number of non-negative integer solutions to $x_1 + x_2 + \dots + x_k = n$ is:
$$\text{Ways} = \binom{n + k - 1}{k - 1} = \binom{n + k - 1}{n}$$

#### Case 2: Every bin MUST receive at least 1 item ($x_i \ge 1$)
First assign 1 item to each of the $k$ bins (using $k$ items). The remaining $n - k$ items are freely distributed among the $k$ bins:
$$\text{Ways} = \binom{n - 1}{k - 1}$$

---

### C. Grid / Lattice Paths

To find the number of unique shortest paths from $(0,0)$ to $(a, b)$ moving only **Right** ($+x$) and **Up** ($+y$):
* Total steps required: $a + b$
* Number of Right steps: $a$, Number of Up steps: $b$
$$\text{Total Paths} = \binom{a + b}{a} = \binom{a + b}{b} = \frac{(a + b)!}{a! \, b!}$$

#### Paths Passing Through an Intermediate Waypoint $(x_1, y_1)$ to $(a, b)$:
Break the path into two sequential stages and apply the Multiplication Principle:
$$\text{Total Paths} = \left(\text{Paths from } (0,0) \text{ to } (x_1, y_1)\right) \times \left(\text{Paths from } (x_1, y_1) \text{ to } (a, b)\right)$$
$$\text{Total Paths} = \binom{x_1 + y_1}{x_1} \times \binom{(a - x_1) + (b - y_1)}{a - x_1}$$

---

### D. Constrained Committee Selection

#### 1. Complement Method ("Cannot Both Serve")
When two specific individuals $A$ and $B$ cannot serve together on a committee of size $r$ chosen from $N$ people:
$$\text{Valid Selections} = \text{Total Unrestricted Selections} - \text{Prohibited Selections (Both In)}$$
$$\text{Valid Selections} = \binom{N}{r} - \binom{N - 2}{r - 2}$$

#### 2. Direct Method ("Must Include / Exclude")
If $a$ individuals must be included and $b$ individuals must be excluded from a committee of size $r$ picked from $N$ people:
$$\text{Valid Selections} = \binom{N - a - b}{r - a}$$

---

## 3. Concept Check Walkthroughs

### Question 1 (Gap Method)
**Scenario:** Line up 5 distinct Auto claim binders and 3 distinct Property claim binders on a shelf such that **no two Property binders are adjacent**.

**Solution Walkthrough:**
1. Arrange 5 distinct Auto binders: $5! = 120$ ways.
2. Placing 5 Auto binders creates $5 + 1 = 6$ gaps:
   $$\text{\underline{\quad}} \text{ A } \text{\underline{\quad}} \text{ A } \text{\underline{\quad}} \text{ A } \text{\underline{\quad}} \text{ A } \text{\underline{\quad}} \text{ A } \text{\underline{\quad}}$$
3. Choose 3 gaps out of 6 for the Property binders: $\binom{6}{3} = 20$ ways.
4. Arrange 3 distinct Property binders in those gaps: $3! = 6$ ways.
5. Combine via Multiplication Principle:
   $$\text{Total Ways} = 5! \times \binom{6}{3} \times 3! = 120 \times 20 \times 6 = \mathbf{14,400}$$

---

### Question 2 (Stars & Bars — Non-Negative Distribution)
**Scenario:** Distribute 8 identical bonus credits among 3 analysts such that **some analysts may receive 0 credits**.

**Solution Walkthrough:**
1. Items $n = 8$ identical credits, Bins $k = 3$ distinct analysts.
2. Constraint: $x_i \ge 0$ (non-negative integer solutions).
3. Apply formula $\binom{n + k - 1}{k - 1}$:
   $$\text{Total Ways} = \binom{8 + 3 - 1}{3 - 1} = \binom{10}{2} = \frac{10 \times 9}{2 \times 1} = \mathbf{45\text{ ways}}$$

---

### Question 3 (Grid Paths)
**Scenario:** Find the number of distinct paths on a grid from $(0,0)$ to $(5,3)$ moving only Right or Up.

**Solution Walkthrough:**
1. Right steps $a = 5$, Up steps $b = 3$. Total steps = $5 + 3 = 8$.
2. Apply formula $\binom{a + b}{b}$:
   $$\text{Total Paths} = \binom{8}{3} = \frac{8 \times 7 \times 6}{3 \times 2 \times 1} = \mathbf{56\text{ distinct paths}}$$

---

## 4. Practice Problem Set 1

### Problem 1 (Gap Method)
An actuary is organizing 10 distinct files on an office shelf: 6 distinct Auto claim files and 4 distinct Property claim files. Calculate the total number of distinct linear arrangements possible if **no two Property claim files are allowed to be adjacent to each other**.

#### Solution:
* **Step 1:** Arrange 6 Auto files: $6! = 720$ ways.
* **Step 2:** 6 Auto files create $6 + 1 = 7$ available gaps.
* **Step 3:** Choose 4 gaps out of 7 and arrange the 4 Property files:
  $$\binom{7}{4} \times 4! = 35 \times 24 = 840 \text{ (or } P(7,4) = 840\text{)}$$
* **Step 4:** Total arrangements:
  $$\text{Total} = 720 \times 840 = \mathbf{604,800}$$

---

### Problem 2 (Stars & Bars — Positive Integer Distribution)
An actuarial manager has 15 identical policy audit files to allocate among 5 regional analysts ($A_1, A_2, A_3, A_4, A_5$). Calculate the total number of distinct ways to distribute all 15 audit files if **each analyst must receive at least 1 file**.

#### Solution:
* **Step 1:** Identical files $n = 15$, Analysts $k = 5$.
* **Step 2:** Constraint $x_i \ge 1$ for all $i$.
* **Step 3:** Apply formula $\binom{n - 1}{k - 1}$:
  $$\text{Total Ways} = \binom{15 - 1}{5 - 1} = \binom{14}{4} = \frac{14 \times 13 \times 12 \times 11}{4 \times 3 \times 2 \times 1} = \mathbf{1,001\text{ ways}}$$

---

### Problem 3 (Constrained Committee Selection — Conflict Constraint)
A task force of 5 actuaries is to be randomly selected from 12 actuaries (7 Life, 5 Health). Alex (Life) and Jordan (Health) **cannot both serve on the task force together**. Calculate the total number of distinct 5-actuary task forces that can be formed.

#### Solution (Complement Method):
* **Step 1:** Total unrestricted choices:
  $$\binom{12}{5} = 792$$
* **Step 2:** Prohibited choices (Both Alex AND Jordan are included):
  $$\binom{10}{3} = 120$$
* **Step 3:** Subtract prohibited from total:
  $$\text{Valid Task Forces} = 792 - 120 = \mathbf{672}$$

---

### Problem 4 (Grid Paths via Waypoint)
An underwriting workflow system tracks claim status on a grid from $(0,0)$ to $(6,4)$, moving only Right or Up. Calculate the total number of distinct paths from $(0,0)$ to $(6,4)$ that **pass through position $(3,2)$**.

#### Solution:
* **Stage 1: $(0,0) \to (3,2)$**
  $$\binom{3 + 2}{3} = \binom{5}{3} = 10 \text{ paths}$$
* **Stage 2: $(3,2) \to (6,4)$**
  $$\text{Right } = 6 - 3 = 3, \quad \text{Up } = 4 - 2 = 2 \implies \binom{3 + 2}{3} = \binom{5}{3} = 10 \text{ paths}$$
* **Stage 3: Combine via Multiplication Principle:**
  $$\text{Total Paths} = 10 \times 10 = \mathbf{100\text{ paths}}$$

---

## 5. Practice Problem Set 2

### Problem 1 (Block Method — Cluster Constraint)
An IT department is installing 11 distinct server units in a single server rack row: 7 distinct Linux servers and 4 distinct Database servers. All 4 Database servers **must be placed directly next to each other as a single cluster**. Calculate the total number of distinct linear arrangements.

#### Solution:
* **Step 1:** Group 4 Database servers into 1 "super-item".
* **Step 2:** Total super-items = 7 Linux + 1 DB block = 8 items.
* **Step 3:** Arrange 8 super-items: $8! = 40,320$ ways.
* **Step 4:** Arrange 4 distinct Database servers within the block: $4! = 24$ ways.
* **Step 5:** Total arrangements:
  $$\text{Total} = 8! \times 4! = 40,320 \times 24 = \mathbf{967,680}$$

---

### Problem 2 (Stars & Bars — Non-Negative Distribution)
An actuarial firm allocates 18 identical laptop computers among 4 newly hired actuaries ($A_1, A_2, A_3, A_4$). Calculate the total number of distinct ways to distribute all 18 laptops if **any actuary may receive 0 laptops**.

#### Solution:
* **Step 1:** Items $n = 18$, Bins $k = 4$, Constraint $x_i \ge 0$.
* **Step 2:** Apply formula $\binom{n + k - 1}{k - 1}$:
  $$\text{Total Ways} = \binom{18 + 4 - 1}{4 - 1} = \binom{21}{3} = \frac{21 \times 20 \times 19}{3 \times 2 \times 1} = \mathbf{1,330\text{ ways}}$$

---

### Problem 3 (Must Include / Exclude Committee Selection)
A 6-person committee is chosen from 15 actuaries (8 Life, 7 Health). Senior Director Sarah **must be included**, and Associate Director Tom **cannot be included**. Calculate the total number of distinct 6-person committees.

#### Solution:
* **Step 1:** Place Sarah on committee $\to$ 1 slot filled, 5 slots remain.
* **Step 2:** Remove Sarah and Tom from pool $\to 15 - 2 = 13$ candidates remain.
* **Step 3:** Choose 5 members from 13 available candidates:
  $$\text{Total Committees} = \binom{13}{5} = \frac{13 \times 12 \times 11 \times 10 \times 9}{5 \times 4 \times 3 \times 2 \times 1} = \mathbf{1,287}$$

---

### Problem 4 (Grid Paths via Waypoint)
An automated claim workflow system processes claims along a rectangular grid from $(0,0)$ to $(7,5)$, moving only Right or Up. Calculate the total number of distinct paths from $(0,0)$ to $(7,5)$ that **pass through position $(4,2)$**.

#### Solution:
* **Stage 1: $(0,0) \to (4,2)$**
  $$\text{Right } = 4, \quad \text{Up } = 2 \implies \binom{4 + 2}{4} = \binom{6}{4} = 15 \text{ paths}$$
* **Stage 2: $(4,2) \to (7,5)$**
  $$\text{Right } = 7 - 4 = 3, \quad \text{Up } = 5 - 2 = 3 \implies \binom{3 + 3}{3} = \binom{6}{3} = 20 \text{ paths}$$
* **Stage 3: Combine:**
  $$\text{Total Paths} = 15 \times 20 = \mathbf{300\text{ paths}}$$

---

## 6. Day 4 Formula Reference Summary

| Concept | Condition | Formula | Concise Description |
| :--- | :--- | :--- | :--- |
| **Block Method** | Items MUST sit together | $\text{Ways} = N! \times r!$ | Group $r$ items into 1 super-item, arrange $N$ total super-items, multiply by internal block arrangements. |
| **Gap Method** | NO TWO items can sit together | $\text{Ways} = m! \times \binom{m+1}{r} \times r!$ | Arrange $m$ unrestricted items first, select $r$ gaps from $m+1$ choices, multiply by internal arrangements. |
| **Stars & Bars ($x_i \ge 0$)** | Bins CAN be empty | $\binom{n + k - 1}{k - 1}$ | Number of ways to distribute $n$ identical items into $k$ distinct bins with no minimum requirement. |
| **Stars & Bars ($x_i \ge 1$)** | Bins CANNOT be empty | $\binom{n - 1}{k - 1}$ | Number of ways to distribute $n$ identical items into $k$ distinct bins with at least 1 item per bin. |
| **Grid Paths** | $(0,0) \to (a,b)$ | $\binom{a + b}{a} = \binom{a + b}{b}$ | Total paths moving only Right ($a$ steps) and Up ($b$ steps). |
| **Waypoint Grid Paths** | $(0,0) \to (x_1, y_1) \to (a,b)$ | $\binom{x_1 + y_1}{x_1} \times \binom{(a-x_1) + (b-y_1)}{a-x_1}$ | Multiply path count to waypoint by path count from waypoint to end. |
| **Conflict Committee** | Person A & B cannot serve together | $\binom{N}{r} - \binom{N-2}{r-2}$ | Total unrestricted committees minus prohibited committees where both are selected. |
| **Include / Exclude Committee** | $a$ included, $b$ excluded | $\binom{N - a - b}{r - a}$ | Reduce candidate pool by $a+b$ and required slots by $a$. |
