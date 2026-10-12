# Q12. What Are Expectation and Variance?

## 1. Introduction

In probability and statistics, **expectation** and **variance** are two fundamental concepts used to describe a random variable.

- **Expectation (expected value):** The probability-weighted average value of a random variable.
- **Variance:** A measure of how spread out the values of a random variable are around its expected value.

Expectation describes the center of a probability distribution, while variance describes its spread.

These concepts are widely used in statistical analysis, probability theory, and machine learning.

## 2. What Is Expectation?

The **expectation**, also called the **expected value** or **population mean**, is the probability-weighted average of the possible values of a random variable.

It is written as:

$$
E[X]
$$

The formula depends on whether the random variable is discrete or continuous.

### 2.1 Expectation of a Discrete Random Variable

For a discrete random variable \(X\), the expected value is:

$$
E[X] = \sum_x x P(X=x)
$$

Here:

- \(x\) represents a possible value of \(X\).
- \(P(X=x)\) is the probability that \(X\) takes the value \(x\).
- The summation includes all possible values of \(X\).

Each possible value is multiplied by its probability, and the products are added together.

### Example: Tossing a Fair Coin

Suppose a fair coin is tossed once.

Define \(X\) as:

- \(X=1\) if the outcome is heads.
- \(X=0\) if the outcome is tails.

The probability distribution is:

| \(X\) | \(P(X=x)\) |
|---|---:|
| 0 | 0.5 |
| 1 | 0.5 |

The expected value is:

$$
E[X] = 0(0.5) + 1(0.5)
$$

$$
E[X] = 0.5
$$

Therefore, the expected value is 0.5.

**Interpretation:** A single toss cannot produce 0.5 heads. Instead, 0.5 is the long-run average number of heads per toss over many independent tosses of a fair coin.

### Example: Expected Number of Heads in Two Tosses

Suppose a fair coin is tossed twice, and \(X\) is the total number of heads.

The probability distribution is:

| \(X\) | \(P(X=x)\) |
|---|---:|
| 0 | 0.25 |
| 1 | 0.50 |
| 2 | 0.25 |

The expectation is:

$$
E[X] = 0(0.25) + 1(0.50) + 2(0.25)
$$

$$
E[X] = 0 + 0.50 + 0.50
$$

$$
E[X] = 1
$$

The expected number of heads in two tosses is 1.

## 3. Expectation of a Continuous Random Variable

For a continuous random variable \(X\) with probability density function \(f_X(x)\), the expected value is:

$$
E[X] = \int_{-\infty}^{\infty} x f_X(x)\,dx
$$

The integral accumulates the values weighted by their probability density.

The expectation is finite when the relevant integrability conditions are satisfied. A common sufficient condition is:

$$
E[|X|] < \infty
$$

### Example: Uniform Distribution

Suppose \(X\) follows a uniform distribution between 0 and 10.

Its probability density function is:

$$
f_X(x) =
\begin{cases}
\frac{1}{10}, & 0 \leq x \leq 10 \\
0, & \text{otherwise}
\end{cases}
$$

The expected value is:

$$
E[X] = \int_0^{10} x \frac{1}{10}\,dx
$$

$$
E[X] = \frac{1}{10}\left[\frac{x^2}{2}\right]_0^{10}
$$

$$
E[X] = \frac{100}{20}
$$

$$
E[X] = 5
$$

The expected value is 5, the midpoint of the interval.

## 4. What Is Variance?

**Variance** measures the expected squared deviation of a random variable from its mean.

It is commonly written as:

$$
\mathrm{Var}(X)
$$

The definition is:

$$
\mathrm{Var}(X) = E[(X-E[X])^2]
$$

Here:

- \(X\) is the random variable.
- \(E[X]\) is its expected value.
- \(X-E[X]\) is the deviation from the mean.
- Squaring the deviation ensures that deviations below and above the mean do not cancel each other out.

A larger variance generally indicates greater spread around the mean. A variance of zero means that the random variable equals a constant with probability one.

### Why Do We Square the Deviations?

Suppose values lie both below and above their mean. If we average the signed deviations, the positive and negative deviations cancel:

$$
E[X-E[X]] = 0
$$

provided the expectation exists.

To measure spread, we square the deviations before averaging them:

