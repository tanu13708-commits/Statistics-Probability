# Q14. Explain the Bernoulli and Binomial Distributions

## 1. Introduction

The **Bernoulli distribution** and the **binomial distribution** are two fundamental probability distributions used to model outcomes involving success and failure.

- **Bernoulli distribution:** Models the outcome of a single trial with two possible outcomes.
- **Binomial distribution:** Models the number of successes in a fixed number of independent Bernoulli trials with the same probability of success.

These distributions are widely used in statistics, probability, experimentation, and machine learning.

### Real-world examples

- Whether a customer clicks an advertisement.
- Whether an email is classified as spam.
- Whether a product is defective.
- Whether a user purchases a product.
- The number of successful conversions in a marketing campaign.

The key difference is that a Bernoulli random variable represents the result of one trial, while a binomial random variable counts successes across multiple trials.

## 2. What Is the Bernoulli Distribution?

A **Bernoulli distribution** models a single random experiment with exactly two possible outcomes, conventionally called success and failure.

Let \(X\) be a Bernoulli random variable:

- \(X=1\) represents success.
- \(X=0\) represents failure.

Let \(p\) denote the probability of success. The probability of failure is \(1-p\).

The probability mass function (PMF) is:

$$
P(X=x)=p^x(1-p)^{1-x}, \qquad x\in\{0,1\}
$$

where:

$$
0\leq p\leq 1
$$

This formula gives:

$$
P(X=1)=p
$$

and:

$$
P(X=0)=1-p
$$

### Example: Customer Click

Suppose a user has a 30% probability of clicking an advertisement.

Define:

$$
X =
\begin{cases}
1, & \text{if the user clicks} \\
0, & \text{if the user does not click}
\end{cases}
$$

The success probability is:

$$
p=0.30
$$

Therefore:

$$
P(X=1)=0.30
$$

$$
P(X=0)=1-0.30=0.70
$$

The random variable follows a Bernoulli distribution with success probability 0.30.

We write:

$$
X\sim \mathrm{Bernoulli}(0.30)
$$

Here, the notation describes a probability model for the outcome of one trial. It does not mean that every individual trial is guaranteed to succeed or fail in a predictable way.

## 3. Mean and Variance of a Bernoulli Random Variable

The Bernoulli distribution has simple expressions for its expected value and variance.

### 3.1 Expected Value

The expected value is:

$$
E[X]=\sum_x xP(X=x)
$$

Since \(X\) can take only the values 0 and 1:

$$
E[X]=0P(X=0)+1P(X=1)
$$

Substituting the probabilities:

$$
E[X]=0(1-p)+1(p)
$$

Therefore:

$$
E[X]=p
$$

**Interpretation:** The expected value of a Bernoulli random variable equals its probability of success.

For example, if the probability that a customer clicks is 0.30, then the expected value of the binary click indicator is 0.30.

This is an average over repeated trials or a probability-model expectation, not a claim that an individual outcome can equal 0.30.

### 3.2 Variance

Variance is defined as:

$$
\mathrm{Var}(X)=E[X^2]-(E[X])^2
$$

Since \(X\) is either 0 or 1, squaring it does not change its value:

$$
X^2=X
$$

Therefore:

$$
E[X^2]=E[X]=p
$$

Substituting into the variance formula:

$$
\mathrm{Var}(X)=p-p^2
$$

Hence:

$$
\mathrm{Var}(X)=p(1-p)
$$

### 3.3 Standard Deviation

The standard deviation is the square root of the variance:

$$
\mathrm{SD}(X)=\sqrt{p(1-p)}
$$

### Important properties

- The expected value is \(p\).
- The variance is \(p(1-p)\).
- The variance is zero when \(p=0\) or \(p=1\), because the outcome is then certain.
- The variance is largest at \(p=0.5\), where the two outcomes are equally likely.

## 4. What Is the Binomial Distribution?

A **binomial distribution** models the number of successes in a fixed number of independent Bernoulli trials, assuming every trial has the same probability of success.

Let:

- \(n\) be the number of trials.
- \(p\) be the probability of success on each trial.
- \(X\) be the total number of successes.

The binomial random variable can take the values:

$$
X\in\{0,1,2,\ldots,n\}
$$

We write:

$$
X\sim \mathrm{Binomial}(n,p)
$$

### Conditions for a Binomial Distribution

