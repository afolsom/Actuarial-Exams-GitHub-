# Actuarial Exam P — Day 2 Study Session (Session 1A.2)
## Topic: Probability as a Set Function & Kolmogorov's Axioms

---

## 1. Guided Learning & Core Objectives

### **Learning Objectives**
By the end of this session, you will be able to:
1. Understand **probability as a set function** mapping subsets of a sample space to real numbers.
2. State and explain **Kolmogorov’s Three Axioms of Probability**.
3. Derive and apply fundamental probability rules directly from the axioms, including the **Complement Rule**, **Empty Set Property**, **Difference Rule**, and **Monotonicity**.
4. Translate actuarial statements into probability inequalities and exact calculations.

---

### **Core Concepts**

#### **1. Probability as a Set Function**
In standard calculus, $f(x)$ maps numbers to numbers. In probability theory, **probability $P$ is a set function**:
* **Domain:** Collection of events (subsets of the sample space $S$).
* **Range:** Real number interval $[0, 1]$.
* For every event $A \subseteq S$, $P(A)$ assigns a real number representing the likelihood that an outcome $\omega \in A$ occurs.

---

#### **2. Kolmogorov's Three Axioms of Probability**
All of probability theory rests on three foundational rules:

1. **Axiom 1 (Non-negativity):**  
   $$P(A) \ge 0 \quad \text{for every event } A$$

2. **Axiom 2 (Normalization / Certainty):**  
   $$P(S) = 1 \quad \text{where } S \text{ is the sample space}$$

3. **Axiom 3 (Countable Additivity):**  
   If $A_1, A_2, A_3, \dots$ is a sequence of mutually exclusive (disjoint) events ($A_i \cap A_j = \varnothing$ for all $i \neq j$), then:
   $$P\left( \bigcup_{i=1}^{\infty} A_i \right) = \sum_{i=1}^{\infty} P(A_i)$$

   For a finite number of disjoint events $A_1, A_2, \dots, A_n$, Axiom 3 reduces to **finite additivity**:
   $$P(A_1 \cup A_2 \cup \dots \cup A_n) = P(A_1) + P(A_2) + \dots + P(A_n)$$

---

#### **3. Derived Probability Properties**

* **Property 1: Probability of the Empty Set**
  $$P(\varnothing) = 0$$

* **Property 2: The Complement Rule**
  $$P(A^c) = 1 - P(A)$$

* **Property 3: Boundedness**
  $$0 \le P(A) \le 1 \quad \text{for any event } A$$

* **Property 4: Difference Rule & Monotonicity**
  If $A \subseteq B$, then:
  1. $P(B \setminus A) = P(B \cap A^c) = P(B) - P(A)$
  2. $P(A) \le P(B)$ (**Monotonicity**)

* **Property 5: Event Partitioning (Law of Total Probability for Sets)**
  For any two events $A$ and $B$:
  $$P(A) = P(A \cap B) + P(A \cap B^c)$$

---

### **Actuarial Application Example**

**Scenario:** An auto insurer determines that for a given policyholder:
* $P(C) = 0.15$ (Collision claim)
* $P(T) = 0.08$ (Theft claim)
* $P(C \cap T^c) = 0.12$ (Collision claim but **no** theft claim)

**Problem:** Calculate $P(C \cap T)$ (both collision and theft claims).

**Solution:**
Using event partitioning on $C$:
$$P(C) = P(C \cap T) + P(C \cap T^c)$$
$$0.15 = P(C \cap T) + 0.12 \implies P(C \cap T) = 0.15 - 0.12 = 0.03$$

---

## 2. Concept Check Questions & Solutions

### **Question 1**
* **Prompt:** If $P(A) = 0.65$ and $A \subseteq B$, what is the smallest possible value for $P(B)$?
* **Answer & Feedback:** **$0.65$**. By **Monotonicity** ($A \subseteq B \implies P(A) \le P(B)$), since $A$ is entirely inside $B$, $P(B)$ must be at least $0.65$.

### **Question 2**
* **Prompt:** State the three Axioms of Probability in your own words.
* **Answer & Feedback:** 
  1. *Non-negativity:* Probabilities are never negative ($P(A) \ge 0$).
  2. *Normalization:* The sample space probability is 1 ($P(S) = 1$).
  3. *Additivity:* For mutually exclusive events, $P(\text{Union}) = \sum P(\text{Individual Events})$.

