# Actuarial Exam P: Day 5 Study Session
**Session 1C.1: Mutually Exclusive Events, Addition Rules, and the Inclusion-Exclusion Principle**
**SOA Exam Objectives:** 1C & 1D

---

## 1. Overview & Learning Objectives

By the end of this study session, you will be able to:
1. Formally define **mutually exclusive (disjoint) events** and apply their probability properties.
2. Apply the **General Addition Rule** for two non-disjoint events ($P(A \cup B) = P(A) + P(B) - P(A \cap B)$).
3. Apply the **Inclusion-Exclusion Principle** for three non-disjoint events ($P(A \cup B \cup C)$).
4. Translate actuarial insurance scenarios (policy coverages, multi-claim risk categories, overlapping benefit plans) into precise addition rule and inclusion-exclusion calculations.

---

## 2. Core Concepts & Theory

### A. Mutually Exclusive (Disjoint) Events
* **Definition:** Two events $A$ and $B$ are **mutually exclusive** (or **disjoint**) if they cannot occur at the same time. In set notation, their intersection is empty:
  $$A \cap B = \varnothing$$
* **Probability Property:** Since the empty set contains no outcomes:
  $$P(A \cap B) = 0$$
* **Special Addition Rule (Disjoint Events):** By Kolmogorov's Axiom 3 (Finite Additivity), if $A$ and $B$ are mutually exclusive, the probability that at least one occurs is the sum of their individual probabilities:
  $$P(A \cup B) = P(A) + P(B)$$
* **Finite Additivity for $n$ Disjoint Events:**
  $$P(A_1 \cup A_2 \cup \dots \cup A_n) = \sum_{i=1}^{n} P(A_i)$$

---

### B. The General Addition Rule (Two Events)
When two events $A$ and $B$ are **not** mutually exclusive (they can happen simultaneously), simply adding $P(A) + P(B)$ double-counts the overlapping region $A \cap B$.

To correct for double-counting, subtract $P(A \cap B)$:

$$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$

* **Rearranged Form for Joint Intersection:**
  $$P(A \cap B) = P(A) + P(B) - P(A \cup B)$$
* **Actuarial Meaning:** $P(A \cup B)$ represents the probability that a policyholder files **at least one** of claim type $A$ or claim type $B$.

---

### C. The Inclusion-Exclusion Principle (Three Events)
For three non-disjoint events $A$, $B$, and $C$, finding the probability that **at least one** event occurs requires extending the addition rule:

$$P(A \cup B \cup C) = P(A) + P(B) + P(C) - P(A \cap B) - P(A \cap C) - P(B \cap C) + P(A \cap B \cap C)$$

#### Why the Formula Works:
1. **Single Probabilities ($P(A) + P(B) + P(C)$):** Counts all outcomes in the union, but double-counts two-way overlaps and triple-counts the central three-way overlap.
2. **Subtract Pairwise Intersections ($- P(A \cap B) - P(A \cap C) - P(B \cap C)$):** Removes double-counting for two-way overlaps.
3. **Add Back Triple Intersection ($+ P(A \cap B \cap C)$):** Subtracting all three pairwise intersections removes the center triple intersection $A \cap B \cap C$ one too many times! Adding it back restores exact balance.

---

### D. Actuarial Application Example
**Scenario:** An insurer offers three policy options: **Auto ($A$)**, **Home ($H$)**, and **Life ($L$)**. An actuarial review shows:
* $P(A) = 0.40$, $P(H) = 0.30$, $P(L) = 0.20$
* $P(A \cap H) = 0.15$, $P(A \cap L) = 0.10$, $P(H \cap L) = 0.05$
* $P(A \cap H \cap L) = 0.02$

**Problem:** Find the probability that a randomly selected customer holds **at least one** coverage ($P(A \cup H \cup L)$).

**Solution:**
$$P(A \cup H \cup L) = P(A) + P(H) + P(L) - P(A \cap H) - P(A \cap L) - P(H \cap L) + P(A \cap H \cap L)$$
$$P(A \cup H \cup L) = 0.40 + 0.30 + 0.20 - 0.15 - 0.10 - 0.05 + 0.02 = \mathbf{0.62}$$

---

## 3. Concept Check Questions & Solutions

### Question 1
If $P(A) = 0.45$ and $P(B) = 0.35$:
1. What is $P(A \cup B)$ if $A$ and $B$ are **mutually exclusive**?
2. What is $P(A \cup B)$ if $A$ and $B$ are **not** mutually exclusive and $P(A \cap B) = 0.12$?

