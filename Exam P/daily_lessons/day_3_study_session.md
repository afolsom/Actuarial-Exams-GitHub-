# Actuarial Exam P — Day 3 Study Session (Session 1B.1)
## Fundamental Counting Principles, Permutations, and Combinations

---

## 1. Session Overview & Learning Objectives

This session focuses on **SOA Objective 1B: Combinatorics and Classical Probability**. Combinatorics provides the counting tools necessary to determine sample space sizes and favorable outcome counts when direct enumeration is impractical.

### Key Objectives:
1. Apply the **Multiplication Principle** (sequential stages) and **Addition Principle** (disjoint choices).
2. Calculate and distinguish between **Permutations** (order matters) and **Combinations** (order does not matter).
3. Compute **Permutations with Indistinguishable/Repeated Objects**.
4. Solve classical probability problems involving sampling with and without replacement in actuarial contexts (e.g., policy auditing, committee selection, risk classification pools).

---

## 2. Core Theoretical Concepts

### A. Fundamental Counting Principles

#### 1. Multiplication Principle (Sequential Choices)
If an experiment consists of $k$ consecutive steps, where:
* Step 1 can be completed in $n_1$ ways,
* Step 2 can be completed in $n_2$ ways,
* ...
* Step $k$ can be completed in $n_k$ ways,

then the total number of distinct outcomes for the entire sequence is:
$$\text{Total Outcomes} = n_1 \times n_2 \times \dots \times n_k$$

#### 2. Addition Principle (Disjoint Alternatives)
If a choice can be made from one of $m$ mutually exclusive sets, with Set 1 containing $n_1$ options, Set 2 containing $n_2$ options, ..., and Set $m$ containing $n_m$ options, then the total number of single-choice options is:
$$\text{Total Options} = n_1 + n_2 + \dots + n_m$$

---

### B. Permutations (Order Matters)

A **permutation** is an ordered arrangement of distinct objects.

#### 1. Basic Permutation Formula
The number of distinct ways to arrange $r$ items selected from a set of $n$ distinct items where **order matters** is:
$$P(n, r) = {}_nP_r = \frac{n!}{(n - r)!}$$

*Note:* $n! = n \times (n-1) \times \dots \times 2 \times 1$, with $0! = 1$.

#### 2. Permutations with Repeated / Indistinguishable Objects
If you have $n$ total objects where $n_1$ are indistinguishable items of type 1, $n_2$ of type 2, ..., and $n_k$ of type $k$ (such that $n_1 + n_2 + \dots + n_k = n$), the number of distinct linear arrangements is:
$$\text{Distinct Arrangements} = \frac{n!}{n_1! \, n_2! \, \dots \, n_k!}$$

---

### C. Combinations (Order Does NOT Matter)

A **combination** is an unordered selection of items from a collection.

#### 1. Combination Formula
The number of distinct ways to choose a subset of $r$ items from $n$ distinct items where **order does not matter** is:
$$C(n, r) = \binom{n}{r} = {}_nC_r = \frac{n!}{r!(n - r)!}$$

#### 2. Useful Algebraic Identities
* **Symmetry Identity:** $\binom{n}{r} = \binom{n}{n - r}$
* **Boundary Values:** $\binom{n}{0} = \binom{n}{n} = 1$
* **Pascal's Identity:** $\binom{n}{r} = \binom{n-1}{r-1} + \binom{n-1}{r}$

---

### D. Classical Probability with Combinatorics

When all outcomes in a finite sample space $S$ are equally likely, the probability of an event $E$ is:
$$P(E) = \frac{n(E)}{n(S)} = \frac{\text{Number of Favorable Outcomes}}{\text{Total Number of Possible Outcomes}}$$

---

## 3. Actuarial Application Example

**Scenario:** An underwriter reviews a pool of 12 commercial liability policies: 7 are Low Risk and 5 are High Risk. The underwriter randomly selects 4 policies for a compliance audit.

**Question:** What is the probability that exactly 3 of the selected policies are Low Risk?

