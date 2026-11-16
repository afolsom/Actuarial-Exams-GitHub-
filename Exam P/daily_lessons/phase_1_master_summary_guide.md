# Phase 1: General Probability — Master Summary, Formula Reference & Problem-Solving Guide

---

## 1. Executive Summary of Phase 1 (Days 1–10)

Phase 1 establishes the mathematical groundwork of probability theory required for **SOA Exam P**. The content spans foundational set theory through advanced conditional inference.

### Core Topic Breakdown

1. **Days 1–2: Set Theory, Event Algebra, and Probability Axioms (Objectives 1A)**
   * **Sample Spaces & Events:** Outcomes ($\omega$), sample spaces ($S$), and events ($A \subseteq S$).
   * **Set Operations:** Union ($\cup$), intersection ($\cap$), complement ($^c$), set difference ($\setminus$).
   * **De Morgan’s Laws:** $(A \cup B)^c = A^c \cap B^c$ and $(A \cap B)^c = A^c \cup B^c$.
   * **Axioms of Probability:** Non-negativity ($P(A) \ge 0$), Normalization ($P(S) = 1$), and Countable Additivity for disjoint sets.
   * **Derived Rules:** Complement rule, monotonicity ($A \subseteq B \implies P(A) \le P(B)$), and bounds ($0 \le P(A) \le 1$).

2. **Days 3–4: Combinatorics & Counting Techniques (Objective 1B)**
   * **Fundamental Principles:** Multiplication principle for sequential steps; Addition principle for disjoint options.
   * **Permutations vs. Combinations:** Permutations (order matters) vs. Combinations (order does not matter).
   * **Advanced Counting:**
     * *Block Method:* Grouping items that must remain adjacent into a single "super-item."
     * *Gap Method:* Placing unrestricted items first, then positioning restricted items into available gaps so no two sit together.
     * *Stars and Bars:* Distributing $n$ identical items into $k$ distinct bins ($\binom{n+k-1}{k-1}$ for non-negative allocations; $\binom{n-1}{k-1}$ for positive allocations).
     * *Grid/Lattice Paths:* $\binom{a+b}{a}$ paths from $(0,0)$ to $(a,b)$ moving right/up.

3. **Day 5: Addition Rules & Inclusion-Exclusion (Objectives 1C & 1D)**
   * **Disjoint Events:** $A \cap B = \varnothing \implies P(A \cup B) = P(A) + P(B)$.
   * **General Addition Rule:** Adjusting for double-counted intersections ($P(A \cup B) = P(A) + P(B) - P(A \cap B)$).
   * **3-Event Inclusion-Exclusion:** Adding individual probabilities, subtracting pairwise overlaps, and adding back the triple intersection.

4. **Day 6: Independent Events & Joint Probabilities (Objective 1C)**
   * **Definition:** $A$ and $B$ are independent if and only if $P(A \cap B) = P(A) \cdot P(B)$ (equivalent to $P(A \mid B) = P(A)$).
   * **Disjoint vs. Independent:** Mutually exclusive events with non-zero probabilities can *never* be independent.
   * **Complements:** If $A$ and $B$ are independent, so are $A^c$ and $B^c$.
   * **"At Least One" Rule:** For $n$ independent events, $P(\text{at least one occurs}) = 1 - \prod_{i=1}^n (1 - P(A_i))$.

5. **Day 7: Multiplication Rules & Sequential Pathways (Objective 1E)**
   * **General Multiplication Rule:** $P(A \cap B) = P(A) \cdot P(B \mid A)$.
   * **Chain Rule:** Extending the product rule across $n$ sequential dependent stages.
   * **Sampling Dynamics:** Replacement (independent, constant probabilities) vs. Without Replacement (dependent, changing denominators).
   * **Pathway Decomposition:** Partitioning complex multi-stage outcomes into mutually exclusive paths, calculating path products, and summing paths.

6. **Day 8: Conditional Probability & Sample Space Reduction (Objective 1F)**
   * **Definition:** $P(A \mid B) = \frac{P(A \cap B)}{P(B)}$ for $P(B) > 0$.
   * **Reduced Sample Space:** Restricting the universal space $S$ down to event $B$.
   * **Tools:** Venn diagrams, two-way contingency tables, and set partitioning.

