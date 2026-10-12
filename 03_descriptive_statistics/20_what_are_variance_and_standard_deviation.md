# Q20. What Are Variance and Standard Deviation?

## 1. Introduction

Variance and standard deviation are two fundamental measures of dispersion in statistics. They describe how spread out the observations are around their mean.

Two datasets can have the same mean but very different levels of variability.

For example:

Dataset A: `48, 49, 50, 51, 52`

Dataset B: `10, 30, 50, 70, 90`

Both datasets have a mean of 50, but Dataset B is much more spread out.

Variance and standard deviation help us quantify this difference.

- **Variance** measures the average squared deviation from the mean.
- **Standard deviation** is the square root of the variance and measures spread in the original units of the data.

These concepts are important in descriptive statistics, probability, hypothesis testing, and machine learning.

---

## 2. What Is Variance?

### Definition

Variance measures how far observations tend to spread around their mean by calculating the average of their squared deviations from that mean.

A small variance indicates that observations are relatively close to the mean. A large variance indicates greater spread around the mean.

### A. Population variance

When the dataset contains the entire population of interest, population variance is calculated as:

$$
\sigma^2 = \frac{1}{N}\sum_{i=1}^{N}(x_i-\mu)^2
$$

Where:

- \(\sigma^2\) = population variance
- \(N\) = number of observations in the population
- \(x_i\) = the \(i\)-th observation
- \(\mu\) = population mean
- \(\sum\) = summation over all observations

### B. Sample variance

When we have a sample and want to estimate the population variance, the usual unbiased sample variance is:

$$
s^2 = \frac{1}{n-1}\sum_{i=1}^{n}(x_i-\bar{x})^2
$$

Where:

- \(s^2\) = sample variance
- \(n\) = sample size
- \(x_i\) = the \(i\)-th sample observation
- \(\bar{x}\) = sample mean
- \(n-1\) = degrees of freedom

**Important distinction:** Population variance divides by \(N\), whereas the usual unbiased sample variance divides by \(n-1\). The sample formula corrects for the tendency of squared deviations around the sample mean to underestimate the population variance.

The \(n-1\) formula is unbiased for population variance under independent, identically distributed sampling with a finite population variance. Other variance estimators may be appropriate under different assumptions or objectives.

---

## 3. How to Calculate Variance Step by Step

Consider the dataset:

`2, 4, 6, 8, 10`

We will calculate its population variance.

### Step 1: Calculate the mean

$$
\mu = \frac{2+4+6+8+10}{5}
$$

$$
\mu = \frac{30}{5} = 6
$$

### Step 2: Calculate the deviation of each observation from the mean

The deviation is:

$$
x_i-\mu
$$

| Observation | Mean | Deviation |
|---:|---:|---:|
| 2 | 6 | -4 |
| 4 | 6 | -2 |
| 6 | 6 | 0 |
| 8 | 6 | 2 |
| 10 | 6 | 4 |

### Step 3: Square each deviation

Squaring removes negative signs and gives greater weight to larger deviations.

| Observation | Deviation | Squared deviation |
|---:|---:|---:|
| 2 | -4 | 16 |
| 4 | -2 | 4 |
| 6 | 0 | 0 |
| 8 | 2 | 4 |
| 10 | 4 | 16 |

### Step 4: Add the squared deviations

$$
\sum_{i=1}^{5}(x_i-\mu)^2 = 16+4+0+4+16
$$

$$
\sum_{i=1}^{5}(x_i-\mu)^2 = 40
$$

### Step 5: Divide by the population size

$$
\sigma^2 = \frac{40}{5}
$$

$$
\boxed{\sigma^2 = 8}
$$

Therefore, the population variance is 8 square units.

### What if these five observations are a sample?

If we instead treat the observations as a sample and calculate the usual unbiased sample variance:

$$
s^2 = \frac{40}{5-1}
$$

$$
s^2 = \frac{40}{4} = 10
$$

The population variance of these five values is 8, while their sample variance is 10. The different denominators reflect different statistical objectives.

---

## 4. What Is Standard Deviation?

### Definition

Standard deviation is the positive square root of variance.

It measures the spread of observations around the mean in the same units as the original data.

### Population standard deviation

$$
\sigma = \sqrt{\frac{1}{N}\sum_{i=1}^{N}(x_i-\mu)^2}
$$

### Sample standard deviation

