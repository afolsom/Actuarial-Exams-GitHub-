# Actuarial Exam P: Day 6 Study Session
## Session 1D.1: Independent Events and Calculating Joint Probabilities (SOA Objective 1C)

---

## 1. Executive Summary & Learning Objectives

Independence is one of the most fundamental concepts in probability theory and actuarial science. It simplifies multi-event joint risk calculations and serves as the foundation for modeling independent policy losses, pricing multi-line coverage, and portfolio risk management.

By completing this session, you will be able to:
1. Formally define **independence** for two events ($A$ and $B$) using product rules and conditional probabilities.
2. Mathematically distinguish between **mutually exclusive (disjoint)** events and **independent** events.
3. Apply independence properties to **complements** ($A^c$, $B^c$) and perform multi-event joint probability calculations (including "at least one" complementary strategies).
4. Extend independence to $n \ge 3$ events and distinguish between **pairwise independence** and **mutual independence**.

---

## 2. Core Theoretical Foundations

### A. Formal Definition of Independent Events
Two events $A$ and $B$ defined on a sample space $S$ are **independent** if the occurrence of $A$ gives no information about whether $B$ occurs (and vice versa).

#### The Product Rule (Necessary & Sufficient Condition)
Events $A$ and $B$ are independent if and only if:
$$P(A \cap B) = P(A) \cdot P(B)$$

#### Conditional Probability Equivalence
If $P(A) > 0$ and $P(B) > 0$, the following conditions are completely equivalent to the product rule:
* $P(A \mid B) = P(A)$
* $P(B \mid A) = P(B)$

---

### B. Independent vs. Mutually Exclusive (Disjoint) Events

| Property | Mutually Exclusive (Disjoint) | Independent |
| :--- | :--- | :--- |
| **Mathematical Definition** | $A \cap B = \varnothing \implies P(A \cap B) = 0$ | $P(A \cap B) = P(A) \cdot P(B)$ |
| **Venn Diagram Representation** | Completely separate circles (no overlap). | Overlapping circles where overlap area equals $P(A)P(B)$. |
| **Intuitive Meaning** | The events **cannot** happen together. | Knowing one occurred gives **no information** about the other. |

> **Key Actuarial Insight:** If two non-trivial events ($P(A) > 0$ and $P(B) > 0$) are **mutually exclusive**, they **CANNOT be independent**. 
> 
> **Proof:** If $A$ and $B$ are disjoint, $P(A \cap B) = 0$. For independence, we require $P(A \cap B) = P(A)P(B)$. Since $P(A)P(B) > 0$, $0 \neq P(A)P(B)$, so they are strongly dependent. Knowing $A$ occurred guarantees $B$ did *not* occur ($P(B \mid A) = 0 \neq P(B)$).

---

### C. Independence of Complements

If $A$ and $B$ are independent, then all combinations of their complements are also independent:
1. $A$ and $B^c$ are independent: $P(A \cap B^c) = P(A) \cdot P(B^c)$
2. $A^c$ and $B$ are independent: $P(A^c \cap B) = P(A^c) \cdot P(B)$
3. $A^c$ and $B^c$ are independent: $P(A^c \cap B^c) = P(A^c) \cdot P(B^c)$

#### The "At Least One" Strategy Formula
Combining De Morgan's Law $(A \cup B)^c = A^c \cap B^c$ with the independence of complements:
$$P(A \cup B) = 1 - P((A \cup B)^c) = 1 - P(A^c \cap B^c) = 1 - P(A^c)P(B^c)$$

For $n$ independent events $A_1, A_2, \dots, A_n$:
$$P(\text{At least one event occurs}) = 1 - \prod_{i=1}^{n} \left(1 - P(A_i)\right)$$

---

### D. Extension to $n \ge 3$ Events: Pairwise vs. Mutual Independence

For three events $A, B,$ and $C$ to be **mutually independent**, four conditions must hold simultaneously:

1. **Pairwise Independence (3 conditions):**
   * $P(A \cap B) = P(A)P(B)$
   * $P(A \cap C) = P(A)P(C)$
   * $P(B \cap C) = P(B)P(C)$
2. **Triple Product Condition (1 condition):**
   * $P(A \cap B \cap C) = P(A)P(B)P(C)$

> **Exam Warning:** Pairwise independence does **NOT** imply mutual independence. On Exam P, "independent" always means **mutually independent** unless specified otherwise.

---

## 3. Concept Check Questions & Detailed Walkthroughs

