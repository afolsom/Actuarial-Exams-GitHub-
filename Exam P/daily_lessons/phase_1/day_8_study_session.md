# Day 8 Study Session: Conditional Probability (Session 1F.1)
**Exam P (Probability) — SOA Objective 1f**

---

## 1. Executive Summary & Learning Objectives

Conditional probability allows us to recalculate and update the probability of an event when new or partial information becomes known. This session covers the formal definition of conditional probability, its properties under independence and mutual exclusivity, set-partitioning rules, and reduced sample space applications to actuarial risk classification.

### **Core Objectives:**
1. Define and compute **Conditional Probability** $P(A \mid B)$ when the sample space is restricted to event $B$.
2. Calculate conditional probabilities using **Venn diagrams, contingency tables, and discrete sample spaces**.
3. Understand and apply the **Conditional Complement Rule** and conditional rules under **Independence**.
4. Solve actuarial conditional probability problems involving policyholder classifications, risk tiers, and claim events.

---

## 2. Core Theoretical Principles & Formulas

### **2.1 Definition of Conditional Probability**
Let $A$ and $B$ be two events in a sample space $S$ such that $P(B) > 0$. The **conditional probability of event $A$ given that event $B$ has occurred**, denoted by $P(A \mid B)$, is defined as:

$$P(A \mid B) = \frac{P(A \cap B)}{P(B)}$$

*   **Sample Space Reduction:** Prior to knowing whether $B$ occurred, the total outcome space is $S$ with $P(S) = 1$. Once $B$ has occurred, $B$ becomes the new reduced sample space. The only outcomes in $A$ that can now occur are those lying within $A \cap B$.

---

### **2.2 Rearranged Forms & Key Properties**

1. **Joint Probability (General Multiplication Rule):**
   $$P(A \cap B) = P(B) \cdot P(A \mid B) = P(A) \cdot P(B \mid A)$$

2. **Conditional Complement Rule:**
   $$P(A^c \mid B) = 1 - P(A \mid B)$$

3. **Conditioning Under Independence:**
   If events $A$ and $B$ are independent ($P(A \cap B) = P(A)P(B)$):
   $$P(A \mid B) = \frac{P(A)P(B)}{P(B)} = P(A)$$
   $$P(B \mid A) = \frac{P(A)P(B)}{P(A)} = P(B)$$

4. **Conditioning Under Mutual Exclusivity:**
   If events $A$ and $B$ are mutually exclusive ($A \cap B = \varnothing \implies P(A \cap B) = 0$):
   $$P(A \mid B) = \frac{0}{P(B)} = 0 \quad (\text{for } P(B) > 0)$$

---

## 3. Actuarial Application Example

### **Scenario:**
An insurer categorizes 100 auto policyholders by age and claim history over the past year:

| Age Group | Filed Claim ($C$) | No Claim ($C^c$) | Total |
| :--- | :--- | :--- | :--- |
| **Young Driver ($Y$)** | 15 | 25 | 40 |
| **Mature Driver ($Y^c$)** | 10 | 50 | 60 |
| **Total** | 25 | 75 | 100 |

### **Questions & Walkthrough:**

1. **Find $P(C \mid Y)$ (Probability of a claim given young driver status):**
   $$P(C \mid Y) = \frac{N(C \cap Y)}{N(Y)} = \frac{15}{40} = 0.375$$

2. **Find $P(Y \mid C)$ (Probability of young driver status given a claim was filed):**
   $$P(Y \mid C) = \frac{N(Y \cap C)}{N(C)} = \frac{15}{25} = 0.60$$

---

## 4. Concept Check Questions & Walkthroughs

### **Question 1**
* **Prompt:** Given $P(A \mid B) = 0.4$ and $P(B \mid A) = 0.5$, express the relationship between $P(A)$ and $P(B)$.
* **Walkthrough:**
  $$P(A \cap B) = P(B) \cdot P(A \mid B) = P(A) \cdot P(B \mid A)$$
  $$P(B) \cdot (0.4) = P(A) \cdot (0.5) \implies P(A) = 0.8 \cdot P(B)$$

---

### **Question 2**
* **Prompt:** True or False? For any two events $A$ and $B$ with $P(A) > 0$ and $P(B) > 0$, $P(A \mid B)$ is always equal to $P(B \mid A)$.
* **Walkthrough:** **False**. By definition:
  $$P(A \mid B) = \frac{P(A \cap B)}{P(B)} \quad \text{and} \quad P(B \mid A) = \frac{P(A \cap B)}{P(A)}$$
  These two expressions are equal if and only if $P(A) = P(B)$ (assuming $P(A \cap B) > 0$).

---

