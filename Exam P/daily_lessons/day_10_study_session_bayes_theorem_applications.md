# Day 10 Study Session: Bayes' Theorem Applications & Probability Tree Diagrams
**Course:** Actuarial Exam P  
**Module:** Phase 1 — General Probability (SOA Objective 1g)  
**Session Code:** Session 1G.2  

---

## 1. Overview & Learning Objectives

Building directly on the Law of Total Probability from Day 9, **Bayes' Theorem** provides a mathematical framework for updating the probability of an underlying cause or state of nature (hypothesis) after observing new evidence or events.

By the end of this session, you should be able to:
1. State and derive **Bayes' Theorem** using conditional probability and the Law of Total Probability.
2. Identify **prior probabilities** $P(B_i)$, **likelihoods** $P(A \mid B_i)$, and compute **posterior probabilities** $P(B_i \mid A)$.
3. Construct and analyze **Probability Tree Diagrams** to organize multi-stage conditional risk structures.
4. Solve actuarial diagnostic testing, policyholder classification, and inverse probability problems.

---

## 2. Theoretical Foundations

### 2.1 Bayes' Theorem Definition
Let $\{B_1, B_2, \dots, B_k\}$ be a formal partition of the sample space $S$ with $P(B_i) > 0$ for all $i$. For any observed event $A$ such that $P(A) > 0$, the **posterior probability** of a specific partition piece $B_j$ given that event $A$ has occurred is:

$$P(B_j \mid A) = \frac{P(B_j \cap A)}{P(A)} = \frac{P(B_j)P(A \mid B_j)}{\sum_{i=1}^{k} P(B_i)P(A \mid B_i)}$$

### 2.2 Terminology Breakdown
* **Prior Probability ($P(B_j)$):** The baseline probability of event $B_j$ before observing new evidence $A$.
* **Likelihood ($P(A \mid B_j)$):** The probability of observing evidence $A$ assuming event $B_j$ is true.
* **Marginal Probability of Evidence ($P(A)$):** The overall unconditional probability of event $A$, computed via the Law of Total Probability across all partition pieces.
* **Posterior Probability ($P(B_j \mid A)$):** The updated probability of event $B_j$ after taking into account the occurrence of event $A$.

### 2.3 Two-Event Special Case
For a single event $B$ and its complement $B^c$:

$$P(B \mid A) = \frac{P(B)P(A \mid B)}{P(B)P(A \mid B) + P(B^c)P(A \mid B^c)}$$

---

## 3. Probability Tree Diagram Architecture

Tree diagrams structure complex conditional probability problems visually:
1. **First-Level Branches:** Represent the prior probabilities of the partition classes $P(B_i)$.
2. **Second-Level Branches:** Represent the conditional probabilities (likelihoods) $P(A \mid B_i)$.
3. **Path Products:** Multiplying probabilities along a path from root to node gives the joint probability of that specific pathway:
   $$P(B_i \cap A) = P(B_i) \cdot P(A \mid B_i)$$
4. **Sum of Paths:** Summing the joint probabilities across all paths terminating in event $A$ yields $P(A)$.
5. **Bayes' Posterior Fraction:**
   $$P(B_j \mid A) = \frac{\text{Path Product for } B_j \cap A}{\text{Sum of all Path Products for } A}$$

---

## 4. Concept Check Walkthroughs

### Concept Check 1
**Question:** Given $P(B) = 0.30$, $P(A \mid B) = 0.80$, and $P(A \mid B^c) = 0.20$. Calculate $P(B \mid A)$.

**Solution:**
1. Find complement prior: $P(B^c) = 1 - P(B) = 1 - 0.30 = 0.70$.
2. Compute joint probabilities:
   * $P(B \cap A) = P(B)P(A \mid B) = (0.30)(0.80) = 0.24$
   * $P(B^c \cap A) = P(B^c)P(A \mid B^c) = (0.70)(0.20) = 0.14$