$$
s = \sqrt{\frac{1}{n-1}\sum_{i=1}^{n}(x_i-\bar{x})^2}
$$

Where:

- \(\sigma\) = population standard deviation
- \(s\) = sample standard deviation

### Example

From the previous example, the population variance was 8.

Therefore:

$$
\sigma = \sqrt{8}
$$

$$
\sigma \approx 2.83
$$

The population standard deviation is approximately 2.83 units.

For the sample variance of 10:

$$
s = \sqrt{10}
$$

$$
s \approx 3.16
$$

The sample standard deviation is approximately 3.16 units.

**Key difference:** Variance is expressed in squared units, while standard deviation is expressed in the original units.

For example, if the data is measured in centimeters:

- Variance is measured in square centimeters.
- Standard deviation is measured in centimeters.

This makes standard deviation easier to interpret alongside the original data.

---

## 5. Why Do We Square the Deviations?

A natural question is why variance uses squared deviations instead of simply averaging the deviations.

Consider the dataset:

`2, 4, 6, 8, 10`

Its mean is 6.

The deviations from the mean are:

`-4, -2, 0, 2, 4`

Their sum is:

$$
-4-2+0+2+4 = 0
$$

The positive and negative deviations cancel each other out.

Therefore, simply averaging the deviations would always produce zero when calculated around the arithmetic mean.

Squaring the deviations solves this problem.

$$
(-4)^2+(-2)^2+0^2+2^2+4^2 = 40
$$

Squaring also penalizes large deviations more strongly than small deviations.

For example:

$$
2^2 = 4
$$

$$
10^2 = 100
$$

A deviation of 10 contributes 25 times as much as a deviation of 2 to the sum of squared deviations.

This property makes variance particularly useful in mathematical statistics and optimization, although it also makes variance sensitive to extreme observations.

---

## 6. Intuition: What Do Variance and Standard Deviation Tell Us?

Consider three datasets:

Dataset A: `48, 49, 50, 51, 52`

Dataset B: `40, 45, 50, 55, 60`

Dataset C: `10, 30, 50, 70, 90`

Each dataset has a mean of 50.

However, their observations have different distances from the mean.

- Dataset A has a small spread.
- Dataset B has a moderate spread.
- Dataset C has a large spread.

Their population variances and standard deviations are:

| Dataset | Mean | Population variance | Population standard deviation |
|---|---:|---:|---:|
| A | 50 | 2 | 1.41 |
| B | 50 | 50 | 7.07 |
| C | 50 | 800 | 28.28 |

These results show that the mean alone does not describe the variability of a dataset.

Variance and standard deviation add information about how dispersed the observations are around that mean.

**Important:** Standard deviation is not the average absolute distance from the mean. It is the square root of the average squared deviation for a population, or the corresponding sample estimate when using sample variance.

---

## 7. Properties of Variance and Standard Deviation

### Property 1: Variance is nonnegative

Variance cannot be negative because every squared deviation is nonnegative.

$$
\sigma^2 \geq 0
$$

Standard deviation is also nonnegative:

$$
\sigma \geq 0
$$

### Property 2: Zero variance means no variability

If all observations have the same value, every deviation from the mean is zero.

For example:

`5, 5, 5, 5, 5`

$$
\sigma^2 = 0
$$

$$
\sigma = 0
$$

### Property 3: Adding a constant does not change variance

If a constant \(c\) is added to every observation, the variance and standard deviation remain unchanged.

$$
\operatorname{Var}(X+c)=\operatorname{Var}(X)
$$

$$
\operatorname{SD}(X+c)=\operatorname{SD}(X)
$$

For example, converting every temperature measurement from one numerical scale to another by adding a constant offset does not change its spread.

### Property 4: Multiplying by a constant changes variance quadratically

If every observation is multiplied by a constant \(a\):

$$
\operatorname{Var}(aX)=a^2\operatorname{Var}(X)
$$

Standard deviation changes by the absolute value of the multiplier:

$$
\operatorname{SD}(aX)=|a|\operatorname{SD}(X)
$$

For example, if every observation is doubled, the variance becomes four times as large and the standard deviation becomes twice as large.

### Property 5: Variance depends on all observations

Unlike range, which uses only the minimum and maximum, variance incorporates every observation's deviation from the mean.

However, because deviations are squared, extreme observations can have a large influence.

---

## 8. Computational Formula for Variance

Variance can also be calculated using an alternative formula.