A random variable follows a binomial distribution when these conditions hold:

1. **Fixed number of trials:** The experiment contains exactly \(n\) trials.
2. **Two outcomes per trial:** Each trial is classified as success or failure.
3. **Independence:** The outcome of one trial does not affect the outcomes of other trials.
4. **Constant success probability:** Every trial has the same probability \(p\) of success.
5. **Success count:** The random variable counts the total number of successes.

If these assumptions are not appropriate, another probability model may be needed.

### Example: Number of Customers Who Click

Suppose 10 customers independently see an advertisement. Each customer has a 30% probability of clicking.

Let \(X\) represent the number of customers who click.

Then:

$$
X\sim \mathrm{Binomial}(10,0.30)
$$

The possible values of \(X\) are:

$$
X\in\{0,1,2,\ldots,10\}
$$

Unlike the Bernoulli variable for one customer, this binomial variable counts successes across all 10 customers.

## 5. Probability Mass Function of the Binomial Distribution

The binomial PMF gives the probability of observing exactly \(k\) successes in \(n\) independent trials.

$$
P(X=k)=\binom{n}{k}p^k(1-p)^{n-k}
$$

where:

$$
k=0,1,2,\ldots,n
$$

The binomial coefficient is:

$$
\binom{n}{k}=\frac{n!}{k!(n-k)!}
$$

Here:

- \(n!\) is the factorial of \(n\).
- \(k!\) is the factorial of \(k\).
- \(p^k\) represents the probability contribution from \(k\) successes.
- \((1-p)^{n-k}\) represents the probability contribution from \(n-k\) failures.
- \(\binom{n}{k}\) counts the number of ways to choose which \(k\) trials are successes.

### Why Is the Binomial Coefficient Needed?

Suppose we conduct three trials and want exactly two successes.

Possible sequences include:

- Success, Success, Failure.
- Success, Failure, Success.
- Failure, Success, Success.

There are three possible arrangements.

Each arrangement has probability:

$$
p^2(1-p)
$$

Because the arrangements are mutually exclusive, their probabilities add:

$$
P(X=2)=3p^2(1-p)
$$

The coefficient 3 is:

$$
\binom{3}{2}=3
$$

In general, the number of arrangements of \(k\) successes among \(n\) trials is \(\binom{n}{k}\). This leads to the binomial PMF.

## 6. Worked Example: Exactly Two Successes

Suppose a fair coin is tossed three times. Let a head be a success.

Then:

$$
n=3,\qquad p=0.5
$$

Let \(X\) count the number of heads.

The probability of exactly two heads is:

$$
P(X=2)=\binom{3}{2}(0.5)^2(0.5)^{3-2}
$$

Since:

$$
\binom{3}{2}=3
$$

we obtain:

$$
P(X=2)=3(0.25)(0.5)
$$

Therefore:

$$
P(X=2)=0.375
$$

So the probability of getting exactly two heads is 37.5%.

## 7. Mean and Variance of a Binomial Random Variable

For a binomial random variable:

$$
X\sim \mathrm{Binomial}(n,p)
$$

the expected value and variance are:

### 7.1 Expected Value

$$
E[X]=np
$$

**Interpretation:** Over repeated experiments, the average number of successes approaches \(np\) under the model assumptions.

For example, if 100 independent customers each have a 30% probability of purchasing:

$$
E[X]=100(0.30)
$$

$$
E[X]=30
$$

The expected number of purchases is 30. The actual number in any one group can be higher or lower.

### 7.2 Variance

$$
\mathrm{Var}(X)=np(1-p)
$$

### 7.3 Standard Deviation

$$
\mathrm{SD}(X)=\sqrt{np(1-p)}
$$

For 100 independent customers with purchase probability 0.30:

$$
\mathrm{Var}(X)=100(0.30)(0.70)
$$

$$
\mathrm{Var}(X)=21
$$

The standard deviation is:

$$
\mathrm{SD}(X)=\sqrt{21}
$$

$$
\mathrm{SD}(X)\approx 4.58
$$

The expected number of purchases is 30, and the standard deviation of the number of purchases is approximately 4.58.

This describes the variability in the count across repeated groups of 100 customers under the model assumptions.

## 8. Why Are the Binomial Mean and Variance Equal to These Formulas?

A binomial random variable can be represented as the sum of independent Bernoulli random variables.