3. Compute marginal probability $P(A)$ using the Law of Total Probability:
   $$P(A) = P(B \cap A) + P(B^c \cap A) = 0.24 + 0.14 = 0.38$$
4. Apply Bayes' Theorem:
   $$P(B \mid A) = \frac{P(B \cap A)}{P(A)} = \frac{0.24}{0.38} = \frac{12}{19} \approx 0.6316$$

---

### Concept Check 2
**Question:** An insurer finds that 70% of drivers are safe ($S$) and 30% are risky ($R$). Safe drivers have a 5% chance of an accident ($A$), while risky drivers have a 25% chance of an accident. Given that a driver had an accident, calculate $P(S \mid A)$.

**Solution:**
1. Set up priors and likelihoods:
   * $P(S) = 0.70$, $P(R) = 0.30$
   * $P(A \mid S) = 0.05$, $P(A \mid R) = 0.25$
2. Compute joint probabilities:
   * $P(S \cap A) = (0.70)(0.05) = 0.035$
   * $P(R \cap A) = (0.30)(0.25) = 0.075$
3. Compute total accident probability:
   $$P(A) = 0.035 + 0.075 = 0.110$$
4. Calculate posterior probability:
   $$P(S \mid A) = \frac{0.035}{0.110} = \frac{7}{22} \approx 0.3182$$

---

### Concept Check 3
**Question:** True or False? The sum of all posterior probabilities across a partition given an event $A$, $\sum_{i=1}^{k} P(B_i \mid A)$, must equal 1. Explain briefly.

**Solution:**
* **Verdict:** **True**
* **Explanation:** Conditioning on event $A$ restricts the sample space to $A$. Since $\{B_1, B_2, \dots, B_k\}$ forms a partition of the total sample space $S$, the subsets $\{B_1 \cap A, B_2 \cap A, \dots, B_k \cap A\}$ form a partition of $A$. Summing their conditional probabilities gives:
  $$\sum_{i=1}^{k} P(B_i \mid A) = \frac{\sum_{i=1}^{k} P(B_i \cap A)}{P(A)} = \frac{P(A)}{P(A)} = 1$$

---

## 5. Practice Problem Set & Full Solutions

### Problem 1 (Diagnostic Medical / Claim Testing)
**Problem:** An insurer uses a screening test to detect fraudulent disability claims ($F$).
* $P(F) = 0.04$
* $P(+ \mid F) = 0.95$ (Sensitivity)
* $P(+ \mid F^c) = 0.03$ (False Positive Rate)

Calculate the posterior probability that a claim is fraudulent given a positive test result, $P(F \mid +)$.

**Full Solution:**
1. $P(F^c) = 1 - 0.04 = 0.96$.
2. Joint probabilities:
   * $P(F \cap +) = (0.04)(0.95) = 0.0380$
   * $P(F^c \cap +) = (0.96)(0.03) = 0.0288$
3. Total positive probability $P(+)$:
   $$P(+) = 0.0380 + 0.0288 = 0.0668$$
4. Apply Bayes' Theorem:
   $$P(F \mid +) = \frac{0.0380}{0.0668} = \mathbf{\frac{95}{167}} \approx \mathbf{0.5689}$$

---

### Problem 2 (Policyholder Risk Reclassification)
**Problem:** Drivers are classified as Low Risk ($B_1$, 50%), Moderate Risk ($B_2$, 35%), or High Risk ($B_3$, 15%). Collision claim probabilities ($C$) per tier are:
* $P(C \mid B_1) = 0.04$
* $P(C \mid B_2) = 0.10$
* $P(C \mid B_3) = 0.30$

1. Calculate the overall claim probability $P(C)$.
2. Given that a driver filed a claim, calculate $P(B_2 \mid C)$.

