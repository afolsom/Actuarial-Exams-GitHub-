# Phase 3 Study Guide: Multivariate Random Variables (Days 25–33)
**Actuarial Exam P | Weight: 23–30%**

---

## Overview & Exam Strategy for Phase 3
Phase 3 transitions from single random variables to systems of multiple random variables. Double integration, region setup, marginalization, conditional distributions, covariance, order statistics, and the Central Limit Theorem form the core of this section.

### Key Skills Tested:
1. **Setting Up Integration Bounds:** Translating non-rectangular domains (triangles, trapezoids, circles) into double integrals.
2. **Conditional Distributions & Expectations:** Finding $f_{Y|X}(y|x)$, $E[Y|X=x]$, and $Var(Y|X=x)$.
3. **Law of Total Expectation & Variance:** Breaking down compound random variables using $E[Y] = E[E[Y|X]]$ and $Var(Y) = E[Var(Y|X)] + Var(E[Y|X])$.
4. **Covariance & Linear Combinations:** Calculating $Cov(X,Y)$ and $Var(aX + bY + c)$.
5. **Order Statistics:** Computing densities and probabilities for $\min(X_1, \dots, X_n)$ and $\max(X_1, \dots, X_n)$.
6. **Central Limit Theorem:** Approximating aggregate losses $\sum X_i$ or average claims $\bar{X}$ using the Normal distribution.

---

## Day 25 (Session 3A.1): Joint Probability Functions & Joint CDFs

### 1. Core Concepts & Definitions
When observing two random variables $(X, Y)$ simultaneously:

#### Discrete Joint PMF:
$$p_{X,Y}(x, y) = P(X = x, Y = y)$$
* **Properties:**
  1. $p_{X,Y}(x, y) \ge 0$ for all $(x,y)$
  2. $\sum_x \sum_y p_{X,Y}(x, y) = 1$

#### Continuous Joint PDF:
$$P((X, Y) \in R) = \iint_R f_{X,Y}(x, y) \, dx \, dy$$
* **Properties:**
  1. $f_{X,Y}(x, y) \ge 0$ for all $(x,y)$
  2. $\int_{-\infty}^{\infty} \int_{-\infty}^{\infty} f_{X,Y}(x, y) \, dx \, dy = 1$

#### Joint Cumulative Distribution Function (CDF):
$$F_{X,Y}(x, y) = P(X \le x, Y \le y)$$
* **Continuous Recovery of PDF:**
  $$f_{X,Y}(x, y) = \frac{\partial^2}{\partial x \partial y} F_{X,Y}(x, y)$$
* **Probability of Rectangular Region $[a, b] \times [c, d]$:**
  $$P(a < X \le b, c < Y \le d) = F(b, d) - F(a, d) - F(b, c) + F(a, c)$$

---

### 2. Common Domain Setups for Continuous Joint PDFs
Setting up bounds correctly is the most critical step on Exam P:

| Domain Shape | Example Bounds Setup | Integration Strategy |
| :--- | :--- | :--- |
| **Rectangle ($0 \le x \le a, 0 \le y \le b$)** | $\int_{0}^{b} \int_{0}^{a} f(x,y) \, dx \, dy$ | Inner and outer bounds are constants. |
| **Triangle ($0 \le x \le y \le 1$)** | $\int_{0}^{1} \int_{0}^{y} f(x,y) \, dx \, dy$ or $\int_{0}^{1} \int_{x}^{1} f(x,y) \, dy \, dx$ | Inner bounds depend on the outer variable. |
| **Bounded Region ($0 \le x+y \le 1, x \ge 0, y \ge 0$)** | $\int_{0}^{1} \int_{0}^{1-x} f(x,y) \, dy \, dx$ | Integrate $y$ from $0$ to $1-x$, then $x$ from $0$ to $1$. |

---

### 3. Worked Actuarial Example
**Problem:** The joint PDF of losses $X$ (auto claim) and $Y$ (home claim) in thousands of dollars is given by:
$$f(x, y) = c(x + y), \quad 0 \le x \le 1, \, 0 \le y \le 2, \, x + y \le 2$$

Find the normalizing constant $c$ and calculate $P(X + Y \le 1)$.

