# SOA Actuarial Exam P – Complete Formula Reference Chart
**Coverage:** Phase 1 (General Probability), Phase 2 (Univariate Random Variables), and Phase 3 (Multivariate Random Variables)

---

## Phase 1: General Probability

### 1. Set Operations & Event Algebra
* **Union ($A \cup B$):** $A$ occurs, or $B$ occurs, or both occur.
* **Intersection ($A \cap B$):** Both $A$ and $B$ occur simultaneously.
* **Complement ($A^c$ or $A'$):** Event $A$ does not occur.
* **Set Difference ($A \setminus B = A \cap B^c$):** Event $A$ occurs, but event $B$ does not occur.
* **De Morgan's Laws:**
  $$(A \cup B)^c = A^c \cap B^c$$
  $$(A \cap B)^c = A^c \cup B^c$$
* **Distributive Laws:**
  $$A \cap (B \cup C) = (A \cap B) \cup (A \cap C)$$
  $$A \cup (B \cap C) = (A \cup B) \cap (A \cup C)$$
* **Event Partitioning:**
  $$A = (A \cap B) \cup (A \cap B^c) \quad \text{where } (A \cap B) \cap (A \cap B^c) = \varnothing$$

---

### 2. Kolmogorov's Axioms & Basic Probability Rules
* **Axiom 1 (Non-negativity):** $P(A) \ge 0$ for all $A \subseteq S$.
* **Axiom 2 (Normalization):** $P(S) = 1$.
* **Axiom 3 (Countable Additivity):** For mutually exclusive events $A_1, A_2, \dots$:
  $$P\left( \bigcup_{i=1}^{\infty} A_i \right) = \sum_{i=1}^{\infty} P(A_i)$$
* **Empty Set:** $P(\varnothing) = 0$
* **Complement Rule:** $P(A^c) = 1 - P(A)$
* **Boundedness:** $0 \le P(A) \le 1$
* **Difference Rule:** If $A \subseteq B$, then $P(B \setminus A) = P(B \cap A^c) = P(B) - P(A)$.
* **Monotonicity:** If $A \subseteq B$, then $P(A) \le P(B)$.
* **Law of Total Probability for Sets:** $P(A) = P(A \cap B) + P(A \cap B^c)$

---

### 3. Probability Inequalities & Bounds
* **Bonferroni's Inequality (Two Events):**
  $$P(A \cap B) \ge P(A) + P(B) - 1$$
* **Bonferroni's Inequality ($n$ Events):**
  $$P\left( \bigcap_{i=1}^{n} A_i \right) \ge \sum_{i=1}^{n} P(A_i) - (n - 1) = 1 - \sum_{i=1}^{n} P(A_i^c)$$
* **Intersection Bounds:**
  $$\max(0, P(A) + P(B) - 1) \le P(A \cap B) \le \min(P(A), P(B))$$
* **Boole's Inequality:**
  $$P\left( \bigcup_{i=1}^{n} A_i \right) \le \sum_{i=1}^{n} P(A_i)$$

---

### 4. Combinatorics & Enumeration Techniques
* **Multiplication Principle:** $\text{Total Outcomes} = n_1 \times n_2 \times \dots \times n_k$
* **Addition Principle:** $\text{Total Options} = n_1 + n_2 + \dots + n_m$ (for disjoint sets)
* **Permutation Formula (Order Matters):**
  $$P(n, r) = {}_nP_r = \frac{n!}{(n - r)!}$$
* **Permutations with Indistinguishable Objects:**
  $$\text{Distinct Arrangements} = \frac{n!}{n_1! \, n_2! \, \dots \, n_k!} \quad \text{where } \sum n_i = n$$
* **Combination Formula (Order Does NOT Matter):**
  $$C(n, r) = \binom{n}{r} = {}_nC_r = \frac{n!}{r!(n - r)!}$$
* **Combinatorial Identities:**
  $$\binom{n}{r} = \binom{n}{n - r}, \quad \binom{n}{0} = \binom{n}{n} = 1, \quad \binom{n}{r} = \binom{n-1}{r-1} + \binom{n-1}{r}$$
* **Stars & Bars (Distributing $n$ identical items into $k$ distinct bins):**
  * *Bins can be empty ($x_i \ge 0$):* $\binom{n + k - 1}{k - 1} = \binom{n + k - 1}{n}$
  * *Bins cannot be empty ($x_i \ge 1$):* $\binom{n - 1}{k - 1}$
* **Proximity Rules:**
  * *Block Method (Must sit together):* $(\text{Arrangements of Super-Items}) \times (\text{Internal Arrangements inside Block})$
  * *Gap Method (No two adjacent):* $m! \times \binom{m + 1}{r} \times r!$ ($m$ unrestricted, $r$ restricted)
* **Grid / Lattice Paths from $(0,0)$ to $(a,b)$:**
  $$\text{Total Paths} = \binom{a + b}{a} = \binom{a + b}{b} = \frac{(a + b)!}{a! \, b!}$$
  $$\text{Paths via Waypoint } (x_1, y_1) = \binom{x_1 + y_1}{x_1} \times \binom{(a - x_1) + (b - y_1)}{a - x_1}$$

---

### 5. Addition Rules & Inclusion-Exclusion
* **Mutually Exclusive (Disjoint) Events:** $A \cap B = \varnothing \implies P(A \cap B) = 0$
  $$P(A \cup B) = P(A) + P(B)$$
* **General Addition Rule (Two Events):**
  $$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$
* **Inclusion-Exclusion Principle (Three Events):**
  $$P(A \cup B \cup C) = P(A) + P(B) + P(C) - P(A \cap B) - P(A \cap C) - P(B \cap C) + P(A \cap B \cap C)$$

---

### 6. Independence & Conditional Probability
* **Definition of Independent Events:**
  $$P(A \cap B) = P(A) \cdot P(B) \iff P(A \mid B) = P(A) \iff P(B \mid A) = P(B)$$
* **Independence of Complements:** If $A$ and $B$ are independent, so are $A$ and $B^c$, $A^c$ and $B$, and $A^c$ and $B^c$.
* **"At Least One" Independent Event:**
  $$P\left( \bigcup_{i=1}^{n} A_i \right) = 1 - \prod_{i=1}^{n} (1 - P(A_i))$$
* **Conditional Probability:**
  $$P(A \mid B) = \frac{P(A \cap B)}{P(B)} \quad \text{for } P(B) > 0$$
* **Multiplication Rule:**
  $$P(A \cap B) = P(A \mid B) P(B) = P(B \mid A) P(A)$$
  $$P(A \cap B \cap C) = P(A) \cdot P(B \mid A) \cdot P(C \mid A \cap B)$$

---

### 7. Law of Total Probability & Bayes' Theorem
* **Law of Total Probability:** For a partition $B_1, B_2, \dots, B_k$ of sample space $S$:
  $$P(A) = \sum_{i=1}^{k} P(A \cap B_i) = \sum_{i=1}^{k} P(A \mid B_i) P(B_i)$$
* **Bayes' Theorem:**
  $$P(B_j \mid A) = \frac{P(A \cap B_j)}{P(A)} = \frac{P(A \mid B_j) P(B_j)}{\sum_{i=1}^{k} P(A \mid B_i) P(B_i)}$$
* **Odds & Posterior Odds:**
  $$\text{Odds}(B) = \frac{P(B)}{P(B^c)}, \quad \text{Posterior Odds } \frac{P(B \mid A)}{P(B^c \mid A)} = \frac{P(B)}{P(B^c)} \times \frac{P(A \mid B)}{P(A \mid B^c)}$$

---

## Phase 2: Univariate Random Variables

### 1. Fundamental Probability Functions & Properties
* **Probability Mass Function (PMF - Discrete):** $p_X(x) = P(X = x)$
  $$\sum_x p_X(x) = 1, \quad p_X(x) \ge 0$$
* **Probability Density Function (PDF - Continuous):** $f_X(x)$
  $$\int_{-\infty}^{\infty} f_X(x) \, dx = 1, \quad f_X(x) \ge 0, \quad P(a \le X \le b) = \int_{a}^{b} f_X(x) \, dx$$
* **Cumulative Distribution Function (CDF):** $F_X(x) = P(X \le x)$
  * *Discrete:* $F_X(x) = \sum_{k \le x} p_X(k)$
  * *Continuous:* $F_X(x) = \int_{-\infty}^{x} f_X(t) \, dt \implies f_X(x) = \frac{d}{dx} F_X(x)$
  * *Properties:* Non-decreasing, $F(-\infty) = 0$, $F(\infty) = 1$, Right-continuous ($P(a < X \le b) = F(b) - F(a)$).

---

### 2. Expectation, Moments, and Measures of Location/Dispersion
* **Expected Value (Mean $\mu$):**
  $$\mathbb{E}[X] = \begin{cases} \sum_x x \cdot p_X(x) & \text{Discrete} \\[6pt] \int_{-\infty}^{\infty} x \cdot f_X(x) \, dx & \text{Continuous} \end{cases}$$
* **Tail Formula for Expectation (Non-negative $X \ge 0$):**
  $$\mathbb{E}[X] = \sum_{k=0}^{\infty} P(X > k) \quad \text{(Discrete)}, \quad \mathbb{E}[X] = \int_{0}^{\infty} (1 - F_X(x)) \, dx \quad \text{(Continuous)}$$
* **Expected Value of a Function $g(X)$ (LOTUS):**
  $$\mathbb{E}[g(X)] = \begin{cases} \sum_x g(x) p_X(x) & \text{Discrete} \\[6pt] \int_{-\infty}^{\infty} g(x) f_X(x) \, dx & \text{Continuous} \end{cases}$$
* **Linearity of Expectation:** $\mathbb{E}[aX + b] = a\mathbb{E}[X] + b$
* **Variance ($\sigma^2$):**
  $$\text{Var}(X) = \mathbb{E}[(X - \mu)^2] = \mathbb{E}[X^2] - (\mathbb{E}[X])^2$$
  $$\text{Var}(aX + b) = a^2 \text{Var}(X)$$
* **Standard Deviation:** $\sigma_X = \sqrt{\text{Var}(X)}$
* **Coefficient of Variation:** $CV = \frac{\sigma_X}{\mu_X}$
* **Raw Moment ($k$-th):** $\mu_k' = \mathbb{E}[X^k]$
* **Central Moment ($k$-th):** $\mu_k = \mathbb{E}[(X - \mu)^k]$
* **Percentile / Quantile ($p$-th percentile $x_p$):** $F_X(x_p) = p \implies x_p = F_X^{-1}(p)$
* **Median ($m$):** $F_X(m) = 0.50$
* **Mode:** The value $x$ that maximizes $p_X(x)$ or $f_X(x)$.

---

### 3. Discrete Parametric Distributions

| Distribution | PMF: $P(X = x)$ | Mean $\mathbb{E}[X]$ | Variance $\text{Var}(X)$ | Notes / MGF |
| :--- | :--- | :--- | :--- | :--- |
| **Bernoulli($p$)** | $p^x (1-p)^{1-x}, \; x \in \{0,1\}$ | $p$ | $p(1-p)$ | $M(t) = (1-p) + pe^t$ |
| **Binomial($n, p$)** | $\binom{n}{x} p^x (1-p)^{n-x}, \; x=0,\dots,n$ | $np$ | $np(1-p)$ | $M(t) = (1-p + pe^t)^n$ |
| **Geometric($p$)** *(Trial of 1st Success)* | $(1-p)^{x-1}p, \; x=1,2,3,\dots$ | $\frac{1}{p}$ | $\frac{1-p}{p^2}$ | Memoryless: $P(X > s+t \mid X > s) = P(X > t)$ |
| **Geometric($p$)** *(Failures before 1st Success)*| $(1-p)^x p, \; x=0,1,2,\dots$ | $\frac{1-p}{p}$ | $\frac{1-p}{p^2}$ | Alternative SOA parametrization |
| **Negative Binomial($r, p$)** | $\binom{x-1}{r-1} p^r (1-p)^{x-r}, \; x=r, r+1, \dots$ | $\frac{r}{p}$ | $\frac{r(1-p)}{p^2}$ | Trial of $r$-th success |
| **Hypergeometric($N, K, n$)** | $\frac{\binom{K}{x}\binom{N-K}{n-x}}{\binom{N}{n}}, \; x=0,\dots,n$ | $n\frac{K}{N}$ | $n\frac{K}{N}\left(1-\frac{K}{N}\right)\frac{N-n}{N-1}$ | Sampling without replacement |
| **Poisson($\lambda$)** | $\frac{e^{-\lambda} \lambda^x}{x!}, \; x=0,1,2,\dots$ | $\lambda$ | $\lambda$ | $M(t) = e^{\lambda(e^t - 1)}$ |

---

### 4. Continuous Parametric Distributions

| Distribution | PDF $f(x)$ / Support | CDF $F(x)$ | Mean $\mathbb{E}[X]$ | Variance $\text{Var}(X)$ |
| :--- | :--- | :--- | :--- | :--- |
| **Continuous Uniform($a, b$)** | $\frac{1}{b-a}, \; x \in [a, b]$ | $\frac{x-a}{b-a}$ | $\frac{a+b}{2}$ | $\frac{(b-a)^2}{12}$ |
| **Exponential($\theta$)** *(Scale $\theta$)* | $\frac{1}{\theta} e^{-x/\theta}, \; x \ge 0$ | $1 - e^{-x/\theta}$ | $\theta$ | $\theta^2$ |
| **Exponential($\lambda$)** *(Rate $\lambda$)* | $\lambda e^{-\lambda x}, \; x \ge 0$ | $1 - e^{-\lambda x}$ | $\frac{1}{\lambda}$ | $\frac{1}{\lambda^2}$ |
| **Gamma($\alpha, \theta$)** | $\frac{x^{\alpha-1} e^{-x/\theta}}{\theta^\alpha \Gamma(\alpha)}, \; x \ge 0$ | Incomplete Gamma | $\alpha\theta$ | $\alpha\theta^2$ |
| **Normal($\mu, \sigma^2$)** | $\frac{1}{\sigma\sqrt{2\pi}} e^{-\frac{1}{2}\left(\frac{x-\mu}{\sigma}\right)^2}$ | $\Phi\left(\frac{x-\mu}{\sigma}\right)$ | $\mu$ | $\sigma^2$ |
| **Pareto($\alpha, \theta$)** | $\frac{\alpha \theta^\alpha}{(x+\theta)^{\alpha+1}}, \; x \ge 0$ | $1 - \left(\frac{\theta}{x+\theta}\right)^\alpha$ | $\frac{\theta}{\alpha-1} \; (\alpha > 1)$ | $\frac{\alpha \theta^2}{(\alpha-1)^2(\alpha-2)} \; (\alpha > 2)$ |

* **Exponential Memoryless Property:** $P(X > s + t \mid X > s) = P(X > t) = e^{-t/\theta}$
* **Standard Normal Transformation ($Z$-score):** $Z = \frac{X - \mu}{\sigma} \sim N(0, 1)$

---

### 5. Insurance Policy Modifications & Loss/Payment Variables
Let $X$ be the ground-up loss random variable ($X \ge 0$).

#### A. Ordinary Deductible ($d$)
* **Payment per loss variable ($Y^L$):**
  $$Y^L = (X - d)_+ = \max(0, X - d) = \begin{cases} 0 & X \le d \\ X - d & X > d \end{cases}$$
  $$\mathbb{E}[Y^L] = \int_{d}^{\infty} (x - d) f_X(x) \, dx = \int_{d}^{\infty} (1 - F_X(x)) \, dx$$
* **Payment per claim variable ($Y^C$):**
  $$Y^C = (X - d \mid X > d)$$
  $$\mathbb{E}[Y^C] = \frac{\mathbb{E}[Y^L]}{P(X > d)} = \frac{\mathbb{E}[Y^L]}{1 - F_X(d)}$$

#### B. Benefit Limit / Policy Maximum ($u$)
* **Coverage limited to maximum loss $u$:**
  $$Y = \min(X, u) = \begin{cases} X & X < u \\ u & X \ge u \end{cases}$$
  $$\mathbb{E}[\min(X, u)] = \int_{0}^{u} x f_X(x) \, dx + u(1 - F_X(u)) = \int_{0}^{u} (1 - F_X(x)) \, dx$$

#### C. Deductible ($d$) AND Maximum Limit ($u$)
* **Maximum payment capped at $u - d$:**
  $$Y^L = \begin{cases} 0 & X \le d \\ X - d & d < X < u \\ u - d & X \ge u \end{cases}$$
  $$\mathbb{E}[Y^L] = \int_{d}^{u} (1 - F_X(x)) \, dx$$

#### D. Coinsurance ($c$) and Inflation ($r$)
* **With Coinsurance factor $c \in (0, 1]$:** $Y^L = c \cdot (X - d)_+$
* **With Inflation rate $r$ (Loss becomes $X(1+r)$):**
  $$\mathbb{E}[\text{Payment with inflation}] = (1+r) \int_{d/(1+r)}^{\infty} \left(x - \frac{d}{1+r}\right) f_X(x) \, dx$$

---

## Phase 3: Multivariate Random Variables

### 1. Joint, Marginal, and Conditional Distributions

#### A. Discrete Joint Distributions
* **Joint PMF:** $p_{X,Y}(x, y) = P(X = x, Y = y)$ where $\sum_x \sum_y p_{X,Y}(x, y) = 1$
* **Marginal PMFs:**
  $$p_X(x) = \sum_y p_{X,Y}(x, y), \quad p_Y(y) = \sum_x p_{X,Y}(x, y)$$
* **Conditional PMF:**
  $$p_{Y \mid X}(y \mid x) = P(Y = y \mid X = x) = \frac{p_{X,Y}(x, y)}{p_X(x)}$$

#### B. Continuous Joint Distributions
* **Joint PDF:** $f_{X,Y}(x, y)$ where $\int_{-\infty}^{\infty} \int_{-\infty}^{\infty} f_{X,Y}(x, y) \, dx \, dy = 1$
* **Joint CDF:**
  $$F_{X,Y}(x, y) = P(X \le x, Y \le y) = \int_{-\infty}^{x} \int_{-\infty}^{y} f_{X,Y}(u, v) \, dv \, du$$
  $$f_{X,Y}(x,y) = \frac{\partial^2}{\partial x \partial y} F_{X,Y}(x,y)$$
* **Marginal PDFs:**
  $$f_X(x) = \int_{-\infty}^{\infty} f_{X,Y}(x, y) \, dy, \quad f_Y(y) = \int_{-\infty}^{\infty} f_{X,Y}(x, y) \, dx$$
* **Conditional PDFs:**
  $$f_{Y \mid X}(y \mid x) = \frac{f_{X,Y}(x, y)}{f_X(x)}, \quad f_{X \mid Y}(x \mid y) = \frac{f_{X,Y}(x, y)}{f_Y(y)}$$
* **Joint Independence:** $X$ and $Y$ are independent if and only if:
  $$f_{X,Y}(x, y) = f_X(x) \cdot f_Y(y) \quad \text{for all } (x, y)$$

---

### 2. Expectation, Covariance, and Correlation

#### A. Expectations of Joint Functions
$$\mathbb{E}[g(X, Y)] = \begin{cases} \sum_x \sum_y g(x, y) p_{X,Y}(x, y) & \text{Discrete} \\[6pt] \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} g(x, y) f_{X,Y}(x, y) \, dx \, dy & \text{Continuous} \end{cases}$$