$$
\mathrm{Var}(X) = E[(X-E[X])^2]
$$

Squaring also gives greater weight to larger deviations.

## 5. Formulas for Variance

### 5.1 Variance of a Discrete Random Variable

For a discrete random variable:

$$
\mathrm{Var}(X) = \sum_x (x-E[X])^2 P(X=x)
$$

The procedure is:

1. Calculate the expected value.
2. Subtract the expected value from each possible value.
3. Square each deviation.
4. Multiply each squared deviation by its probability.
5. Add the weighted squared deviations.

### 5.2 Variance of a Continuous Random Variable

For a continuous random variable with PDF \(f_X(x)\):

$$
\mathrm{Var}(X) = \int_{-\infty}^{\infty} (x-E[X])^2 f_X(x)\,dx
$$

This integral calculates the probability-weighted average squared deviation from the mean.

## 6. The Shortcut Formula for Variance

An equivalent formula for variance is:

$$
\mathrm{Var}(X) = E[X^2] - (E[X])^2
$$

This is called the **computational formula for variance**.

For a discrete random variable:

$$
E[X^2] = \sum_x x^2 P(X=x)
$$

For a continuous random variable:

$$
E[X^2] = \int_{-\infty}^{\infty} x^2 f_X(x)\,dx
$$

These formulas apply when the corresponding moments exist.

### Derivation of the Shortcut Formula

Start with the definition:

$$
\mathrm{Var}(X) = E[(X-E[X])^2]
$$

Expand the square:

$$
\mathrm{Var}(X) = E[X^2 - 2X E[X] + (E[X])^2]
$$

Using the linearity of expectation:

$$
\mathrm{Var}(X) = E[X^2] - 2E[X]E[X] + (E[X])^2
$$

Simplify:

$$
\mathrm{Var}(X) = E[X^2] - 2(E[X])^2 + (E[X])^2
$$

Therefore:

$$
\mathrm{Var}(X) = E[X^2] - (E[X])^2
$$

This formula is useful for simplifying probability calculations and statistical derivations.

## 7. Worked Example: Calculating Expectation and Variance

Suppose a random variable \(X\) has the following distribution:

| \(X\) | \(P(X=x)\) |
|---|---:|
| 0 | 0.25 |
| 1 | 0.50 |
| 2 | 0.25 |

### Step 1: Calculate the Expectation

$$
E[X] = \sum_x xP(X=x)
$$

$$
E[X] = 0(0.25) + 1(0.50) + 2(0.25)
$$

$$
E[X] = 0 + 0.50 + 0.50
$$

$$
E[X] = 1
$$

### Step 2: Calculate the Second Moment

$$
E[X^2] = \sum_x x^2 P(X=x)
$$

$$
E[X^2] = 0^2(0.25) + 1^2(0.50) + 2^2(0.25)
$$

$$
E[X^2] = 0 + 0.50 + 1
$$

$$
E[X^2] = 1.5
$$

### Step 3: Calculate the Variance

Use the shortcut formula:

$$
\mathrm{Var}(X) = E[X^2] - (E[X])^2
$$

Substitute the values:

$$
\mathrm{Var}(X) = 1.5 - 1^2
$$

$$
\mathrm{Var}(X) = 0.5
$$

Therefore:

- Expected value = 1.
- Variance = 0.5.

## 8. What Is Standard Deviation?

**Standard deviation** is the square root of variance. It measures spread in the same units as the original variable.

It is written as:

$$
\sigma_X = \sqrt{\mathrm{Var}(X)}
$$

For the previous example:

$$
\sigma_X = \sqrt{0.5}
$$

$$
\sigma_X \approx 0.7071
$$

Standard deviation is often easier to interpret than variance because it uses the original measurement scale.

### Variance vs. Standard Deviation

| Feature | Variance | Standard deviation |
|---|---|---|
| Definition | Expected squared deviation from the mean | Square root of variance |
| Units | Squared units | Original units |
| Interpretation | Measures squared spread | Measures spread in the original scale |
| Value | Nonnegative | Nonnegative |

## 9. Important Properties of Expectation

### Property 1: Expectation of a Constant

For a constant \(c\):

$$
E[c] = c
$$

### Property 2: Multiplication by a Constant

For a constant \(a\):

$$
E[aX] = aE[X]
$$