**Solution:**
1. **Find $c$:**
   $$\int_{0}^{1} \int_{0}^{2-x} c(x + y) \, dy \, dx = 1$$
   Evaluate inner integral with respect to $y$:
   $$\int_{0}^{2-x} (x+y) \, dy = \left[ xy + \frac{y^2}{2} \right]_{0}^{2-x} = x(2-x) + \frac{(2-x)^2}{2} = 2x - x^2 + \frac{4 - 4x + x^2}{2} = 2 - \frac{x^2}{2}$$
   Evaluate outer integral with respect to $x$:
   $$c \int_{0}^{1} \left( 2 - \frac{x^2}{2} \right) dx = c \left[ 2x - \frac{x^3}{6} \right]_{0}^{1} = c \left( 2 - \frac{1}{6} \right) = \frac{11}{6} c = 1 \implies c = \frac{6}{11}$$

2. **Calculate $P(X + Y \le 1)$:**
   $$P(X + Y \le 1) = \int_{0}^{1} \int_{0}^{1-x} \frac{6}{11} (x + y) \, dy \, dx$$
   Inner integral:
   $$\int_{0}^{1-x} (x+y) \, dy = \left[ xy + \frac{y^2}{2} \right]_{0}^{1-x} = x(1-x) + \frac{(1-x)^2}{2} = \frac{1 - x^2}{2}$$
   Outer integral:
   $$\frac{6}{11} \int_{0}^{1} \frac{1 - x^2}{2} \, dx = \frac{3}{11} \left[ x - \frac{x^3}{3} \right]_{0}^{1} = \frac{3}{11} \left( \frac{2}{3} \right) = \mathbf{\frac{2}{11}}$$

---

## Day 26 (Session 3B.1): Marginal & Conditional Distributions

### 1. Core Formulas

#### Marginal Distributions (Collapsing one variable):
* **Discrete:**
  $$p_X(x) = \sum_{y} p(x,y), \quad p_Y(y) = \sum_{x} p(x,y)$$
* **Continuous:**
  $$f_X(x) = \int_{-\infty}^{\infty} f(x,y) \, dy, \quad f_Y(y) = \int_{-\infty}^{\infty} f(x,y) \, dx$$

#### Conditional Distributions (Given a fixed value):
* **Conditional Density of $Y$ given $X = x$:**
  $$f_{Y|X}(y|x) = \frac{f(x,y)}{f_X(x)}, \quad \text{for } f_X(x) > 0$$
* **Conditional Density of $X$ given $Y = y$:**
  $$f_{X|Y}(x|y) = \frac{f(x,y)}{f_Y(y)}, \quad \text{for } f_Y(y) > 0$$

---

### 2. Criteria for Independence of $X$ and $Y$
Two continuous random variables $X$ and $Y$ are **independent** if and only if **BOTH** conditions are satisfied:
1. **Factorization of PDF:** $f(x,y) = f_X(x) \cdot f_Y(y)$ for all $(x,y)$, OR $f(x,y) = g(x) \cdot h(y)$.
2. **Separable Support Region:** The support region $S$ must be rectangular aligned with the axes:
   $$S = \{ (x,y) \mid a \le x \le b, \, c \le y \le d \}$$
   *(If the support region is triangular or dependent such as $0 \le x \le y \le 1$, $X$ and $Y$ are AUTOMATICALLY DEPENDENT!)*

---

### 3. Worked Actuarial Example
**Problem:** Let $X$ and $Y$ have joint PDF $f(x,y) = 8xy$ for $0 < x < y < 1$.
1. Find the marginal density $f_X(x)$.
2. Find the conditional density $f_{Y|X}(y|x)$.
3. Calculate $P\left( Y > \frac{1}{2} \;\middle|\; X = \frac{1}{4} \right)$.

**Solution:**
1. **Marginal $f_X(x)$:**
   Integrate $y$ over its valid bounds given $x$ (from $y = x$ to $y = 1$):
   $$f_X(x) = \int_{x}^{1} 8xy \, dy = \left[ 4xy^2 \right]_{x}^{1} = 4x(1 - x^2) = 4x - 4x^3, \quad 0 < x < 1$$

2. **Conditional Density $f_{Y|X}(y|x)$:**
   $$f_{Y|X}(y|x) = \frac{f(x,y)}{f_X(x)} = \frac{8xy}{4x(1 - x^2)} = \frac{2y}{1 - x^2}, \quad \text{for } x < y < 1$$