For a population:

$$
\sigma^2 = \frac{1}{N}\sum_{i=1}^{N}x_i^2-\mu^2
$$

Equivalently:

$$
\operatorname{Var}(X)=E[X^2]-(E[X])^2
$$

Here:

- \(E[X]\) is the expected value of \(X\).
- \(E[X^2]\) is the expected value of the squared variable.

For a finite population, the formula means:

$$
\text{Variance} =
\text{Mean of squared values} - (\text{Mean})^2
$$

### Example

Consider:

`2, 4, 6`

The mean is:

$$
\mu = \frac{2+4+6}{3} = 4
$$

The mean of squared values is:

$$
E[X^2] = \frac{2^2+4^2+6^2}{3}
$$

$$
E[X^2] = \frac{4+16+36}{3}
$$

$$
E[X^2] = \frac{56}{3}
$$

Using the computational formula:

$$
\sigma^2 = \frac{56}{3}-4^2
$$

$$
\sigma^2 = \frac{56}{3}-16
$$

$$
\sigma^2 = \frac{8}{3}
$$

Therefore:

$$
\sigma^2 \approx 2.67
$$

This matches the result obtained by averaging the squared deviations from the mean.

**Practical note:** The computational formula can be convenient, but subtracting two large, nearly equal quantities can cause numerical precision problems in some computational settings. Numerically stable algorithms are often preferred for large or high-precision datasets.

---

## 9. Variance of a Random Variable

In probability theory, variance measures the spread of a random variable around its expected value.

For a random variable \(X\):

$$
\operatorname{Var}(X)=E[(X-E[X])^2]
$$

An equivalent identity is:

$$
\operatorname{Var}(X)=E[X^2]-(E[X])^2
$$

The standard deviation is:

$$
\operatorname{SD}(X)=\sqrt{\operatorname{Var}(X)}
$$

### Example: Fair die

Suppose \(X\) is the outcome of a fair six-sided die.

The expected value is:

$$
E[X]=\frac{1+2+3+4+5+6}{6}=3.5
$$

The expected squared value is:

$$
E[X^2]=\frac{1^2+2^2+3^2+4^2+5^2+6^2}{6}
$$

$$
E[X^2]=\frac{91}{6}
$$

Therefore, the variance is:

$$
\operatorname{Var}(X)=\frac{91}{6}-(3.5)^2
$$

$$
\operatorname{Var}(X)=\frac{35}{12}
$$

The standard deviation is:

$$
\operatorname{SD}(X)=\sqrt{\frac{35}{12}}
$$

$$
\operatorname{SD}(X)\approx 1.71
$$

The expected value is 3.5, even though a single die roll cannot produce 3.5. The variance quantifies the variability of possible outcomes around that expected value.

---

## 10. Variance and Standard Deviation in the Normal Distribution

Variance and standard deviation are especially important for the normal distribution.

A normal distribution is commonly described by two parameters:

- Mean \(\mu\), which determines the center.
- Standard deviation \(\sigma\), which determines the spread.

Its probability density function is:

$$
f(x)=\frac{1}{\sigma\sqrt{2\pi}}
e^{-\frac{(x-\mu)^2}{2\sigma^2}}
$$

A larger standard deviation produces a wider, more spread-out normal distribution. A smaller standard deviation produces a narrower distribution.

For a normal distribution:

- Approximately 68% of observations lie within one standard deviation of the mean.
- Approximately 95% lie within two standard deviations.
- Approximately 99.7% lie within three standard deviations.

These are approximate probabilities for an ideal normal distribution, not universal rules for all datasets.

Standard deviation is therefore useful for understanding the spread of normally distributed measurements and calculating standardized scores.

---

## 11. Variance and Standard Deviation in Machine Learning

Variance and standard deviation appear throughout machine learning, including preprocessing, probability models, feature analysis, and model evaluation.

### A. Feature scaling and standardization

Standardization transforms a numerical feature by subtracting its mean and dividing by its standard deviation.

$$
z=\frac{x-\mu}{\sigma}
$$

For a sample, preprocessing usually estimates these quantities from the training data.

### Example

Suppose a feature has mean 50 and standard deviation 10.

For an observation of 70:

$$
z=\frac{70-50}{10}
$$

$$
z=2
$$

The observation is two standard deviations above the mean.

Standardization is useful for many models, including linear models with regularization, support vector machines, and distance-based methods such as k-nearest neighbors.

