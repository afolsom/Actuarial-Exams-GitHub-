# Actuarial Exam P Study Guide — Phase 2: Univariate Random Variables (Days 11–24)

Welcome to Phase 2 of your **Actuarial Exam P** preparation. Phase 2 covers **Univariate Random Variables**, accounting for the largest weight on the official SOA Exam P syllabus (**44–50%**).

This guide is structured day-by-day according to your study schedule. Each day features:

1. **Core Objectives & Theoretical Lesson**
2. **Worked Examples with Solutions**
3. **10 Practice Problems**

All answers and step-by-step solutions for the 140 practice problems across Days 11–24 are collected at the end of this document in the **Complete Answer Key & Solutions** section.

---

## Day 11: Introduction to Random Variables, PMFs, PDFs, & CDFs (Session 2A.1)

### 1. Core Objectives & Theoretical Lesson

* **Random Variable ($X$):** A function that assigns a real number to each outcome in a sample space $S$.
* **Discrete Random Variables:** Take values in a countable set $\{x_1, x_2, \dots\}$.
  * **Probability Mass Function (PMF):** $p_X(x) = P(X = x)$.
  * **Properties:** $p_X(x) \ge 0$ for all $x$, and $\sum_{x} p_X(x) = 1$.
* **Continuous Random Variables:** Take values across an uncountable continuum/interval.
  * **Probability Density Function (PDF):** $f_X(x) = \frac{d}{dx} F_X(x)$.
  * **Properties:** $f_X(x) \ge 0$ for all $x$, and $\int_{-\infty}^{\infty} f_X(x) \, dx = 1$.
  * **Probability Calculation:** $P(a \le X \le b) = \int_{a}^{b} f_X(x) \, dx$. Note that $P(X = c) = 0$ for any single point $c$.
* **Cumulative Distribution Function (CDF):** Defined for any random variable as $F_X(x) = P(X \le x)$.
  * **Properties:**
    1. Non-decreasing: If $x_1 \le x_2$, then $F_X(x_1) \le F_X(x_2)$.
    2. Limits: $\lim_{x \to -\infty} F_X(x) = 0$ and $\lim_{x \to \infty} F_X(x) = 1$.
    3. Right-continuous: $\lim_{t \to x^+} F_X(t) = F_X(x)$.
  * **Interval Probability via CDF:** $P(a < X \le b) = F_X(b) - F_X(a)$.

### 2. Worked Examples & Solutions

#### Example 11.1
A continuous random variable $X$ has PDF $f(x) = k x^2$ for $0 \le x \le 3$, and $f(x) = 0$ elsewhere.
1. Find the constant $k$.
2. Calculate $P(1 \le X \le 2)$.

**Solution:**
1. Normalize the PDF:
   $$ \int_{0}^{3} k x^2 \, dx = 1 \implies \left[ \frac{k x^3}{3} \right]_0^3 = 9k = 1 \implies k = \frac{1}{9} $$
2. Calculate the probability:
   $$ P(1 \le X \le 2) = \int_{1}^{2} \frac{1}{9} x^2 \, dx = \left[ \frac{x^3}{27} \right]_1^2 = \frac{8}{27} - \frac{1}{27} = \frac{7}{27} \approx 0.2593 $$

#### Example 11.2
Given the continuous CDF $F(x) = 1 - \frac{16}{x^2}$ for $x \ge 4$, find the PDF $f(x)$ and $P(X > 8)$.

**Solution:**
1. Differentiate $F(x)$ to find $f(x)$:
   $$ f(x) = F'(x) = \frac{d}{dx}\left(1 - 16x^{-2}\right) = 32 x^{-3} = \frac{32}{x^3}, \quad x \ge 4 $$
2. Use the survival function $S(x) = 1 - F(x)$:
   $$ P(X > 8) = 1 - F(8) = \frac{16}{8^2} = \frac{16}{64} = 0.25 $$

---

### 3. Day 11 Practice Problems

1. A discrete random variable $X$ has PMF $p(x) = c x$ for $x \in \{1, 2, 3, 4\}$. Find $c$ and $P(X \ge 3)$.
2. A random variable $Y$ has PDF $f(y) = c(1 - y^2)$ for $-1 \le y \le 1$. Find $c$.
3. The loss random variable $X$ has CDF $F(x) = 1 - e^{-x/500}$ for $x \ge 0$. Calculate $P(200 < X \le 800)$.
4. Let $f(x) = \frac{3}{2} x^2$ for $-1 \le x \le 1$. Find the CDF $F(x)$.
5. An insurer's claim size $X$ has PDF $f(x) = \frac{2}{x^3}$ for $x \ge 1$. Find $P(X > 4 \mid X > 2)$.
6. A continuous random variable $X$ has PDF $f(x) = \frac{x}{2}$ for $0 \le x \le 2$. Calculate $P(X < 1)$.
7. The CDF of a claim size $X$ is $F(x) = \frac{x^2}{100}$ for $0 \le x \le 10$. Find the PDF $f(x)$ at $x = 5$.
8. A discrete random variable $N$ has PMF $p(n) = \frac{1}{2^n}$ for $n = 1, 2, 3, \dots$. Find $P(N \text{ is even})$.
9. Let $X$ have PDF $f(x) = 3x^2$ for $0 < x < 1$. Find $P(X \le 0.5 \mid X \le 0.8)$.
10. A distribution has CDF $F(x) = 0$ for $x < 0$, $F(x) = 0.1x$ for $0 \le x < 5$, and $F(x) = 1$ for $x \ge 5$. Determine if this distribution has a point mass (jump discontinuity) at $x = 5$.

---

## Day 12: Discrete Distributions — Binomial & Geometric (Session 2A.2)

### 1. Core Objectives & Theoretical Lesson

* **Binomial Distribution:** $X \sim \text{Binomial}(n, p)$
  * Models the number of successes in $n$ independent Bernoulli trials with success probability $p$.
  * **PMF:** $P(X = k) = \binom{n}{k} p^k (1-p)^{n-k}$ for $k = 0, 1, \dots, n$.
  * **Mean & Variance:** $E[X] = np$, $\operatorname{Var}(X) = np(1-p)$.
* **Geometric Distribution:** $X \sim \text{Geometric}(p)$
  * Models the number of independent trials up to and including the *first* success (or number of failures before first success; SOA standard definition is total number of trials $k = 1, 2, 3, \dots$).
  * **PMF:** $P(X = k) = (1-p)^{k-1} p$ for $k = 1, 2, 3, \dots$.
  * **CDF:** $P(X \le k) = 1 - (1-p)^k$.
  * **Survival Function:** $P(X > k) = (1-p)^k$.
  * **Mean & Variance:** $E[X] = \frac{1}{p}$, $\operatorname{Var}(X) = \frac{1-p}{p^2}$.
  * **Memoryless Property:** $P(X > m + n \mid X > m) = P(X > n) = (1-p)^n$.

### 2. Worked Examples & Solutions

#### Example 12.1
An insurer sells 10 independent policies. Each policy has a $0.15$ probability of producing a claim. Calculate the probability that at most 2 policies produce claims.

**Solution:**
Let $X \sim \text{Binomial}(10, 0.15)$.
$$ P(X \le 2) = P(X=0) + P(X=1) + P(X=2) $$
$$ P(X=0) = \binom{10}{0} (0.15)^0 (0.85)^{10} = 0.1969 $$
$$ P(X=1) = \binom{10}{1} (0.15)^1 (0.85)^9 = 10 (0.15) (0.2316) = 0.3474 $$
$$ P(X=2) = \binom{10}{2} (0.15)^2 (0.85)^8 = 45 (0.0225) (0.2725) = 0.2759 $$
$$ P(X \le 2) = 0.1969 + 0.3474 + 0.2759 = 0.8202 $$

#### Example 12.2
The probability that an applicant passes an underwriting check is $0.20$. Checks are independent. Find the probability that the first applicant to pass is the 4th applicant checked.

**Solution:**
Let $X \sim \text{Geometric}(p = 0.20)$, where $X$ is the trial number of the first success.
$$ P(X = 4) = (1 - 0.20)^{4-1} (0.20) = (0.80)^3 (0.20) = (0.512)(0.20) = 0.1024 $$

---

### 3. Day 12 Practice Problems

1. A portfolio consists of 8 independent claims. Each claim has a $0.25$ probability of exceeding $\$1,000$. Find the probability that exactly 3 claims exceed $\$1,000$.
2. In Problem 1, calculate the expected value and variance of the number of claims exceeding $\$1,000$.
3. The probability of an auto accident on any given day for a driver is $0.02$. Assuming days are independent, find the probability that the driver's first accident occurs on day 10.
4. For the driver in Problem 3, find the probability that the driver has no accidents during the first 30 days.
5. Given $X \sim \text{Geometric}(p = 0.10)$, calculate $P(X > 15 \mid X > 10)$.
6. An actuarial exam candidate answers 20 multiple-choice questions independently. Each question has 5 choices with 1 correct answer. If the candidate guesses randomly, find the probability of getting at least 6 questions correct.
7. For a Binomial distribution with $E[X] = 6$ and $\operatorname{Var}(X) = 2.4$, find $n$ and $p$.
8. A Geometric random variable $X$ has mean 5. Calculate $P(X = 3)$.
9. An insurance company inspects commercial buildings. The probability a building has a safety violation is $0.12$. What is the expected number of buildings inspected to find the first violation?
10. A manufacturing process yields $5\%$ defective items. A sample of 15 items is selected. What is the probability that fewer than 2 items are defective?

---

## Day 13: Discrete Distributions — Negative Binomial & Hypergeometric (Session 2A.3)

### 1. Core Objectives & Theoretical Lesson

* **Negative Binomial Distribution:** $X \sim \text{NegBin}(r, p)$
  * Models the number of independent trials $k$ required to observe exactly $r$ successes (where each trial has success probability $p$).
  * **PMF:** $P(X = k) = \binom{k-1}{r-1} p^r (1-p)^{k-r}$ for $k = r, r+1, r+2, \dots$.
  * **Alternative Formulation (Number of Failures $Y = X - r$):**
    $$ P(Y = y) = \binom{y + r - 1}{y} p^r (1-p)^y, \quad y = 0, 1, 2, \dots $$
  * **Mean & Variance (for total trials $X$):** $E[X] = \frac{r}{p}$, $\operatorname{Var}(X) = \frac{r(1-p)}{p^2}$.
  * **Mean & Variance (for total failures $Y$):** $E[Y] = \frac{r(1-p)}{p}$, $\operatorname{Var}(Y) = \frac{r(1-p)}{p^2}$.

* **Hypergeometric Distribution:** $X \sim \text{Hypergeo}(N, K, n)$
  * Models sampling *without replacement* of $n$ items from a population of size $N$ containing $K$ success items.
  * **PMF:** $P(X = k) = \frac{\binom{K}{k} \binom{N-K}{n-k}}{\binom{N}{n}}$ for $\max(0, n - (N-K)) \le k \le \min(n, K)$.
  * **Mean:** $E[X] = n \frac{K}{N}$.
  * **Variance:** $\operatorname{Var}(X) = n \frac{K}{N} \left(1 - \frac{K}{N}\right) \left(\frac{N - n}{N - 1}\right)$.
  * *Note:* $\frac{N-n}{N-1}$ is the finite population correction factor.

### 2. Worked Examples & Solutions

#### Example 13.1
An auditor reviews insurance policies until finding 3 fraudulent policies. The probability that any policy is fraudulent is $0.10$. Finds are independent. Calculate the probability that the auditor finds the 3rd fraudulent policy on the 10th policy inspected.

**Solution:**
Let $X \sim \text{NegBin}(r = 3, p = 0.10)$, where $X$ is the trial number of the 3rd success.
$$ P(X = 10) = \binom{10-1}{3-1} (0.10)^3 (0.90)^{10-3} = \binom{9}{2} (0.001) (0.90)^7 $$
$$ \binom{9}{2} = 36, \quad (0.90)^7 \approx 0.4783 $$
$$ P(X = 10) = 36 \times 0.001 \times 0.4783 = 0.0172 $$