Let \(X_i\) indicate whether trial \(i\) is a success:

$$
X_i =
\begin{cases}
1, & \text{if trial }i\text{ succeeds} \\
0, & \text{otherwise}
\end{cases}
$$

Each trial follows:

$$
X_i\sim \mathrm{Bernoulli}(p)
$$

The total number of successes is:

$$
X=X_1+X_2+\cdots+X_n
$$

### 8.1 Deriving the Mean

By linearity of expectation:

$$
E[X]=E[X_1+X_2+\cdots+X_n]
$$

Therefore:

$$
E[X]=E[X_1]+E[X_2]+\cdots+E[X_n]
$$

Each Bernoulli variable has expected value \(p\), so:

$$
E[X]=p+p+\cdots+p
$$

There are \(n\) terms:

$$
E[X]=np
$$

Importantly, linearity of expectation does not require independence.

### 8.2 Deriving the Variance

For independent random variables, the variance of their sum is the sum of their variances.

Therefore:

$$
\mathrm{Var}(X)=\sum_{i=1}^{n}\mathrm{Var}(X_i)
$$

Each Bernoulli variable has variance \(p(1-p)\):

$$
\mathrm{Var}(X)=\sum_{i=1}^{n}p(1-p)
$$

There are \(n\) identical terms:

$$
\mathrm{Var}(X)=np(1-p)
$$

The independence assumption matters for this variance derivation. If trial outcomes are dependent, the variance may include covariance terms and the binomial model may not apply.

## 9. Bernoulli vs. Binomial Distribution

| Feature | Bernoulli distribution | Binomial distribution |
|---|---|---|
| Number of trials | One | Fixed number \(n\) |
| Random variable | Outcome of one trial | Number of successes |
| Possible values | 0 or 1 | 0 through \(n\) |
| Parameters | \(p\) | \(n,p\) |
| Mean | \(p\) | \(np\) |
| Variance | \(p(1-p)\) | \(np(1-p)\) |
| Example | Whether one customer clicks | Number of customers who click among 100 |

A Bernoulli distribution is a special case of a binomial distribution when \(n=1\).

$$
\mathrm{Bernoulli}(p)=\mathrm{Binomial}(1,p)
$$

The two models are closely related because the binomial distribution counts successes across repeated Bernoulli trials.

## 10. Probability of At Least One Success

A common binomial probability question asks for the probability of at least one success.

For:

$$
X\sim \mathrm{Binomial}(n,p)
$$

we want:

$$
P(X\geq 1)
$$

It is often easiest to use the complement rule.

The complement of at least one success is zero successes:

$$
P(X\geq 1)=1-P(X=0)
$$

Using the binomial PMF:

$$
P(X=0)=\binom{n}{0}p^0(1-p)^n
$$

Since \(\binom{n}{0}=1\) and \(p^0=1\):

$$
P(X=0)=(1-p)^n
$$

Therefore:

$$
P(X\geq 1)=1-(1-p)^n
$$

### Example

Suppose a customer independently clicks an advertisement with probability 0.20. Five customers see the advertisement.

The probability that at least one customer clicks is:

$$
P(X\geq 1)=1-(1-0.20)^5
$$

$$
P(X\geq 1)=1-(0.80)^5
$$

$$
P(X\geq 1)=1-0.32768
$$

$$
P(X\geq 1)=0.67232
$$

The probability of at least one click is 67.232%.

## 11. Probability of No Success

For a binomial random variable:

$$
X\sim \mathrm{Binomial}(n,p)
$$

the probability of zero successes is:

$$
P(X=0)=(1-p)^n
$$

This is useful when calculating the probability that no customer purchases, no component fails, or no event occurs across a fixed number of independent trials.

For example, if a product has a 2% probability of being defective and 10 products are independently inspected, the probability that none is defective is:

$$
P(X=0)=(1-0.02)^{10}
$$

$$
P(X=0)=(0.98)^{10}
$$

$$
P(X=0)\approx 0.8171
$$

The probability that none of the 10 products is defective is approximately 81.71%, assuming independence and a constant defect probability.

## 12. When Is the Binomial Distribution Not Appropriate?

The binomial model requires a fixed number of trials, two outcomes per trial, independence, and a constant success probability.

It may not be appropriate in the following situations.