### **Question 3**
* **Prompt:** An actuary determines that $P(A \cup B) = 0.80$ and $P(A^c \cap B^c) = 0.20$. Is this statement mathematically consistent with the axioms of probability? Explain.
* **Answer & Feedback:** **Yes, it is consistent.** By De Morgan's Law, $A^c \cap B^c = (A \cup B)^c$. Since $A \cup B$ and $(A \cup B)^c$ are complementary events, $P(A \cup B) + P((A \cup B)^c) = 0.80 + 0.20 = 1.00$, which satisfies Axioms 2 and 3.

---

## 3. Practice Problem Set 1

### **Problem 1**
**Question:** $35\%$ of policyholders file a collision claim ($C$), $20\%$ file a comprehensive claim ($K$), and $10\%$ file both claims. Calculate $P(C \cap K^c)$ (collision claim but **not** a comprehensive claim).

* **Given:** $P(C) = 0.35$, $P(K) = 0.20$, $P(C \cap K) = 0.10$
* **Formula:** $P(C \cap K^c) = P(C) - P(C \cap K)$
* **Step-by-Step Calculation:**
  $$P(C \cap K^c) = 0.35 - 0.10 = 0.25$$
* **Key Learning Note:** Subtracting $P(K)$ ($0.20$) instead of $P(C \cap K)$ ($0.10$) is a common error. $P(K)$ includes claims with no collision ($C^c \cap K$), which are not part of $P(C)$ to begin with.
* **Final Answer:** **$0.25$**

---

### **Problem 2**
**Question:** Let $P(A) = 0.70$ and $P(B) = 0.50$. Calculate:
1. Minimum possible value for $P(A \cap B)$
2. Maximum possible value for $P(A \cap B)$

* **Step-by-Step Solution:**
  1. **Minimum Value:**
     $$P(A \cup B) = P(A) + P(B) - P(A \cap B) \implies P(A \cap B) = P(A) + P(B) - P(A \cup B)$$
     Since $P(A \cup B) \le 1$:
     $$\text{Minimum } P(A \cap B) = 0.70 + 0.50 - 1.00 = 0.20$$
  2. **Maximum Value:**
     By Monotonicity, $(A \cap B) \subseteq A$ and $(A \cap B) \subseteq B$, so $P(A \cap B) \le \min(P(A), P(B))$.
     $$\text{Maximum } P(A \cap B) = \min(0.70, 0.50) = 0.50$$
* **Final Answer:** **$0.20 \le P(A \cap B) \le 0.50$** (Minimum = **$0.20$**, Maximum = **$0.50$**)

---

### **Problem 3**
**Question:** Given $P(X \cup Y) = 0.85$ and $P(X \cap Y^c) = 0.40$, calculate $P(Y)$.

* **Formula:** $P(X \cup Y) = P(X \cap Y^c) + P(Y)$
* **Step-by-Step Calculation:**
  $$0.85 = 0.40 + P(Y) \implies P(Y) = 0.85 - 0.40 = 0.45$$
* **Final Answer:** **$0.45$**

---

### **Problem 4**
**Question:** Let $P(E_1) = 0.08$ (death $\le 10$ yrs), $P(E_2) = 0.15$ (death between $10\text{--}20$ yrs), and $P(E_3) = 0.77$ (death $> 20$ yrs).
1. Verify if $\{E_1, E_2, E_3\}$ forms a valid partition of sample space $S$.
2. Calculate the probability that a policyholder survives past 10 years.

* **Step-by-Step Solution:**
  1. **Partition Check:** The time intervals are mutually exclusive and exhaustive.
     $$P(E_1) + P(E_2) + P(E_3) = 0.08 + 0.15 + 0.77 = 1.00$$
     Thus, $\{E_1, E_2, E_3\}$ is a valid partition.
  2. **Survival Past 10 Years:**
     $$P(\text{Survive } > 10) = P(E_2) + P(E_3) = 0.15 + 0.77 = 0.92$$
     *(Or via Complement Rule: $1 - P(E_1) = 1 - 0.08 = 0.92$)*
* **Final Answer:** **Valid Partition; $P(\text{Survive } > 10) = 0.92$**