### Property 3: Addition of Random Variables

For random variables \(X\) and \(Y\), when the expectations exist:

$$
E[X+Y] = E[X] + E[Y]
$$

This property does not require independence.

More generally, for constants \(a\), \(b\), and \(c\):

$$
E[aX+bY+c] = aE[X] + bE[Y] + c
$$

### Property 4: Expectation of a Function

For a discrete random variable:

$$
E[g(X)] = \sum_x g(x)P(X=x)
$$

For a continuous random variable with a PDF:

$$
E[g(X)] = \int_{-\infty}^{\infty} g(x)f_X(x)\,dx
$$

These formulas apply when the expectation exists.

In general, the expectation of a function is not equal to the function of the expectation:

$$
E[g(X)] \ne g(E[X])
$$

For example, \(E[X^2]\) is not generally equal to \((E[X])^2\).

## 10. Important Properties of Variance

### Property 1: Variance Is Nonnegative

$$
\mathrm{Var}(X) \geq 0
$$

This is because squared deviations cannot be negative.

### Property 2: Variance of a Constant

For a constant \(c\):

$$
\mathrm{Var}(c) = 0
$$

A constant has no variability.

### Property 3: Adding a Constant

Adding a constant changes the mean but not the variance:

$$
\mathrm{Var}(X+c) = \mathrm{Var}(X)
$$

### Property 4: Multiplying by a Constant

Multiplying a random variable by a constant changes its variance by the square of that constant:

$$
\mathrm{Var}(aX) = a^2\mathrm{Var}(X)
$$

For example, doubling a random variable multiplies its variance by four.

### Property 5: Variance of a Linear Transformation

For constants \(a\) and \(b\):

$$
\mathrm{Var}(aX+b) = a^2\mathrm{Var}(X)
$$

### Property 6: Variance of a Sum

For random variables \(X\) and \(Y\) with finite variances:

$$
\mathrm{Var}(X+Y) = \mathrm{Var}(X) + \mathrm{Var}(Y) + 2\mathrm{Cov}(X,Y)
$$

Covariance measures how two random variables vary together.

If \(X\) and \(Y\) are independent, their covariance is zero. Therefore:

$$
\mathrm{Var}(X+Y) = \mathrm{Var}(X) + \mathrm{Var}(Y)
$$

Independence is sufficient for this simplification. Zero covariance is also sufficient, even when the variables are not independent.

For more than two random variables, the variance of their sum includes the individual variances and twice each pairwise covariance.

## 11. Intuitive Example: Same Mean, Different Variance

Consider two datasets.

**Dataset A:**

$$
10,\ 10,\ 10,\ 10,\ 10
$$

**Dataset B:**

$$
2,\ 6,\ 10,\ 14,\ 18
$$

Both datasets have mean 10.

For Dataset A, every value equals the mean, so the variance is zero.

For Dataset B, the values vary around the mean, so the variance is positive.

This illustrates an important principle:

**Two datasets can have the same mean but different variances.**

The mean describes the center, while variance describes spread around the center.

## 12. Population Variance vs. Sample Variance

It is important to distinguish population variance from sample variance.

### 12.1 Population Variance

If the complete population contains \(N\) values \(x_1,x_2,\ldots,x_N\), its mean is:

$$
\mu = \frac{1}{N}\sum_{i=1}^{N}x_i
$$

The population variance is:

$$
\sigma^2 = \frac{1}{N}\sum_{i=1}^{N}(x_i-\mu)^2
$$

This formula describes the variance of the complete population.

### 12.2 Sample Variance

If we observe a sample of \(n\) values, its sample mean is:

$$
\bar{x} = \frac{1}{n}\sum_{i=1}^{n}x_i
$$

The usual unbiased estimator of the population variance is:

$$
s^2 = \frac{1}{n-1}\sum_{i=1}^{n}(x_i-\bar{x})^2
$$

The denominator is \(n-1\), rather than \(n\), because the sample mean is estimated from the same observations. Under standard random-sampling assumptions, this correction makes the sample variance an unbiased estimator of the population variance.

If the goal is simply to calculate the variance of the observed dataset, dividing by \(n\) may be appropriate instead.

### Comparison

