# Day 7 Study Session (Session 1E.1)
## Multiplication Rules and Complex Multi-Step Probability Calculations

---

### **1. Session Overview & Learning Objectives**
This session focuses on **SOA Objective 1e: Multiplication Rules and Multi-Step Probability Calculations**. It builds upon prior set theory, combinatorics, addition rules, and independence to analyze sequential processes and conditional probability pathways.

#### **Learning Objectives**
1. Apply the **General Multiplication Rule** to calculate joint probabilities for dependent sequential events.
2. Extend the multiplication rule to $n$ sequential steps using the **Chain Rule of Probability**.
3. Distinguish between sequential sampling **with replacement** (independent stages) and **without replacement** (dependent stages).
4. Solve **complex multi-step probability calculations** by decomposing multi-stage outcomes into mutually exclusive pathways using multiplication and addition rules.

---

### **2. Core Theoretical Concepts**

#### **A. The General Multiplication Rule**
For any two events $A$ and $B$ defined on a sample space $S$, the probability that both events occur is given by:

$$P(A \cap B) = P(A) \cdot P(B \mid A)$$

Equivalently, if event $B$ is considered first:

$$P(A \cap B) = P(B) \cdot P(A \mid B)$$

* **Independence Special Case:** If $A$ and $B$ are independent events, then $P(B \mid A) = P(B)$, which simplifies the formula to:

$$P(A \cap B) = P(A) \cdot P(B)$$

---

#### **B. The Chain Rule for $n$ Sequential Events**
When an experiment consists of a sequence of $n$ consecutive events ($A_1, A_2, \dots, A_n$), the joint probability that all $n$ events occur is obtained by multiplying conditional probabilities across each stage:

$$P(A_1 \cap A_2 \cap \dots \cap A_n) = P(A_1) \cdot P(A_2 \mid A_1) \cdot P(A_3 \mid A_1 \cap A_2) \cdots P(A_n \mid A_1 \cap A_2 \cap \dots \cap A_{n-1})$$

---

#### **C. Sampling With Replacement vs. Without Replacement**

| Feature | Sampling With Replacement | Sampling Without Replacement |
| :--- | :--- | :--- |
| **Stage Dependence** | Stages are **independent** | Stages are **dependent** |
| **Probabilities** | Constant across draws | Change dynamically after each draw |
| **Calculation Method** | Constant product: $P(A)^k$ | Sequential Chain Rule / Combinatorics |

---

#### **D. Multi-Step Probability Pathways**
When an overall event $E$ can occur through multiple distinct sequence paths:
1. **Multiply along each pathway:** Use the General Multiplication Rule (or Chain Rule) to calculate the joint probability for that specific sequence.
2. **Add across different pathways:** Because distinct sequence paths are **mutually exclusive**, use the Addition Rule to sum the path probabilities:

$$P(E) = P(\text{Path 1}) + P(\text{Path 2}) + \dots + P(\text{Path } k)$$

---

### **3. Actuarial Application Example**

#### **Scenario**
An insurer has a pool of 10 claim files: 6 high-risk claims and 4 low-risk claims. An auditor selects 3 claim files sequentially at random **without replacement**.

#### **Question**
What is the probability that the auditor selects a high-risk claim on the 1st draw, a low-risk claim on the 2nd draw, and a high-risk claim on the 3rd draw?

#### **Solution Walkthrough**
1. **Define Events:**
   * $H_1$: High-risk claim on 1st draw
   * $L_2$: Low-risk claim on 2nd draw
   * $H_3$: High-risk claim on 3rd draw

2. **Apply the Chain Rule:**
   $$P(H_1 \cap L_2 \cap H_3) = P(H_1) \cdot P(L_2 \mid H_1) \cdot P(H_3 \mid H_1 \cap L_2)$$

3. **Calculate Sequential Probabilities:**
   * $P(H_1) = \frac{6}{10}$
   * $P(L_2 \mid H_1) = \frac{4}{9}$ (9 files remain, 4 low-risk)
   * $P(H_3 \mid H_1 \cap L_2) = \frac{5}{8}$ (8 files remain, 5 high-risk)

4. **Compute Joint Probability:**
   $$P(H_1 \cap L_2 \cap H_3) = \frac{6}{10} \times \frac{4}{9} \times \frac{5}{8} = \frac{120}{720} = \frac{1}{6} \approx 0.1667$$

---

### **4. Concept Check Questions & Solutions**

#### **Concept Check 1**
* **Question:** A box contains 5 red files and 3 blue files. Two files are drawn sequentially **without replacement**. Calculate the probability that both files drawn are red.
* **Solution:**
  * First draw: $P(R_1) = \frac{5}{8}$
  * Second draw: $P(R_2 \mid R_1) = \frac{4}{7}$
  * Joint Probability: $P(R_1 \cap R_2) = \frac{5}{8} \times \frac{4}{7} = \frac{20}{56} = \frac{5}{14} \approx 0.3571$

#### **Concept Check 2**
* **Question:** An underwriter reviews 3 independent policy applications. The probability of approving each application is $0.70$, $0.80$, and $0.90$, respectively. Calculate the probability that the underwriter approves all three applications.
* **Solution:**
  * Since reviews are independent:
    $$P(A_1 \cap A_2 \cap A_3) = P(A_1) \cdot P(A_2) \cdot P(A_3) = 0.70 \times 0.80 \times 0.90 = 0.504$$