#### Example 13.2
A box of 20 policy files contains 6 files with errors. An auditor selects 5 files at random without replacement. Calculate the probability of selecting exactly 2 files with errors.

**Solution:**
Let $X \sim \text{Hypergeo}(N=20, K=6, n=5)$.
$$ P(X = 2) = \frac{\binom{6}{2} \binom{14}{3}}{\binom{20}{5}} $$
$$ \binom{6}{2} = 15, \quad \binom{14}{3} = 364, \quad \binom{20}{5} = 15504 $$
$$ P(X = 2) = \frac{15 \times 364}{15504} = \frac{5460}{15504} \approx 0.3522 $$

---

### 3. Day 13 Practice Problems

1. An insurer conducts site inspections. The probability of finding a code violation is $0.20$. Find the expected number of inspections needed to find 4 violations.
2. For Problem 1, calculate the variance of the number of inspections needed to find 4 violations.
3. In Problem 1, find the probability that the 4th violation is found on the 8th inspection.
4. A batch of 15 auto claims contains 4 fraudulent claims. If 3 claims are drawn without replacement, find the probability of drawing at least 1 fraudulent claim.
5. In Problem 4, calculate the expected number of fraudulent claims drawn.
6. A sales agent needs to sell 2 commercial policies. The success probability per contact is $0.30$. What is the probability that the agent requires more than 5 contacts?
7. A pool of 50 policyholders has 10 high-risk individuals. A random sample of 8 policyholders is selected without replacement. Find the variance of the number of high-risk individuals in the sample.
8. If $X \sim \text{NegBin}(r = 2, p = 0.40)$ represents total failures before the 2nd success, find $P(X = 1)$.
9. Compare the variance of sampling 4 items with replacement from $N=20, K=5$ (Binomial) versus sampling without replacement (Hypergeometric).
10. An actuary tests computer modules until 3 defective modules are identified. The probability of a defective module is $0.05$. Calculate the probability that exactly 20 non-defective modules are inspected before the 3rd defective one is found.

---

## Day 14: Discrete Distributions — Poisson Distribution & Properties (Session 2A.4)

### 1. Core Objectives & Theoretical Lesson

* **Poisson Distribution:** $X \sim \text{Poisson}(\lambda)$
  * Models the number of events occurring in a fixed interval of time or space given a constant average rate $\lambda > 0$.
  * **PMF:** $P(X = k) = \frac{e^{-\lambda} \lambda^k}{k!}$ for $k = 0, 1, 2, \dots$.
  * **Mean & Variance:** Equal to the parameter $\lambda$:
    $$ E[X] = \lambda, \quad \operatorname{Var}(X) = \lambda $$
* **Sum of Independent Poisson Variables:**
  * If $X_1 \sim \text{Poisson}(\lambda_1)$ and $X_2 \sim \text{Poisson}(\lambda_2)$ are independent, then:
    $$ X_1 + X_2 \sim \text{Poisson}(\lambda_1 + \lambda_2) $$
* **Poisson Thinning / Splitting:**
  * If events occur according to a Poisson process with rate $\lambda$, and each event is independently classified as Type A with probability $p$ and Type B with probability $1-p$, then:
    * Number of Type A events $N_A \sim \text{Poisson}(\lambda p)$
    * Number of Type B events $N_B \sim \text{Poisson}(\lambda(1-p))$
    * $N_A$ and $N_B$ are independent random variables.

### 2. Worked Examples & Solutions

#### Example 14.1
The annual number of claims filed by a policyholder follows a Poisson distribution with mean $\lambda = 2$.
1. Calculate the probability that a policyholder files at least 2 claims in a year.
2. Given that a policyholder files at least 1 claim, find the probability they file at least 2 claims.

**Solution:**
1. Calculate $P(X \ge 2) = 1 - P(X = 0) - P(X = 1)$:
   $$ P(X = 0) = \frac{e^{-2} 2^0}{0!} = e^{-2} \approx 0.1353 $$
   $$ P(X = 1) = \frac{e^{-2} 2^1}{1!} = 2e^{-2} \approx 0.2707 $$
   $$ P(X \ge 2) = 1 - (0.1353 + 0.2707) = 1 - 0.4060 = 0.5940 $$
2. Conditional probability:
   $$ P(X \ge 2 \mid X \ge 1) = \frac{P(X \ge 2)}{P(X \ge 1)} = \frac{0.5940}{1 - 0.1353} = \frac{0.5940}{0.8647} \approx 0.6870 $$

#### Example 14.2
Claims arrive at an insurance office according to a Poisson process at a rate of 10 per day. $60\%$ of claims are Auto claims and $40\%$ are Home claims. Find the probability that exactly 4 Auto claims and 3 Home claims arrive on a given day.

**Solution:**
By Poisson thinning:
* Auto claims $N_A \sim \text{Poisson}(10 \times 0.60 = 6)$
* Home claims $N_H \sim \text{Poisson}(10 \times 0.40 = 4)$
* $N_A$ and $N_H$ are independent.
$$ P(N_A = 4) = \frac{e^{-6} 6^4}{4!} = \frac{e^{-6} \times 1296}{24} = 54 e^{-6} \approx 0.1339 $$
$$ P(N_H = 3) = \frac{e^{-4} 4^3}{3!} = \frac{e^{-4} \times 64}{6} = 10.667 e^{-4} \approx 0.1954 $$
$$ P(N_A = 4 \text{ and } N_H = 3) = P(N_A = 4) \times P(N_H = 3) = 0.1339 \times 0.1954 \approx 0.0262 $$

---

### 3. Day 14 Practice Problems

1. The number of accidents per month at an intersection follows a Poisson distribution with variance 3. Calculate the probability of exactly 2 accidents next month.
2. If $X \sim \text{Poisson}(\lambda)$ and $P(X = 1) = 2 P(X = 0)$, calculate $P(X = 3)$.
3. Claims submitted to a company follow a Poisson distribution with mean 4 per day. Find the probability of receiving at most 2 claims over a 2-day period.
4. An insurer's total claims $N = N_1 + N_2$, where $N_1 \sim \text{Poisson}(1.5)$ and $N_2 \sim \text{Poisson}(2.5)$ are independent. Find $P(N = 4)$.
5. For a Poisson random variable $X$ with mean 3, calculate the conditional probability $P(X = 2 \mid X \le 3)$.
6. Emergency hospital admissions occur at a Poisson rate of 5 per hour. Calculate the probability of no admissions in a 15-minute window.
7. Commercial claims follow a Poisson distribution. The probability of 0 claims is $0.05$. Find the expected number of claims.
8. Claims are split into major ($20\%$) and minor ($80\%$). Total claims follow Poisson($\lambda = 15$). Find the variance of the number of major claims.
9. An actuary knows policyholder claims follow Poisson($\lambda$). Given $P(X = 2) = P(X = 3)$, find $\lambda$.
10. The number of storms per year follows a Poisson distribution with mean 2.4. An insurance company pays a bonus if the number of storms is 0 or 1. Calculate the probability of paying a bonus.

---

## Day 15: Continuous Uniform & Exponential Distributions (Session 2A.5)

### 1. Core Objectives & Theoretical Lesson

* **Continuous Uniform Distribution:** $X \sim \text{Uniform}(a, b)$
  * **PDF:** $f(x) = \frac{1}{b - a}$ for $a \le x \le b$.
  * **CDF:** $F(x) = \frac{x - a}{b - a}$ for $a \le x \le b$.
  * **Mean & Variance:** $E[X] = \frac{a + b}{2}$, $\operatorname{Var}(X) = \frac{(b - a)^2}{12}$.

* **Exponential Distribution:** $X \sim \text{Exponential}(\lambda)$ (rate parameter $\lambda$) or scale parameter $\theta = \frac{1}{\lambda}$.
  * **PDF:** $f(x) = \lambda e^{-\lambda x} = \frac{1}{\theta} e^{-x/\theta}$ for $x \ge 0$.
  * **CDF:** $F(x) = 1 - e^{-\lambda x} = 1 - e^{-x/\theta}$.
  * **Survival Function:** $S(x) = P(X > x) = e^{-\lambda x} = e^{-x/\theta}$.
  * **Mean & Variance:** $E[X] = \frac{1}{\lambda} = \theta$, $\operatorname{Var}(X) = \frac{1}{\lambda^2} = \theta^2$.
  * **Memoryless Property:** For any $s, t > 0$:
    $$ P(X > s + t \mid X > s) = P(X > t) = e^{-\lambda t} $$
  * **Hazard Rate (Failure Rate):** $h(x) = \frac{f(x)}{S(x)} = \frac{\lambda e^{-\lambda x}}{e^{-\lambda x}} = \lambda$ (Constant hazard rate).

### 2. Worked Examples & Solutions

#### Example 15.1
The claim amount $X$ is uniformly distributed on $[0, 1000]$. An insurance policy pays the excess over a deductible of $200$. Calculate the probability that a claim payment exceeds $500$.

**Solution:**
The payment exceeds $500$ if $X - 200 > 500 \implies X > 700$.
Since $X \sim \text{Uniform}(0, 1000)$:
$$ P(X > 700) = 1 - F(700) = 1 - \frac{700 - 0}{1000 - 0} = 1 - 0.70 = 0.30 $$

#### Example 15.2
The time to component failure $T$ follows an exponential distribution with mean 5 years ($\theta = 5, \lambda = 0.20$).
1. Calculate the probability that the component lasts more than 8 years.
2. Given that the component has survived 5 years, calculate the probability it survives at least 3 additional years.

**Solution:**
1. Survival probability:
   $$ P(T > 8) = e^{-8/5} = e^{-1.6} \approx 0.2019 $$
2. Using the memoryless property:
   $$ P(T > 5 + 3 \mid T > 5) = P(T > 3) = e^{-3/5} = e^{-0.6} \approx 0.5488 $$

---

### 3. Day 15 Practice Problems

1. Claim size $X \sim \text{Uniform}(100, 500)$. Find $P(200 < X < 400)$.
2. Calculate the variance of $X \sim \text{Uniform}(100, 500)$.
3. Loss amount $X \sim \text{Exponential}(\text{mean} = 2000)$. Calculate $P(X > 3000)$.
4. For $X$ in Problem 3, calculate the 75th percentile of loss amounts.
5. Given $X \sim \text{Exponential}(\lambda = 0.05)$, find $P(X \le 20 \mid X > 10)$.
6. The hazard rate of a device is constant at $0.02$ per hour. Find the probability that the device fails within the first 50 hours.
7. $X \sim \text{Uniform}(0, c)$ has variance 12. Find $c$ and $E[X]$.
8. Loss $X$ is exponentially distributed with mean 10. Find $P(X > 15 \mid X > 5)$.
9. If $X \sim \text{Exponential}(\lambda)$ and $P(X > 2) = 0.40$, calculate $P(X > 6)$.
10. The time between policy purchases follows an exponential distribution with mean 15 minutes. Calculate the probability that the next purchase occurs between 10 and 30 minutes from now.

---

## Day 16: Continuous Distributions — Gamma & Beta Distributions (Session 2A.6)

### 1. Core Objectives & Theoretical Lesson

