# Day 9 Study Session: Law of Total Probability and Partitioning Sample Spaces
**Course:** Actuarial Exam P  
**Module:** General Probability (Phase 1)  
**Session:** 1G.1 (SOA Objective 1g)

---

## Learning Objectives
By the end of this session, you will be able to:
1. Define a **formal partition** of a sample space $S$ using mutually exclusive and collectively exhaustive events.
2. State and apply the **Law of Total Probability (LTP)** to evaluate unconditional probabilities.
3. Translate actuarial multi-tier risk structures (e.g., policyholder risk classes, driver age groups, claim type categories) into precise LTP equations.
4. Solve multi-stage conditional probability problems using tree diagrams and partition tables.

---

## 1. Core Theory: Partitions of a Sample Space

A collection of events $\{B_1, B_2, \dots, B_k\}$ forms a **partition** of the sample space $S$ if two conditions are met:
1. **Mutually Exclusive (Disjoint):** No two events share any outcomes.
   $$B_i \cap B_j = \varnothing \quad \text{for all } i \neq j$$
2. **Collectively Exhaustive:** The union of all events covers the entire sample space $S$.
   $$\bigcup_{i=1}^{k} B_i = B_1 \cup B_2 \cup \dots \cup B_k = S$$

Because the partition elements cover $S$ without overlap, their probabilities sum to 1:
$$\sum_{i=1}^{k} P(B_i) = P(B_1) + P(B_2) + \dots + P(B_k) = 1$$

---

## 2. The Law of Total Probability (LTP)

Let $\{B_1, B_2, \dots, B_k\}$ be a partition of $S$ such that $P(B_i) > 0$ for all $i$. For any event $A \subseteq S$, the unconditional probability $P(A)$ is obtained by summing the joint probabilities across all partition pieces:

$$P(A) = \sum_{i=1}^{k} P(A \cap B_i)$$

Applying the General Multiplication Rule ($P(A \cap B_i) = P(B_i) \cdot P(A \mid B_i)$):

$$P(A) = P(B_1)P(A \mid B_1) + P(B_2)P(A \mid B_2) + \dots + P(B_k)P(A \mid B_k)$$

### Two-Event Special Case
For a single partitioning event $B$ and its complement $B^c$:
$$P(A) = P(B)P(A \mid B) + P(B^c)P(A \mid B^c)$$

---

## 3. Concept Check Walkthroughs

### Concept Check 1
**Question:** Let $B$ be an event with $P(B) = 0.40$. If $P(A \mid B) = 0.70$ and $P(A \mid B^c) = 0.20$, calculate $P(A)$ using the Law of Total Probability.

**Walkthrough:**
1. **Identify Partition & Complement:**  
   $P(B) = 0.40 \implies P(B^c) = 1 - 0.40 = 0.60$.
2. **Apply Two-Event LTP:**  
   $$P(A) = P(B)P(A \mid B) + P(B^c)P(A \mid B^c)$$
3. **Compute:**  
   $$P(A) = (0.40)(0.70) + (0.60)(0.20) = 0.28 + 0.12 = \mathbf{0.40}$$

---

### Concept Check 2
**Question:** An insurer classifies property policies into Residential ($60\%$) and Commercial ($40\%$). The probability of a storm loss is $0.08$ for Residential policies and $0.15$ for Commercial policies. What is the total probability that a policy incurs a storm loss?

**Walkthrough:**
1. **Define Events:**  
   $R$ = Residential ($P(R) = 0.60$), $C$ = Commercial ($P(C) = 0.40$).  
   $L$ = Storm Loss. $P(L \mid R) = 0.08$, $P(L \mid C) = 0.15$.
2. **Apply LTP:**  
   $$P(L) = P(R)P(L \mid R) + P(C)P(L \mid C)$$
3. **Compute:**  
   $$P(L) = (0.60)(0.08) + (0.40)(0.15) = 0.048 + 0.060 = \mathbf{0.108} \text{ (10.8\%)}$$

---

### Concept Check 3
**Question:** True or False? The events $E_1, E_2, E_3$ form a valid partition of sample space $S$ if $P(E_1) = 0.40$, $P(E_2) = 0.35$, $P(E_3) = 0.25$, and $P(E_1 \cap E_2) = 0.05$.

**Walkthrough:**
1. **Check Requirements:** A partition requires events to be mutually exclusive ($P(E_i \cap E_j) = 0$ for $i \neq j$).
2. **Test:** Here, $P(E_1 \cap E_2) = 0.05 \neq 0$.
3. **Conclusion:** Because $E_1$ and $E_2$ overlap, they are not mutually exclusive.  
   **Answer:** **False**