### Solution:
1. **Total Sample Space Size $n(S)$:** Number of ways to choose any 4 policies out of 12 without replacement (order does not matter):
   $$n(S) = \binom{12}{4} = \frac{12 \times 11 \times 10 \times 9}{4 \times 3 \times 2 \times 1} = 495$$

2. **Favorable Outcomes $n(E)$:** Select 3 Low Risk policies (out of 7) **AND** 1 High Risk policy (out of 5) to form a complete 4-policy sample:
   $$n(E) = \binom{7}{3} \times \binom{5}{1} = 35 \times 5 = 175$$

3. **Probability Calculation:**
   $$P(\text{Exactly 3 Low Risk}) = \frac{n(E)}{n(S)} = \frac{175}{495} = \frac{35}{99} \approx 0.3535$$

---

## 4. Concept Check Questions & Walkthroughs

### Question 1
* **Part A:** Should you use permutations or combinations if an actuary is assigning 3 distinct officer roles (President, Vice-President, Treasurer) from a committee of 10 people?
  * **Answer:** **Permutations**. Order matters because the roles are distinct. $P(10, 3) = 10 \times 9 \times 8 = 720$.
* **Part B:** What if the actuary is selecting a 3-person subcommittee with no distinct roles?
  * **Answer:** **Combinations**. Order does not matter. $\binom{10}{3} = \frac{10 \times 9 \times 8}{3 \times 2 \times 1} = 120$.

### Question 2
Calculate $\binom{8}{3}$ and $P(8, 3)$.
* $\binom{8}{3} = \frac{8 \times 7 \times 6}{3 \times 2 \times 1} = 56$
* $P(8, 3) = 8 \times 7 \times 6 = 336$

### Question 3
An auto insurer issues policy numbers consisting of 2 uppercase letters followed by 3 digits ($0–9$). How many distinct policy numbers can be created if letters and digits can be repeated?
* **Solution (Slot Method / Multiplication Principle):**
  $$\text{Code} = [\text{Letter 1}] \, [\text{Letter 2}] \, [\text{Digit 1}] \, [\text{Digit 2}] \, [\text{Digit 3}]$$
  $$\text{Total} = 26 \times 26 \times 10 \times 10 \times 10 = 26^2 \times 10^3 = 676,000$$

---

## 5. Primary Practice Problem Set & Solutions

### Problem 1
An insurance company's quality control auditor reviews a portfolio of 15 commercial policies: 8 in Region A, 4 in Region B, and 3 in Region C. The auditor selects 4 policies at random without replacement. Calculate the probability that the sample contains **exactly 2 policies from Region A, 1 policy from Region B, and 1 policy from Region C**.

#### Solution:
* **Sample Space Size:**
  $$n(S) = \binom{15}{4} = 1,365$$
* **Favorable Outcomes:**
  $$n(E) = \binom{8}{2} \times \binom{4}{1} \times \binom{3}{1} = 28 \times 4 \times 3 = 336$$
* **Probability:**
  $$P(E) = \frac{336}{1,365} = \frac{16}{65} \approx 0.2462$$

---

### Problem 2
An actuary is organizing a shelf of 9 claim files: 4 red files (Auto), 3 blue files (Property), and 2 green files (Liability). Files of the same color are indistinguishable from one another. Calculate the total number of **distinct linear arrangements** possible for these 9 claim files.

#### Solution:
* Apply the formula for permutations with indistinguishable objects:
  $$\text{Distinct Arrangements} = \frac{n!}{n_1! \, n_2! \, n_3!} = \frac{9!}{4! \, 3! \, 2!} = \frac{362,880}{24 \times 6 \times 2} = 1,260$$

---

### Problem 3
An auto insurer creates 6-character policy identification codes formatted as follows:
* The **first 2 characters** must be uppercase letters ($A–Z$) with **no repeated letters** allowed.
* The **last 4 characters** must be digits ($0–9$), where the **first digit cannot be 0**, but digits **may be repeated**.

Calculate the total number of distinct policy identification codes that can be generated under these rules.