3. **Calculate Conditional Probability:**
   For $X = \frac{1}{4}$, the conditional density of $Y$ is:
   $$f_{Y|X}\left(y \;\middle|\; \frac{1}{4}\right) = \frac{2y}{1 - (1/4)^2} = \frac{2y}{15/16} = \frac{32}{15} y, \quad \frac{1}{4} < y < 1$$
   Calculate probability $P\left(Y > \frac{1}{2} \;\middle|\; X = \frac{1}{4}\right)$:
   $$P\left(Y > \frac{1}{2} \;\middle|\; X = \frac{1}{4}\right) = \int_{1/2}^{1} \frac{32}{15} y \, dy = \left[ \frac{16}{15} y^2 \right]_{1/2}^{1} = \frac{16}{15} \left( 1 - \frac{1}{4} \right) = \frac{16}{15} \left( \frac{3}{4} \right) = \mathbf{\frac{4}{5}}$$

---

## Day 27 (Session 3C.1): Joint Moments & Conditional Expectations

### 1. Key Definitions & Formulas

#### Joint Expectation of $g(X,Y)$:
* **Continuous Case:**
  $$E[g(X,Y)] = \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} g(x,y) f(x,y) \, dx \, dy$$
* **Special Case $g(X,Y) = XY$:**
  $$E[XY] = \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} xy f(x,y) \, dx \, dy$$

#### Conditional Expectation:
* **Conditional Expectation of $Y$ given $X = x$:**
  $$E[Y | X = x] = \int_{-\infty}^{\infty} y \cdot f_{Y|X}(y|x) \, dy$$
  *(Note: $E[Y|X=x]$ is a function of $x$. $E[Y|X]$ is a random variable that depends on $X$.)*

#### Law of Total Expectation (Double Expectation Rule):
$$E[Y] = E_X \left[ E_{Y|X}[Y | X] \right]$$
* **Continuous Form:** $E[Y] = \int_{-\infty}^{\infty} E[Y | X = x] f_X(x) \, dx$
* **Discrete Form:** $E[Y] = \sum_x E[Y | X = x] P(X = x)$

---

### 2. Worked Actuarial Example
**Problem:** An insurance company models claim counts $N$ and claim severity $X$. $N$ follows a Poisson distribution with mean $\Lambda$, where $\Lambda$ itself is a continuous random variable uniformly distributed on $[1, 3]$. 

Calculate the expected total claim count $E[N]$.

**Solution:**
1. Given conditional distribution: $N | \Lambda = \lambda \sim Poisson(\lambda) \implies E[N | \Lambda = \lambda] = \lambda$.
2. Thus, the conditional expectation random variable is $E[N | \Lambda] = \Lambda$.
3. Apply the Law of Total Expectation:
   $$E[N] = E[E[N | \Lambda]] = E[\Lambda]$$
4. Since $\Lambda \sim Uniform(1, 3)$, its expectation is:
   $$E[\Lambda] = \frac{1 + 3}{2} = \mathbf{2}$$

---

## Day 28 (Session 3D.1): Conditional Variance & Law of Total Variance

### 1. Core Formulas

#### Conditional Variance of $Y$ given $X = x$:
$$Var(Y | X = x) = E[Y^2 | X = x] - \left( E[Y | X = x] \right)^2$$
Alternatively:
$$Var(Y | X = x) = \int_{-\infty}^{\infty} (y - E[Y|X=x])^2 f_{Y|X}(y|x) \, dy$$

#### Law of Total Variance (EVVE Rule):
$$\mathbf{Var(Y) = E[Var(Y|X)] + Var(E[Y|X])}$$

* **Verbal Mnemonic:** "Expected Value of Variance plus Variance of Expected Value" (EVVE).
* **Component Meaning:**
  1. $E[Var(Y|X)]$: The average within-group variation.
  2. $Var(E[Y|X])$: The variation between group means.

---

### 2. Step-by-Step Procedure for EVVE Rule

1. Compute $E[Y | X]$ as a function of $X$, say $h(X)$.
2. Compute $Var(Y | X)$ as a function of $X$, say $g(X)$.
3. Take the expectation of $g(X)$ to find $E[Var(Y|X)]$.
4. Take the variance of $h(X)$ to find $Var(E[Y|X])$.
5. Sum the two values: $Var(Y) = E[g(X)] + Var(h(X))$.

---

### 3. Worked Actuarial Example
**Problem:** The number of workplace injuries $N$ in a factory on a given day follows a Poisson distribution with parameter $\lambda$. The parameter $\lambda$ varies daily according to a Uniform distribution on $[0, 3]$.