---

## 4. Day 9 Practice Problem Set & Walkthroughs

### Problem 1
**Scenario:** An insurance company categorizes its policyholders into Young ($Y$) and Mature ($M$). Young drivers make up $30\%$ of policyholders ($P(Y) = 0.30$).
* $P(\text{Claim} \mid Y) = 0.20$
* $P(\text{Claim} \mid M) = 0.05$

**Question:** Calculate $P(C)$, the overall probability a randomly chosen policyholder files a claim.

**Solution:**
1. $P(M) = 1 - P(Y) = 1 - 0.30 = 0.70$.
2. Apply LTP:
   $$P(C) = P(Y)P(C \mid Y) + P(M)P(C \mid M)$$
   $$P(C) = (0.30)(0.20) + (0.70)(0.05) = 0.060 + 0.035 = \mathbf{0.095} \text{ (9.5\%)}$$

---

### Problem 2
**Scenario:** A property portfolio has three risk tiers: Low Risk ($B_1$, $50\%$), Moderate Risk ($B_2$, $35\%$), and High Risk ($B_3$, $15\%$).
* $P(L \mid B_1) = 0.02$
* $P(L \mid B_2) = 0.08$
* $P(L \mid B_3) = 0.24$

**Question:** Calculate $P(L)$, the overall probability a policy incurs a property loss.

**Solution:**
1. Verify partition: $0.50 + 0.35 + 0.15 = 1.00$.
2. Apply General LTP:
   $$P(L) = P(B_1)P(L \mid B_1) + P(B_2)P(L \mid B_2) + P(B_3)P(L \mid B_3)$$
   $$P(L) = (0.50)(0.02) + (0.35)(0.08) + (0.15)(0.24)$$
   $$P(L) = 0.010 + 0.028 + 0.036 = \mathbf{0.074} \text{ (7.4\%)}$$

---

### Problem 3
**Scenario:** An actuary models disability claims:
1. $P(\text{Injury } I) = 0.12$.
2. $P(\text{Disability } D \mid I) = 0.25$.
3. $P(\text{Disability } D \mid I^c) = 0.03$.

**Question:** Calculate the unconditional probability of a disability claim ($P(D)$).

**Solution:**
1. $P(I^c) = 1 - 0.12 = 0.88$.
2. Apply Two-Event LTP:
   $$P(D) = P(I)P(D \mid I) + P(I^c)P(D \mid I^c)$$
   $$P(D) = (0.12)(0.25) + (0.88)(0.03)$$
   $$P(D) = 0.030 + 0.0264 = \mathbf{0.0564} \text{ (5.64\%)}$$

---

### Problem 4
**Scenario:** Claims arrive from Center A ($40\%$), Center B ($35\%$), and Center C ($25\%$).
* $P(\text{Error } E \mid A) = 0.05$
* $P(\text{Error } E \mid B) = 0.08$
* $P(\text{Error } E \mid C) = 0.12$

**Questions:**
1. Calculate $P(E)$, the overall probability of a claim having an administrative error.
2. Calculate $P(E^c)$, the probability a claim is error-free.

**Solution:**
1. **Part 1:**
   $$P(E) = P(A)P(E \mid A) + P(B)P(E \mid B) + P(C)P(E \mid C)$$
   $$P(E) = (0.40)(0.05) + (0.35)(0.08) + (0.25)(0.12)$$
   $$P(E) = 0.020 + 0.028 + 0.030 = \mathbf{0.078} \text{ (7.8\%)}$$
2. **Part 2:**
   $$P(E^c) = 1 - P(E) = 1 - 0.078 = \mathbf{0.922} \text{ (92.2\%)}$$

---

## 5. Day 9 Formula Summary

| Concept | Formula | Notes |
| :--- | :--- | :--- |
| **Partition Conditions** | $B_i \cap B_j = \varnothing$, $\bigcup B_i = S$ | Mutually exclusive & collectively exhaustive |
| **Law of Total Probability (General)** | $P(A) = \sum_{i=1}^{k} P(B_i)P(A \mid B_i)$ | Unconditional probability across $k$ partition tiers |
| **Law of Total Probability (2 Events)** | $P(A) = P(B)P(A \mid B) + P(B^c)P(A \mid B^c)$ | Standard binary partition using complement |