#### Solution:
* Slot 1 (Letter 1): 26 choices
* Slot 2 (Letter 2, no repeat): 25 choices
* Slot 3 (Digit 1, non-zero): 9 choices
* Slot 4 (Digit 2, repetition allowed): 10 choices
* Slot 5 (Digit 3, repetition allowed): 10 choices
* Slot 6 (Digit 4, repetition allowed): 10 choices
* **Total Codes:**
  $$\text{Total} = 26 \times 25 \times 9 \times 10 \times 10 \times 10 = 5,850,000$$

---

### Problem 4
A department consists of 10 underwriters: 6 experienced underwriters and 4 novice underwriters. A special audit committee of 5 underwriters is randomly selected from this group. Calculate the probability that the committee contains **at least 2 novice underwriters**.

#### Solution:
* **Sample Space Size:** $n(S) = \binom{10}{5} = 252$
* **Partitioning Favorable Cases ("At least 2 novice"):**
  * **2 Novice, 3 Experienced:** $n(E_2) = \binom{4}{2} \times \binom{6}{3} = 6 \times 20 = 120$
  * **3 Novice, 2 Experienced:** $n(E_3) = \binom{4}{3} \times \binom{6}{2} = 4 \times 15 = 60$
  * **4 Novice, 1 Experienced:** $n(E_4) = \binom{4}{4} \times \binom{6}{1} = 1 \times 6 = 6$
* **Total Favorable Outcomes:**
  $$n(E) = 120 + 60 + 6 = 186$$
* **Probability:**
  $$P(E) = \frac{186}{252} = \frac{31}{42} \approx 0.7381$$

---

## 6. Additional Practice Problem Set & Solutions

### Problem 1
An auditor reviews a portfolio of 18 policies: 9 Auto, 6 Homeowners, and 3 Commercial. The auditor selects 5 policies at random without replacement. Calculate the probability that the sample contains **at least 4 Auto policies**.

#### Solution:
* $n(S) = \binom{18}{5} = 8,568$
* **Case 1 (4 Auto, 1 Non-Auto):** $n(A_4) = \binom{9}{4} \times \binom{9}{1} = 126 \times 9 = 1,134$
* **Case 2 (5 Auto, 0 Non-Auto):** $n(A_5) = \binom{9}{5} \times \binom{9}{0} = 126 \times 1 = 126$
* **Total Favorable:** $n(E) = 1,134 + 126 = 1,260$
* **Probability:**
  $$P(E) = \frac{1,260}{8,568} = \frac{5}{34} \approx 0.1471$$

---

### Problem 2
An IT security system generates 7-character access identification codes formatted as follows:
* First 3 characters: Uppercase letters ($A–Z$) with **no repeated letters** allowed.
* Last 4 characters: Digits ($0–9$) with **no repeated digits** allowed (the first digit *can* be 0).

Calculate the total number of distinct access identification codes that can be generated.

#### Solution:
* **Letters Part:** $P(26, 3) = 26 \times 25 \times 24 = 15,600$
* **Digits Part:** $P(10, 4) = 10 \times 9 \times 8 \times 7 = 5,040$
* **Total Codes:**
  $$\text{Total} = 15,600 \times 5,040 = 78,624,000$$

---

### Problem 3
An actuary arranges 10 claim file folders on a shelf: 5 blue folders (Auto), 3 yellow folders (Property), and 2 red folders (Liability). Folders of the same color are indistinguishable. Calculate the number of **distinct linear arrangements** possible if **all 3 yellow folders must be placed directly next to each other (side-by-side)**.

#### Solution:
* **Group Yellow Folders:** Treat the 3 identical yellow folders as **1 Yellow Block** ($[YYY]$).
* **Super-Items to Arrange ($N = 8$):** 5 Blue, 1 Yellow Block, 2 Red.
* **Arrangements of Super-Items:**
  $$\text{Arrangements} = \frac{8!}{5! \, 1! \, 2!} = \frac{40,320}{120 \times 1 \times 2} = 168$$
* **Internal Arrangements of Yellow Block:** $\frac{3!}{3!} = 1$ (since identical).
* **Total Arrangements:** $168 \times 1 = 168$.