#### Solution:
1. **Mutually Exclusive:** $P(A \cap B) = 0 \implies P(A \cup B) = 0.45 + 0.35 = \mathbf{0.80}$
2. **Not Mutually Exclusive:** $P(A \cup B) = 0.45 + 0.35 - 0.12 = \mathbf{0.68}$

---

### Question 2
An auto policyholder can incur claims in three mutually exclusive categories: Collision ($C$), Comprehensive ($K$), or Liability ($L$). If $P(C) = 0.20$, $P(K) = 0.12$, and $P(L) = 0.18$, what is the probability that the policyholder incurs **at least one** claim?

#### Solution:
Since the categories are mutually exclusive, $P(C \cap K) = P(C \cap L) = P(K \cap L) = 0$. By finite additivity:
$$P(C \cup K \cup L) = P(C) + P(K) + P(L) = 0.20 + 0.12 + 0.18 = \mathbf{0.50}$$

---

### Question 3
An insurer determines that for three policy coverages $A, B,$ and $C$, $P(A \cup B \cup C) = 0.75$, $P(A) = 0.40$, $P(B) = 0.35$, and $P(C) = 0.30$. If no policyholder holds all three coverages simultaneously ($P(A \cap B \cap C) = 0$), what is the sum of the pairwise joint probabilities $P(A \cap B) + P(A \cap C) + P(B \cap C)$?

#### Solution:
Let $S = P(A \cap B) + P(A \cap C) + P(B \cap C)$. Using 3-event Inclusion-Exclusion:
$$P(A \cup B \cup C) = P(A) + P(B) + P(C) - S + P(A \cap B \cap C)$$
$$0.75 = 0.40 + 0.35 + 0.30 - S + 0$$
$$0.75 = 1.05 - S \implies S = 1.05 - 0.75 = \mathbf{0.30}$$

---

## 4. Day 5 Practice Problem Set

### Problem 1
An insurer determines that among policyholders with commercial property coverage:
* $30\%$ suffer a fire loss ($F$).
* $25\%$ suffer a water damage loss ($W$).
* $15\%$ suffer a theft loss ($T$).
* $10\%$ suffer both fire and water damage.
* $8\%$ suffer both fire and theft.
* $5\%$ suffer both water damage and theft.
* $2\%$ suffer all three types of loss.

Calculate the probability that a randomly chosen policyholder suffers **at least one** of these three types of loss.

#### Solution:
Apply the 3-event Inclusion-Exclusion Principle:
$$P(F \cup W \cup T) = P(F) + P(W) + P(T) - P(F \cap W) - P(F \cap T) - P(W \cap T) + P(F \cap W \cap T)$$
$$P(F \cup W \cup T) = (0.30 + 0.25 + 0.15) - (0.10 + 0.08 + 0.05) + 0.02$$
$$P(F \cup W \cup T) = 0.70 - 0.23 + 0.02 = \mathbf{0.49}$$

---

### Problem 2
An auto insurance company offers three optional coverages: **Roadside Assistance ($R$)**, **Rental Car Reimbursement ($C$)**, and **Glass Protection ($G$)**.
You are given:
* $P(R) = 0.45$, $P(C) = 0.35$, $P(G) = 0.25$
* $P(R \cap C) = 0.15$, $P(R \cap G) = 0.10$, $P(C \cap G) = 0.08$
* The probability that a policyholder holds **none** of the three coverages is $0.25$.

Calculate the probability that a randomly selected policyholder holds **all three** coverages simultaneously ($P(R \cap C \cap G)$).

#### Solution:
1. **Find Union Probability:**
   $$P(R \cup C \cup G) = 1 - P(\text{None}) = 1 - 0.25 = 0.75$$
2. **Apply Inclusion-Exclusion:**
   $$P(R \cup C \cup G) = P(R) + P(C) + P(G) - P(R \cap C) - P(R \cap G) - P(C \cap G) + P(R \cap C \cap G)$$
   $$0.75 = (0.45 + 0.35 + 0.25) - (0.15 + 0.10 + 0.08) + P(R \cap C \cap G)$$
   $$0.75 = 1.05 - 0.33 + P(R \cap C \cap G)$$
   $$0.75 = 0.72 + P(R \cap C \cap G)$$
   $$P(R \cap C \cap G) = 0.75 - 0.72 = \mathbf{0.03}$$

---

### Problem 3
An actuary analyzes claims for a group health policy with two benefit categories: **Dental ($D$)** and **Vision ($V$)**.
* $40\%$ of policyholders file a Dental claim.
* $30\%$ of policyholders file a Vision claim.
* The probability of filing a Vision claim given that no Dental claim was filed is $0.20$.