### **Question 3**
* **Prompt:** An actuary knows that $60\%$ of policyholders have Auto coverage ($A$), $40\%$ have Home coverage ($H$), and $25\%$ have both $A$ and $H$. Calculate $P(H \mid A^c)$.
* **Walkthrough:**
  1. Apply conditional probability definition:
     $$P(H \mid A^c) = \frac{P(H \cap A^c)}{P(A^c)}$$
  2. Denominator $P(A^c) = 1 - P(A) = 1 - 0.60 = 0.40$.
  3. Numerator $P(H \cap A^c) = P(H) - P(A \cap H) = 0.40 - 0.25 = 0.15$.
  4. Evaluate:
     $$P(H \mid A^c) = \frac{0.15}{0.40} = 0.375$$

---

## 5. Day 8 Practice Problem Set & Full Solutions

### **Problem 1: Restricted Sample Space & Reduced Probability**
An underwriter reviews a group of 200 commercial liability policies categorized by risk level and claim history:

| Risk Level | Claim Filed ($C$) | No Claim Filed ($C^c$) | Total |
| :--- | :--- | :--- | :--- |
| **High Risk ($H$)** | 45 | 15 | 60 |
| **Low Risk ($H^c$)** | 20 | 120 | 140 |
| **Total** | 65 | 135 | 200 |

1. Calculate $P(C \mid H)$:
   $$P(C \mid H) = \frac{45}{60} = \mathbf{0.75}$$
2. Calculate $P(H \mid C)$:
   $$P(H \mid C) = \frac{45}{65} = \frac{9}{13} \approx \mathbf{0.69}$$
3. Calculate $P(H^c \mid C^c)$:
   $$P(H^c \mid C^c) = \frac{120}{135} = \frac{8}{9} \approx \mathbf{0.89}$$

---

### **Problem 2: Conditional Complement & Set Properties**
An auto insurance company determines that among its policyholders:
* $50\%$ have collision coverage ($C$)
* $35\%$ have comprehensive coverage ($K$)
* $20\%$ have both collision and comprehensive coverage ($C \cap K$)

1. Calculate $P(K \mid C)$:
   $$P(K \mid C) = \frac{P(K \cap C)}{P(C)} = \frac{0.20}{0.50} = \mathbf{0.40}$$
2. Calculate $P(K^c \mid C)$:
   $$P(K^c \mid C) = 1 - P(K \mid C) = 1 - 0.40 = \mathbf{0.60}$$
3. Calculate $P(K \mid C^c)$:
   $$P(K \cap C^c) = P(K) - P(K \cap C) = 0.35 - 0.20 = 0.15$$
   $$P(C^c) = 1 - P(C) = 1 - 0.50 = 0.50$$
   $$P(K \mid C^c) = \frac{0.15}{0.50} = \mathbf{0.30}$$

---

### **Problem 3: Independent vs. Mutually Exclusive Events**
Let $A$ and $B$ be two events with $P(A) = 0.40$ and $P(B) = 0.25$.

1. If $A$ and $B$ are **independent**:
   $$P(A \mid B) = P(A) = \mathbf{0.40}$$
   $$P(A \mid B^c) = P(A) = \mathbf{0.40}$$
2. If $A$ and $B$ are **mutually exclusive (disjoint)**:
   $$P(A \cap B) = 0 \implies P(A \mid B) = \frac{0}{0.25} = \mathbf{0.0}$$

---

### **Problem 4: Sequential Claim Audit (Sampling Without Replacement)**
A folder contains 15 claim files: 9 Auto claims and 6 Health claims. Two files are drawn sequentially without replacement.

1. Conditional probability that the second file drawn is Health given first is Auto ($P(H_2 \mid A_1)$):
   $$P(H_2 \mid A_1) = \frac{6}{14} = \frac{3}{7} \approx \mathbf{0.4286}$$
2. Joint probability that the first file is Auto and second file is Health ($P(A_1 \cap H_2)$):
   $$P(A_1 \cap H_2) = P(A_1) \cdot P(H_2 \mid A_1) = \frac{9}{15} \times \frac{6}{14} = \frac{54}{210} = \frac{9}{35} \approx \mathbf{0.2571}$$

---

## 6. Day 8 Formula Reference Cheat Sheet

| Formula Name | Equation | Verbal Description |
| :--- | :--- | :--- |
| **Conditional Probability Definition** | $P(A \mid B) = \frac{P(A \cap B)}{P(B)}$ | The likelihood of event $A$ occurring given that event $B$ has already occurred. |
| **Joint Probability / General Multiplication Rule** | $P(A \cap B) = P(B) \cdot P(A \mid B)$ | The joint probability of two events equals the probability of the condition times the conditional probability of the target event. |
| **Conditional Complement Rule** | $P(A^c \mid B) = 1 - P(A \mid B)$ | Given event $B$, the conditional probability of $A^c$ is one minus the conditional probability of $A$. |
| **Independence Conditional Property** | $P(A \mid B) = P(A)$ | If two events are independent, knowing that one occurred provides zero new information about the other. |
| **Disjoint Conditional Property** | $P(A \mid B) = 0$ | If two events are mutually exclusive, the occurrence of one guarantees the non-occurrence of the other. |