#### B. Conditional Expectation & Variance
* **Conditional Expectation:**
  $$\mathbb{E}[Y \mid X = x] = \int_{-\infty}^{\infty} y f_{Y \mid X}(y \mid x) \, dy$$
* **Law of Total Expectation (Double Expectation):**
  $$\mathbb{E}[Y] = \mathbb{E}[\mathbb{E}[Y \mid X]]$$
* **Conditional Variance:**
  $$\text{Var}(Y \mid X = x) = \mathbb{E}[Y^2 \mid X = x] - (\mathbb{E}[Y \mid X = x])^2$$
* **Law of Total Variance (EVVE Rule):**
  $$\text{Var}(Y) = \mathbb{E}[\text{Var}(Y \mid X)] + \text{Var}(\mathbb{E}[Y \mid X])$$

#### C. Covariance & Correlation Coefficient
* **Covariance Definition:**
  $$\text{Cov}(X, Y) = \mathbb{E}[(X - \mu_X)(Y - \mu_Y)] = \mathbb{E}[XY] - \mathbb{E}[X]\mathbb{E}[Y]$$
  *(Note: If $X$ and $Y$ are independent, $\text{Cov}(X, Y) = 0$. The converse is not generally true).*
* **Covariance Properties:**
  $$\text{Cov}(X, X) = \text{Var}(X)$$
  $$\text{Cov}(aX + b, cY + d) = ac \, \text{Cov}(X, Y)$$
  $$\text{Cov}(X + Y, Z) = \text{Cov}(X, Z) + \text{Cov}(Y, Z)$$
