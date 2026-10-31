# Phase 4 Study Guide: Comprehensive Review & Practice Exams (Days 34–37)

**Actuarial Exam P | Final Review & Execution Strategy**

## Overview & Exam Strategy for Phase 4

Phase 4 transitions your focus from learning individual topics to mastering full-length exam execution under realistic Computer-Based Testing (CBT) conditions. Exam P consists of **30 multiple-choice questions** to be completed in **3 hours (180 minutes)**, giving an average of **6 minutes per question**.

### Phase 4 Objectives:
1. **Master the Three-Pass Triage Strategy:** Maximize your score by prioritizing high-confidence, quick-solve questions first.
2. **Execute Diagnostic Error Analysis:** Systematically log and eliminate recurring errors using a 4-category taxonomy.
3. **Optimize Calculator & Formula Recall:** Harness maximum speed with the TI-30XS MultiView and instant formula retrieval.
4. **Eliminate Guessing Penalties:** Ensure 100% submission completion using strategic elimination principles (there is no penalty for guessing).

---

## Day 34 (Session 4.1): Timed Mock Exam 1 & Three-Pass Triage Strategy

### 1. CBT Exam Mechanics & Time Budgeting

* **Total Duration:** 180 Minutes (3 Hours)
* **Question Count:** 30 Questions (5 choice options per question: A, B, C, D, E)
* **Average Pace:** 6 minutes per question
* **Scoring Structure:** Score is based strictly on the number of correct answers. **No penalty for incorrect answers.** Unanswered questions are marked incorrect.
* **Pilot Questions:** 5 of the 30 questions may be non-scored pilot questions tested by the SOA for future exams. Treat **every** question as scored, but if a question feels completely unfamiliar or overly convoluted, it may be a pilot question—do not let it ruin your pacing.

### 2. The Three-Pass Triage Strategy

Do not solve questions strictly in linear order (1 to 30). Use the CBT exam software features (**Flag for Review** and **Next/Previous**) to execute a 3-pass workflow:

```
+-----------------------------------------------------------------------+
|                           180-MINUTE TIMELINE                         |
|                                                                       |
| [Pass 1: Min 0 - 60]    -->  [Pass 2: Min 60 - 150] --> [Pass 3: 150-180]|
| Fast & Direct (~12-15 Qs)   Moderate & Calc (~10-12 Qs)  Hard/Guess (~3-5 Qs)|
+-----------------------------------------------------------------------+
```

#### Pass 1: Quick Wins (Target: Minutes 0–60)
* **Goal:** Solve 12–15 straightforward questions in 2–4 minutes each.
* **Question Types:** Set operations, discrete probability mass functions, basic exponential/uniform properties, simple Bayes' theorem, basic independence/covariance calculations.
* **Action:** If a problem requires more than 2 steps of integration or complex region setup, **Flag it immediately and skip to the next question.**

#### Pass 2: Core Actuarial & Calculus Problems (Target: Minutes 60–150)
* **Goal:** Solve 10–12 moderate-complexity questions taking 5–7 minutes each.
* **Question Types:** Continuous bivariate integration, insurance policy modifications (deductibles, benefit limits, coinsurance), transformation of variables, EVVE rule, Order Statistics.
* **Action:** Set up integrals carefully. If an integral evaluation gets messy, re-verify the region bounds before continuing.

#### Pass 3: Complex, Unfamiliar, & Strategic Guessing (Target: Minutes 150–180)
* **Goal:** Address remaining flagged questions, re-check calculations, and ensure **zero unanswered questions remain**.
* **Action:** Spend remaining time on remaining hard problems. In the final 5 minutes, place an educated guess on any unresolved questions.

### 3. Target Time Checkpoints

| Checkpoint | Target Completed Questions | Remaining Time | Status Assessment |
| --- | --- | --- | --- |
| **60 Minutes Elapsed** | 10–12 Questions | 120 Minutes | On track if Pass 1 is wrapping up. |
| **120 Minutes Elapsed** | 20–22 Questions | 60 Minutes | On track if majority of Pass 2 is complete. |
| **165 Minutes Elapsed** | 28–30 Questions | 15 Minutes | Final review phase; check flagged items. |
| **175 Minutes Elapsed** | All 30 Answered | 5 Minutes | Verify zero questions are left blank. |

---

## Day 35 (Session 4.2): Diagnostic Review & Error Taxonomy

Completing a practice exam is only half the task; the real score improvement comes from a rigorous diagnostic post-mortem.

### 1. The 4-Category Error Taxonomy

Analyze every incorrect or sluggishly answered question from Mock Exam 1 and assign it to one of four categories:

```
                       +-----------------------+
                       |    ERROR TAXONOMY     |
                       +-----------------------+
                                   |
        +------------------+-------+-------+------------------+
        |                  |               |                  |
  [1. Concept Flaw]  [2. Calc Slip]  [3. Misread]   [4. Pacing Panic]
```