Calculate $Var(N)$.

**Solution:**
1. **Identify Conditional Moments:**
   Given $\lambda$, $N | \lambda \sim Poisson(\lambda)$.
   * $E[N | \lambda] = \lambda$
   * $Var(N | \lambda) = \lambda$

2. **Compute Components for Law of Total Variance:**
   * $E[Var(N | \lambda)] = E[\lambda]$
   * $Var(E[N | \lambda]) = Var(\lambda)$

3. **Calculate Moments of $\lambda \sim Uniform(0, 3)$:**
   * $E[\lambda] = \frac{0 + 3}{2} = 1.5$
   * $Var(\lambda) = \frac{(3 - 0)^2}{12} = \frac{9}{12} = 0.75$

4. **Apply EVVE Rule:**
   $$Var(N) = E[Var(N|\lambda)] + Var(E[N|\lambda]) = E[\lambda] + Var(\lambda)$$
   $$Var(N) = 1.5 + 0.75 = \mathbf{2.25}$$

---

## Day 29 (Session 3E.1): Covariance & Correlation Coefficient

### 1. Key Definitions & Operational Formulas

#### Covariance:
$$Cov(X, Y) = E[(X - \mu_X)(Y - \mu_Y)] = E[XY] - E[X]E[Y]$$

#### Properties of Covariance:
1. $Cov(X, X) = Var(X)$
2. $Cov(X, Y) = Cov(Y, X)$
3. $Cov(aX + b, cY + d) = ac \cdot Cov(X, Y)$
4. $Cov(X + Y, Z) = Cov(X, Z) + Cov(Y, Z)$

#### Correlation Coefficient ($\rho_{X,Y}$):
$$\rho_{X,Y} = \frac{Cov(X,Y)}{\sigma_X \sigma_Y} = \frac{Cov(X,Y)}{\sqrt{Var(X) Var(Y)}}$$
* **Range:** $-1 \le \rho_{X,Y} \le 1$
* **Interpretation:**
  * $\rho = +1$: Perfect positive linear relationship.
  * $\rho = -1$: Perfect negative linear relationship.
  * $\rho = 0$: Uncorrelated (no linear relationship).

#### Independence vs. Uncorrelatedness:
$$\text{Independent} \implies Cov(X,Y) = 0 \quad (\rho = 0)$$
$$\mathbf{Cov(X,Y) = 0 \;\nRightarrow\; \text{Independent!}}$$
*(Zero covariance means no **linear** relationship; nonlinear dependency can still exist.)*

#### Variance of Linear Combinations:
$$Var(aX + bY + c) = a^2 Var(X) + b^2 Var(Y) + 2ab \, Cov(X,Y)$$
$$Var(aX - bY + c) = a^2 Var(X) + b^2 Var(Y) - 2ab \, Cov(X,Y)$$

---

### 2. Worked Actuarial Example
**Problem:** An actuary analyzes personal auto claims $M$ and commercial auto claims $N$. You are given:
* $Var(M) = 1600$
* $Var(N) = 900$
* Correlation $\rho_{M,N} = 0.64$

Calculate $Var(M + N)$ and $Var(M - 2N + 5)$.

**Solution:**
1. **Find Covariance $Cov(M,N)$:**
   $$\rho_{M,N} = \frac{Cov(M,N)}{\sigma_M \sigma_N} \implies Cov(M,N) = \rho_{M,N} \sqrt{Var(M)} \sqrt{Var(N)}$$
   $$Cov(M,N) = 0.64 \times \sqrt{1600} \times \sqrt{900} = 0.64 \times 40 \times 30 = 768$$

2. **Calculate $Var(M + N)$:**
   $$Var(M + N) = Var(M) + Var(N) + 2 Cov(M,N)$$
   $$Var(M + N) = 1600 + 900 + 2(768) = 2500 + 1536 = \mathbf{4036}$$

3. **Calculate $Var(M - 2N + 5)$:**
   $$Var(M - 2N + 5) = 1^2 Var(M) + (-2)^2 Var(N) + 2(1)(-2) Cov(M,N)$$
   $$Var(M - 2N + 5) = 1600 + 4(900) - 4(768) = 1600 + 3600 - 3072 = \mathbf{2128}$$

---

## Day 30 (Session 3F.1): Order Statistics