* **Pearson Correlation Coefficient ($\rho$):**
  $$\rho_{X,Y} = \frac{\text{Cov}(X, Y)}{\sigma_X \sigma_Y} \quad \text{where } -1 \le \rho_{X,Y} \le 1$$

---

### 3. Linear Combinations of Random Variables
Let $L = aX + bY + c$:

* **Expectation of Linear Combination:**
  $$\mathbb{E}[aX + bY + c] = a\mathbb{E}[X] + b\mathbb{E}[Y] + c$$
* **Variance of General Linear Combination:**
  $$\text{Var}(aX + bY) = a^2 \text{Var}(X) + b^2 \text{Var}(Y) + 2ab \, \text{Cov}(X, Y)$$
* **Variance of Linear Combination (Independent $X, Y$):**
  $$\text{Var}(aX + bY) = a^2 \text{Var}(X) + b^2 \text{Var}(Y)$$
* **General $n$-Variable Linear Combination $S = \sum_{i=1}^{n} a_i X_i$:**
  $$\mathbb{E}[S] = \sum_{i=1}^{n} a_i \mathbb{E}[X_i]$$
  $$\text{Var}(S) = \sum_{i=1}^{n} a_i^2 \text{Var}(X_i) + 2 \sum_{1 \le i < j \le n} a_i a_j \text{Cov}(X_i, X_j)$$