### Concept Check 1
**Question:** Let $A$ and $B$ be independent events with $P(A) = 0.40$ and $P(B) = 0.30$.
* (a) Calculate $P(A \cap B)$.
* (b) Calculate $P(A \cup B)$.
* (c) Calculate $P(A \cap B^c)$.

#### Solutions & Walkthroughs:
* **(a)** By the product rule for independent events:
  $$P(A \cap B) = P(A) \cdot P(B) = (0.40)(0.30) = \mathbf{0.12}$$
* **(b)** By the General Addition Rule:
  $$P(A \cup B) = P(A) + P(B) - P(A \cap B) = 0.40 + 0.30 - 0.12 = \mathbf{0.58}$$
* **(c)** Using event partitioning ($P(A) = P(A \cap B) + P(A \cap B^c)$) or independence of complements:
  $$P(A \cap B^c) = P(A) \cdot P(B^c) = 0.40 \times (1 - 0.30) = 0.40 \times 0.70 = \mathbf{0.28}$$

---

### Concept Check 2
**Question:** True or False? "If two non-empty events $A$ and $B$ are mutually exclusive, they can also be independent if $P(A)P(B) = 0$." Explain briefly.

#### Solution & Explanation:
**False.** If $A$ and $B$ are non-empty events, $P(A) > 0$ and $P(B) > 0$, so their product $P(A)P(B) > 0$. 
For mutually exclusive events, $P(A \cap B) = 0$.
Since $0 \neq P(A)P(B)$, the independence product rule $P(A \cap B) = P(A)P(B)$ cannot hold. Mutually exclusive non-empty events are always dependent.

---

### Concept Check 3
**Question:** An insurance portfolio consists of 4 independent policyholders. Each policyholder has a $0.15$ probability of filing a claim in a given month. What is the probability that **exactly one** policyholder files a claim? (Solve using basic probability axioms and counting).

#### Solution & Walkthrough (Without Binomial Distribution):
1. **Identify Single Event & Complement Probabilities:**
   * $P(\text{Claim}) = 0.15$
   * $P(\text{No Claim}) = 1 - 0.15 = 0.85$
2. **Calculate Probability of a Specific Sequence:**
   The probability that only Policyholder 1 files a claim and the remaining 3 do not:
   $$P(C_1 \cap C_2^c \cap C_3^c \cap C_4^c) = (0.15)(0.85)(0.85)(0.85) = (0.15)(0.85)^3 = 0.09211875$$
3. **Count the Disjoint Mutually Exclusive Scenarios:**
   There are $\binom{4}{1} = 4$ mutually exclusive ways for exactly one policyholder to file a claim ($P_1$ only, $P_2$ only, $P_3$ only, or $P_4$ only).
4. **Apply Special Addition Rule for Disjoint Events:**
   $$P(\text{Exactly 1 Claim}) = 4 \times 0.09211875 = \mathbf{0.368475} \approx \mathbf{0.3685}$$

---

## 4. Practice Problem Set & Full Solutions

### Problem 1 (Intersection & Complement Properties)
**Scenario:** An underwriter reviews two independent commercial policies, Policy $A$ and Policy $B$. $P(A) = 0.25$ and $P(B) = 0.40$.

Calculate the probability that:
* (a) Both policies incur a claim during the year.
* (b) Neither policy incurs a claim during the year.
* (c) Policy $A$ incurs a claim, but Policy $B$ does not.

#### Full Solution:
* **(a) Both policies claim ($P(A \cap B)$):**
  $$P(A \cap B) = P(A) \cdot P(B) = (0.25)(0.40) = \mathbf{0.10}$$
* **(b) Neither policy claims ($P(A^c \cap B^c)$):**
  $$P(A^c) = 1 - 0.25 = 0.75, \quad P(B^c) = 1 - 0.40 = 0.60$$
  $$P(A^c \cap B^c) = P(A^c) \cdot P(B^c) = (0.75)(0.60) = \mathbf{0.45}$$
* **(c) Policy A claims, Policy B does not ($P(A \cap B^c)$):**
  $$P(A \cap B^c) = P(A) \cdot P(B^c) = (0.25)(0.60) = \mathbf{0.15}$$

---

### Problem 2 (Testing Independence vs. Mutual Exclusivity)
**Scenario:** For events $E$ (collision) and $F$ (moving violation):
* $P(E) = 0.15$
* $P(F) = 0.20$
* $P(E \cup F) = 0.32$

1. Calculate $P(E \cap F)$.
2. Are events $E$ and $F$ independent? Show mathematical proof.
3. Are events $E$ and $F$ mutually exclusive? Explain.