### 1. Definitions & Formulas for Independent R.V.s
Let $X_1, X_2, \dots, X_n$ be $n$ independent and identically distributed (i.i.d.) continuous random variables with CDF $F(x)$ and PDF $f(x)$.

When arranged in increasing order:
$$X_{(1)} \le X_{(2)} \le \dots \le X_{(n)}$$
* $X_{(1)} = \min(X_1, X_2, \dots, X_n)$ (Smallest / Minimum order statistic)
* $X_{(n)} = \max(X_1, X_2, \dots, X_n)$ (Largest / Maximum order statistic)

---

### 2. Maximum Order Statistic $Y = X_{(n)} = \max(X_i)$

* **CDF of Maximum:**
  $$F_{(n)}(y) = P(\max(X_i) \le y) = P(X_1 \le y, X_2 \le y, \dots, X_n \le y) = [F(y)]^n$$
* **PDF of Maximum:**
  $$f_{(n)}(y) = \frac{d}{dy} [F(y)]^n = n [F(y)]^{n-1} f(y)$$

---

### 3. Minimum Order Statistic $Y = X_{(1)} = \min(X_i)$

* **Survival Function of Minimum:**
  $$S_{(1)}(y) = P(\min(X_i) > y) = P(X_1 > y, X_2 > y, \dots, X_n > y) = [S(y)]^n = [1 - F(y)]^n$$
* **CDF of Minimum:**
  $$F_{(1)}(y) = 1 - [1 - F(y)]^n$$
* **PDF of Minimum:**
  $$f_{(1)}(y) = n [1 - F(y)]^{n-1} f(y)$$

---

### 4. Special Case: Exponential Order Statistics
If $X_1, X_2, \dots, X_n \stackrel{\text{i.i.d.}}{\sim} Exp(\lambda)$ (where $E[X] = 1/\lambda$):
* **Minimum $X_{(1)}$:**
  $$X_{(1)} \sim Exp(n\lambda)$$
  Expected minimum time: $E[X_{(1)}] = \frac{1}{n\lambda}$.

---

### 5. Worked Actuarial Example
**Problem:** A machine has 3 identical components operating independently. The lifetime $X$ of each component in years has PDF:
$$f(x) = \frac{2}{x^3}, \quad x > 1$$
Calculate the probability that the largest of the 3 component lifetimes is less than 2.5.

**Solution:**
1. **Find individual CDF $F(x)$:**
   $$F(x) = \int_{1}^{x} 2t^{-3} \, dt = \left[ -t^{-2} \right]_{1}^{x} = 1 - \frac{1}{x^2}, \quad x > 1$$

2. **Calculate $F(2.5)$:**
   $$F(2.5) = 1 - \frac{1}{2.5^2} = 1 - \frac{1}{6.25} = 1 - 0.16 = 0.84$$

3. **Apply CDF formula for Maximum ($n=3$):**
   $$P(X_{(3)} < 2.5) = [F(2.5)]^3 = (0.84)^3 = \mathbf{0.5927}$$

---

## Day 31 (Session 3G.1): Linear Combinations & Bivariate Normal Distributions

### 1. Bivariate Normal Distribution Properties
If $(X, Y)$ follow a Bivariate Normal distribution with parameters $(\mu_X, \mu_Y, \sigma_X^2, \sigma_Y^2, \rho)$:

#### Marginal Distributions:
$$X \sim N(\mu_X, \sigma_X^2), \quad Y \sim N(\mu_Y, \sigma_Y^2)$$

#### Conditional Distribution of $Y$ given $X = x$:
$$Y | X = x \sim N(\mu_{Y|X}, \sigma_{Y|X}^2)$$
Where:
* **Conditional Mean:** $\mu_{Y|X} = E[Y | X = x] = \mu_Y + \rho \frac{\sigma_Y}{\sigma_X} (x - \mu_X)$
* **Conditional Variance:** $\sigma_{Y|X}^2 = Var(Y | X = x) = \sigma_Y^2 (1 - \rho^2)$

#### Linear Combination of Bivariate Normals:
For any constants $a$ and $b$, $W = aX + bY$ is **normally distributed**:
$$W \sim N\left( a\mu_X + b\mu_Y, \; a^2 \sigma_X^2 + b^2 \sigma_Y^2 + 2ab \rho \sigma_X \sigma_Y \right)$$

---