**Full Solution:**
1. **Part 1 (Overall Probability $P(C)$):**
   $$P(C) = P(B_1)P(C \mid B_1) + P(B_2)P(C \mid B_2) + P(B_3)P(C \mid B_3)$$
   $$P(C) = (0.50)(0.04) + (0.35)(0.10) + (0.15)(0.30) = 0.020 + 0.035 + 0.045 = \mathbf{0.100} \text{ (or } 10\%\text{)}$$

2. **Part 2 (Posterior $P(B_2 \mid C)$):**
   $$P(B_2 \mid C) = \frac{P(B_2 \cap C)}{P(C)} = \frac{0.035}{0.100} = \mathbf{0.35}$$

---

### Problem 3 (Two-Stage Sequential Audit)
**Problem:** Office A processes 60% of claim files ($P(A) = 0.60$), and Office B processes 40% ($P(B) = 0.40$).
* $P(E \mid A) = 0.05$ (Error probability for Office A)
* $P(E \mid B) = 0.10$ (Error probability for Office B)

Calculate the probability that a selected file found to be **error-free** ($E^c$) originated from Office A, $P(A \mid E^c)$.

**Full Solution:**
1. Find conditional error-free probabilities:
   * $P(E^c \mid A) = 1 - 0.05 = 0.95$
   * $P(E^c \mid B) = 1 - 0.10 = 0.90$
2. Joint error-free probabilities:
   * $P(A \cap E^c) = (0.60)(0.95) = 0.570$
   * $P(B \cap E^c) = (0.40)(0.90) = 0.360$
3. Total error-free probability $P(E^c)$:
   $$P(E^c) = 0.570 + 0.360 = 0.930$$
4. Apply Bayes' Theorem:
   $$P(A \mid E^c) = \frac{P(A \cap E^c)}{P(E^c)} = \frac{0.570}{0.930} = \mathbf{\frac{19}{31}} \approx \mathbf{0.6129}$$

---

### Problem 4 (Multi-Level Conditional Risk Classification)
**Problem:** Applicants are Smokers ($S$, 20%) or Non-Smokers ($S^c$, 80%). 5-year condition ($H$) probabilities are:
* $P(H \mid S) = 0.25$
* $P(H \mid S^c) = 0.05$

Given that a policyholder developed condition $H$, calculate $P(S^c \mid H)$.

**Full Solution:**
1. Joint probabilities:
   * $P(S \cap H) = (0.20)(0.25) = 0.050$
   * $P(S^c \cap H) = (0.80)(0.05) = 0.040$
2. Total condition probability $P(H)$:
   $$P(H) = 0.050 + 0.040 = 0.090$$
3. Apply Bayes' Theorem:
   $$P(S^c \mid H) = \frac{P(S^c \cap H)}{P(H)} = \frac{0.040}{0.090} = \mathbf{\frac{4}{9}} \approx \mathbf{0.4444}$$

---

## 6. Day 10 Formula Reference Cheat Sheet

| Formula Name | Mathematical Expression | Verbal Description / Context |
| :--- | :--- | :--- |
| **Bayes' Theorem (General)** | $P(B_j \mid A) = \frac{P(B_j)P(A \mid B_j)}{\sum_{i=1}^k P(B_i)P(A \mid B_i)}$ | Posterior probability of partition $B_j$ given event $A$ equals joint probability divided by total probability of $A$. |
| **Bayes' Theorem (Two Events)** | $P(B \mid A) = \frac{P(B)P(A \mid B)}{P(B)P(A \mid B) + P(B^c)P(A \mid B^c)}$ | Posterior probability for a binary partition $B$ and $B^c$. |
| **Path Product (Joint Prob.)** | $P(B_i \cap A) = P(B_i) \cdot P(A \mid B_i)$ | Probability along a specific branch sequence in a probability tree diagram. |
| **Posterior Sum Axiom** | $\sum_{i=1}^k P(B_i \mid A) = 1$ | The sum of all posterior probabilities across a partition given event $A$ must equal $1$. |