It is not always necessary for every model. Tree-based methods, for example, are generally much less sensitive to feature scaling.

**Avoid data leakage:** Estimate the mean and standard deviation on the training data, then reuse those values to transform validation and test data.

### B. Detecting unusual observations

A z-score expresses the distance from the mean in standard-deviation units.

$$
z=\frac{x-\mu}{\sigma}
$$

A large absolute z-score can indicate an unusual observation, particularly when the feature is approximately normally distributed.

However, a large z-score does not automatically prove that a value is erroneous or should be removed. The feature distribution, context, and potential consequences must be considered.

### C. Gaussian Naive Bayes

Gaussian Naive Bayes assumes that each numerical feature follows a Gaussian distribution within each class.

For a feature \(X\) and class \(C\), the class-conditional density is modeled using a class-specific mean and variance:

$$
X\mid C=c \sim \mathcal{N}(\mu_c,\sigma_c^2)
$$

The model uses these estimated parameters to calculate the likelihood of observed features for each class.

### D. Bias-variance trade-off

The bias-variance trade-off is a fundamental concept in supervised learning.

- **High bias:** A model may be too simple to capture the underlying relationship.
- **High variance:** A model may be overly sensitive to the training data and perform inconsistently on new samples.

This use of the word *variance* refers to variability in a model's predictions across different training datasets. It is related to, but not identical to, the variance of a single numerical feature.

A high-variance model may overfit the training data.

### E. Variance in model evaluation

Model performance can vary across different training samples, validation splits, or cross-validation folds.

Reporting both average performance and its variability can help assess how stable a model is.

For example, a model with slightly better average accuracy but much greater variation across folds may be less reliable than a more consistent model, depending on the application.

---

## 12. Limitations of Variance and Standard Deviation

### 1. Sensitivity to outliers

Because deviations are squared, extreme observations can contribute disproportionately to variance.

Standard deviation inherits this sensitivity.

### 2. Variance uses squared units

If data is measured in meters, variance is measured in square meters. This can make variance less intuitive to interpret directly.

Standard deviation is expressed in meters, making it easier to compare with the original measurements.

### 3. Standard deviation does not describe the entire distribution

Two datasets can have the same standard deviation but different shapes, skewness, or tail behavior.

Therefore, standard deviation should not be treated as a complete description of a distribution.

### 4. Interpretation depends on the distribution

The rule that approximately 68% of observations lie within one standard deviation of the mean applies to a normal distribution. It does not generally hold for arbitrary distributions.

### 5. Sample and population formulas are different

Using \(n\) instead of \(n-1\) for the usual unbiased sample variance changes the result.

Always determine whether you are describing a complete population or estimating population variance from a sample.

---

## 13. Common Interview Questions and Answers

### Q1. What is variance?

**Answer:** Variance measures the average squared deviation of observations from their mean. It quantifies the spread of the data.

### Q2. What is standard deviation?

**Answer:** Standard deviation is the square root of variance. It measures dispersion in the original units of the data.

### Q3. What is the difference between variance and standard deviation?

**Answer:** Variance uses squared deviations and is expressed in squared units. Standard deviation is its square root and is expressed in the original units.

### Q4. Why do we square deviations when calculating variance?

**Answer:** Squaring prevents positive and negative deviations from cancelling out and gives greater weight to large deviations.

### Q5. Why does sample variance use \(n-1\)?

**Answer:** The sample mean is estimated from the same observations, which makes the sum of squared deviations tend to be too small when divided by \(n\) for estimating population variance. Dividing by \(n-1\) corrects this bias under standard random-sampling assumptions.

### Q6. Can variance be negative?

**Answer:** No. Variance is calculated from squared deviations, so it cannot be negative.

### Q7. What does zero standard deviation mean?

**Answer:** It means all observations have the same value, so there is no observed variability.

### Q8. How does standard deviation help in feature scaling?

**Answer:** Standardization subtracts the feature mean and divides by its standard deviation, producing a feature measured in standard-deviation units.

### Q9. How is variance used in Gaussian Naive Bayes?

**Answer:** Gaussian Naive Bayes estimates a mean and variance for each numerical feature within each class and uses them to model class-conditional Gaussian likelihoods.

### Q10. What is the difference between statistical variance and model variance?

**Answer:** Statistical variance describes variability in a random variable or dataset. Model variance describes how much a model's predictions change when the training data changes.

