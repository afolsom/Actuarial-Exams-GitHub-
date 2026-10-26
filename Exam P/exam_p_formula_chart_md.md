# Actuarial Exam P Master Formula Chart

---

## Day 1: Sample Spaces, Set Operations, & Event Algebra

### 1. Fundamental Set Operations
* **Union ($A \cup B$):** Event $A$ occurs, OR event $B$ occurs, OR both occur.
  * *Verbal Description:* The set of all outcomes belonging to event $A$, event $B$, or both.
* **Intersection ($A \cap B$):** Event $A$ AND event $B$ occur simultaneously.
  * *Verbal Description:* The set of outcomes shared in common by both event $A$ and event $B$.
* **Complement ($A^c$ or $A'$):** Event $A$ does NOT occur.
  * *Verbal Description:* All outcomes in the sample space that lie outside of event $A$.
* **Set Difference ($A \setminus B = A \cap B^c$):** Event $A$ occurs, BUT event $B$ does NOT occur.
  * *Verbal Description:* The set of outcomes belonging exclusively to event $A$ and not to event $B$.
* **Null / Empty Event ($\varnothing$):** An impossible event containing no outcomes.
  * *Verbal Description:* The set with zero outcomes, representing an event that cannot occur.

### 2. De Morgan's Laws
* **Complement of Union:** $(A \cup B)^c = A^c \cap B^c$
  * *Verbal Description:* The event that neither $A$ nor $B$ occurs is equal to $A$ not occurring AND $B$ not occurring simultaneously.
* **Complement of Intersection:** $(A \cap B)^c = A^c \cup B^c$
  * *Verbal Description:* The event that $A$ and $B$ do not both occur is equal to $A$ failing to occur OR $B$ failing to occur.

### 3. Set Distributive & Partition Rules
* **Distributive Laws:**
  * $A \cap (B \cup C) = (A \cap B) \cup (A \cap C)$
    * *Verbal Description:* The intersection of $A$ with a union equals the union of $A$'s intersections with each individual set.
  * $A \cup (B \cap C) = (A \cup B) \cap (A \cup C)$
    * *Verbal Description:* The union of $A$ with an intersection equals the intersection of $A$'s unions with each individual set.
* **Partitioning an Event:**
  * $A = (A \cap B) \cup (A \cap B^c)$
    * *Verbal Description:* Event $A$ can be decomposed into two mutually exclusive parts: $A$ occurring with $B$, and $A$ occurring without $B$.

---

## Day 2: Axioms of Probability & Basic Probability Rules

### 1. Kolmogorov's Axioms of Probability
* **Axiom 1 (Non-negativity):** $P(A) \ge 0$
  * *Verbal Description:* Every event has a probability that is zero or positive; probabilities can never be negative.
* **Axiom 2 (Normalization / Certainty):** $P(S) = 1$
  * *Verbal Description:* The total probability of the entire sample space (the certain event) is always equal to 1.
* **Axiom 3 (Countable Additivity):** For mutually exclusive (disjoint) events $A_1, A_2, \dots$ where $A_i \cap A_j = \varnothing$ for $i \neq j$:
  $$P\left(\bigcup_{i=1}^{\infty} A_i\right) = \sum_{i=1}^{\infty} P(A_i)$$
  * *Verbal Description:* For any countable sequence of disjoint events, the probability that at least one occurs is the sum of their individual probabilities.
* **Finite Additivity:** $P(A_1 \cup A_2 \cup \dots \cup A_n) = P(A_1) + P(A_2) + \dots + P(A_n)$
  * *Verbal Description:* For a finite collection of mutually exclusive events, the probability of their union equals the sum of their individual probabilities.

### 2. Derived Properties & Basic Rules
* **Empty Set Rule:** $P(\varnothing) = 0$
  * *Verbal Description:* An impossible event containing no outcomes has a probability of exactly zero.
* **Complement Rule:** $P(A^c) = 1 - P(A)$
  * *Verbal Description:* The probability that event $A$ does not occur equals 1 minus the probability that $A$ does occur.
* **Boundedness:** $0 \le P(A) \le 1$
  * *Verbal Description:* All event probabilities are bounded between 0 (impossible) and 1 (certain).
* **Difference Rule:** $P(B \setminus A) = P(B \cap A^c) = P(B) - P(A)$ for $A \subseteq B$
  * *Verbal Description:* If event $A$ is entirely contained within event $B$, the probability of $B$ occurring without $A$ is $P(B)$ minus $P(A)$.
* **Monotonicity:** If $A \subseteq B$, then $P(A) \le P(B)$
  * *Verbal Description:* A sub-event cannot have a higher probability than the larger event containing it.
* **Law of Total Probability for Sets (Partitioning):** $P(A) = P(A \cap B) + P(A \cap B^c)$
  * *Verbal Description:* The total probability of event $A$ is the sum of the probability of $A$ happening with $B$ and $A$ happening without $B$.

### 3. Additive Laws & Set Difference Shortcuts
* **General Addition Rule (Two Events):**
  $$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$
  * *Verbal Description:* The probability that $A$ or $B$ occurs is the sum of their individual probabilities minus the double-counted intersection probability.
* **Union Decomposition:**
  $$P(A \cup B) = P(A) + P(B \cap A^c)$$
  * *Verbal Description:* The probability of $A$ or $B$ equals the probability of $A$ plus the probability of $B$ occurring exclusively without $A$.
* **Shortcut Set Difference Formulas:**
  * $P(B \cap A^c) = P(A \cup B) - P(A)$
    * *Verbal Description:* The probability of $B$ only equals the combined union probability minus $P(A)$.
  * $P(A \cap B^c) = P(A \cup B) - P(B)$
    * *Verbal Description:* The probability of $A$ only equals the combined union probability minus $P(B)$.
* **Symmetric Difference Formula:**
  $$P(A \Delta B) = P(A) + P(B) - 2P(A \cap B)$$
  * *Verbal Description:* The probability that *exactly one* of event $A$ or event $B$ occurs, excluding the outcome where both occur.

### 4. Intersection Bounds & Bonferroni's Inequality
* **Intersection Bounds (Two Events):**
  * **Minimum Possible Intersection:**
    $$P(A \cap B) \ge P(A) + P(B) - 1$$
    *(Note: $P(A \cap B) = P(A) + P(B) - P(A \cup B)$ when $P(A \cup B) = 1$)*
    * *Verbal Description:* The smallest possible intersection probability occurs when the union spans the entire sample space ($P(A \cup B) = 1$).
  * **Maximum Possible Intersection:**
    $$P(A \cap B) \le \min(P(A), P(B))$$
    * *Verbal Description:* The maximum intersection probability is restricted by the smaller of the two individual event probabilities.
* **Bonferroni's Inequality:**
  * **Two-Event Case:**
    $$P(A \cap B) \ge P(A) + P(B) - 1 \quad \text{or} \quad P(A \cap B) \ge 1 - P(A^c) - P(B^c)$$
    * *Verbal Description:* The simultaneous occurrence of two events is at least 1 minus the sum of their individual complements' probabilities.
  * **Three-Event Case ($n = 3$):**
    $$P(A \cap B \cap C) \ge P(A) + P(B) + P(C) - 2$$
    * *Verbal Description:* Lower bound for the simultaneous occurrence of three events, obtained by subtracting 2 from the sum of their probabilities.
  * **General $n$-Event Form:**
    $$P(A_1 \cap A_2 \cap \dots \cap A_n) \ge \sum_{i=1}^{n} P(A_i) - (n - 1)$$
    $$P(A_1 \cap A_2 \cap \dots \cap A_n) \ge 1 - \sum_{i=1}^{n} P(A_i^c)$$
    * *Verbal Description:* Lower bound for the simultaneous occurrence of $n$ events, derived by subtracting $(n - 1)$ from the sum of individual probabilities, or subtracting the sum of all complement probabilities from 1.

---

## Day 3: Combinatorics, Permutations, & Combinations

### 1. Fundamental Counting Principles
* **Multiplication Principle (Sequential Choices):**
  $$\text{Total Outcomes} = n_1 \times n_2 \times \dots \times n_k$$
  * *Verbal Description:* If a procedure consists of $k$ sequential steps with $n_i$ options at step $i$, the total number of combined outcomes is the product of the options at each step.
* **Addition Principle (Disjoint Alternatives):**
  $$\text{Total Options} = n_1 + n_2 + \dots + n_m$$
  * *Verbal Description:* If a single selection can be made from one of $m$ mutually exclusive sets, the total number of options is the sum of the sizes of each set.

### 2. Permutations (Order Matters)
* **Basic Permutation Formula:**
  $$P(n, r) = {}_nP_r = \frac{n!}{(n - r)!}$$
  *(where $n! = n \times (n-1) \times \dots \times 2 \times 1$ and $0! = 1$)*
  * *Verbal Description:* The number of distinct ordered arrangements of $r$ items chosen without replacement from a set of $n$ distinct items.
* **Permutations with Repeated / Indistinguishable Objects:**
  $$\text{Distinct Arrangements} = \frac{n!}{n_1! \, n_2! \, \dots \, n_k!}$$
  *(where $n_1 + n_2 + \dots + n_k = n$)*
  * *Verbal Description:* The number of distinct linear arrangements of $n$ total items when the items belong to $k$ groups of identical/indistinguishable objects.

### 3. Combinations (Order Does NOT Matter)
* **Combination Formula:**
  $$C(n, r) = \binom{n}{r} = {}_nC_r = \frac{n!}{r!(n - r)!}$$
  * *Verbal Description:* The number of ways to choose an unordered subset or committee of $r$ items from $n$ distinct available items.
* **Useful Algebraic Identities:**
  * **Symmetry:** $\binom{n}{r} = \binom{n}{n - r}$
    * *Verbal Description:* Selecting $r$ items to include in a group is identical to selecting $n - r$ items to exclude.
  * **Boundary Values:** $\binom{n}{0} = \binom{n}{n} = 1$
    * *Verbal Description:* There is exactly 1 way to select zero items (the empty set) or all $n$ items.
  * **Pascal's Identity:** $\binom{n}{r} = \binom{n-1}{r-1} + \binom{n-1}{r}$
    * *Verbal Description:* The number of ways to choose $r$ items from $n$ equals the combinations that include a specific item plus the combinations that exclude that item.

### 4. Classical Probability with Combinatorics
* **Equally Likely Outcomes Formula:**
  $$P(E) = \frac{n(E)}{n(S)} = \frac{\text{Number of Favorable Outcomes}}{\text{Total Number of Possible Outcomes}}$$
  * *Verbal Description:* In a sample space of equally likely outcomes, the probability of an event equals the count of favorable outcomes divided by the total number of sample space outcomes.