---

## 4. Practice Problem Set 2 (Additional Practice)

### **Problem 1**
**Question:** $40\%$ file liability claim ($L$), $25\%$ file property claim ($P$), and $50\%$ file neither claim ($P(L^c \cap P^c) = 0.50$). Calculate $P(L \cap P^c)$ (liability claim only).

* **Formulas:**
  1. $P(L \cup P) = 1 - P(L^c \cap P^c)$
  2. $P(L \cap P) = P(L) + P(P) - P(L \cup P)$
  3. $P(L \cap P^c) = P(L) - P(L \cap P)$
* **Step-by-Step Calculation:**
  1. $P(L \cup P) = 1 - 0.50 = 0.50$
  2. $P(L \cap P) = 0.40 + 0.25 - 0.50 = 0.15$
  3. $P(L \cap P^c) = 0.40 - 0.15 = 0.25$
* **Final Answer:** **$0.25$**

---

### **Problem 2**
**Question:** $\{E_1, E_2, E_3\}$ forms a complete partition of $S$. Given $P(E_1 \cup E_2) = 0.65$ and $P(E_2 \cup E_3) = 0.75$, calculate $P(E_2)$.

* **Formulas & Properties:**
  1. $P(E_1) + P(E_2) + P(E_3) = 1$
  2. $P(E_1 \cup E_2) = P(E_1) + P(E_2) = 0.65$
  3. $P(E_2 \cup E_3) = P(E_2) + P(E_3) = 0.75$
* **Step-by-Step Calculation:**
  1. $P(E_3) = 1 - P(E_1 \cup E_2) = 1 - 0.65 = 0.35$
  2. $P(E_2) = P(E_2 \cup E_3) - P(E_3) = 0.75 - 0.35 = 0.40$
* **Final Answer:** **$0.40$**

---

### **Problem 3**
**Question:** Given independent/general risks $A, B, C$ with $P(A) = 0.90$, $P(B) = 0.85$, $P(C) = 0.80$. Using **Bonferroni's Inequality**, determine the minimum possible value for $P(A \cap B \cap C)$.

* **Bonferroni's Inequality Formula ($n = 3$):**
  $$P(A \cap B \cap C) \ge P(A) + P(B) + P(C) - 2$$
* **Step-by-Step Calculation:**
  $$P(A \cap B \cap C) \ge 0.90 + 0.85 + 0.80 - 2 = 2.55 - 2 = 0.55$$
* **Final Answer:** **$0.55$**

---

### **Problem 4**
**Question:** Given $P(A) = 0.60$, $P(B) = 0.45$, and $P(A \cup B) = 0.80$. Calculate $P(B \cap A^c)$ (event $B$ occurs, but $A$ does not).

* **Step-by-Step Calculation:**
  1. **Intersection:** $P(A \cap B) = P(A) + P(B) - P(A \cup B) = 0.60 + 0.45 - 0.80 = 0.25$
  2. **Set Difference:** $P(B \cap A^c) = P(B) - P(A \cap B) = 0.45 - 0.25 = 0.20$
  *(Shortcut: $P(B \cap A^c) = P(A \cup B) - P(A) = 0.80 - 0.60 = 0.20$)*
* **Final Answer:** **$0.20$**

---

## 5. Day 2 Formulas Summary

* **Additive Law of Probability:**
  $$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$

* **Intersection Bounds (Two Events):**
  $$\text{Min } P(A \cap B) = P(A) + P(B) - 1 \quad (\text{when } P(A \cup B) = 1)$$
  $$\text{Max } P(A \cap B) = \min(P(A), P(B))$$

* **Bonferroni's Inequality:**
  * Two events: $P(A \cap B) \ge P(A) + P(B) - 1$
  * Three events: $P(A \cap B \cap C) \ge P(A) + P(B) + P(C) - 2$
  * General $n$ events: $P\left( \bigcap_{i=1}^n A_i \right) \ge \sum_{i=1}^n P(A_i) - (n - 1)$

* **Set Difference & Union Shortcuts:**
  $$P(B \cap A^c) = P(A \cup B) - P(A)$$
  $$P(A \cap B^c) = P(A \cup B) - P(B)$$
  $$P(A \Delta B) = P(A) + P(B) - 2P(A \cap B)$$