#### Full Solution:
1. **Find $P(E \cap F)$ using General Addition Rule:**
   $$P(E \cup F) = P(E) + P(F) - P(E \cap F)$$
   $$0.32 = 0.15 + 0.20 - P(E \cap F) \implies P(E \cap F) = 0.35 - 0.32 = \mathbf{0.03}$$
2. **Test for Independence:**
   $$P(E) \cdot P(F) = (0.15)(0.20) = 0.03$$
   Since $P(E \cap F) = 0.03 = P(E) \cdot P(F)$, events $E$ and $F$ are **independent**.
3. **Test for Mutual Exclusivity:**
   Events are mutually exclusive if $P(E \cap F) = 0$. Since $P(E \cap F) = 0.03 \neq 0$, events $E$ and $F$ are **NOT mutually exclusive**.

---

### Problem 3 ("At Least One" Independent Event Strategy)
**Scenario:** A commercial liability insurer covers 5 independent factories. Each factory has a $p = 0.12$ probability of experiencing a hazardous spill in a given month.

Calculate the probability that **at least one** factory experiences a spill during the month.

#### Full Solution:
1. **Identify Complement Event:**
   The complement of "at least one factory experiences a spill" is "zero factories experience a spill" (all 5 operate cleanly).
2. **Calculate Single Non-Spill Probability:**
   $$P(F_i^c) = 1 - 0.12 = 0.88$$
3. **Calculate Joint Non-Spill Probability using Independence:**
   $$P(\text{No spills}) = (0.88)^5 = 0.5277319$$
4. **Apply Complement Rule:**
   $$P(\text{At least one spill}) = 1 - P(\text{No spills}) = 1 - (0.88)^5 = 1 - 0.5277319 = \mathbf{0.4722681} \approx \mathbf{0.4723}$$

---

### Problem 4 (Multi-Event Joint Probabilities for Disjoint Outcomes)
**Scenario:** An audit department reviews claim files from 3 independent adjusters ($A_1, A_2, A_3$). The processing error probabilities are:
* $P(A_1) = 0.10 \implies P(A_1^c) = 0.90$
* $P(A_2) = 0.15 \implies P(A_2^c) = 0.85$
* $P(A_3) = 0.20 \implies P(A_3^c) = 0.80$

Calculate the probability that **exactly one** of the three adjusters makes a processing error.

#### Full Solution:
1. **Decompose "Exactly One Error" into Mutually Exclusive Cases:**
   * Case 1 (Adjuster 1 only): $A_1 \cap A_2^c \cap A_3^c$
   * Case 2 (Adjuster 2 only): $A_1^c \cap A_2 \cap A_3^c$
   * Case 3 (Adjuster 3 only): $A_1^c \cap A_2^c \cap A_3$
2. **Compute Joint Probabilities via Independence:**
   * $P(A_1 \cap A_2^c \cap A_3^c) = (0.10)(0.85)(0.80) = 0.068$
   * $P(A_1^c \cap A_2 \cap A_3^c) = (0.90)(0.15)(0.80) = 0.108$
   * $P(A_1^c \cap A_2^c \cap A_3) = (0.90)(0.85)(0.20) = 0.153$
3. **Sum Disjoint Probabilities:**
   $$P(\text{Exactly 1 Error}) = 0.068 + 0.108 + 0.153 = \mathbf{0.329}$$

---

## 5. Day 6 Formula Summary Cheat Sheet

| Formula Name | Mathematical Expression | Concise Description / Verbal Rule |
| :--- | :--- | :--- |
| **Product Rule (Independence)** | $P(A \cap B) = P(A) \cdot P(B)$ | $A$ and $B$ are independent iff their joint probability equals the product of their individual probabilities. |
| **Conditional Equivalence** | $P(A \mid B) = P(A)$ | Occurrence of $B$ does not alter the probability of $A$. |
| **Independence of Complements** | $P(A^c \cap B^c) = P(A^c) \cdot P(B^c)$ | If $A$ and $B$ are independent, their complements are also independent. |
| **At Least One Rule ($n$ Events)** | $P(\text{At least 1}) = 1 - \prod_{i=1}^n (1 - P(A_i))$ | Subtract from 1 the joint probability that none of the independent events occur. |
| **Mutual Independence ($n=3$)** | Pairwise (3) + Triple Product $P(A \cap B \cap C) = P(A)P(B)P(C)$ | All pairwise conditions AND the full joint product must hold simultaneously. |