| Feature | Population variance | Usual sample variance estimator |
|---|---|---|
| Purpose | Describe a complete population | Estimate population variance from a sample |
| Mean used | Population mean \(\mu\) | Sample mean \(\bar{x}\) |
| Denominator | \(N\) | \(n-1\) |
| Common notation | \(\sigma^2\) | \(s^2\) |

## 13. Applications in Machine Learning

### 13.1 Bias-Variance Trade-Off

The bias-variance trade-off describes two important sources of prediction error in many supervised-learning settings.

- **Bias:** Error caused by overly restrictive assumptions or systematic model limitations.
- **Variance:** Sensitivity of a model's predictions to changes in its training data.

A model with high bias may underfit the data. A model with high variance may overfit the training data.

Balancing these factors can help improve generalization to unseen data.

### 13.2 Feature Scaling and Standardization

Feature standardization commonly uses the mean and standard deviation:

$$
z = \frac{x-\mu}{\sigma}
$$

Here:

- \(x\) is the original feature value.
- \(\mu\) is the feature mean.
- \(\sigma\) is the feature standard deviation.

This transformation centers the feature around zero and scales it by its standard deviation, provided the standard deviation is nonzero.

Standardization can be useful for algorithms sensitive to feature scales, including regularized linear models, support vector machines, and many gradient-based models.

### 13.3 Loss Functions

Many machine-learning objectives involve expected losses.

$$
E[L(Y,\hat{Y})]
$$

Here:

- \(Y\) is the true target.
- \(\hat{Y}\) is the model prediction.
- \(L\) is the loss function.

In practice, the expected loss is often approximated by the average loss over training examples.

### 13.4 Probabilistic Predictions

Probabilistic models can estimate an expected outcome and a measure of uncertainty.

For example, a model predicting delivery time might estimate the expected delivery duration and the variance of the predicted distribution.

A larger predictive variance indicates greater spread in the predicted outcomes under the model.

### 13.5 Weight Initialization and Training Stability

Some neural-network initialization methods use weight variance to help maintain suitable activation and gradient scales across layers.

Poorly chosen scales can contribute to vanishing or exploding activations and gradients.

Variance is therefore important when designing and understanding neural-network initialization methods.

## 14. Common Mistakes

### Mistake 1: Thinking the Expected Value Must Be a Possible Outcome

The expected value is a probability-weighted average. It does not need to be one of the possible values of the random variable.

For example, a random variable that takes only 0 or 1 can have an expected value of 0.3.

### Mistake 2: Confusing \(E[X^2]\) with \((E[X])^2\)

These are generally different quantities.

The correct variance formula is:

$$
\mathrm{Var}(X) = E[X^2] - (E[X])^2
$$

Do not assume that \(E[X^2]\) equals \((E[X])^2\).

### Mistake 3: Forgetting to Square the Constant in Variance

The correct rule is:

$$
\mathrm{Var}(aX) = a^2\mathrm{Var}(X)
$$

Variance scales by the square of the multiplier.

### Mistake 4: Assuming Variance Can Be Negative

Variance cannot be negative because it is the expectation of a squared deviation.

### Mistake 5: Assuming Variances Always Add

For two random variables:

$$
\mathrm{Var}(X+Y) = \mathrm{Var}(X) + \mathrm{Var}(Y) + 2\mathrm{Cov}(X,Y)
$$

The covariance term cannot be ignored unless it is zero.

### Mistake 6: Confusing Population and Sample Variance

Population variance divides by \(N\), while the usual unbiased sample variance estimator divides by \(n-1\).

The appropriate formula depends on the goal of the calculation.

## 15. Common Interview Questions and Answers

### Q1. What is expectation?

**Answer:** Expectation is the probability-weighted average of a random variable's possible values.

For a discrete random variable:

$$
E[X] = \sum_x xP(X=x)
$$

### Q2. What is variance?

**Answer:** Variance measures the expected squared deviation of a random variable from its mean.

$$
\mathrm{Var}(X) = E[(X-E[X])^2]
$$

### Q3. What is the shortcut formula for variance?

**Answer:**

$$
\mathrm{Var}(X) = E[X^2] - (E[X])^2
$$

### Q4. What is the difference between variance and standard deviation?

**Answer:** Standard deviation is the square root of variance. Variance uses squared units, while standard deviation uses the original units.

### Q5. Can expectation be negative?