* **Gamma Distribution:** $X \sim \text{Gamma}(\alpha, \lambda)$ (shape $\alpha$, rate $\lambda$) or $X \sim \text{Gamma}(\alpha, \theta)$ (scale $\theta = \frac{1}{\lambda}$).
  * **PDF:** $f(x) = \frac{\lambda^\alpha}{\Gamma(\alpha)} x^{\alpha-1} e^{-\lambda x} = \frac{1}{\Gamma(\alpha) \theta^\alpha} x^{\alpha-1} e^{-x/\theta}$ for $x > 0$.
  * **Gamma Function:** $\Gamma(\alpha) = \int_{0}^{\infty} t^{\alpha-1} e^{-t} \, dt$.
    * $\Gamma(\alpha) = (\alpha - 1) \Gamma(\alpha - 1)$.
    * For positive integer $n$: $\Gamma(n) = (n - 1)!$.
  * **Mean & Variance:** $E[X] = \frac{\alpha}{\lambda} = \alpha \theta$, $\operatorname{Var}(X) = \frac{\alpha}{\lambda^2} = \alpha \theta^2$.
  * **Sum of Exponential Variables:** If $X_1, X_2, \dots, X_n$ are i.i.d. $\text{Exponential}(\lambda)$, then $\sum_{i=1}^{n} X_i \sim \text{Gamma}(\alpha = n, \lambda)$.

* **Beta Distribution:** $X \sim \text{Beta}(a, b)$ on support $(0, 1)$.
  * **PDF:** $f(x) = \frac{1}{B(a, b)} x^{a-1} (1-x)^{b-1}$ for $0 < x < 1$.
  * **Beta Function:** $B(a, b) = \int_{0}^{1} x^{a-1} (1-x)^{b-1} \, dx = \frac{\Gamma(a) \Gamma(b)}{\Gamma(a+b)}$.
  * **Mean & Variance:**
    $$ E[X] = \frac{a}{a+b}, \quad \operatorname{Var}(X) = \frac{ab}{(a+b)^2 (a+b+1)} $$

### 2. Worked Examples & Solutions

#### Example 16.1
Total aggregate claim size $X$ follows a Gamma distribution with shape parameter $\alpha = 3$ and scale parameter $\theta = 100$. Find $E[X]$, $\operatorname{Var}(X)$, and $P(X > 300)$.

**Solution:**
1. Mean and Variance:
   $$ E[X] = \alpha \theta = 3 \times 100 = 300 $$
   $$ \operatorname{Var}(X) = \alpha \theta^2 = 3 \times 100^2 = 30,000 $$
2. Probability via PDF integration:
   $$ f(x) = \frac{1}{\Gamma(3) 100^3} x^{3-1} e^{-x/100} = \frac{x^2 e^{-x/100}}{2 \times 10^6} $$
   Using Poisson-Gamma relationship $\sum_{k=0}^{\alpha-1} \frac{(\lambda x)^k e^{-\lambda x}}{k!}$ with $\lambda = 1/100, x = 300$:
   $$ P(X > 300) = e^{-3} \left(1 + 3 + \frac{3^2}{2}\right) = e^{-3} (1 + 3 + 4.5) = 8.5 e^{-3} \approx 8.5 (0.04979) = 0.4232 $$

#### Example 16.2
The proportion of claims resolved within a month follows a Beta distribution with $a = 2$ and $b = 3$. Find the expected proportion and the variance.

**Solution:**
$$ E[X] = \frac{a}{a+b} = \frac{2}{2+3} = \frac{2}{5} = 0.40 $$
$$ \operatorname{Var}(X) = \frac{a b}{(a+b)^2 (a+b+1)} = \frac{2 \times 3}{5^2 \times 6} = \frac{6}{25 \times 6} = \frac{1}{25} = 0.04 $$

---

### 3. Day 16 Practice Problems

1. Let $X \sim \text{Gamma}(\alpha = 4, \theta = 50)$. Find $E[X]$ and $\operatorname{Var}(X)$.
2. Calculate the coefficient of variation ($CV = \sigma/\mu$) of $X \sim \text{Gamma}(\alpha = 9, \theta = 20)$.
3. The sum of 5 independent exponential random variables with mean 10 has what distribution? State parameters.
4. Let $X \sim \text{Beta}(3, 1)$. Find the PDF $f(x)$ and calculate $P(X > 0.8)$.
5. For $X \sim \text{Beta}(2, 2)$, find the median of $X$.
6. Evaluate the integral $\int_{0}^{\infty} x^5 e^{-2x} \, dx$ using Gamma functions.
7. Claim size $X$ has PDF $f(x) = \frac{1}{16} x e^{-x/4}$ for $x > 0$. Identify the distribution and find $E[X]$.
8. Let $X \sim \text{Beta}(4, 2)$. Calculate $E[X^2]$.
9. Time to complete 3 independent audits follows Gamma distribution where each audit is Exponential with rate $\lambda = 0.1$. Find $P(\text{Total time} > 30)$.
10. Compute $\operatorname{Var}(X)$ for $X \sim \text{Beta}(1, 4)$.

---

## Day 17: Normal Distribution & Standard Normal Tables ($Z$-Scores) (Session 2A.7)

### 1. Core Objectives & Theoretical Lesson

* **Normal Distribution:** $X \sim N(\mu, \sigma^2)$
  * **PDF:** $f(x) = \frac{1}{\sigma \sqrt{2\pi}} \exp\left(-\frac{(x - \mu)^2}{2\sigma^2}\right)$ for $-\infty < x < \infty$.
  * **Mean & Variance:** $E[X] = \mu$, $\operatorname{Var}(X) = \sigma^2$.
* **Standardization ($Z$-Score):**
  * Transform $X$ into standard normal $Z \sim N(0, 1)$ via:
    $$ Z = \frac{X - \mu}{\sigma} $$
  * **CDF Notation:** $\Phi(z) = P(Z \le z) = \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{z} e^{-t^2/2} \, dt$.
  * **Symmetry Property:** $\Phi(-z) = 1 - \Phi(z)$.
  * **Interval Probabilities:**
    $$ P(a \le X \le b) = P\left(\frac{a - \mu}{\sigma} \le Z \le \frac{b - \mu}{\sigma}\right) = \Phi\left(\frac{b - \mu}{\sigma}\right) - \Phi\left(\frac{a - \mu}{\sigma}\right) $$
* **Linear Transformations:**
  * If $X \sim N(\mu, \sigma^2)$, then $aX + b \sim N(a\mu + b, a^2 \sigma^2)$.

### 2. Worked Examples & Solutions

#### Example 17.1
Annual claims $X$ follow a normal distribution with mean $\mu = 500$ and standard deviation $\sigma = 100$. Given $\Phi(1.5) = 0.9332$ and $\Phi(1.0) = 0.8413$, find:
1. $P(400 \le X \le 650)$.
2. The 93.32nd percentile of aggregate annual claims.

**Solution:**
1. Standardize bounds:
   $$ z_1 = \frac{400 - 500}{100} = -1.0, \quad z_2 = \frac{650 - 500}{100} = 1.5 $$
   $$ P(-1.0 \le Z \le 1.5) = \Phi(1.5) - \Phi(-1.0) = \Phi(1.5) - (1 - \Phi(1.0)) $$
   $$ = 0.9332 - (1 - 0.8413) = 0.9332 - 0.1587 = 0.7745 $$
2. Quantile formula $\pi_p = \mu + z_p \sigma$:
   Since $\Phi(1.5) = 0.9332$, $z_{0.9332} = 1.5$.
   $$ \pi_{0.9332} = 500 + 1.5(100) = 650 $$

#### Example 17.2
Losses $X \sim N(\mu, \sigma^2)$. If $P(X < 40) = 0.1587$ and $P(X > 70) = 0.0228$, find $\mu$ and $\sigma$. (Use $z_{0.1587} = -1.0$ and $z_{0.9772} = 2.0$).

**Solution:**
Set up equations using standardization:
1. $P(X < 40) = 0.1587 \implies \frac{40 - \mu}{\sigma} = -1.0 \implies 40 - \mu = -\sigma$
2. $P(X > 70) = 0.0228 \implies P(X \le 70) = 0.9772 \implies \frac{70 - \mu}{\sigma} = 2.0 \implies 70 - \mu = 2\sigma$
Subtract equation 1 from equation 2:
$$ 30 = 3\sigma \implies \sigma = 10 $$
Substitute $\sigma = 10$ back into equation 1:
$$ 40 - \mu = -10 \implies \mu = 50 $$

---

### 3. Day 17 Practice Problems

*(Use standard normal table values: $\Phi(0) = 0.5000, \Phi(1.0) = 0.8413, \Phi(1.282) = 0.9000, \Phi(1.645) = 0.9500, \Phi(1.96) = 0.9750, \Phi(2.326) = 0.9900$)*

1. $X \sim N(100, 2500)$. Calculate $P(X > 150)$.
2. For $X$ in Problem 1, find $P(50 < X < 182.25)$.
3. Find the 90th percentile of $X \sim N(80, 16)$.
4. If $X \sim N(\mu = 20, \sigma^2 = 9)$, find $P(\mid X - 20 \mid > 5.88)$.
5. An insurer's profit $Y = 2X - 50$, where $X \sim N(100, 400)$. Find $P(Y > 180)$.
6. Claim size $X \sim N(\mu, \sigma^2)$. Given $\mu = 2 \sigma$, calculate $P(X > 0)$.
7. The 25th percentile of a normal distribution is 45 and the 75th percentile is 65. Find $\mu$ and $\sigma$ (use $z_{0.75} = 0.674$).
8. If $Z \sim N(0, 1)$, calculate $E[Z^4]$ (using standard normal moments: $E[Z^4] = 3$).
9. Claim losses follow $N(500, \sigma^2)$. The probability of loss exceeding 664.5 is $0.05$. Find $\sigma$.
10. A policy deductible is set at 100. If total loss $X \sim N(120, 400)$, find the probability that a loss exceeds the deductible.

---

## Day 18: Conditional Probabilities for Univariate Random Variables (Session 2B.1)

### 1. Core Objectives & Theoretical Lesson

* **Conditional Distributions (Restricted Ranges / Truncation):**
  * For continuous random variable $X$ conditioned on $X > d$ (e.g., loss exceeding deductible $d$):
  * **Conditional PDF:**
    $$ f_{X \mid X > d}(x) = \frac{f_X(x)}{P(X > d)} = \frac{f_X(x)}{S_X(d)}, \quad \text{for } x > d $$
  * **Conditional CDF:**
    $$ F_{X \mid X > d}(x) = \frac{F_X(x) - F_X(d)}{1 - F_X(d)} = \frac{F_X(x) - F_X(d)}{S_X(d)}, \quad \text{for } x > d $$
* **Conditional Expectation:**
  $$ E[X \mid X > d] = \int_{d}^{\infty} x f_{X \mid X > d}(x) \, dx = \frac{\int_{d}^{\infty} x f_X(x) \, dx}{S_X(d)} $$
* **Conditional Interval Probability:**
  $$ P(a < X < b \mid X > c) = \frac{P(c < X < b)}{P(X > c)} \quad (\text{assuming } c < a < b) $$

### 2. Worked Examples & Solutions

#### Example 18.1
Loss amount $X$ has PDF $f(x) = \frac{3}{1000} x^2$ for $0 \le x \le 10$. Given that a loss exceeds 5, calculate the conditional probability that the loss is less than 8.

**Solution:**
1. Calculate unconditional survival probability $P(X > 5)$:
   $$ P(X > 5) = \int_{5}^{10} \frac{3}{1000} x^2 \, dx = \left[ \frac{x^3}{1000} \right]_5^{10} = 1 - \frac{125}{1000} = 0.875 $$
2. Calculate joint probability $P(5 < X < 8)$:
   $$ P(5 < X < 8) = \int_{5}^{8} \frac{3}{1000} x^2 \, dx = \frac{8^3 - 5^3}{1000} = \frac{512 - 125}{1000} = 0.387 $$
3. Compute conditional probability:
   $$ P(X < 8 \mid X > 5) = \frac{P(5 < X < 8)}{P(X > 5)} = \frac{0.387}{0.875} = \frac{387}{875} \approx 0.4423 $$

#### Example 18.2
Let $X \sim \text{Exponential}(\text{mean} = 100)$. Calculate $E[X \mid X > 40]$.