7. **Days 9–10: Law of Total Probability & Bayes' Theorem (Objective 1G)**
   * **Partitions:** Sets $\{B_1, B_2, \dots, B_k\}$ that are mutually exclusive ($B_i \cap B_j = \varnothing$) and collectively exhaustive ($\sum P(B_i) = 1$).
   * **Law of Total Probability (LTP):** Unconditional probability obtained by weighting conditional probabilities across all partition pieces: $P(A) = \sum_{i=1}^k P(B_i) P(A \mid B_i)$.
   * **Bayes' Theorem:** Updating prior probabilities $P(B_j)$ into posterior probabilities $P(B_j \mid A)$ given observed evidence $A$.
   * **Tree Diagrams:** Structuring prior probabilities (1st branch level), likelihoods (2nd branch level), path products (joint probabilities), and posterior ratios.

---

## 2. Concise Phase 1 Master Formula Chart

> **Note on Optimization:** To eliminate redundancy, general expressions are presented in their canonical form. Specific cases (e.g., 2-event variants) derive naturally by setting $k=2$.

### Section 1: Set Operations & Event Algebra
* **De Morgan’s Laws:**
  $$(A \cup B)^c = A^c \cap B^c \quad \text{and} \quad (A \cap B)^c = A^c \cup B^c$$
  *Verbal:* The complement of a union is the intersection of the complements; the complement of an intersection is the union of the complements.
* **Set Difference / Partition Rule:**
  $$P(A \cap B^c) = P(A \setminus B) = P(A) - P(A \cap B)$$
  *Verbal:* The probability of $A$ occurring without $B$ equals the probability of $A$ minus the joint overlap of $A$ and $B$.

### Section 2: Axioms & Basic Properties
* **Probability Axioms (Kolmogorov):**
  $$P(A) \ge 0, \quad P(S) = 1, \quad P\left(\bigcup_{i=1}^{\infty} A_i\right) = \sum_{i=1}^{\infty} P(A_i) \quad (\text{for disjoint } A_i)$$
* **Complement Rule:**
  $$P(A^c) = 1 - P(A)$$
  *Verbal:* The probability an event does not occur is 1 minus the probability it does occur.

### Section 3: Combinatorics & Counting
* **Permutations (Ordered Selection):**
  $${}_nP_r = P(n, r) = \frac{n!}{(n - r)!}$$
  *Verbal:* Number of ways to select and arrange $r$ items from $n$ distinct items where order matters.
* **Permutations with Repeated/Indistinguishable Items:**
  $$\text{Arrangements} = \frac{n!}{n_1! \, n_2! \dots n_k!} \quad \text{where } \sum n_i = n$$
  *Verbal:* Total permutations divided by the factorials of each set of identical items.
* **Combinations (Unordered Selection):**
  $$\binom{n}{r} = {}_nC_r = \frac{n!}{r!(n - r)!}$$
  *Verbal:* Number of ways to select a subset of $r$ items from $n$ distinct items where order does not matter.
* **Stars and Bars (Distributing $n$ Identical Items into $k$ Distinct Bins):**
  $$\text{Non-negative } (x_i \ge 0): \binom{n + k - 1}{k - 1} \qquad \text{Positive } (x_i \ge 1): \binom{n - 1}{k - 1}$$
* **Grid/Lattice Paths:**
  $$\text{Paths from } (0,0) \text{ to } (a,b) \text{ moving Right/Up} = \binom{a + b}{a}$$

### Section 4: Addition Rules & Inclusion-Exclusion
* **General Addition Rule (Two Events):**
  $$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$
  *Verbal:* Sum of individual probabilities minus the double-counted intersection.
* **Inclusion-Exclusion Principle (Three Events):**
  $$P(A \cup B \cup C) = \sum P(A) - \sum P(A \cap B) + P(A \cap B \cap C)$$
  *Verbal:* Add single probabilities, subtract pairwise intersections, add back the triple intersection.

### Section 5: Independence
* **Independence Criterion:**
  $$P(A \cap B) = P(A) \cdot P(B) \iff P(A \mid B) = P(A)$$
  *Verbal:* Two events are independent if their joint probability equals the product of their individual probabilities.
* **"At Least One" Rule for $n$ Independent Events:**
  $$P\left(\bigcup_{i=1}^n A_i\right) = 1 - \prod_{i=1}^n \left(1 - P(A_i)\right)$$
  *Verbal:* One minus the probability that all $n$ independent events fail to occur.