1. **Category 1: Conceptual / Theoretical Flaw**
   * *Symptom:* Didn't know which formula to apply or misapplied a core probability property (e.g., confusing $E[Y|X]$ with $E[Y]$, or confusing ordinary deductible with franchise deductible).
   * *Remediation:* Re-read corresponding Phase 1–3 daily module, review core formulas, and rewrite concept summary cards.

2. **Category 2: Calculus / Algebraic Slip**
   * *Symptom:* Correct setup, but made an integration error, sign error, or arithmetic blunder.
   * *Remediation:* Practice manual integration steps; utilize TI-30XS numerical integration (`table` or data features) to cross-check arithmetic.

3. **Category 3: Misreading / Interpretation Error**
   * *Symptom:* Solved for loss variable $X$ instead of payment variable $Y$; missed "at least", "given that", or "per claim" vs. "per policy".
   * *Remediation:* Adopt a double-underline strategy during setup: underline the target variable and key policy terms before writing equations.

4. **Category 4: Time Pressure / Pacing Panic**
   * *Symptom:* Spent 12+ minutes on a single problem, resulting in rushed guesses on later questions.
   * *Remediation:* Enforce a strict **3-minute bail-out rule** during Pass 1.

### 2. Diagnostic Review Log Template

Use the following structure to log and review missed questions:

| Question # | Primary Topic | Error Category | Root Cause Analysis | Corrective Action / Key Insight |
| --- | --- | --- | --- | --- |
| **Q07** | Policy Deductible ($Y$) | Misread | Solved for $E[X]$ instead of $E[Y = \max(X-d, 0)]$. | Always state target variable explicitly ($X$ vs $Y$) first. |
| **Q14** | EVVE Rule | Concept Flaw | Forgot to square $E[Y|X]$ when evaluating $Var(E[Y|X])$. | $Var(g(X)) = E[g(X)^2] - (E[g(X)])^2$. |
| **Q22** | Continuous Joint PDF | Calc Slip | Flipped double-integral bounds for $y > x$. | Draw support region on scratch paper before writing bounds. |

---

## Day 36 (Session 4.3): Timed Mock Exam 2 & Strategic Adjustments

### 1. Strategic Guessing & Elimination Workflow

Since there is **no penalty for wrong answers**, a blank response is equivalent to giving away points.

#### Elimination Algorithm:
1. **Check Boundary Constraints:** If a probability must lie in $[0, 1]$, eliminate choices $< 0$ or $> 1$.
2. **Dimension / Scale Check:** If finding an expected cost where losses are scaled by factor $k$, verify that units match.
3. **Symmetry Arguments:** In uniform or standard normal contexts, eliminate choices that violate domain symmetry.
4. **Educated Guessing:** If down to 2 choices, select and move on. If completely blind, pick a consistent letter choice (e.g., always C) for un-attempted items in the final minute.

### 2. TI-30XS MultiView Calculator Optimization

Maximize calculation speed with these specific TI-30XS calculator features:

```
+------------------------------------------------------------------------+
|                      TI-30XS MULTIVIEW KEY STROKES                     |
+------------------------------------------------------------------------+
|  Feature             | Key Sequence                                    |
+----------------------+-------------------------------------------------+
|  Combinations        | [n] [math] -> PRB -> 2: nCr -> [r]              |
|  Permutations        | [n] [math] -> PRB -> 1: nPr -> [r]              |
|  Factorials          | [n] [math] -> PRB -> 3: !                       |
|  Data / One-Var Stats| [data] (enter x, freq) -> [2nd] [data] (STAT)   |
|  Table / PDF Values  | [table] -> enter f(x) -> set start & step       |
|  Memory Store        | [sto->] [x n t a b c d]                         |
|  Recall Memory       | [2nd] [recall]                                  |
+----------------------+-------------------------------------------------+
```

#### Calculator Tips for Exam Day:
* **Storing Intermediate Results:** Never write down truncated decimals on scratch paper to re-type them. Store intermediate values in variables `x`, `y`, `z`, `a`, `b`, `c`.
* **Discrete Distributions via Table:** Use `[table]` to generate values for discrete PMFs quickly (e.g., $f(x) = \binom{n}{x} p^x (1-p)^{n-x}$) to find cumulative sums $P(X \le k)$.

---

## Day 37 (Session 4.4): Final Pre-Exam Checklist & Execution Plan

### 1. Master Formula Recall Verification

Verify rapid recall of these non-negotiable formulas across all 3 exam phases:

#### General Probability (Phase 1)
* **De Morgan's Laws:** $(A \cup B)^c = A^c \cap B^c$, $(A \cap B)^c = A^c \cup B^c$
* **Inclusion-Exclusion:** $P(A \cup B \cup C) = \sum P(A) - \sum P(A \cap B) + P(A \cap B \cap C)$
* **Bayes' Theorem:** $P(A_i \mid B) = \frac{P(B \mid A_i) P(A_i)}{\sum_j P(B \mid A_j) P(A_j)}$