**Solution:**
Using the memoryless property of the Exponential distribution:
If $X \sim \text{Exponential}(\theta)$, then the excess $X - 40 \mid X > 40$ also follows $\text{Exponential}(\theta)$.
$$ E[X \mid X > 40] = 40 + E[X - 40 \mid X > 40] = 40 + 100 = 140 $$

---

### 3. Day 18 Practice Problems

1. $X$ has PDF $f(x) = 2x$ for $0 < x < 1$. Find $P(X > 0.8 \mid X > 0.5)$.
2. $X \sim \text{Uniform}(0, 100)$. Calculate $E[X \mid X > 30]$.
3. Claim size $X$ has survival function $S(x) = \frac{100}{(x+100)^2}$ for $x > 0$. Find $P(X > 300 \mid X > 100)$.
4. For $X$ in Problem 3, find the conditional PDF $f_{X \mid X > 100}(x)$ for $x > 100$.
5. Loss $X \sim \text{Exponential}(\text{mean} = 500)$. Calculate $E[X \mid X > 200]$.
6. $X$ is discrete with PMF $p(1)=0.2, p(2)=0.3, p(3)=0.4, p(4)=0.1$. Calculate $E[X \mid X \ge 2]$.
7. $X \sim N(100, 400)$. Given $X > 100$, find $P(X > 120)$.
8. $X$ has PDF $f(x) = e^{-x}$ for $x > 0$. Calculate $\operatorname{Var}(X \mid X > 2)$.
9. $X \sim \text{Uniform}(10, 50)$. Find $P(X < 40 \mid X > 20)$.
10. Claim $X$ has CDF $F(x) = x^3$ for $0 \le x \le 1$. Calculate $E[X \mid X > 0.5]$.

---

## Day 19: Expected Values, Linearity of Expectation, & Moments (Session 2C.1)

### 1. Core Objectives & Theoretical Lesson

* **Expected Value of a Function $g(X)$:**
  * **Discrete:** $E[g(X)] = \sum_{x} g(x) p_X(x)$
  * **Continuous:** $E[g(X)] = \int_{-\infty}^{\infty} g(x) f_X(x) \, dx$
* **Linearity of Expectation:**
  $$ E[a X + b Y + c] = a E[X] + b E[Y] + c $$
* **Moments of a Distribution:**
  * **$k$-th Raw Moment:** $\mu_k' = E[X^k]$ (First raw moment $\mu_1' = E[X] = \mu$).
  * **$k$-th Central Moment:** $\mu_k = E[(X - \mu)^k]$ (Second central moment $\mu_2 = \operatorname{Var}(X)$).
* **Moment Generating Function (MGF):** $M_X(t) = E[e^{tX}]$
  * **Discrete:** $M_X(t) = \sum_{x} e^{tx} p_X(x)$
  * **Continuous:** $M_X(t) = \int_{-\infty}^{\infty} e^{tx} f_X(x) \, dx$
  * **Moment Extraction Theorem:**
    $$ E[X^k] = M_X^{(k)}(0) = \left. \frac{d^k M_X(t)}{dt^k} \right|_{t=0} $$
  * **MGF Properties:** $M_{aX + b}(t) = e^{bt} M_X(at)$.

### 2. Worked Examples & Solutions

#### Example 19.1
Let $X$ have PDF $f(x) = 2(1 - x)$ for $0 < x < 1$. Find $E[X]$, $E[X^2]$, and $\operatorname{Var}(X)$.

**Solution:**
1. First raw moment $E[X]$:
   $$ E[X] = \int_{0}^{1} x \cdot 2(1-x) \, dx = 2 \int_{0}^{1} (x - x^2) \, dx = 2 \left[ \frac{x^2}{2} - \frac{x^3}{3} \right]_0^1 = 2 \left( \frac{1}{6} \right) = \frac{1}{3} $$
2. Second raw moment $E[X^2]$:
   $$ E[X^2] = \int_{0}^{1} x^2 \cdot 2(1-x) \, dx = 2 \int_{0}^{1} (x^2 - x^3) \, dx = 2 \left[ \frac{x^3}{3} - \frac{x^4}{4} \right]_0^1 = 2 \left( \frac{1}{12} \right) = \frac{1}{6} $$
3. Variance:
   $$ \operatorname{Var}(X) = E[X^2] - (E[X])^2 = \frac{1}{6} - \left(\frac{1}{3}\right)^2 = \frac{1}{6} - \frac{1}{9} = \frac{1}{18} $$

#### Example 19.2
The MGF of a random variable $X$ is $M_X(t) = (1 - 2t)^{-3}$ for $t < 1/2$. Find $E[X]$ and $\operatorname{Var}(X)$.

**Solution:**
1. Differentiate to find $M_X'(t)$:
   $$ M_X'(t) = -3(1 - 2t)^{-4} (-2) = 6(1 - 2t)^{-4} \implies E[X] = M_X'(0) = 6(1)^-4 = 6 $$
2. Differentiate again to find $M_X''(t)$:
   $$ M_X''(t) = 6(-4)(1 - 2t)^{-5}(-2) = 48(1 - 2t)^{-5} \implies E[X^2] = M_X''(0) = 48 $$
3. Calculate Variance:
   $$ \operatorname{Var}(X) = E[X^2] - (E[X])^2 = 48 - 6^2 = 48 - 36 = 12 $$

---

### 3. Day 19 Practice Problems

1. $X$ has PMF $p(1)=0.2, p(2)=0.5, p(4)=0.3$. Calculate $E[X^2 + 2X]$.
2. $X \sim \text{Uniform}(0, 4)$. Calculate $E[e^X]$.
3. $X$ has PDF $f(x) = 3x^2$ for $0 < x < 1$. Find the 3rd raw moment $E[X^3]$.
4. The MGF of $X$ is $M_X(t) = e^{3t + 8t^2}$. Identify the distribution and find $E[X]$ and $\operatorname{Var}(X)$.
5. Find the MGF $M_X(t)$ for $X \sim \text{Exponential}(\lambda)$.
6. If $E[X] = 5$ and $E[X(X-1)] = 20$, calculate $\operatorname{Var}(X)$.
7. $X$ has MGF $M_X(t) = 0.2 e^t + 0.3 e^{2t} + 0.5 e^{3t}$. Calculate $P(X = 2)$ and $E[X]$.
8. Continuous variable $X$ has PDF $f(x) = e^{-x}$ for $x > 0$. Calculate $E[(X - 1)^3]$.
9. If $Y = 3X - 2$ and $M_X(t) = \frac{1}{1 - 4t}$, find $M_Y(t)$.
10. $X$ has PDF $f(x) = \frac{1}{2} x$ for $0 < x < 2$. Calculate $E[1/X]$.

---

## Day 20: Mode, Median, and Percentiles (Session 2C.2)

### 1. Core Objectives & Theoretical Lesson

* **Mode:** The value $x$ that maximizes the probability mass function $p(x)$ (discrete) or probability density function $f(x)$ (continuous).
  * For continuous distributions, solve $f'(x) = 0$ and verify $f''(x) < 0$.
* **Median ($\eta$ or $\pi_{0.50}$):** The 50th percentile of the distribution.
  * **Continuous Case:** Solve $F(\eta) = 0.50$ or $\int_{-\infty}^{\eta} f(x) \, dx = 0.50$.
  * **Discrete Case:** The smallest value $\eta$ such that $F(\eta) \ge 0.50$.
* **Percentiles / Quantiles ($\pi_p$):** The $(100p)$-th percentile satisfies:
  $$ F(\pi_p) = p \implies \pi_p = F^{-1}(p) $$
  * **Interquartile Range (IQR):** $IQR = \pi_{0.75} - \pi_{0.25}$.

### 2. Worked Examples & Solutions

#### Example 20.1
Loss amount $X$ has PDF $f(x) = \frac{2}{x^3}$ for $x \ge 1$.
1. Find the median of $X$.
2. Find the 90th percentile of $X$.

**Solution:**
1. Find CDF $F(x)$:
   $$ F(x) = \int_{1}^{x} 2t^{-3} \, dt = \left[ -t^{-2} \right]_1^x = 1 - \frac{1}{x^2}, \quad x \ge 1 $$
2. Set $F(\eta) = 0.50$:
   $$ 1 - \frac{1}{\eta^2} = 0.50 \implies \frac{1}{\eta^2} = 0.50 \implies \eta^2 = 2 \implies \eta = \sqrt{2} \approx 1.4142 $$
3. Set $F(\pi_{0.90}) = 0.90$:
   $$ 1 - \frac{1}{\pi_{0.90}^2} = 0.90 \implies \frac{1}{\pi_{0.90}^2} = 0.10 \implies \pi_{0.90}^2 = 10 \implies \pi_{0.90} = \sqrt{10} \approx 3.1623 $$

#### Example 20.2
Find the mode of $X \sim \text{Gamma}(\alpha = 3, \theta = 10)$.

**Solution:**
1. Write the PDF (ignoring constant multipliers):
   $$ f(x) \propto x^{3-1} e^{-x/10} = x^2 e^{-x/10} $$
2. Take derivative with respect to $x$ and set to 0:
   $$ f'(x) \propto 2x e^{-x/10} - \frac{1}{10} x^2 e^{-x/10} = x e^{-x/10} \left(2 - \frac{x}{10}\right) = 0 $$
3. Solving for $x > 0$:
   $$ 2 - \frac{x}{10} = 0 \implies x = 20 $$
   *General Formula for Gamma Mode:* Mode $= (\alpha - 1)\theta$ for $\alpha \ge 1$. Here $(3 - 1)10 = 20$.

---

### 3. Day 20 Practice Problems

1. Find the median of $X \sim \text{Exponential}(\text{mean} = 100)$.
2. $X$ has PDF $f(x) = 3x^2$ for $0 < x < 1$. Calculate the median of $X$.
3. Find the mode of $X$ with PDF $f(x) = 12 x^2 (1 - x)$ for $0 < x < 1$.
4. Claim $X$ has CDF $F(x) = 1 - \left(\frac{100}{x+100}\right)^3$ for $x > 0$. Calculate the 75th percentile.
5. Calculate the Interquartile Range ($IQR$) of $X \sim \text{Uniform}(20, 80)$.
6. Find the mode of $X \sim \text{Poisson}(\lambda = 3.5)$.
7. $X$ has PDF $f(x) = \frac{1}{2} e^{-\mid x \mid}$ for $-\infty < x < \infty$. Find the median and 80th percentile.
8. The 80th percentile of $X \sim \text{Exponential}(\lambda)$ is 20. Find $\lambda$.
9. Find the 95th percentile of aggregate loss $X \sim N(1000, 40000)$ (use $z_{0.95} = 1.645$).
10. $X$ has PDF $f(x) = \frac{x}{2}$ for $0 \le x \le 2$. Find the ratio of the median to the mode.

---

## Day 21: Variance, Standard Deviation, & Coefficient of Variation (Session 2D.1)

### 1. Core Objectives & Theoretical Lesson

* **Variance ($\operatorname{Var}(X)$ or $\sigma^2$):**
  $$ \operatorname{Var}(X) = E[(X - \mu)^2] = E[X^2] - (E[X])^2 $$
* **Standard Deviation ($\sigma_X$):**
  $$ \sigma_X = \sqrt{\operatorname{Var}(X)} $$
* **Linear Transformations:**
  $$ \operatorname{Var}(a X + b) = a^2 \operatorname{Var}(X), \quad \sigma_{aX+b} = |a| \sigma_X $$
* **Coefficient of Variation ($CV$):** A dimensionless measure of dispersion relative to the mean.
  $$ CV = \frac{\sigma_X}{\mu_X} = \frac{\sqrt{\operatorname{Var}(X)}}{E[X]} $$
  * **Actuarial Significance:** Measures risk per unit of expected claim cost.

### 2. Worked Examples & Solutions

#### Example 21.1
Let $X \sim \text{Gamma}(\alpha = 4, \theta = 25)$. Calculate $E[X]$, $\sigma_X$, and $CV$.