### 2. Worked Actuarial Example
**Problem:** Total annual auto claims $X$ and property claims $Y$ follow a Bivariate Normal distribution with:
* $\mu_X = 15, \, \sigma_X = 4$
* $\mu_Y = 20, \, \sigma_Y = 5$
* Correlation $\rho = 0.50$

Calculate $P(Y > 22 \mid X = 19)$.

**Solution:**
1. **Find Conditional Mean $E[Y \mid X = 19]$:**
   $$E[Y \mid X = 19] = \mu_Y + \rho \frac{\sigma_Y}{\sigma_X} (19 - \mu_X) = 20 + 0.50 \left( \frac{5}{4} \right) (19 - 15)$$
   $$E[Y \mid X = 19] = 20 + 0.50 (1.25)(4) = 20 + 2.5 = 22.5$$

2. **Find Conditional Variance $Var(Y \mid X = 19)$:**
   $$Var(Y \mid X = 19) = \sigma_Y^2 (1 - \rho^2) = 5^2 (1 - 0.50^2) = 25 (1 - 0.25) = 18.75$$
   $$\sigma_{Y|X=19} = \sqrt{18.75} \approx 4.33$$

3. **Standardize and Compute Probability:**
   $$P(Y > 22 \mid X = 19) = P\left( Z > \frac{22 - 22.5}{4.33} \right) = P(Z > -0.115) = \Phi(0.115) \approx \mathbf{0.5458}$$

---

## Day 32 (Session 3H.1): Sums & Distributions of Independent Random Variables

### 1. Closure Properties Under Addition
When adding independent random variables from the same family, their sums follow specific distributions:

| Distribution Family | Individual Variables | Sum $S_n = \sum X_i$ Distribution |
| :--- | :--- | :--- |
| **Normal** | $X_i \sim N(\mu_i, \sigma_i^2)$ | $S_n \sim N\left(\sum \mu_i, \sum \sigma_i^2\right)$ |
| **Poisson** | $X_i \sim Poisson(\lambda_i)$ | $S_n \sim Poisson\left(\sum \lambda_i\right)$ |
| **Gamma (Same Scale $\theta$)** | $X_i \sim Gamma(\alpha_i, \theta)$ | $S_n \sim Gamma\left(\sum \alpha_i, \theta\right)$ |
| **Exponential (Same Scale $\theta$)** | $X_i \sim Exp(\theta) \equiv Gamma(1, \theta)$ | $S_n \sim Gamma(n, \theta)$ |
| **Binomial (Same $p$)** | $X_i \sim Bin(n_i, p)$ | $S_n \sim Bin\left(\sum n_i, p\right)$ |
| **Negative Binomial (Same $p$)** | $X_i \sim NegBin(r_i, p)$ | $S_n \sim NegBin\left(\sum r_i, p\right)$ |

---

### 2. General Expectation and Variance Formulas for Sums
For any random variables $X_1, X_2, \dots, X_n$:
* **Linearly Unconditional Expectation:**
  $$E\left[ \sum_{i=1}^{n} a_i X_i \right] = \sum_{i=1}^{n} a_i E[X_i]$$
* **Variance for Independent Variables:**
  $$Var\left( \sum_{i=1}^{n} a_i X_i \right) = \sum_{i=1}^{n} a_i^2 Var(X_i)$$

---

### 3. Worked Actuarial Example
**Problem:** An insurance company sells auto policies to a trucking company and a shuttle service. Claims from the trucking company $N_1 \sim Poisson(2)$ and shuttle service $N_2 \sim Poisson(3)$ are independent.

Calculate $P(N_1 = 2 \mid N_1 + N_2 = 5)$.

**Solution:**
1. Sum of independent Poisson variables: $S = N_1 + N_2 \sim Poisson(2 + 3 = 5)$.
2. The conditional distribution of $N_1$ given $N_1 + N_2 = s$ is **Binomial**:
   $$N_1 \mid (N_1 + N_2 = s) \sim Binomial\left(s, \, p = \frac{\lambda_1}{\lambda_1 + \lambda_2}\right)$$
   Here, $s = 5$ and $p = \frac{2}{2 + 3} = 0.40$.
3. Compute Binomial probability:
   $$P(N_1 = 2 \mid S = 5) = \binom{5}{2} (0.40)^2 (0.60)^{5-2} = 10 \times 0.16 \times 0.216 = \mathbf{0.3456}$$

---

## Day 33 (Session 3I.1): Central Limit Theorem (CLT)