### 12.1 Changing Success Probabilities

Suppose the first trial has success probability 0.20 and the second has success probability 0.70.

If these probabilities differ, the number of successes generally does not follow a binomial distribution.

For independent trials with different success probabilities, the count may instead follow a Poisson-binomial distribution.

### 12.2 Dependent Trials

Suppose customers influence one another's purchasing decisions, so one customer's outcome affects another's.

The independence assumption may fail, making the ordinary binomial model inappropriate.

### 12.3 Sampling Without Replacement

When drawing items without replacement from a finite population, the probability of success may change after each draw.

For example, the number of defective items found in a sample drawn without replacement from a finite batch is often modeled using the hypergeometric distribution rather than the binomial distribution.

The binomial distribution may still be a useful approximation when the sample is small relative to the population and the success probability changes negligibly.

### 12.4 Random Number of Trials

The binomial distribution assumes a fixed number of trials.

If the number of trials itself is random, a different model or a conditional model may be necessary.

## 13. Relationship to Other Probability Distributions

### 13.1 Bernoulli and Binomial

A Bernoulli random variable models one binary outcome. A binomial random variable sums \(n\) independent Bernoulli outcomes with the same success probability.

$$
X=\sum_{i=1}^{n}X_i
$$

### 13.2 Binomial and Poisson

When \(n\) is large, \(p\) is small, and \(np\) remains moderate, a binomial distribution may be approximated by a Poisson distribution with rate:

$$
\lambda=np
$$

The approximation is:

$$
\mathrm{Binomial}(n,p)\approx \mathrm{Poisson}(\lambda)
$$

This is an approximation, not an exact identity.

It is useful for modeling rare events, such as a small number of defects among many independently manufactured items.

### 13.3 Binomial and Normal

Under suitable conditions, a binomial distribution can be approximated by a normal distribution.

For a binomial random variable:

$$
X\sim \mathrm{Binomial}(n,p)
$$

the mean and variance are:

$$
\mu=np
$$

$$
\sigma^2=np(1-p)
$$

A normal approximation is often reasonable when both \(np\) and \(n(1-p)\) are sufficiently large. A common rule of thumb is that both should be at least 5 or 10, although the required accuracy depends on the application and the probability being estimated.

The approximating normal distribution is:

$$
X\approx N(np,np(1-p))
$$

Here, the second parameter denotes the variance.

When using a continuous normal distribution to approximate discrete binomial probabilities, a continuity correction can improve accuracy.

For example:

$$
P(X\leq k)\approx P(Y\leq k+0.5)
$$

where \(Y\) is the approximating normal random variable.

## 14. Applications in Machine Learning and Data Science

### 14.1 Binary Classification

Many classification problems involve two possible outcomes.

Examples include:

- Spam or not spam.
- Fraud or not fraud.
- Churn or no churn.
- Click or no click.
- Purchase or no purchase.

A Bernoulli distribution can model an individual binary outcome when the probability of success is known or estimated.

For example, if a model estimates that a customer has a 70% probability of purchasing, a binary purchase indicator can be modeled as:

$$
Y\sim \mathrm{Bernoulli}(0.70)
$$

This describes the probabilistic outcome for that customer.

### 14.2 Logistic Regression

Logistic regression estimates a probability for a binary outcome.

Its predicted probability can be written as:

$$
p_i=P(Y_i=1\mid X_i)
$$

A Bernoulli likelihood for the observed label is:

$$
P(Y_i=y_i\mid X_i)=p_i^{y_i}(1-p_i)^{1-y_i}
$$

where \(y_i\) is either 0 or 1.

For independent observations under this model, the likelihood across observations is:

$$
L=\prod_{i=1}^{n}p_i^{y_i}(1-p_i)^{1-y_i}
$$

Maximizing this likelihood is equivalent to minimizing the negative log-likelihood, which is closely related to binary cross-entropy loss.

This is one reason the Bernoulli distribution is central to binary classification.

### 14.3 Conversion Rate Modeling

Suppose a website receives 1,000 independent visits and each visit has the same conversion probability \(p\).

If \(X\) is the number of conversions, then:

$$
X\sim \mathrm{Binomial}(1000,p)
$$

The expected number of conversions is:

$$
E[X]=1000p
$$

The variance is:

$$
\mathrm{Var}(X)=1000p(1-p)
$$