---

### 4. Order Statistics
Let $X_1, X_2, \dots, X_n$ be independent and identically distributed (i.i.d.) random variables with common PDF $f(x)$ and CDF $F(x)$. Arrange in ascending order: $Y_{(1)} \le Y_{(2)} \le \dots \le Y_{(n)}$.

#### A. Maximum Order Statistic $Y_{(n)} = \max(X_1, \dots, X_n)$
* **CDF:** $F_{Y_{(n)}}(y) = [F(y)]^n$
* **PDF:** $f_{Y_{(n)}}(y) = n [F(y)]^{n-1} f(y)$

#### B. Minimum Order Statistic $Y_{(1)} = \min(X_1, \dots, X_n)$
* **CDF:** $F_{Y_{(1)}}(y) = 1 - [1 - F(y)]^n$
* **PDF:** $f_{Y_{(1)}}(y) = n [1 - F(y)]^{n-1} f(y)$

#### C. General $k$-th Order Statistic $Y_{(k)}$
* **PDF:**
  $$f_{Y_{(k)}}(y) = \frac{n!}{(k-1)! (n-k)!} [F(y)]^{k-1} [1 - F(y)]^{n-k} f(y)$$

---

### 5. Central Limit Theorem (CLT) & Normal Approximations
Let $X_1, X_2, \dots, X_n$ be i.i.d. random variables with mean $\mu$ and variance $\sigma^2 < \infty$.

