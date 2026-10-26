# Actuarial Exam P: Day 1 Complete Lesson Notes

---

## Part 1: Guided Learning Session (Session 1A.1)
**Topic:** Sample Spaces, Outcomes, Events, Venn Diagrams, and Set Operations  
**Core Objective:** Understand the foundational building blocks of probability theory for Actuarial Exam P.

---

### 1. Fundamental Definitions

* **Random Experiment:** A process whose outcome cannot be predicted with certainty (e.g., observing whether an insurance policyholder files a claim during a year).
* **Sample Space ($S$ or $\Omega$):** The set of *all possible outcomes* of a random experiment.
  * *Example:* In an auto insurance policy, $S = \{0, 1, 2, 3, \dots\}$ where outcomes represent the number of claims filed in a year.
* **Outcome ($\omega$):** A single point in the sample space $S$.
* **Event ($A$):** Any subset of the sample space $S$ ($A \subseteq S$). An event $A$ is said to occur if the actual observed outcome belongs to $A$.
  * *Null Event ($\varnothing$):* The empty set (an impossible event).

---

### 2. Essential Set Operations

Let $A$ and $B$ be two events defined on a sample space $S$:

| Operation | Notation | Meaning in English | Actuarial Example |
| :--- | :--- | :--- | :--- |
| **Union** | $A \cup B$ | Event $A$ occurs, or event $B$ occurs, or **both** occur. | Policyholder has **Auto** or **Home** coverage (or both). |
| **Intersection** | $A \cap B$ | Both $A$ **and** $B$ occur simultaneously. | Policyholder has **both** Auto and Home coverage. |
| **Complement** | $A^c$ (or $A'$) | Event $A$ does **not** occur. | Policyholder does **not** file a claim. |
| **Difference** | $A \setminus B = A \cap B^c$ | Event $A$ occurs, **but** $B$ does not occur. | Policyholder has Auto coverage **only** (no Home coverage). |

---

### 3. Key Set Identities & De Morgan's Laws

On Exam P, word descriptions must frequently be translated into set expressions using these core laws:

#### **De Morgan's Laws:**
1. **$(A \cup B)^c = A^c \cap B^c$**
   * *Verbal meaning:* "Neither $A$ nor $B$ occurs".
   * *Actuarial context:* A customer buys neither Collision nor Disability coverage.
2. **$(A \cap B)^c = A^c \cup B^c$**
   * *Verbal meaning:* "Not both $A$ and $B$ occur" (at least one of $A$ or $B$ fails to occur).

#### **Distributive Laws:**
* $A \cap (B \cup C) = (A \cap B) \cup (A \cap C)$
* $A \cup (B \cap C) = (A \cup B) \cap (A \cup C)$

#### **Partitioning an Event:**
Any event $A$ can be partitioned relative to another event $B$:
$$A = (A \cap B) \cup (A \cap B^c)$$
*(where $A \cap B$ and $A \cap B^c$ are mutually exclusive sets)*.

---

### 4. Venn Diagrams & Actuarial Translation

Consider three policy coverages: **$A$ (Auto)**, **$H$ (Home)**, and **$L$ (Life)**.

* **"At least one coverage":** $A \cup H \cup L$
* **"All three coverages":** $A \cap H \cap L$
* **"Exactly one coverage":** $(A \cap H^c \cap L^c) \cup (A^c \cap H \cap L^c) \cup (A^c \cap H^c \cap L)$
* **"Exactly two coverages":** $(A \cap H \cap L^c) \cup (A \cap H^c \cap L) \cup (A^c \cap H \cap L)$
* **"None of the coverages":** $(A \cup H \cup L)^c = A^c \cap H^c \cap L^c$

---

### 5. Guided Check Point & Solutions

**Scenario:** An insurer classifies policyholders by claim severity ($L$: Low, $M$: Medium, $H$: High) and driver experience ($F$: First-year driver).

1. **The claim is not high severity:** $H^c$
2. **The claim is low or medium severity, and driver is first-year:** $F \cap (L \cup M)$
3. **First-year driver with neither low nor medium severity claim:** $F \cap (L^c \cap M^c)$ *(Equivalent to $F \cap H$)*

---

## Part 2: Conceptual Deep Dive – Understanding Events

### 1. The Four-Level Hierarchy
* **Random Experiment:** Process with uncertain results (e.g., observing a policyholder for 1 year).
* **Outcome ($\omega$):** A single, granular, indivisible result.
* **Sample Space ($S$):** The complete universe of all possible outcomes.
* **Event ($A$):** Any subset or condition imposed on outcomes ($A \subseteq S$). Occurs if observed $\omega \in A$.

### 2. Event Types & Classifications
* **Simple Event:** Contains exactly one outcome (e.g., rolling a $3 \rightarrow \{3\}$).
* **Compound Event:** Combines two or more outcomes (e.g., rolling an odd number $\rightarrow \{1, 3, 5\}$).
* **Mutually Exclusive (Disjoint):** $A \cap B = \varnothing$ (cannot occur together).
* **Exhaustive:** $A_1 \cup A_2 \cup \dots \cup A_k = S$ (covers all outcomes).
* **Partition:** Sets that are both mutually exclusive and exhaustive.

---

## Part 3: Day 1 Core Practice Problem Set & Solutions

### Problem 1
**Question:** Write a set expression for: Auto policy ($A$) and at least one of Home ($H$) or Life ($L$), but not both Home and Life.  
**Solution:**
$$(A \cap (H \cup L)) \cap (H \cap L)^c$$

---

### Problem 2
**Question:** Simplify $(E \cup F^c)^c \cup (E \cap F)$.  
**Solution & Proof:**
1. Apply De Morgan's Law: $(E \cup F^c)^c = E^c \cap F$
2. Substitute back: $(E^c \cap F) \cup (E \cap F)$
3. Apply Commutative & Distributive Laws: $F \cap (E^c \cup E)$
4. Complement & Identity: $F \cap S = F$  
**Final Answer:** $F$

---

### Problem 3
**Question:** Express the event that a commercial fleet vehicle incurs **exactly two** of Collision ($C$), Mechanical ($M$), and Vandalism ($V$).  
**Solution:**
$$(C \cap M \cap V^c) \cup (C \cap M^c \cap V) \cup (C^c \cap M \cap V)$$

---

### Problem 4
**Scenario:** 1,000 policyholders ($N(S) = 1000$).
* $N(A \cap B^c) = 350$ (Auto only)
* $N(A^c \cap B) = 200$ (Home only)
* $N((A \cup B)^c) = 150$ (Neither)

**Part 1 Notation for both policies:** $A \cap B$  
**Part 2 Calculation:**
$$N(A \cap B^c) + N(A^c \cap B) + N((A \cup B)^c) + N(A \cap B) = N(S)$$
$$350 + 200 + 150 + x = 1000$$
$$700 + x = 1000 \implies x = 300$$
**Final Answer:** 300 policyholders have both policies.

---

## Part 4: Additional Practice – Set Algebra & Simplification

### Problem 1
**Expression:** $[(A \cap B)^c \cap A] \cup (A \cap B)$  
**Simplification Steps:**
1. De Morgan's: $[(A^c \cup B^c) \cap A] \cup (A \cap B)$
2. Distribute $A$: $[(A^c \cap A) \cup (B^c \cap A)] \cup (A \cap B) = (A \cap B^c) \cup (A \cap B)$
3. Factor out $A \cap$: $A \cap (B^c \cup B) = A \cap S = A$  
**Final Answer:** $A$

---

### Problem 2
**Expression:** $(A \cup B) \cap (A \cup B^c)$  
**Simplification Steps:**
1. Factor out $A \cup$ (Distributive Law): $A \cup (B \cap B^c)$
2. Complement Law: $A \cup \varnothing = A$  
**Final Answer:** $A$

---

### Problem 3
**Expression:** $[(A^c \cup B^c)^c \cup (A \cap B^c)]^c$  
**Simplification Steps:**
1. De Morgan's inside: $(A^c \cup B^c)^c = A \cap B$
2. Substitute: $[(A \cap B) \cup (A \cap B^c)]^c$
3. Factor $A \cap$: $[A \cap (B \cup B^c)]^c = [A \cap S]^c = A^c$  
**Final Answer:** $A^c$

---

### Problem 4
**Expression:** $(A \cap B^c) \cup (B \cap A^c) \cup (A \cap B)$  
**Simplification Steps:**
1. Group terms: $[(A \cap B^c) \cup (A \cap B)] \cup (B \cap A^c)$
2. Factor $A \cap$: $[A \cap (B^c \cup B)] \cup (B \cap A^c) = A \cup (B \cap A^c)$
3. Distribute $A \cup$: $(A \cup B) \cap (A \cup A^c) = (A \cup B) \cap S = A \cup B$  
**Final Answer:** $A \cup B$