### Q11. Is a high standard deviation always bad?

**Answer:** No. It indicates greater spread, but whether that is undesirable depends on the context. Variation in manufacturing measurements may be a problem, while variation in a dataset may represent meaningful differences.

### Q12. Is standard deviation the average distance from the mean?

**Answer:** Not exactly. Standard deviation is the square root of the average squared deviation for a population, or the corresponding sample estimate. Mean absolute deviation instead averages the absolute distances from a chosen center.

---

## 14. Practice Problems

Try solving the following questions before looking at the answers.

### Problem 1

Calculate the population variance and population standard deviation of:

`2, 4, 6, 8, 10`

### Problem 2

Calculate the population variance of:

`5, 5, 5, 5, 5`

### Problem 3

A dataset has a population variance of 25. What is its population standard deviation?

### Problem 4

A sample contains four observations:

`2, 4, 6, 8`

Calculate the sample variance using \(n-1\).

### Problem 5

Why is variance more sensitive to outliers than some other measures of dispersion?

### Problem 6

A feature has a mean of 100 and a standard deviation of 15. Calculate the z-score of an observation equal to 130.

### Problem 7

If every observation is multiplied by 3, how do the variance and standard deviation change?

### Problem 8

A fair six-sided die has an expected value of 3.5 and a variance of \(35/12\). Calculate its standard deviation to two decimal places.

---

## 15. Practice Problem Answers

### Answer 1

Dataset:

`2, 4, 6, 8, 10`

Mean:

$$
\mu = \frac{2+4+6+8+10}{5}=6
$$

Squared deviations:

$$
(2-6)^2=16
$$

$$
(4-6)^2=4
$$

$$
(6-6)^2=0
$$

$$
(8-6)^2=4
$$

$$
(10-6)^2=16
$$

Population variance:

$$
\sigma^2 = \frac{16+4+0+4+16}{5}
$$

$$
\sigma^2 = \frac{40}{5}=8
$$

Population standard deviation:

$$
\sigma = \sqrt{8}\approx 2.83
$$

### Answer 2

Every observation equals 5, so every deviation from the mean is zero.

$$
\sigma^2=0
$$

Population standard deviation:

$$
\sigma=0
$$

### Answer 3

Standard deviation is the square root of variance.

$$
\sigma=\sqrt{25}=5
$$

### Answer 4

Sample mean:

$$
\bar{x}=\frac{2+4+6+8}{4}=5
$$

Squared deviations:

$$
(2-5)^2+(4-5)^2+(6-5)^2+(8-5)^2
$$

$$
=9+1+1+9=20
$$

Sample variance:

$$
s^2=\frac{20}{4-1}
$$

$$
s^2=\frac{20}{3}\approx 6.67
$$

### Answer 5

Variance squares the deviations from the mean. This makes large deviations contribute disproportionately to the total, so extreme observations can substantially increase variance.

### Answer 6

The z-score is:

$$
z=\frac{x-\mu}{\sigma}
$$

$$
z=\frac{130-100}{15}
$$

$$
z=2
$$

The observation is two standard deviations above the mean.

### Answer 7

If every observation is multiplied by 3, the variance is multiplied by \(3^2=9\), while the standard deviation is multiplied by 3.

$$
\operatorname{Var}(3X)=9\operatorname{Var}(X)
$$

$$
\operatorname{SD}(3X)=3\operatorname{SD}(X)
$$

### Answer 8

$$
\sigma=\sqrt{\frac{35}{12}}
$$

$$
\sigma\approx 1.71
$$

The standard deviation is approximately 1.71.

---

## 16. Key Takeaways

- Variance measures the average squared deviation from the mean.
- Standard deviation is the square root of variance.
- Population variance divides by \(N\); the usual unbiased sample variance divides by \(n-1\).
- Variance is measured in squared units, while standard deviation uses the original units.
- Squaring deviations prevents cancellation and gives more weight to extreme observations.
- Both measures are sensitive to outliers.
- The identity \(\operatorname{Var}(X)=E[X^2]-(E[X])^2\) is useful in probability and statistics.
- Standard deviation is central to z-scores, normal distributions, and many machine learning preprocessing methods.
- Statistical variance and model variance are related concepts but describe different kinds of variability.
- **Interview rule:** Variance quantifies squared spread; standard deviation expresses that spread in the original units.