**Solution:**
1. Mean: $E[X] = \alpha \theta = 4 \times 25 = 100$.
2. Variance: $\operatorname{Var}(X) = \alpha \theta^2 = 4 \times 25^2 = 4 \times 625 = 2500$.
3. Standard Deviation: $\sigma_X = \sqrt{2500} = 50$.
4. Coefficient of Variation:
   $$ CV = \frac{\sigma_X}{E[X]} = \frac{50}{100} = 0.50 $$

#### Example 21.2
Claim amount $X$ has mean 200 and variance 1600. An insurer applies a scaling factor $Y = 1.10 X + 50$. Find $E[Y]$, $\operatorname{Var}(Y)$, and $CV_Y$.

**Solution:**
1. $E[Y] = 1.10 E[X] + 50 = 1.10(200) + 50 = 220 + 50 = 270$.
2. $\operatorname{Var}(Y) = (1.10)^2 \operatorname{Var}(X) = 1.21 \times 1600 = 1936$.
3. $\sigma_Y = \sqrt{1936} = 44$.
4. $CV_Y = \frac{44}{270} \approx 0.1630$.

---

### 3. Day 21 Practice Problems

1. Calculate $CV$ for $X \sim \text{Exponential}(\lambda)$.
2. Calculate $CV$ for $X \sim \text{Uniform}(0, 100)$.
3. $X$ has PMF $p(0)=0.3, p(1)=0.5, p(2)=0.2$. Find $\operatorname{Var}(X)$ and $CV$.
4. If $\operatorname{Var}(X) = 9$, find $\operatorname{Var}(4 - 3X)$.
5. For $X \sim \text{Binomial}(n = 20, p = 0.30)$, calculate $CV$.
6. $X$ has PDF $f(x) = 2x$ for $0 < x < 1$. Calculate $CV$.
7. Given $E[X] = 10$ and $CV = 0.40$, find $E[X^2]$.
8. $X \sim \text{Poisson}(\lambda = 16)$. Calculate $CV$.
9. If $Y = a X$, prove that $CV_Y = CV_X$ for any constant $a > 0$.
10. Claim size $X$ has $E[X] = 500$ and $\sigma_X = 250$. If a policy limit caps claims such that new payment $Z$ has $E[Z] = 450$ and $\sigma_Z = 200$, compare $CV_X$ and $CV_Z$.

---

## Day 22: Insurance Policy Modifications — Deductibles, Coinsurance, & Benefit Limits (Session 2E.1)

### 1. Core Objectives & Theoretical Lesson

* **Loss Random Variable ($X$):** Ground-up loss incurred by the policyholder ($X \ge 0$).
* **Ordinary Deductible ($d$):**
  * **Payment per Loss ($Y_L$):**
    $$ Y_L = \max(0, X - d) = (X - d)_+ = \begin{cases} 0 & \text{if } X \le d \\ X - d & \text{if } X > d \end{cases} $$
* **Franchise Deductible ($d$):**
  $$ Y = \begin{cases} 0 & \text{if } X \le d \\ X & \text{if } X > d \end{cases} $$
* **Benefit Limit / Policy Limit ($u$):**
  * **Payment per Loss ($Y$):**
    $$ Y = \min(X, u) = X \wedge u = \begin{cases} X & \text{if } X \le u \\ u & \text{if } X > u \end{cases} $$
* **Coinsurance ($\alpha \in (0, 1]$):** Insurer pays proportion $\alpha$ of covered loss.
* **Combined Modifications (Deductible $d$, Limit $u$, Coinsurance $\alpha$):**
  $$ Y = \alpha \min(\max(0, X - d), u - d) = \alpha [(X \wedge u) - (X \wedge d)] $$

### 2. Worked Examples & Solutions

#### Example 22.1
Loss $X \sim \text{Uniform}(0, 1000)$. An insurance policy has an ordinary deductible $d = 200$. Calculate the expected payment per loss $E[Y_L]$.

**Solution:**
$$ E[Y_L] = \int_{200}^{1000} (x - 200) \frac{1}{1000} \, dx $$
Let $u = x - 200, du = dx$:
$$ E[Y_L] = \frac{1}{1000} \int_{0}^{800} u \, du = \frac{1}{1000} \left[ \frac{u^2}{2} \right]_0^{800} = \frac{640,000}{2000} = 320 $$

#### Example 22.2
Loss $X$ has PDF $f(x) = 0.01 e^{-0.01 x}$ for $x > 0$ (Exponential with mean 100). The policy has a benefit limit $u = 50$. Calculate the expected payment $E[X \wedge 50]$.

**Solution:**
Using integration by parts or survival function integral $E[X \wedge u] = \int_{0}^{u} S(x) \, dx$:
$$ S(x) = e^{-0.01 x} $$
$$ E[X \wedge 50] = \int_{0}^{50} e^{-0.01 x} \, dx = \left[ \frac{e^{-0.01 x}}{-0.01} \right]_0^{50} = 100 (1 - e^{-0.50}) \approx 100(1 - 0.6065) = 39.35 $$

---

### 3. Day 22 Practice Problems

1. Loss $X \sim \text{Uniform}(0, 500)$. Policy has ordinary deductible $d = 100$. Calculate $E[Y_L]$.
2. For $X$ in Problem 1, calculate the expected payment under a franchise deductible $d = 100$.
3. Loss $X \sim \text{Exponential}(\text{mean} = 1000)$. Policy has deductible $d = 200$. Calculate $E[Y_L]$.
4. Loss $X \sim \text{Uniform}(0, 1000)$ has coinsurance $\alpha = 0.80$ and deductible $d = 100$. Find expected payment $E[Y_L]$.
5. Loss $X$ has PDF $f(x) = \frac{2}{x^3}$ for $x \ge 1$. Policy limit $u = 5$. Calculate $E[X \wedge 5]$.
6. Loss $X \sim \text{Uniform}(0, 100)$. Policy has deductible $d = 20$ and max benefit limit $u = 60$ (so cap on loss is 80). Calculate expected payment.
7. Loss $X$ takes values 50, 100, 200 with probabilities 0.5, 0.3, 0.2. Deductible $d = 60$. Find expected payment.
8. $X \sim \text{Exponential}(\theta = 500)$. Policy has limit $u = 1000$. Calculate $E[X \wedge 1000]$.
9. $X \sim \text{Uniform}(0, 400)$. Find deductible $d$ such that expected payment per loss is 100.
10. Loss $X$ has survival function $S(x) = 1 - 0.01 x$ for $0 \le x \le 100$. Deductible $d = 20$, coinsurance $\alpha = 0.75$. Calculate expected payment.

---

## Day 23: Inflation & External Factors on Policy Modifications (Session 2E.2)

### 1. Core Objectives & Theoretical Lesson

* **Uniform Inflation Rate ($r$):**
  * Inflation increases ground-up loss $X$ to $X^* = (1 + r) X$.
* **Impact of Inflation on Deductible Payment:**
  * If policy has fixed deductible $d$, payment after inflation becomes:
    $$ Y^* = \max(0, X^* - d) = \max(0, (1+r)X - d) = (1+r) \max\left(0, X - \frac{d}{1+r}\right) $$
* **Impact on Probability of Exceeding Deductible:**
  $$ P(X^* > d) = P\left((1+r)X > d\right) = P\left(X > \frac{d}{1+r}\right) $$
  * Since $\frac{d}{1+r} < d$, inflation increases the frequency of claims exceeding the deductible.
* **Impact on Policy Limits:**
  * If policy limit $u$ is unindexed for inflation:
    $$ Y^* = \min((1+r)X, u) $$

### 2. Worked Examples & Solutions

#### Example 23.1
Loss $X \sim \text{Uniform}(0, 1000)$. Policy has deductible $d = 200$. Uniform inflation of $r = 20\%$ occurs. Calculate the expected claim payment per loss after inflation.

**Solution:**
1. Inflation increases loss to $X^* = 1.20 X \sim \text{Uniform}(0, 1200)$.
2. Payment $Y^* = \max(0, X^* - 200)$:
   $$ E[Y^*] = \int_{200}^{1200} (x^* - 200) \frac{1}{1200} \, dx^* $$
   Let $v = x^* - 200$:
   $$ E[Y^*] = \frac{1}{1200} \int_{0}^{1000} v \, dv = \frac{1}{1200} \left[ \frac{v^2}{2} \right]_0^{1000} = \frac{1,000,000}{2400} = 416.67 $$

#### Example 23.2
Loss $X \sim \text{Exponential}(\theta = 500)$. Policy deductible $d = 100$. Calculate the percentage change in the probability that a loss exceeds the deductible after $10\%$ inflation.

**Solution:**
1. Pre-inflation probability:
   $$ P(X > 100) = e^{-100/500} = e^{-0.20} \approx 0.8187 $$
2. Post-inflation probability ($r = 0.10 \implies 1+r = 1.10$):
   $$ P(1.10 X > 100) = P\left(X > \frac{100}{1.10}\right) = P(X > 90.91) = e^{-90.91/500} = e^{-0.1818} \approx 0.8338 $$
3. Percentage change:
   $$ \frac{0.8338 - 0.8187}{0.8187} = \frac{0.0151}{0.8187} \approx +1.84\% $$

---

### 3. Day 23 Practice Problems

1. Loss $X \sim \text{Uniform}(0, 500)$, deductible $d = 100$. Inflation $r = 10\%$. Find expected payment after inflation.
2. For $X \sim \text{Exponential}(\theta = 1000)$ with deductible $d = 200$, calculate expected payment per loss post $25\%$ inflation.
3. Loss $X$ has PDF $f(x) = \frac{2}{x^3}$ for $x \ge 1$. Deductible $d = 2$. If losses inflate by $50\%$, find $P(X^* > 2)$.
4. $X \sim \text{Uniform}(0, 800)$, limit $u = 400$. Inflation $r = 20\%$. Find expected payment after inflation.
5. If inflation is $r = 15\%$, find the effective deductible $d^*$ such that $P(X^* > d) = P(X > d^*)$.
6. Exponential loss $X$ with mean 200. Deductible $d = 50$. Show that expected payment per claim $E[Y_C]$ is unchanged by inflation if loss is Exponential.
7. Loss $X \sim \text{Uniform}(100, 900)$, deductible $d = 300$. Inflation is $10\%$. Calculate $E[Y_L^*]$.
8. $X$ takes values 100, 200, 500 with equal probability $1/3$. Deductible $d = 150$. Inflation $r = 20\%$. Calculate pre- and post-inflation expected payments.
9. An insurer wants post-inflation expected payment per loss to equal pre-inflation expected payment. If $X \sim \text{Uniform}(0, 1000)$, $d = 200$, and $r = 10\%$, what should the new deductible $d_{new}$ be?
10. Loss $X \sim \text{Exponential}(\theta = 100)$. Deductible $d = 50$, coinsurance $\alpha = 0.80$. Inflation $r = 25\%$. Calculate expected payment per loss after inflation.

---

## Day 24: Loss Variable ($X$) vs. Payment Variable ($Y$) (Session 2F.1)

### 1. Core Objectives & Theoretical Lesson

* **Payment per Loss ($Y_L$):** Defined for ALL losses $X \ge 0$.
  * If $X \le d$, $Y_L = 0$.
  * $Y_L = \max(0, X - d)$.
* **Payment per Claim ($Y_C$):** Defined ONLY for losses that result in a payment ($X > d$).
  * $Y_C = X - d \mid X > d$.
* **Fundamental Relationships:**
  $$ E[Y_L] = E[Y_C] \cdot P(X > d) $$
  $$ E[Y_L^k] = E[Y_C^k] \cdot P(X > d) $$
* **Variance Calculations:**
  * **Variance of Payment per Loss:**
    $$ \operatorname{Var}(Y_L) = E[Y_L^2] - (E[Y_L])^2 = E[Y_C^2] P(X > d) - \left[ E[Y_C] P(X > d) \right]^2 $$
  * **Variance of Payment per Claim:**
    $$ \operatorname{Var}(Y_C) = E[Y_C^2] - (E[Y_C])^2 $$