#### **Concept Check 3**
* **Question:** An auto insurer classifies a policy processing system into two stages. There is a $0.20$ probability that Stage 1 triggers a manual review ($R_1$). If Stage 1 triggers a manual review, the probability that Stage 2 requires an audit ($A_2$) is $0.65$. If Stage 1 does not trigger a manual review, the probability that Stage 2 requires an audit is $0.10$. Calculate the overall probability that a policy requires an audit at Stage 2.
* **Solution:**
  * $P(R_1) = 0.20 \implies P(R_1^c) = 0.80$
  * $P(A_2 \mid R_1) = 0.65$
  * $P(A_2 \mid R_1^c) = 0.10$
  * Apply Law of Total Probability / Pathway Decomposition:
    $$P(A_2) = P(R_1 \cap A_2) + P(R_1^c \cap A_2)$$
    $$P(A_2) = P(R_1) \cdot P(A_2 \mid R_1) + P(R_1^c) \cdot P(A_2 \mid R_1^c)$$
    $$P(A_2) = (0.20 \times 0.65) + (0.80 \times 0.10) = 0.13 + 0.08 = 0.21$$

---

### **5. Day 7 Practice Problem Set & Full Solutions**

#### **Problem 1**
An auditor reviews a portfolio of 12 insurance claim files containing 5 high-risk claims and 7 low-risk claims. Three claim files are selected sequentially at random **without replacement**. Calculate the probability that the auditor selects a high-risk claim on the 1st draw, a low-risk claim on the 2nd draw, and a high-risk claim on the 3rd draw.

* **Solution:**
  1. $P(H_1) = \frac{5}{12}$
  2. $P(L_2 \mid H_1) = \frac{7}{11}$
  3. $P(H_3 \mid H_1 \cap L_2) = \frac{4}{10}$
  4. Chain Rule:
     $$P(H_1 \cap L_2 \cap H_3) = \frac{5}{12} \times \frac{7}{11} \times \frac{4}{10} = \frac{140}{1320} = \frac{7}{66} \approx 0.10606$$

---

#### **Problem 2**
A commercial risk assessment process requires a building to pass three sequential inspection stages ($S_1, S_2, S_3$) to receive an operational insurance certificate:
* $P(S_1) = 0.80$
* $P(S_2 \mid S_1) = 0.75$
* $P(S_3 \mid S_1 \cap S_2) = 0.90$

Calculate the probability that a building successfully passes all three inspection stages.

* **Solution:**
  1. Chain Rule for sequential conditional stages:
     $$P(S_1 \cap S_2 \cap S_3) = P(S_1) \cdot P(S_2 \mid S_1) \cdot P(S_3 \mid S_1 \cap S_2)$$
  2. Arithmetic:
     $$P(S_1 \cap S_2 \cap S_3) = 0.80 \times 0.75 \times 0.90 = 0.60 \times 0.90 = 0.54$$

---

#### **Problem 3**
An online auto insurance portal evaluates applicant risk in a two-stage screening process:
* There is a $0.30$ probability that an applicant is classified as "High Risk" ($H$) at Stage 1.
* If classified as "High Risk", the probability of requiring a comprehensive audit ($A$) at Stage 2 is $0.70$.
* If NOT classified as "High Risk" ($H^c$), the probability of requiring a comprehensive audit ($A$) at Stage 2 is $0.15$.

Calculate the overall probability that an applicant's claim application requires a comprehensive audit at Stage 2.

* **Solution:**
  1. Identify Given Probabilities:
     * $P(H) = 0.30 \implies P(H^c) = 0.70$
     * $P(A \mid H) = 0.70$
     * $P(A \mid H^c) = 0.15$
  2. Decompose into Mutually Exclusive Pathways:
     * Pathway 1: $P(H \cap A) = 0.30 \times 0.70 = 0.210$
     * Pathway 2: $P(H^c \cap A) = 0.70 \times 0.15 = 0.105$
  3. Sum Across Pathways:
     $$P(A) = 0.210 + 0.105 = 0.315$$

---

#### **Problem 4**
A box contains 6 red claim files and 4 blue claim files. Two claim files are selected sequentially at random **without replacement**. Calculate the probability that the two selected claim files are of **different colors** (one red and one blue, in either order).

* **Solution:**
  1. Identify Pathways for Different Colors:
     * Pathway 1 ($R_1 \cap B_2$): Red first, Blue second
     * Pathway 2 ($B_1 \cap R_2$): Blue first, Red second
  2. Calculate Joint Probabilities:
     * $P(R_1 \cap B_2) = \frac{6}{10} \times \frac{4}{9} = \frac{24}{90}$
     * $P(B_1 \cap R_2) = \frac{4}{10} \times \frac{6}{9} = \frac{24}{90}$
  3. Sum Mutually Exclusive Pathways:
     $$P(\text{Different Colors}) = \frac{24}{90} + \frac{24}{90} = \frac{48}{90} = \frac{8}{15} \approx 0.5333$$

---

### **6. Day 7 Formula Cheat Sheet**

| Formula Name | Mathematical Expression | Verbal Description |
| :--- | :--- | :--- |
| **General Multiplication Rule** | $P(A \cap B) = P(A) \cdot P(B \mid A)$ | Probability of two dependent events occurring is the first event's probability times the conditional probability of the second given the first. |
| **Independent Multiplication Rule** | $P(A \cap B) = P(A) \cdot P(B)$ | Joint probability of independent events is the simple product of their individual probabilities. |
| **Sequential Chain Rule** | $P(\bigcap_{i=1}^n A_i) = P(A_1) \cdot P(A_2 \mid A_1) \cdots P(A_n \mid \bigcap_{j=1}^{n-1} A_j)$ | Product of conditional probabilities across $n$ sequential stages. |
| **Multi-Step Pathway Decomposition** | $P(E) = \sum_{k} P(\text{Path}_k)$ | Sum of joint probabilities across mutually exclusive sequential pathways that yield event $E$. |