Calculate the probability that a policyholder files **at least one** claim ($P(D \cup V)$).

#### Solution:
1. **Given Values:** $P(D) = 0.40$, $P(V) = 0.30$, and $P(V \mid D^c) = 0.20$.
2. **Find Complement $P(D^c)$:**
   $$P(D^c) = 1 - P(D) = 1 - 0.40 = 0.60$$
3. **Find $P(V \cap D^c)$ (Vision Only):**
   $$P(V \mid D^c) = \frac{P(V \cap D^c)}{P(D^c)} \implies P(V \cap D^c) = 0.20 \times 0.60 = 0.12$$
4. **Calculate Union $P(D \cup V)$ via Partitioning:**
   The union $D \cup V$ decomposes into the disjoint union of filing a Dental claim ($D$) and filing a Vision claim without Dental ($V \cap D^c$):
   $$P(D \cup V) = P(D) + P(V \cap D^c) = 0.40 + 0.12 = \mathbf{0.52}$$

---

### Problem 4
A policyholder can incur claims in four distinct risk pools ($A, B, C,$ and $D$). Pools $A, B,$ and $C$ are **mutually exclusive** of each other. Pool $D$ overlaps with each of the other three pools such that:
* $P(A) = 0.15$, $P(B) = 0.20$, $P(C) = 0.25$, $P(D) = 0.30$
* $P(A \cap D) = 0.05$, $P(B \cap D) = 0.04$, $P(C \cap D) = 0.06$

Calculate the probability that the policyholder incurs a claim in **at least one** of the four pools ($P(A \cup B \cup C \cup D)$).

#### Walkthrough Solution (Two Methods):

##### Method 1: Grouping Disjoint Pools (Shortest Path)
1. Combine the mutually exclusive pools $A, B,$ and $C$ into a single event $E = A \cup B \cup C$:
   $$P(E) = P(A) + P(B) + P(C) = 0.15 + 0.20 + 0.25 = 0.60$$
2. Calculate the total overlap between $E$ and pool $D$:
   $$P(E \cap D) = P(A \cap D) + P(B \cap D) + P(C \cap D) = 0.05 + 0.04 + 0.06 = 0.15$$
3. Apply 2-event General Addition Rule between $E$ and $D$:
   $$P(A \cup B \cup C \cup D) = P(E \cup D) = P(E) + P(D) - P(E \cap D)$$
   $$P(A \cup B \cup C \cup D) = 0.60 + 0.30 - 0.15 = \mathbf{0.75}$$

##### Method 2: Full Inclusion-Exclusion Principle
$$P(A \cup B \cup C \cup D) = \sum P(\text{Singles}) - \sum P(\text{Pairs}) + \sum P(\text{Triples}) - P(\text{4-way})$$
1. **Sum of Singles:** $0.15 + 0.20 + 0.25 + 0.30 = 0.90$
2. **Sum of Pairs:** Since $A, B, C$ are disjoint, $P(A \cap B) = P(A \cap C) = P(B \cap C) = 0$.
   $$\text{Sum of Pairs} = P(A \cap D) + P(B \cap D) + P(C \cap D) = 0.05 + 0.04 + 0.06 = 0.15$$
3. **Triples & 4-Way Intersections:** Any intersection containing two or more of $A, B, C$ is empty ($\varnothing$), so all triple and 4-way intersections equal $0$.
4. **Combine:**
   $$P(A \cup B \cup C \cup D) = 0.90 - 0.15 + 0 - 0 = \mathbf{0.75}$$

---

## 5. Day 5 Formula Summary Reference

| Concept | Mathematical Formula | Verbal Description / Key Application |
| :--- | :--- | :--- |
| **Disjoint Condition** | $A \cap B = \varnothing \implies P(A \cap B) = 0$ | Two events cannot happen at the same time. |
| **Disjoint Addition Rule** | $P(A \cup B) = P(A) + P(B)$ | Union of non-overlapping events is the sum of their probabilities. |
| **General Addition Rule** | $P(A \cup B) = P(A) + P(B) - P(A \cap B)$ | Corrects for double-counting overlapping region $A \cap B$. |
| **3-Event Inclusion-Exclusion** | $P(A \cup B \cup C) = \sum P_i - \sum P_{ij} + P_{ijk}$ | Sum singles, subtract pairs, add back triple intersection. |
| **Union Decomposition** | $P(A \cup B) = P(A) + P(B \cap A^c)$ | Splits union into event $A$ and the portion of $B$ outside $A$. |