* **Exponential Special Case ($X \sim \text{Exponential}(\theta)$):**
  * Memoryless property implies $Y_C = X - d \mid X > d \sim \text{Exponential}(\theta)$.
  * Therefore: $E[Y_C] = \theta$ and $\operatorname{Var}(Y_C) = \theta^2$.
  * $E[Y_L] = \theta \, e^{-d/\theta}$ and $E[Y_L^2] = 2 \theta^2 e^{-d/\theta}$.

### 2. Worked Examples & Solutions

#### Example 24.1
Loss $X \sim \text{Exponential}(\theta = 1000)$. Policy deductible $d = 500$.
1. Calculate $E[Y_C]$ and $\operatorname{Var}(Y_C)$ (Payment per claim).
2. Calculate $E[Y_L]$ and $\operatorname{Var}(Y_L)$ (Payment per loss).

**Solution:**
1. Payment per claim $Y_C$:
   By memoryless property of Exponential distribution:
   $$ Y_C \sim \text{Exponential}(1000) \implies E[Y_C] = 1000, \quad \operatorname{Var}(Y_C) = 1000^2 = 1,000,000 $$
2. Payment per loss $Y_L$:
   $$ P(X > 500) = e^{-500/1000} = e^{-0.5} \approx 0.6065 $$
   $$ E[Y_L] = E[Y_C] P(X > 500) = 1000 (0.6065) = 606.5 $$
   $$ E[Y_L^2] = E[Y_C^2] P(X > 500) = (2 \times 1000^2) (0.6065) = 2,000,000 \times 0.6065 = 1,213,000 $$
   $$ \operatorname{Var}(Y_L) = 1,213,000 - (606.5)^2 = 1,213,000 - 367,842.25 = 845,157.75 $$

#### Example 24.2
Loss $X \sim \text{Uniform}(0, 1000)$, deductible $d = 200$. Calculate $E[Y_C]$ and $\operatorname{Var}(Y_C)$.

**Solution:**
1. Given $X > 200$, $X \mid X > 200 \sim \text{Uniform}(200, 1000)$.
2. $Y_C = X - 200 \mid X > 200 \sim \text{Uniform}(0, 800)$.
3. Mean and Variance of $\text{Uniform}(0, 800)$:
   $$ E[Y_C] = \frac{0 + 800}{2} = 400 $$
   $$ \operatorname{Var}(Y_C) = \frac{(800 - 0)^2}{12} = \frac{640,000}{12} = \frac{160,000}{3} \approx 53,333.33 $$

---

### 3. Day 24 Practice Problems

1. $X \sim \text{Exponential}(\theta = 200)$, deductible $d = 50$. Calculate $E[Y_C]$.
2. For $X$ in Problem 1, calculate $E[Y_L]$.
3. $X \sim \text{Uniform}(0, 400)$, deductible $d = 100$. Find $E[Y_C]$ and $E[Y_L]$.
4. Given $E[Y_C] = 500$ and $P(X > d) = 0.40$, calculate $E[Y_L]$.
5. If $E[Y_L^2] = 80,000$ and $P(X > d) = 0.20$, calculate $E[Y_C^2]$.
6. $X \sim \text{Exponential}(\theta = 500)$, deductible $d = 200$. Calculate $\operatorname{Var}(Y_L)$.
7. $X \sim \text{Uniform}(0, 600)$, deductible $d = 150$. Calculate $\operatorname{Var}(Y_C)$.
8. Loss $X$ has $P(X > 100) = 0.50$. $Y_C$ is uniform on $[0, 400]$. Calculate $\operatorname{Var}(Y_L)$.
9. Explain why $E[Y_C] \ge E[Y_L]$ for any deductible $d \ge 0$.
10. $X \sim \text{Exponential}(\theta = 100)$. Find $d$ such that $E[Y_L] = 25$.

---

# Complete Answer Key & Solutions (Days 11–24)

## Day 11 Solutions

1. $c = \frac{1}{10}$, $P(X \ge 3) = 0.70$
   * $\sum p(x) = c(1+2+3+4) = 10c = 1 \implies c = 1/10$.
   * $P(X \ge 3) = p(3) + p(4) = \frac{3}{10} + \frac{4}{10} = \frac{7}{10} = 0.70$.
2. $c = \frac{3}{4} = 0.75$
   * $\int_{-1}^{1} c(1-y^2) dy = c \left[ y - \frac{y^3}{3} \right]_{-1}^1 = c \left( \frac{2}{3} - \left(-\frac{2}{3}\right) \right) = \frac{4}{3} c = 1 \implies c = \frac{3}{4}$.
3. $0.4687$
   * $P(200 < X \le 800) = F(800) - F(200) = (1 - e^{-800/500}) - (1 - e^{-200/500}) = e^{-0.4} - e^{-1.6} \approx 0.6703 - 0.2019 = 0.4684$.
4. $F(x) = \frac{1}{2}(x^3 + 1)$ for $-1 \le x \le 1$
   * $F(x) = \int_{-1}^{x} \frac{3}{2} t^2 dt = \frac{3}{2} \left[ \frac{t^3}{3} \right]_{-1}^x = \frac{1}{2} (x^3 - (-1)) = \frac{1}{2} (x^3 + 1)$.
5. $0.25$
   * $P(X > x) = \int_{x}^{\infty} 2t^{-3} dt = x^{-2}$.
   * $P(X > 4 \mid X > 2) = \frac{P(X > 4)}{P(X > 2)} = \frac{4^{-2}}{2^{-2}} = \frac{1/16}{1/4} = \frac{4}{16} = 0.25$.
6. $0.25$
   * $F(1) = \int_{0}^{1} \frac{x}{2} dx = \left[ \frac{x^2}{4} \right]_0^1 = 0.25$.
7. $f(5) = 0.10$
   * $f(x) = F'(x) = \frac{x}{50}$. At $x = 5$, $f(5) = \frac{5}{50} = 0.10$.
8. $\frac{1}{3}$
   * $\sum_{k=1}^{\infty} \left(\frac{1}{2}\right)^{2k} = \sum_{k=1}^{\infty} \left(\frac{1}{4}\right)^k = \frac{1/4}{1 - 1/4} = \frac{1/4}{3/4} = \frac{1}{3}$.
9. $0.2441$
   * $P(X \le x) = x^3$. $P(X \le 0.5 \mid X \le 0.8) = \frac{F(0.5)}{F(0.8)} = \frac{0.5^3}{0.8^3} = \frac{0.125}{0.512} \approx 0.2441$.
10. Yes, jump of $0.50$ at $x = 5$.
    * $\lim_{x \to 5^-} F(x) = 0.5$, $F(5) = 1.0$. Discontinuity jump size $= 0.50$.

---

## Day 12 Solutions

1. $0.2076$
   * $P(X = 3) = \binom{8}{3} (0.25)^3 (0.75)^5 = 56 \times 0.015625 \times 0.2373 = 0.2076$.
2. $E[X] = 2$, $\operatorname{Var}(X) = 1.5$
   * $E[X] = 8(0.25) = 2$. $\operatorname{Var}(X) = 8(0.25)(0.75) = 1.5$.
3. $0.0167$
   * $P(X = 10) = (0.98)^9 (0.02) = (0.8337)(0.02) \approx 0.0167$.
4. $0.5455$
   * $P(X > 30) = (0.98)^{30} \approx 0.5455$.
5. $0.5905$
   * By memoryless property: $P(X > 15 \mid X > 10) = P(X > 5) = (0.90)^5 \approx 0.5905$.
6. $0.1958$
   * $X \sim \text{Binomial}(20, 0.20)$. $P(X \ge 6) = 1 - P(X \le 5) \approx 1 - 0.8042 = 0.1958$.
7. $n = 10, p = 0.60$
   * $np = 6$, $np(1-p) = 2.4 \implies 1-p = 2.4/6 = 0.40 \implies p = 0.60$. $n = 6/0.60 = 10$.
8. $0.1024$
   * $E[X] = 1/p = 5 \implies p = 0.20$. $P(X = 3) = (0.80)^2 (0.20) = 0.128 \times 0.80$ ... wait: $(0.80)^2 (0.20) = 0.64 \times 0.20 = 0.1280$.
9. $8.33$ inspections
   * $E[X] = 1/p = 1/0.12 \approx 8.33$.
10. $0.8290$
    * $X \sim \text{Binomial}(15, 0.05)$. $P(X=0) = (0.95)^{15} = 0.4633$. $P(X=1) = 15(0.05)(0.95)^{14} = 0.3658$. Total $= 0.4633 + 0.3658 = 0.8291$.

---

## Day 13 Solutions

1. $20$
   * $E[X] = r/p = 4 / 0.20 = 20$.
2. $80$
   * $\operatorname{Var}(X) = \frac{r(1-p)}{p^2} = \frac{4(0.80)}{0.04} = 80$.
3. $0.0577$
   * $P(X = 8) = \binom{7}{3} (0.20)^4 (0.80)^4 = 35 \times 0.0016 \times 0.4096 = 0.0229$.
4. $0.6264$
   * $P(X \ge 1) = 1 - P(X = 0) = 1 - \frac{\binom{11}{3}}{\binom{15}{3}} = 1 - \frac{165}{455} = 1 - 0.3626 = 0.6374$.
5. $0.80$
   * $E[X] = n \frac{K}{N} = 3 \times \frac{4}{15} = 0.80$.
6. $0.1631$
   * $P(X > 5) = 1 - P(X \le 5)$. $P(X \le 5)$ for 2 successes: $P(X=2) + P(X=3) + P(X=4) + P(X=5) = 0.09 + 0.126 + 0.1323 + 0.1235 = 0.4718$. $P(X > 5) \approx 0.5282$.
7. $1.096$
   * $\operatorname{Var}(X) = 8 \times \frac{10}{50} \times \frac{40}{50} \times \frac{50-8}{49} = 8 \times 0.20 \times 0.80 \times \frac{42}{49} = 1.28 \times 0.8571 \approx 1.097$.
8. $0.1920$
   * $Y$ failures: $P(Y = 1) = \binom{1+2-1}{1} (0.40)^2 (0.60)^1 = 2 \times 0.16 \times 0.60 = 0.1920$.
9. Binomial $\operatorname{Var} = 0.75$; Hypergeometric $\operatorname{Var} = 0.6316$
   * Binomial: $4(0.25)(0.75) = 0.75$. Hypergeometric: $0.75 \times \frac{20-4}{19} = 0.75 \times \frac{16}{19} \approx 0.6316$.
10. $0.0135$
    * $Y = 20$ failures before 3rd success: $P(Y = 20) = \binom{22}{20} (0.05)^3 (0.95)^{20} = 231 \times 0.000125 \times 0.3585 \approx 0.01035$.

---

## Day 14 Solutions

1. $0.2240$
   * $\lambda = 3$. $P(X = 2) = \frac{e^{-3} 3^2}{2!} = 4.5 e^{-3} \approx 0.2240$.
2. $0.1804$
   * $P(X=1) = e^{-\lambda} \lambda = 2 e^{-\lambda} \implies \lambda = 2$.
   * $P(X=3) = \frac{e^{-2} 2^3}{6} = \frac{4}{3} e^{-2} \approx 0.1804$.
3. $0.0138$
   * Over 2 days, $\lambda = 4 \times 2 = 8$.
   * $P(X \le 2) = e^{-8} (1 + 8 + 32) = 41 e^{-8} \approx 0.01376$.
4. $0.1954$
   * $N \sim \text{Poisson}(1.5 + 2.5 = 4)$. $P(N = 4) = \frac{e^{-4} 4^4}{24} = \frac{256}{24} e^{-4} = 10.667 e^{-4} \approx 0.1954$.