* **Sum Distribution ($S_n = \sum_{i=1}^{n} X_i$):**
  $$\mathbb{E}[S_n] = n\mu, \quad \text{Var}(S_n) = n\sigma^2$$
  $$S_n \approx N(n\mu, n\sigma^2) \quad \text{as } n \to \infty$$
* **Sample Mean Distribution ($\bar{X}_n = \frac{1}{n} S_n$):**
  $$\mathbb{E}[\bar{X}_n] = \mu, \quad \text{Var}(\bar{X}_n) = \frac{\sigma^2}{n}$$
  $$\bar{X}_n \approx N\left(\mu, \frac{\sigma^2}{n}\right) \quad \text{as } n \to \infty$$
* **Standardized CLT $Z$-score:**
  $$Z = \frac{S_n - n\mu}{\sigma \sqrt{n}} = \frac{\bar{X}_n - \mu}{\sigma / \sqrt{n}} \xrightarrow{d} N(0, 1)$$
* **Continuity Correction (Discrete to Continuous Normal):**
  For integer-valued $S_n$, approximate $P(a \le S_n \le b)$ using:
  $$P(a - 0.5 \le S_n \le b + 0.5) \approx P\left( \frac{a - 0.5 - n\mu}{\sigma \sqrt{n}} \le Z \le \frac{b + 0.5 - n\mu}{\sigma \sqrt{n}} \right)$$