**Answer:** Yes. A random variable can have a negative expected value if its probability-weighted outcomes produce a negative mean.

### Q6. Can variance be negative?

**Answer:** No. Variance is nonnegative because it is the expectation of a squared deviation, when defined.

### Q7. What happens to variance when a constant is added?

**Answer:** Adding a constant does not change variance.

$$
\mathrm{Var}(X+c) = \mathrm{Var}(X)
$$

### Q8. What happens to variance when a random variable is multiplied by a constant?

**Answer:** Variance is multiplied by the square of that constant.

$$
\mathrm{Var}(aX) = a^2\mathrm{Var}(X)
$$

### Q9. Does expectation require independence?

**Answer:** No. Linearity of expectation holds without independence, provided the relevant expectations exist.

$$
E[X+Y] = E[X] + E[Y]
$$

### Q10. When can the variance of a sum be simplified?

**Answer:** When the variables have zero covariance, the variance of their sum equals the sum of their variances. Independence is sufficient for zero covariance when the relevant moments are finite.

### Q11. Why is sample variance often calculated using \(n-1\)?

**Answer:** Under standard random-sampling assumptions, using \(n-1\) gives an unbiased estimator of population variance because the sample mean is estimated from the same observations.

### Q12. How are expectation and variance used in machine learning?

**Answer:** They are used in probabilistic predictions, feature standardization, expected-loss calculations, uncertainty estimation, neural-network initialization, and understanding the bias-variance trade-off.

## 16. Practice Problems

### Problem 1: Calculate Expectation

A random variable \(X\) has this distribution:

| \(X\) | Probability |
|---|---:|
| 1 | 0.2 |
| 2 | 0.5 |
| 3 | 0.3 |

Calculate \(E[X]\).

**Solution:**

$$
E[X] = 1(0.2) + 2(0.5) + 3(0.3)
$$

$$
E[X] = 0.2 + 1.0 + 0.9
$$

$$
E[X] = 2.1
$$

### Problem 2: Calculate Variance

Using the same distribution, calculate \(\mathrm{Var}(X)\).

**Step 1: Calculate the second moment.**

$$
E[X^2] = 1^2(0.2) + 2^2(0.5) + 3^2(0.3)
$$

$$
E[X^2] = 0.2 + 2.0 + 2.7
$$

$$
E[X^2] = 4.9
$$

**Step 2: Apply the variance formula.**

$$
\mathrm{Var}(X) = E[X^2] - (E[X])^2
$$

$$
\mathrm{Var}(X) = 4.9 - 2.1^2
$$

$$
\mathrm{Var}(X) = 4.9 - 4.41
$$

$$
\mathrm{Var}(X) = 0.49
$$

### Problem 3: Calculate Standard Deviation

Using the variance from Problem 2:

$$
\sigma_X = \sqrt{0.49}
$$

$$
\sigma_X = 0.7
$$

### Problem 4: Variance Under Scaling

Suppose:

$$
\mathrm{Var}(X) = 4
$$

Let \(Y=3X+2\). Calculate \(\mathrm{Var}(Y)\).

**Solution:**

$$
\mathrm{Var}(3X+2) = 3^2\mathrm{Var}(X)
$$

$$
\mathrm{Var}(Y) = 9(4)
$$

$$
\mathrm{Var}(Y) = 36
$$

### Problem 5: Variance of a Sum

Suppose \(X\) and \(Y\) are independent random variables, and each has variance 4.

Calculate the variance of \(X+Y\).

**Solution:**

Because the variables are independent, their covariance is zero.

$$
\mathrm{Var}(X+Y) = \mathrm{Var}(X) + \mathrm{Var}(Y)
$$

$$
\mathrm{Var}(X+Y) = 4 + 4
$$

$$
\mathrm{Var}(X+Y) = 8
$$

## 17. Final Summary

- **Expectation** describes the probability-weighted average of a random variable.
- **Variance** measures the expected squared deviation from the mean.
- **Standard deviation** is the square root of variance.
- The shortcut formula for variance is the second moment minus the square of the mean.
- Expectation is linear even when random variables are dependent.
- The variance of a sum includes covariance terms unless the covariance terms are zero.
- Population variance and sample variance use different denominators because they serve different purposes.
- Expectation and variance are fundamental to statistics, uncertainty estimation, and machine learning.