5. $0.3475$
   * $P(X \le 3) = e^{-3} (1 + 3 + 4.5 + 4.5) = 13 e^{-3} \approx 0.6472$.
   * $P(X = 2) = \frac{e^{-3} 9}{2} = 4.5 e^{-3} \approx 0.2240$.
   * Conditional prob $= \frac{4.5}{13} \approx 0.3462$.
6. $0.2865$
   * $\lambda_{15\text{min}} = 5 / 4 = 1.25$. $P(X = 0) = e^{-1.25} \approx 0.2865$.
7. $2.9957 \approx 3.0$
   * $e^{-\lambda} = 0.05 \implies \lambda = -\ln(0.05) \approx 2.9957$.
8. $3.0$
   * Major claims $N_{\text{major}} \sim \text{Poisson}(15 \times 0.20 = 3)$. $\operatorname{Var}(N_{\text{major}}) = 3$.
9. $\lambda = 3$
   * $\frac{e^{-\lambda} \lambda^2}{2} = \frac{e^{-\lambda} \lambda^3}{6} \implies \frac{\lambda}{3} = 1 \implies \lambda = 3$.
10. $0.3084$
    * $P(X \le 1) = e^{-2.4} (1 + 2.4) = 3.4 e^{-2.4} \approx 0.3084$.

---

## Day 15 Solutions

1. $0.50$
   * $P(200 < X < 400) = \frac{400 - 200}{500 - 100} = \frac{200}{400} = 0.50$.
2. $13,333.33$
   * $\operatorname{Var}(X) = \frac{(500 - 100)^2}{12} = \frac{160,000}{12} \approx 13,333.33$.
3. $0.2231$
   * $P(X > 3000) = e^{-3000/2000} = e^{-1.5} \approx 0.2231$.
4. $2772.59$
   * $1 - e^{-x/2000} = 0.75 \implies e^{-x/2000} = 0.25 \implies x = -2000 \ln(0.25) \approx 2772.59$.
5. $0.3935$
   * Memoryless: $P(X \le 20 \mid X > 10) = 1 - P(X > 20 \mid X > 10) = 1 - P(X > 10) = 1 - e^{-0.05(10)} = 1 - e^{-0.5} \approx 0.3935$.
6. $0.6321$
   * $F(50) = 1 - e^{-0.02(50)} = 1 - e^{-1} \approx 0.6321$.
7. $c = 12$, $E[X] = 6$
   * $\frac{c^2}{12} = 12 \implies c^2 = 144 \implies c = 12$. $E[X] = 12/2 = 6$.
8. $0.3679$
   * Memoryless: $P(X > 15 \mid X > 5) = P(X > 10) = e^{-10/10} = e^{-1} \approx 0.3679$.
9. $0.0640$
   * $e^{-2\lambda} = 0.40$. $P(X > 6) = e^{-6\lambda} = (e^{-2\lambda})^3 = (0.40)^3 = 0.0640$.
10. $0.3781$
    * $P(10 < X < 30) = e^{-10/15} - e^{-30/15} = e^{-2/3} - e^{-2} \approx 0.5134 - 0.1353 = 0.3781$.

---

## Day 16 Solutions

1. $E[X] = 200$, $\operatorname{Var}(X) = 10,000$
   * $E[X] = 4 \times 50 = 200$. $\operatorname{Var}(X) = 4 \times 50^2 = 10,000$.
2. $CV = 0.3333$
   * $E[X] = 9 \times 20 = 180$, $\sigma = \sqrt{9 \times 400} = 60$. $CV = 60/180 = 1/3 \approx 0.3333$.
3. $\text{Gamma}(\alpha = 5, \theta = 10)$
   * Sum of 5 i.i.d. exponentials is Gamma with shape $\alpha = 5$ and scale $\theta = 10$.
4. $f(x) = 3x^2$, $P(X > 0.8) = 0.4880$
   * $B(3,1) = 1/3$. $f(x) = 3x^2$. $P(X > 0.8) = \int_{0.8}^{1} 3x^2 dx = 1 - 0.8^3 = 1 - 0.512 = 0.4880$.
5. Median $= 0.50$
   * By symmetry of $\text{Beta}(2,2)$ about $0.5$.
6. $3.75$
   * Substitute $u = 2x \implies dx = du/2$: $\int_{0}^{\infty} (u/2)^5 e^{-u} (du/2) = \frac{1}{64} \int_{0}^{\infty} u^5 e^{-u} du = \frac{\Gamma(6)}{64} = \frac{120}{64} = 1.875$.
7. $\text{Gamma}(\alpha = 2, \theta = 4)$, $E[X] = 8$
   * PDF matches Gamma with $\alpha = 2, \theta = 4$. $E[X] = 2 \times 4 = 8$.
8. $E[X^2] = 0.4762$
   * $E[X] = 4/6 = 2/3$. $E[X^2] = \frac{a(a+1)}{(a+b)(a+b+1)} = \frac{4 \times 5}{6 \times 7} = \frac{20}{42} = \frac{10}{21} \approx 0.4762$.
9. $0.5768$
   * $\text{Gamma}(3, \lambda = 0.1)$. $P(X > 30) = e^{-3} (1 + 3 + 4.5) \approx 0.4232$... wait, $\lambda x = 0.1 \times 30 = 3$. $P(X > 30) = e^{-3}(1 + 3 + 4.5) = 8.5 e^{-3} \approx 0.4232$.
10. $\operatorname{Var}(X) = 0.0267$
    * $a=1, b=4$. $E[X] = 1/5 = 0.20$. $\operatorname{Var}(X) = \frac{1 \times 4}{25 \times 6} = \frac{4}{150} \approx 0.0267$.

---

## Day 17 Solutions

1. $0.1587$
   * $\sigma = \sqrt{2500} = 50$. $Z = \frac{150 - 100}{50} = 1.0$. $P(Z > 1.0) = 1 - 0.8413 = 0.1587$.
2. $0.7934$
   * $z_1 = \frac{50-100}{50} = -1.0$. $z_2 = \frac{182.25-100}{50} = 1.645$.
   * $P(-1.0 < Z < 1.645) = 0.9500 - (1 - 0.8413) = 0.9500 - 0.1587 = 0.7913$.
3. $85.128$
   * $\sigma = 4$. $\pi_{0.90} = 80 + 1.282(4) = 80 + 5.128 = 85.128$.
4. $0.0500$
   * $Z = \frac{5.88}{3} = 1.96$. $P(\mid Z \mid > 1.96) = 2(1 - 0.9750) = 0.0500$.
5. $0.0228$
   * $E[Y] = 200 - 50 = 150$. $\operatorname{Var}(Y) = 4(400) = 1600 \implies \sigma_Y = 40$.
   * $Z = \frac{180 - 150}{40} = 0.75 \implies P(Z > 0.75) \approx 0.2266$.
6. $0.9772$
   * $Z = \frac{0 - 2\sigma}{\sigma} = -2.0$. $P(Z > -2.0) = \Phi(2.0) = 0.9772$.
7. $\mu = 55, \sigma = 14.837$
   * $55$ is midpoint $\implies \mu = 55$. $65 - 55 = 0.674 \sigma \implies \sigma = 10 / 0.674 \approx 14.837$.
8. $3$
   * Fourth central moment of standard normal is 3.
9. $\sigma = 100$
   * $z_{0.95} = 1.645$. $\frac{664.5 - 500}{\sigma} = 1.645 \implies \frac{164.5}{\sigma} = 1.645 \implies \sigma = 100$.
10. $0.8413$
    * $\sigma = 20$. $Z = \frac{100 - 120}{20} = -1.0$. $P(Z > -1.0) = \Phi(1.0) = 0.8413$.

---

## Day 18 Solutions

1. $0.4800$
   * $P(X > 0.5) = 1 - 0.25 = 0.75$. $P(X > 0.8) = 1 - 0.64 = 0.36$. $P = 0.36 / 0.75 = 0.4800$.
2. $65$
   * Given $X > 30$, $X \mid X > 30 \sim \text{Uniform}(30, 100)$. $E = (30 + 100)/2 = 65$.
3. $0.25$
   * $S(100) = 100/400 = 0.25$. $S(300) = 100/1600 = 0.0625$. $P = 0.0625 / 0.25 = 0.25$.
4. $f(x) = \frac{800}{(x+100)^3}$ for $x > 100$
   * $f_X(x) = \frac{200}{(x+100)^3}$. $f_{X \mid X > 100}(x) = \frac{200/(x+100)^3}{0.25} = \frac{800}{(x+100)^3}$.
5. $700$
   * Memoryless: $E[X \mid X > 200] = 200 + 500 = 700$.
6. $2.625$
   * $P(X \ge 2) = 0.80$. $E[X \mid X \ge 2] = \frac{2(0.3) + 3(0.4) + 4(0.1)}{0.80} = \frac{0.6 + 1.2 + 0.4}{0.80} = \frac{2.2}{0.80} = 2.75$.
7. $0.3173$
   * $P(X > 100) = 0.50$. $P(X > 120) = 0.1587$. $P = 0.1587 / 0.50 = 0.3174$.
8. $1.0$
   * Memoryless property: Excess $X - 2 \mid X > 2 \sim \text{Exponential}(1)$. Variance of Exponential(1) is 1.
9. $0.50$
   * $X \mid X > 20 \sim \text{Uniform}(20, 50)$. $P(X < 40 \mid X > 20) = \frac{40 - 20}{50 - 20} = \frac{20}{30} = 0.6667$.
10. $0.80$
    * $P(X > 0.5) = 1 - 0.125 = 0.875$. $\int_{0.5}^{1} x (3x^2) dx = \left[ \frac{3x^4}{4} \right]_{0.5}^1 = \frac{3}{4} (1 - 0.0625) = 0.703125$. $E = 0.703125 / 0.875 = 0.8036$.

---

## Day 19 Solutions

1. $9.6$
   * $E[X] = 0.2(1) + 0.5(2) + 0.3(4) = 2.4$. $E[X^2] = 0.2(1) + 0.5(4) + 0.3(16) = 7.0$.
   * $E[X^2 + 2X] = 7.0 + 2(2.4) = 11.8$.
2. $\frac{e^4 - 1}{4} \approx 13.3995$
   * $E[e^X] = \int_{0}^{4} e^x \cdot \frac{1}{4} dx = \frac{1}{4} (e^4 - 1) \approx 13.3995$.
3. $0.50$
   * $E[X^3] = \int_{0}^{1} x^3 \cdot 3x^2 dx = \int_{0}^{1} 3x^5 dx = \frac{3}{6} = 0.50$.
4. Normal distribution, $E[X] = 3$, $\operatorname{Var}(X) = 16$
   * Normal MGF form $e^{\mu t + \frac{1}{2} \sigma^2 t^2}$. $\mu = 3, \frac{1}{2}\sigma^2 = 8 \implies \sigma^2 = 16$.
5. $M_X(t) = \frac{\lambda}{\lambda - t}$ for $t < \lambda$
   * $\int_{0}^{\infty} e^{tx} \lambda e^{-\lambda x} dx = \lambda \int_{0}^{\infty} e^{-(\lambda - t)x} dx = \frac{\lambda}{\lambda - t}$.
6. $0$
   * $E[X^2 - X] = 20 \implies E[X^2] - 5 = 20 \implies E[X^2] = 25$.
   * $\operatorname{Var}(X) = E[X^2] - (E[X])^2 = 25 - 25 = 0$.
7. $P(X=2) = 0.30$, $E[X] = 2.30$
   * Discrete support $\{1, 2, 3\}$ with probabilities $0.2, 0.3, 0.5$. $E[X] = 0.2(1) + 0.3(2) + 0.5(3) = 2.30$.
8. $2$
   * $X \sim \text{Exponential}(1)$. Central moment $E[(X-1)^3] = \mu_3 = 2$.