---

### Problem 4
A task force of 6 actuaries is randomly selected from a department consisting of 8 Life actuaries and 6 Health actuaries. Calculate the probability that the task force contains an **equal number of Life actuaries and Health actuaries** (3 Life and 3 Health).

#### Solution:
* $n(S) = \binom{14}{6} = 3,003$
* $n(E) = \binom{8}{3} \times \binom{6}{3} = 56 \times 20 = 1,120$
* **Probability:**
  $$P(E) = \frac{1,120}{3,003} = \frac{160}{429} \approx 0.3730$$

---

## 7. Drill Practice Problem Set & Solutions

### Problem 1
An underwriter audits a batch of 16 commercial policies: 10 Auto and 6 Property. The underwriter selects 4 policies at random without replacement. Calculate the probability that the audit sample contains **at most 1 Property policy**.

#### Solution:
* $n(S) = \binom{16}{4} = 1,820$
* **Case 1 (0 Property, 4 Auto):** $n(P_0) = \binom{6}{0} \times \binom{10}{4} = 1 \times 210 = 210$
* **Case 2 (1 Property, 3 Auto):** $n(P_1) = \binom{6}{1} \times \binom{10}{3} = 6 \times 120 = 720$
* $n(E) = 210 + 720 = 930$
* **Probability:**
  $$P(E) = \frac{930}{1,820} = \frac{93}{182} \approx 0.5110$$

---

### Problem 2
An actuary displays 8 policy binders on a shelf: 4 red, 2 blue, and 2 white. Binders of the same color are indistinguishable. Calculate the number of **distinct linear arrangements** possible if **all 4 red binders must be placed directly next to each other**.

#### Solution:
* Group 4 Red binders into **1 Red Block** ($[RRRR]$).
* Super-items to arrange ($N = 5$): 1 Red Block, 2 Blue, 2 White.
* **Arrangements:**
  $$\text{Arrangements} = \frac{5!}{1! \, 2! \, 2!} = \frac{120}{4} = 30$$

---

### Problem 3
A risk management system generates 5-character secure passcodes according to the following rules:
* 1st character: Non-zero digit ($1–9$).
* 2nd and 3rd characters: Uppercase vowels $\{A, E, I, O, U\}$ with **no repeated vowels**.
* 4th and 5th characters: Numerical digits ($0–9$), **repetition allowed**.

Calculate the total number of distinct secure passcodes that can be generated.

#### Solution:
$$\text{Total} = \underbrace{9}_{\text{Digit 1}} \times \underbrace{5}_{\text{Vowel 1}} \times \underbrace{4}_{\text{Vowel 2}} \times \underbrace{10}_{\text{Digit 2}} \times \underbrace{10}_{\text{Digit 3}} = 18,000$$

---

### Problem 4
A company forms a 4-person committee chosen at random from 12 employees: 5 Senior Actuaries, 4 Associate Actuaries, and 3 Actuarial Analysts. Calculate the probability that the committee contains **at least 1 Actuarial Analyst**.

#### Solution:
* $n(S) = \binom{12}{4} = 495$
* **Case 1 (1 Analyst, 3 Non-Analysts):** $n(Z_1) = \binom{3}{1} \times \binom{9}{3} = 3 \times 84 = 252$
* **Case 2 (2 Analysts, 2 Non-Analysts):** $n(Z_2) = \binom{3}{2} \times \binom{9}{2} = 3 \times 36 = 108$
* **Case 3 (3 Analysts, 1 Non-Analyst):** $n(Z_3) = \binom{3}{3} \times \binom{9}{1} = 1 \times 9 = 9$
* $n(E) = 252 + 108 + 9 = 369$
* **Probability:**
  $$P(E) = \frac{369}{495} = \frac{41}{55} \approx 0.7455$$

---

## 8. Summary Formula Reference Sheet

| Concept | Formula | Key Condition / Use Case |
| :--- | :---: | :--- |
| **Multiplication Principle** | $\prod_{i=1}^k n_i = n_1 \times n_2 \times \dots \times n_k$ | Sequential multi-stage choices