This provides a probability model for variation in the number of conversions.

In real-world applications, visitor outcomes may not be independent or have identical probabilities. Traffic source, device, user segment, and time can all affect conversion probability.

### 14.4 A/B Testing

In an A/B test, each user may either convert or not convert.

For a group of \(n\) users with a common conversion probability \(p\), the number of conversions can be modeled as:

$$
X\sim \mathrm{Binomial}(n,p)
$$

For example, the conversion counts for two website versions can be compared to evaluate whether their conversion rates differ.

The model assumptions and the experimental design matter. Users should be assigned appropriately, and repeated or dependent observations may require a more careful analysis.

### 14.5 Modeling Defects

Suppose a manufacturing process produces items with a constant defect probability \(p\), and defect outcomes are independent.

The number of defective items in a batch of \(n\) items can be modeled as:

$$
X\sim \mathrm{Binomial}(n,p)
$$

This allows analysts to estimate expected defect counts and calculate probabilities of exceeding quality-control thresholds.

## 15. Common Mistakes

### Mistake 1: Confusing Bernoulli and Binomial Distributions

Bernoulli models a single binary outcome. Binomial models the number of successes across a fixed number of qualifying trials.

### Mistake 2: Forgetting the Independence Assumption

A fixed number of binary trials is not enough to guarantee a binomial distribution. The trials must also be independent and have the same success probability.

### Mistake 3: Confusing the Mean with the Actual Count

For a binomial random variable:

$$
E[X]=np
$$

This is the expected count, not a guarantee that the observed count equals \(np\).

### Mistake 4: Forgetting the Failure Probability

The probability of failure is:

$$
1-p
$$

The probability of exactly \(k\) successes includes the probability of \(n-k\) failures.

### Mistake 5: Omitting the Binomial Coefficient

The term:

$$
\binom{n}{k}
$$

counts the number of different arrangements of \(k\) successes among \(n\) trials. Without it, the formula generally gives the probability of a particular arrangement rather than the probability of exactly \(k\) successes.

### Mistake 6: Using a Binomial Model for Sampling Without Replacement

Sampling without replacement from a finite population usually changes the success probability after each draw. A hypergeometric model may be more appropriate.

### Mistake 7: Assuming the Poisson or Normal Approximation Is Always Accurate

Approximations depend on the parameter values and the desired accuracy. Check their conditions before using them.

## 16. Common Interview Questions and Answers

### Q1. What is a Bernoulli distribution?

**Answer:** It models one trial with two outcomes, commonly represented as 1 for success and 0 for failure, with success probability \(p\).

### Q2. What is a binomial distribution?

**Answer:** It models the number of successes in a fixed number of independent Bernoulli trials with the same success probability.

### Q3. What is the mean of a Bernoulli random variable?

**Answer:**

$$
E[X]=p
$$

### Q4. What is the variance of a Bernoulli random variable?

**Answer:**

$$
\mathrm{Var}(X)=p(1-p)
$$

### Q5. What is the mean of a binomial random variable?

**Answer:**

$$
E[X]=np
$$

### Q6. What is the variance of a binomial random variable?

**Answer:**

$$
\mathrm{Var}(X)=np(1-p)
$$

### Q7. Why does the binomial PMF contain a binomial coefficient?

**Answer:** The coefficient counts the number of ways to arrange \(k\) successes among \(n\) trials.

### Q8. What is the relationship between Bernoulli and binomial distributions?

**Answer:** A binomial random variable is the sum of \(n\) independent Bernoulli random variables with the same success probability. Bernoulli is the special case where \(n=1\).

### Q9. What is the probability of at least one success?

**Answer:**

$$
P(X\geq 1)=1-(1-p)^n
$$

This follows from taking the complement of zero successes.

### Q10. When is a binomial distribution inappropriate?

**Answer:** It is inappropriate when the number of trials is not fixed, trials are dependent, or the success probability changes across trials, unless a suitable approximation or alternative model is justified.

### Q11. How is the Bernoulli distribution used in logistic regression?

**Answer:** Logistic regression estimates the probability of a binary label. The observed label is commonly modeled with a Bernoulli distribution, and model parameters can be estimated by maximizing the likelihood.

### Q12. When can a binomial distribution be approximated by a Poisson distribution?