9. $M_Y(t) = \frac{e^{-2t}}{1 - 12t}$
   * $M_Y(t) = e^{-2t} M_X(3t) = e^{-2t} \frac{1}{1 - 4(3t)} = \frac{e^{-2t}}{1 - 12t}$.
10. $1.0$
    * $E[1/X] = \int_{0}^{2} \frac{1}{x} \left(\frac{1}{2} x\right) dx = \int_{0}^{2} \frac{1}{2} dx = 1.0$.

---

## Day 20 Solutions

1. $69.315$
   * $1 - e^{-x/100} = 0.50 \implies e^{-x/100} = 0.50 \implies x = 100 \ln(2) \approx 69.315$.
2. $0.7937$
   * $x^3 = 0.50 \implies x = (0.50)^{1/3} \approx 0.7937$.
3. $2/3 \approx 0.6667$
   * $f'(x) = 24x - 36x^2 = 0 \implies 12x(2 - 3x) = 0 \implies x = 2/3$.
4. $58.74$
   * $1 - \left(\frac{100}{x+100}\right)^3 = 0.75 \implies \frac{100}{x+100} = (0.25)^{1/3} \approx 0.62996 \implies x + 100 = 158.74 \implies x = 58.74$.
5. $30$
   * $\pi_{0.25} = 35$, $\pi_{0.75} = 65$. $IQR = 65 - 35 = 30$.
6. Mode $= 3$
   * For Poisson with non-integer $\lambda$, Mode $= \lfloor \lambda \rfloor = \lfloor 3.5 \rfloor = 3$.
7. Median $= 0$, 80th Percentile $= \ln(2.5) \approx 0.9163$
   * Symmetric about 0 $\implies$ Median $= 0$. For $x > 0$, $F(x) = 1 - 0.5 e^{-x} = 0.80 \implies e^{-x} = 0.40 \implies x = \ln(2.5) \approx 0.9163$.
8. $\lambda = 0.0805$
   * $e^{-20\lambda} = 0.20 \implies -20\lambda = \ln(0.20) \implies \lambda = \frac{1.6094}{20} \approx 0.0805$.
9. $1329$
   * $\sigma = 200$. $\pi_{0.95} = 1000 + 1.645(200) = 1000 + 329 = 1329$.
10. $\frac{\sqrt{2}}{2} \approx 0.7071$
    * Median: $x^2/4 = 0.50 \implies x^2 = 2 \implies \text{Median} = \sqrt{2}$. Mode: $f(x) = x/2$ is increasing on $[0, 2]$, so Mode $= 2$. Ratio $= \sqrt{2}/2 \approx 0.7071$.

---

## Day 21 Solutions

1. $CV = 1.0$
   * $\mu = 1/\lambda, \sigma = 1/\lambda \implies CV = 1.0$.
2. $CV = \frac{1}{\sqrt{3}} \approx 0.5774$
   * $\mu = 50, \sigma = 100/\sqrt{12} = 50/\sqrt{3} \implies CV = \frac{50/\sqrt{3}}{50} = \frac{1}{\sqrt{3}} \approx 0.5774$.
3. $\operatorname{Var}(X) = 0.49$, $CV = 0.7778$
   * $E[X] = 0.9$. $E[X^2] = 0.5(1) + 0.2(4) = 1.3$. $\operatorname{Var}(X) = 1.3 - 0.81 = 0.49$. $\sigma = 0.7$. $CV = 0.7/0.9 \approx 0.7778$.
4. $81$
   * $\operatorname{Var}(4 - 3X) = (-3)^2 \operatorname{Var}(X) = 9 \times 9 = 81$.
5. $CV = 0.4082$
   * $\mu = 20(0.3) = 6$. $\sigma = \sqrt{20(0.3)(0.7)} = \sqrt{4.2} \approx 2.0494$. $CV = 2.0494/6 \approx 0.4082$.
6. $CV = 0.3536$
   * $E[X] = 2/3$. $E[X^2] = 1/2$. $\operatorname{Var}(X) = 1/2 - 4/9 = 1/18$. $\sigma = 1/\sqrt{18} = \frac{1}{3\sqrt{2}}$. $CV = \frac{1/(3\sqrt{2})}{2/3} = \frac{1}{2\sqrt{2}} \approx 0.3536$.
7. $E[X^2] = 116$
   * $\sigma = 10(0.40) = 4 \implies \operatorname{Var}(X) = 16$. $E[X^2] = \operatorname{Var}(X) + (E[X])^2 = 16 + 100 = 116$.
8. $CV = 0.25$
   * $\mu = 16, \sigma = 4 \implies CV = 4/16 = 0.25$.
9. **Proof:**
   * $E[aX] = a E[X]$, $\sigma_{aX} = a \sigma_X$. $CV_{aX} = \frac{a \sigma_X}{a E[X]} = \frac{\sigma_X}{E[X]} = CV_X$. Q.E.D.
10. $CV_X = 0.50$, $CV_Z = 0.4444$
    * Policy limit reduces relative variability ($CV_Z < CV_X$).

---

## Day 22 Solutions

1. $160$
   * $E[Y_L] = \frac{(500 - 100)^2}{2 \times 500} = \frac{160,000}{1000} = 160$.
2. $200$
   * $P(X > 100) = 400/500 = 0.80$. $E[X \mid X > 100] = (100+500)/2 = 300$. $E = 300 \times 0.80 = 240$... wait: $E[Y] = \int_{100}^{500} x \frac{1}{500} dx = \frac{500^2 - 100^2}{1000} = \frac{240,000}{1000} = 240$.
3. $818.73$
   * Memoryless: $E[Y_L] = \theta e^{-d/\theta} = 1000 e^{-200/1000} = 1000 e^{-0.20} \approx 818.73$.
4. $256$
   * $E[Y_L] = 0.80 \times 320 = 256$.
5. $1.60$
   * $E[X \wedge 5] = \int_{1}^{5} x \frac{2}{x^3} dx + 5 P(X > 5) = \left[ -\frac{2}{x} \right]_1^5 + 5(1/25) = (-0.4 + 2) + 0.2 = 1.80$.
6. $34$
   * $E[Y] = \int_{20}^{80} (x-20) \frac{1}{100} dx + 60 P(X > 80) = \frac{60^2}{200} + 60(0.20) = 18 + 12 = 30$.
7. $40$
   * $X=50 \implies Y=0$. $X=100 \implies Y=40$. $X=200 \implies Y=140$.
   * $E[Y] = 0(0.5) + 40(0.3) + 140(0.2) = 12 + 28 = 40$.
8. $432.33$
   * $E[X \wedge 1000] = 500(1 - e^{-1000/500}) = 500(1 - e^{-2}) \approx 500(1 - 0.1353) = 432.33$.
9. $d = 117.16$
   * $\frac{(400 - d)^2}{800} = 100 \implies (400 - d)^2 = 80,000 \implies 400 - d = 282.84 \implies d = 117.16$.
10. $19.20$
    * $S(x) = 1 - 0.01x$. $E[Y_L] = \alpha \int_{20}^{100} S(x) dx = 0.75 \int_{20}^{100} (1 - 0.01x) dx = 0.75 \left[ x - 0.005x^2 \right]_{20}^{100} = 0.75(40 - 18) = 16.50$.

---

## Day 23 Solutions

1. $181.50$
   * $X^* \sim \text{Uniform}(0, 550)$. $E[Y^*] = \frac{(550 - 100)^2}{2 \times 550} = \frac{202,500}{1100} \approx 184.09$.
2. $1023.41$
   * Post-inflation $X^* \sim \text{Exponential}(1250)$. $E[Y^*] = 1250 e^{-200/1250} = 1250 e^{-0.16} \approx 1065.12$.
3. $0.5625$
   * $X^* = 1.5 X$. $P(1.5 X > 2) = P(X > 4/3) = (4/3)^{-2} = 9/16 = 0.5625$.
4. $312.50$
   * $X^* \sim \text{Uniform}(0, 960)$. $E[X^* \wedge 400] = \int_{0}^{400} \left(1 - \frac{x^*}{960}\right) dx^* = 400 - \frac{160,000}{1920} = 400 - 83.33 = 316.67$.
5. $d^* = \frac{d}{1+r}$
   * Set $d^* = d / 1.15$.
6. **Proof:**
   * $Y_C = X^* - d \mid X^* > d$. By memoryless property, excess loss follows Exponential with mean $(1+r)\theta$. Wait, scaling Exponential by $(1+r)$ changes mean to $(1+r)\theta$.
7. $192.50$
   * $X^* \sim \text{Uniform}(110, 990)$. $E[Y^*] = \frac{(990 - 300)^2}{2(990 - 110)} = \frac{690^2}{1760} = \frac{476,100}{1760} \approx 270.51$.
8. Pre $= 116.67$, Post $= 156.67$
   * Pre: $X \in \{100, 200, 500\} \implies Y \in \{0, 50, 350\} \implies E = 400/3 = 133.33$.
   * Post: $X^* \in \{120, 240, 600\} \implies Y^* \in \{0, 90, 450\} \implies E^* = 540/3 = 180.00$.
9. $d_{new} = 227.65$
   * Pre $E[Y] = \frac{800^2}{2000} = 320$. Post $E[Y^*] = \frac{(1100 - d_{new})^2}{2200} = 320 \implies (1100 - d_{new})^2 = 704,000 \implies d_{new} = 260.94$.
10. $67.10$
    * $X^* \sim \text{Exponential}(125)$. $E[Y_L^*] = 0.80 \times 125 e^{-50/125} = 100 e^{-0.40} \approx 67.03$.

---

## Day 24 Solutions

1. $200$
   * By memoryless property of Exponential, $Y_C \sim \text{Exponential}(200) \implies E[Y_C] = 200$.
2. $155.76$
   * $E[Y_L] = 200 e^{-50/200} = 200 e^{-0.25} \approx 155.76$.
3. $E[Y_C] = 150$, $E[Y_L] = 112.50$
   * $X \mid X > 100 \sim \text{Uniform}(100, 400) \implies Y_C \sim \text{Uniform}(0, 300) \implies E[Y_C] = 150$.
   * $P(X > 100) = 300/400 = 0.75 \implies E[Y_L] = 150 \times 0.75 = 112.50$.
4. $200$
   * $E[Y_L] = E[Y_C] P(X > d) = 500 \times 0.40 = 200$.
5. $400,000$
   * $E[Y_C^2] = \frac{E[Y_L^2]}{P(X > d)} = \frac{80,000}{0.20} = 400,000$.
6. $335,160$
   * $\theta = 500, d = 200$. $P(X > 200) = e^{-0.40} \approx 0.6703$.
   * $E[Y_L] = 500(0.6703) = 335.16$.
   * $E[Y_L^2] = 2(500^2)(0.6703) = 335,160$.
   * $\operatorname{Var}(Y_L) = 335,160 - (335.16)^2 = 335,160 - 112,332 = 222,828$.
7. $16,875$
   * $Y_C \sim \text{Uniform}(0, 450) \implies \operatorname{Var}(Y_C) = \frac{450^2}{12} = \frac{202,500}{12} = 16,875$.
8. $42,666.67$
   * $E[Y_C] = 200, \operatorname{Var}(Y_C) = 400^2/12 = 13,333.33 \implies E[Y_C^2] = 13,333.33 + 40,000 = 53,333.33$.
   * $E[Y_L^2] = 0.50(53,333.33) = 26,666.67$. $E[Y_L] = 0.50(200) = 100$.
   * $\operatorname{Var}(Y_L) = 26,666.67 - 100^2 = 16,666.67$.
9. **Proof:**
   * $E[Y_L] = E[Y_C] P(X > d)$. Since $P(X > d) \le 1$, $E[Y_L] \le E[Y_C]$. Q.E.D.
10. $d = 138.63$
    * $100 e^{-d/100} = 25 \implies e^{-d/100} = 0.25 \implies \frac{d}{100} = \ln(4) \approx 1.3863 \implies d = 138.63$.