#### Univariate Random Variables (Phase 2)
* **Poisson PMF:** $P(X = k) = \frac{e^{-\lambda} \lambda^k}{k!}, \quad E[X] = \lambda, \, Var(X) = \lambda$
* **Exponential Memoryless:** $P(X > s + t \mid X > s) = P(X > t) = e^{-\lambda t}$
* **Gamma Distribution:** $E[X] = \alpha \theta, \, Var(X) = \alpha \theta^2$
* **Normal Standardizing:** $Z = \frac{X - \mu}{\sigma}$
* **Insurance Payment Expectations:**
  * Ordinary Deductible $d$: $E[Y] = \int_{d}^{\infty} (x - d) f(x) \, dx = \int_{d}^{\infty} S(x) \, dx$
  * Maximum Benefit Limit $u$: $E[X \wedge u] = \int_{0}^{u} S(x) \, dx$

#### Multivariate Random Variables (Phase 3)
* **Conditional Density:** $f_{Y|X}(y|x) = \frac{f(x,y)}{f_X(x)}$
* **Law of Total Expectation:** $E[Y] = E[E[Y|X]]$
* **Law of Total Variance (EVVE):** $Var(Y) = E[Var(Y|X)] + Var(E[Y|X])$
* **Covariance Shortcut:** $Cov(X,Y) = E[XY] - E[X]E[Y]$
* **Variance of Linear Combination:** $Var(aX + bY) = a^2 Var(X) + b^2 Var(Y) + 2ab \, Cov(X,Y)$
* **Order Statistics:**
  * Maximum: $F_{(n)}(y) = [F(y)]^n, \quad f_{(n)}(y) = n [F(y)]^{n-1} f(y)$
  * Minimum: $S_{(1)}(y) = [S(y)]^n, \quad f_{(1)}(y) = n [S(y)]^{n-1} f(y)$
* **CLT Standardized Sum:** $Z = \frac{\sum X_i - n\mu}{\sigma \sqrt{n}} \sim N(0, 1)$

---

### 2. Standard Normal ($Z$) Table Quick Reference

$$
\begin{array}{|c|c|c|c|c|c|c|c|}
\hline
z & 0.00 & 0.50 & 1.00 & 1.282 & 1.645 & 1.960 & 2.326 & 2.576 \\
\hline
\Phi(z) & 0.5000 & 0.6915 & 0.8413 & 0.9000 & 0.9500 & 0.9750 & 0.9900 & 0.9950 \\
\hline
\end{array}
$$

* **Upper-Tail Benchmarks:**
  * $P(Z > 1.282) = 0.10$ (90th percentile)
  * $P(Z > 1.645) = 0.05$ (95th percentile)
  * $P(Z > 1.960) = 0.025$ (97.5th percentile)
  * $P(Z > 2.326) = 0.01$ (99th percentile)

---

### 3. T-Minus 24-Hour Checklist

#### Day Before Exam:
- [ ] **No Heavy Problem Solving:** Review summary formula sheets only. Do not attempt full mock exams.
- [ ] **Gather Required Documents:** SOA appointment confirmation, government-issued photo ID (matching registration name exactly).
- [ ] **Approved Calculator Check:** Confirm your calculator is SOA-approved (TI-30XS MultiView recommended). Reset memory and verify battery state.
- [ ] **Test Center Logistics:** Confirm test location, driving/transit route, parking details, and arrive 30 minutes prior to scheduled time.

#### Exam Day Execution:
- [ ] **Pacing Mindset:** Execute the 3-pass strategy strictly. Do not get trapped by any single question.
- [ ] **Scratch Paper Management:** Divide scratch sheets into clear grid sections labeled with question numbers to prevent copy errors.
- [ ] **Final 5-Minute Sweep:** Verify that **every single question (1 to 30)** has an answer selected before time expires.

---

## Phase 4 Strategy Quick Reference & Decision Tree

```
                           +--------------------------------+
                           |  START QUESTION (Max 6 Mins)   |
                           +--------------------------------+
                                           |
                                           v
                          /---------------------------------\
                         /   Can I solve this directly in    \
                        <           < 3 minutes?              >
                         \                                   /
                          \---------------------------------/
                                    /             \
                                   /               \
                             YES  /                 \  NO
                                 v                   v
                     +-------------------+   +--------------------+
                     |  Solve & Record   |   |  FLAG & SKIP TO    |
                     |  Answer (Pass 1)  |   |  NEXT (Pass 2/3)   |
                     +-------------------+   +--------------------+
                                                      |
                                                      v
                                            /--------------------\
                                           /  Remaining time      \
                                          <   < 5 minutes left?    >
                                           \                      /
                                            \--------------------/
                                              /                \
                                        YES  /                  \ NO
                                            v                    v
                                +-------------------+    +-------------------+
                                | Place Educated    |    | Set up integral / |
                                | Guess on all Blank|    | EVVE / Algebra    |
                                | Items immediately |    | carefully         |
                                +-------------------+    +-------------------+
```