**Answer:** A common situation is when \(n\) is large, \(p\) is small, and \(np\) remains moderate. The Poisson rate is set to \(\lambda=np\).

### Q13. How does the binomial distribution relate to A/B testing?

**Answer:** When each user has a binary conversion outcome and the assumptions are appropriate, the conversion count in each group can be modeled with a binomial distribution.

## 17. Practice Problems

### Problem 1: Bernoulli Probability

A user has a 40% probability of clicking an advertisement. Let \(X=1\) indicate a click and \(X=0\) indicate no click.

Find:

1. \(P(X=1)\)
2. \(P(X=0)\)
3. \(E[X]\)
4. \(\mathrm{Var}(X)\)

**Solution:**

The success probability is:

$$
p=0.40
$$

Therefore:

$$
P(X=1)=0.40
$$

$$
P(X=0)=1-0.40=0.60
$$

The expected value is:

$$
E[X]=p=0.40
$$

The variance is:

$$
\mathrm{Var}(X)=p(1-p)
$$

$$
\mathrm{Var}(X)=0.40(0.60)
$$

$$
\mathrm{Var}(X)=0.24
$$

### Problem 2: Exactly Three Successes

A fair coin is tossed five times. Find the probability of exactly three heads.

**Solution:**

Here:

$$
n=5,\qquad p=0.5,\qquad k=3
$$

Using the binomial PMF:

$$
P(X=3)=\binom{5}{3}(0.5)^3(0.5)^2
$$

Since:

$$
\binom{5}{3}=10
$$

we obtain:

$$
P(X=3)=10(0.125)(0.25)
$$

$$
P(X=3)=0.3125
$$

The probability is 31.25%.

### Problem 3: Expected Number of Purchases

A website receives 200 independent visits. Each visit has a purchase probability of 0.05.

Find the expected number of purchases and the standard deviation.

**Solution:**

The parameters are:

$$
n=200,\qquad p=0.05
$$

The expected count is:

$$
E[X]=np
$$

$$
E[X]=200(0.05)=10
$$

The variance is:

$$
\mathrm{Var}(X)=np(1-p)
$$

$$
\mathrm{Var}(X)=200(0.05)(0.95)
$$

$$
\mathrm{Var}(X)=9.5
$$

The standard deviation is:

$$
\mathrm{SD}(X)=\sqrt{9.5}
$$

$$
\mathrm{SD}(X)\approx 3.08
$$

The expected number of purchases is 10, with a standard deviation of approximately 3.08.

### Problem 4: At Least One Defective Item

Each item has a 2% probability of being defective. Assume 20 items are independently produced with the same defect probability.

Find the probability that at least one item is defective.

**Solution:**

The number of defective items follows:

$$
X\sim \mathrm{Binomial}(20,0.02)
$$

Using the complement rule:

$$
P(X\geq 1)=1-P(X=0)
$$

Therefore:

$$
P(X\geq 1)=1-(1-0.02)^{20}
$$

$$
P(X\geq 1)=1-(0.98)^{20}
$$

$$
P(X\geq 1)\approx 0.3324
$$

The probability that at least one item is defective is approximately 33.24%.

### Problem 5: Identify the Distribution

Choose the most appropriate distribution under each scenario.

1. Whether a single email is spam.
2. The number of spam emails among 50 independent emails with the same spam probability.
3. The number of defective items selected without replacement from a small finite batch with a known number of defective items.

**Solution:**

1. **Bernoulli distribution**, because there is one binary outcome.
2. **Binomial distribution**, assuming independence and a constant spam probability.
3. **Hypergeometric distribution**, because sampling without replacement from a finite population changes the probabilities across draws.

## 18. Final Summary

- The Bernoulli distribution models one binary trial.
- The binomial distribution counts successes across a fixed number of independent trials with the same success probability.
- For a Bernoulli random variable, the mean is \(p\) and the variance is \(p(1-p)\).
- For a binomial random variable, the mean is \(np\) and the variance is \(np(1-p)\).
- The binomial PMF includes a binomial coefficient to count possible arrangements of successes.
- The probability of at least one success is \(1-(1-p)^n\).
- The binomial model requires a fixed trial count, binary outcomes, independence, and a constant success probability.
- Bernoulli models are important in binary classification, while binomial models are useful for conversion counts, quality control, and experiments.
- Poisson and normal distributions can approximate the binomial distribution under suitable conditions.