### 1. Statement of the Central Limit Theorem
Let $X_1, X_2, \dots, X_n$ be a sequence of $n$ independent and identically distributed (i.i.d.) random variables with mean $E[X_i] = \mu$ and finite variance $Var(X_i) = \sigma^2$.

As $n$ becomes large ($n \ge 30$):

#### Total Sum $S_n = \sum_{i=1}^{n} X_i$:
$$S_n \approx N\left( n\mu, \, n\sigma^2 \right)$$
Standardized Z-score:
$$Z = \frac{S_n - n\mu}{\sigma \sqrt{n}} \sim N(0, 1)$$

#### Sample Mean $\bar{X}_n = \frac{1}{n} \sum_{i=1}^{n} X_i$:
$$\bar{X}_n \approx N\left( \mu, \, \frac{\sigma^2}{n} \right)$$
Standardized Z-score:
$$Z = \frac{\bar{X}_n - \mu}{\sigma / \sqrt{n}} \sim N(0, 1)$$

---

### 2. Continuity Correction (For Discrete Approximations)
When approximating a discrete sum $S_n$ taking integer values using a continuous Normal distribution:
* $P(S_n \le k) \approx P\left( Z \le \frac{(k + 0.5) - n\mu}{\sigma \sqrt{n}} \right)$
* $P(S_n \ge k) \approx P\left( Z \ge \frac{(k - 0.5) - n\mu}{\sigma \sqrt{n}} \right)$
* $P(S_n = k) \approx P\left( \frac{(k - 0.5) - n\mu}{\sigma \sqrt{n}} \le Z \le \frac{(k + 0.5) - n\mu}{\sigma \sqrt{n}} \right)$

---

### 3. Worked Actuarial Example
**Problem:** An insurer has 100 independent health insurance policies. The claim amount for each policy has mean $\mu = 500$ and standard deviation $\sigma = 100$. 

Calculate the probability that the total aggregate claims for the 100 policies exceed 52,000.

**Solution:**
1. **Identify Parameters:**
   * $n = 100$
   * Individual mean $\mu = 500$, variance $\sigma^2 = 100^2 = 10,000$
2. **Mean and Variance of Total Aggregate Claims $S_{100}$:**
   * $E[S_{100}] = n\mu = 100 \times 500 = 50,000$
   * $Var(S_{100}) = n\sigma^2 = 100 \times 10,000 = 1,000,000$
   * Standard deviation $\sigma_{S_{100}} = \sqrt{1,000,000} = 1,000$
3. **Standardize for Normal Approximation:**
   $$P(S_{100} > 52,000) = P\left( Z > \frac{52,000 - 50,000}{1,000} \right) = P(Z > 2.00)$$
4. **Compute Probability:**
   $$P(Z > 2.00) = 1 - \Phi(2.00) = 1 - 0.9772 = \mathbf{0.0228}$$

---

## Phase 3 Formula Quick Reference & Cheat Sheet

$$\begin{array}{|l|l|}
\hline
\textbf{Concept} & \textbf{Formula} \\ \hline
\text{Joint PDF Normalization} & \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} f(x,y) \, dx \, dy = 1 \\ \hline
\text{Marginal Density } f_X(x) & \int_{-\infty}^{\infty} f(x,y) \, dy \\ \hline
\text{Conditional Density } f_{Y|X}(y|x) & \frac{f(x,y)}{f_X(x)} \\ \hline
\text{Law of Total Expectation} & E[Y] = E[E[Y|X]] \\ \hline
\text{Law of Total Variance (EVVE)} & Var(Y) = E[Var(Y|X)] + Var(E[Y|X]) \\ \hline
\text{Covariance } Cov(X,Y) & E[XY] - E[X]E[Y] \\ \hline
\text{Correlation } \rho_{X,Y} & \frac{Cov(X,Y)}{\sigma_X \sigma_Y} \\ \hline
\text{Variance of } aX + bY & a^2 Var(X) + b^2 Var(Y) + 2ab Cov(X,Y) \\ \hline
\text{Max Order Stat PDF } f_{(n)}(y) & n [F(y)]^{n-1} f(y) \\ \hline
\text{Min Order Stat Survival } S_{(1)}(y) & [1 - F(y)]^n \\ \hline
\text{CLT Standardized Sum } Z & \frac{\sum X_i - n\mu}{\sigma \sqrt{n}} \\ \hline
\end{array}$$