### Section 6: Conditional Probability & Sequential Rules
* **Conditional Probability:**
  $$P(A \mid B) = \frac{P(A \cap B)}{P(B)} \quad (P(B) > 0)$$
  *Verbal:* The probability of $A$ given $B$ is the joint probability divided by the conditioning event's probability.
* **Chain Rule (Sequential Product):**
  $$P(A_1 \cap A_2 \cap \dots \cap A_n) = P(A_1) \cdot P(A_2 \mid A_1) \cdot P(A_3 \mid A_1 \cap A_2) \cdots P(A_n \mid A_1 \cap \dots \cap A_{n-1})$$

### Section 7: Total Probability & Bayes' Theorem
* **Law of Total Probability (LTP):**
  $$P(A) = \sum_{i=1}^k P(B_i) P(A \mid B_i) \quad \text{where } \{B_1, \dots, B_k\} \text{ partitions } S$$
  *Verbal:* The unconditional probability of $A$ is the weighted sum of its conditional probabilities across a complete partition.
* **Bayes' Theorem (General Form):**
  $$P(B_j \mid A) = \frac{P(B_j \cap A)}{P(A)} = \frac{P(B_j) P(A \mid B_j)}{\sum_{i=1}^k P(B_i) P(A \mid B_i)}$$
  *Verbal:* Posterior probability equals the specific path product divided by the sum of all path products leading to event $A$.

---

## 3. General Problem-Solving Strategy for Phase 1 Questions

When presented with a Phase 1 question on Exam P, follow this structured 5-step approach:

```
[Step 1: Define Events] ──> [Step 2: Identify Target] ──> [Step 3: Choose Tool Structure]
                                                                  │
[Step 5: Sanity Check]  <── [Step 4: Execute Calculation] <───────┘
```

### Step 1: Formally Define Events and Given Quantities
* Read the word problem carefully and assign precise letter variables to events (e.g., $A$ = Auto policy, $H$ = High risk, $C$ = File claim).
* Translate verbal descriptions into mathematical statements:
  * *"Neither A nor B"* $\longrightarrow P(A^c \cap B^c) = P((A \cup B)^c)$
  * *"A given B"* $\longrightarrow P(A \mid B)$
  * *"A or B but not both"* $\longrightarrow P(A \Delta B) = P(A \cup B) - P(A \cap B)$
  * *"At least one of A, B, C"* $\longrightarrow P(A \cup B \cup C)$

### Step 2: Identify the Target Quantity
* Clearly specify what the question asks for (e.g., find $P(B_2 \mid C)$, find $P(A \cup B)$, or calculate total possible arrangements).

### Step 3: Select the Appropriate Problem-Solving Framework

| Question Keyword / Structure | Recommended Framework | Primary Tool / Formula |
| :--- | :--- | :--- |
| **Categorical Policy Data / Overlapping Coverages** | Two-way Table or Venn Diagram | $P(A \cup B) = P(A) + P(B) - P(A \cap B)$ |
| **Selecting Committees / Ordering Items / Bins** | Combinatorics | Combinations $\binom{n}{r}$, Permutations, Stars & Bars |
| **Multi-Stage Sequential Process** | Tree Diagram / Chain Rule | $P(A \cap B) = P(A) P(B \mid A)$ |
| **Population Split into Risk Tiers / Groups** | Law of Total Probability (LTP) | $P(A) = \sum P(B_i) P(A \mid B_i)$ |
| **Given Outcome Observed, Find Cause/Origin** | Bayes' Theorem | $P(B_j \mid A) = \frac{P(B_j)P(A \mid B_j)}{\text{LTP denominator}}$ |
| **"At Least One" Independent Failure/Success** | Complement Rule | $P(\text{At least 1}) = 1 - P(\text{None}) = 1 - \prod (1 - P_i)$ |

### Step 4: Execute the Algebraic/Arithmetic Calculation
* Substitute known values into the chosen formula.
* Keep intermediate steps in exact fraction format when possible to prevent premature rounding errors.

### Step 5: Perform Actuarial Sanity Checks
* **Probability Bounds Check:** Ensure $0 \le P(\text{Event}) \le 1$. If a result is negative or $> 1$, re-check double-counting in unions or incorrect denominators.
* **Complement Check:** Ensure probabilities across a partition sum to 1 ($\sum P(B_i) = 1$ and $\sum P(B_i \mid A) = 1$).
* **Monotonicity Check:** Verify that $P(A \cap B) \le P(A) \le P(A \cup B)$.