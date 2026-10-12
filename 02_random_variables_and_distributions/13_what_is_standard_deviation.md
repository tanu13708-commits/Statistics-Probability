# Q13. What Is Standard Deviation?

## 1. Introduction

**Standard deviation** is a statistical measure that describes how much the values of a dataset or random variable tend to vary around their mean.

- A **small standard deviation** indicates that values tend to be close to the mean.
- A **large standard deviation** indicates that values tend to be more spread out.
- A **standard deviation of zero** means all values are identical, or equivalently, a random variable is constant with probability one.

Standard deviation is widely used in statistics, data analysis, probability, and machine learning.

## 2. Definition of Standard Deviation

Standard deviation is the square root of variance.

For a random variable \(X\), it is defined as:

$$
\sigma_X = \sqrt{\mathrm{Var}(X)}
$$

Using the definition of variance:

$$
\sigma_X = \sqrt{E[(X-E[X])^2]}
$$

Here:

- \(\sigma_X\) is the standard deviation of \(X\).
- \(E[X]\) is the expected value of \(X\).
- \(\mathrm{Var}(X)\) is the variance of \(X\).

Standard deviation measures spread in the same units as the original variable, whereas variance is expressed in squared units.

## 3. Population Standard Deviation

When the entire population is available, the population standard deviation is calculated using the population mean.

Suppose the population contains \(N\) values:

$$
x_1,x_2,\ldots,x_N
$$

The population mean is:

$$
\mu = \frac{1}{N}\sum_{i=1}^{N}x_i
$$

The population variance is:

$$
\sigma^2 = \frac{1}{N}\sum_{i=1}^{N}(x_i-\mu)^2
$$

Therefore, the population standard deviation is:

$$
\sigma = \sqrt{\frac{1}{N}\sum_{i=1}^{N}(x_i-\mu)^2}
$$

### Example: Population Standard Deviation

Consider the population:

$$
2,\ 4,\ 6
$$

**Step 1: Calculate the mean.**

$$
\mu = \frac{2+4+6}{3}
$$

$$
\mu = 4
$$

**Step 2: Calculate deviations from the mean.**

| Value \(x_i\) | Deviation \(x_i-\mu\) | Squared deviation |
|---:|---:|---:|
| 2 | -2 | 4 |
| 4 | 0 | 0 |
| 6 | 2 | 4 |

**Step 3: Calculate the population variance.**

$$
\sigma^2 = \frac{4+0+4}{3}
$$

$$
\sigma^2 = \frac{8}{3}
$$

**Step 4: Calculate the population standard deviation.**

$$
\sigma = \sqrt{\frac{8}{3}}
$$

$$
\sigma \approx 1.633
$$

Therefore, the population standard deviation is approximately 1.633.

## 4. Sample Standard Deviation

In practice, we often observe a sample rather than the entire population.

For a sample of \(n\) observations, the sample mean is:

$$
\bar{x} = \frac{1}{n}\sum_{i=1}^{n}x_i
$$

The usual sample variance estimator is:

$$
s^2 = \frac{1}{n-1}\sum_{i=1}^{n}(x_i-\bar{x})^2
$$

The sample standard deviation is:

$$
s = \sqrt{\frac{1}{n-1}\sum_{i=1}^{n}(x_i-\bar{x})^2}
$$

The denominator is \(n-1\) because the usual sample variance formula is an unbiased estimator of the population variance under standard random-sampling assumptions. The square root of this estimator, however, is not generally an unbiased estimator of the population standard deviation.

### Example: Sample Standard Deviation

Suppose a sample contains:

$$
2,\ 4,\ 6
$$

**Step 1: Calculate the sample mean.**

$$
\bar{x} = \frac{2+4+6}{3}
$$

$$
\bar{x} = 4
$$

**Step 2: Calculate the squared deviations.**

$$
(2-4)^2 = 4
$$

$$
(4-4)^2 = 0
$$

$$
(6-4)^2 = 4
$$

**Step 3: Calculate the sample variance.**

There are three observations, so \(n-1=2\).

$$
s^2 = \frac{4+0+4}{2}
$$

$$
s^2 = 4
$$

**Step 4: Calculate the sample standard deviation.**

$$
s = \sqrt{4}
$$

$$
s = 2
$$

The sample standard deviation is 2.

Notice that the same three observed values produce different results depending on whether they are treated as the entire population or as a sample used to estimate population variability.

## 5. Population vs. Sample Standard Deviation

| Feature | Population standard deviation | Sample standard deviation |
|---|---|---|
| Purpose | Describes the complete population | Estimates population spread from a sample |
| Mean used | Population mean \(\mu\) | Sample mean \(\bar{x}\) |
| Denominator inside variance | \(N\) | \(n-1\) |
| Common notation | \(\sigma\) | \(s\) |

Use the population formula when the complete population is available and the goal is to describe that population. Use the usual sample formula when estimating population variability from a sample.

## 6. Why Do We Take the Square Root of Variance?

Variance measures the average squared deviation from the mean.

For example, if a variable is measured in meters:

- Its deviations are measured in meters.
- Its squared deviations are measured in square meters.
- Its variance is measured in square meters.

The square root converts the measurement back to meters.

$$
\text{Standard deviation} = \sqrt{\text{Variance}}
$$

This makes standard deviation easier to interpret in the context of the original data.

## 7. Standard Deviation vs. Variance

Both measures describe spread, but they differ in their units and interpretation.

| Feature | Variance | Standard deviation |
|---|---|---|
| Definition | Average squared deviation from the mean | Square root of variance |
| Units | Squared units | Original units |
| Sensitivity to large deviations | Large deviations are strongly weighted | Also sensitive to large deviations |
| Interpretation | Mathematical measure of squared spread | Spread expressed on the original scale |

For a random variable \(X\):

$$
\mathrm{Var}(X) = E[(X-E[X])^2]
$$

The standard deviation is:

$$
\sigma_X = \sqrt{\mathrm{Var}(X)}
$$

## 8. Important Properties of Standard Deviation

### Property 1: Standard Deviation Is Nonnegative

$$
\sigma_X \geq 0
$$

Standard deviation cannot be negative because variance is nonnegative.

### Property 2: Standard Deviation of a Constant

If \(c\) is a constant:

$$
\mathrm{SD}(c) = 0
$$

All values of a constant variable are identical, so there is no spread.

### Property 3: Adding a Constant

Adding a constant shifts all values but does not change their spread.

$$
\mathrm{SD}(X+c) = \mathrm{SD}(X)
$$

For example, adding 10 to every observation increases the mean by 10 but leaves the standard deviation unchanged.

### Property 4: Multiplying by a Constant

Multiplying a random variable by a constant changes the standard deviation by the absolute value of that constant.

$$
\mathrm{SD}(aX) = |a|\mathrm{SD}(X)
$$

For example, multiplying every value by 3 multiplies the standard deviation by 3.

Multiplying every value by -2 multiplies the standard deviation by 2, because spread cannot be negative.

### Property 5: Linear Transformation

For constants \(a\) and \(b\):

$$
\mathrm{SD}(aX+b) = |a|\mathrm{SD}(X)
$$

The constant \(b\) shifts the data, while \(a\) changes its scale.

### Property 6: Standard Deviation of a Sum

For random variables \(X\) and \(Y\) with finite variances:

$$
\mathrm{Var}(X+Y) = \mathrm{Var}(X) + \mathrm{Var}(Y) + 2\mathrm{Cov}(X,Y)
$$

Therefore:

$$
\mathrm{SD}(X+Y) = \sqrt{\mathrm{Var}(X+Y)}
$$

If \(X\) and \(Y\) are independent, their covariance is zero, and:

$$
\mathrm{SD}(X+Y) = \sqrt{\mathrm{Var}(X)+\mathrm{Var}(Y)}
$$

Standard deviations generally do not simply add, even when the variables are independent.

## 9. Intuitive Example: Comparing Two Datasets

Consider the following datasets.

**Dataset A:**

$$
48,\ 49,\ 50,\ 51,\ 52
$$

**Dataset B:**

$$
10,\ 30,\ 50,\ 70,\ 90
$$

Both datasets have the same mean:

$$
\bar{x} = 50
$$

However, Dataset B is much more spread out around the mean.

Therefore, Dataset B has a larger standard deviation than Dataset A.

This example illustrates an important principle:

**Two datasets can have the same mean but different standard deviations.**

The mean tells us where the center is, while standard deviation tells us how widely the values are spread around it.

## 10. Standard Deviation and the Normal Distribution

Standard deviation plays an important role in the normal distribution.

For a normally distributed random variable:

$$
X \sim N(\mu,\sigma^2)
$$

Here:

- \(\mu\) is the mean.
- \(\sigma^2\) is the variance.
- \(\sigma\) is the standard deviation.

For a normal distribution, approximately:

- 68% of values lie within one standard deviation of the mean.
- 95% lie within two standard deviations of the mean.
- 99.7% lie within three standard deviations of the mean.

These are approximate empirical-rule percentages for a normal distribution. They should not be assumed for every distribution.

The corresponding intervals are:

$$
[\mu-\sigma,\ \mu+\sigma]
$$

$$
[\mu-2\sigma,\ \mu+2\sigma]
$$

$$
[\mu-3\sigma,\ \mu+3\sigma]
$$

### Example

Suppose examination scores are approximately normally distributed with:

$$
\mu = 70
$$

$$
\sigma = 10
$$

Approximately 68% of scores lie between:

$$
70-10 = 60
$$

and:

$$
70+10 = 80
$$

Therefore, approximately 68% of scores lie between 60 and 80.

Approximately 95% lie between 50 and 90, and approximately 99.7% lie between 40 and 100, under the normal-distribution assumption.

## 11. Z-Scores and Standard Deviation

A **z-score** measures how many standard deviations an observation lies above or below the mean.

For a population with mean \(\mu\) and standard deviation \(\sigma\):

$$
z = \frac{x-\mu}{\sigma}
$$

For a sample-based standardization, the sample mean and sample standard deviation may be used:

$$
z = \frac{x-\bar{x}}{s}
$$

The interpretation is:

- \(z=0\): The observation equals the mean.
- \(z=1\): The observation is one standard deviation above the mean.
- \(z=-1\): The observation is one standard deviation below the mean.
- \(z=2\): The observation is two standard deviations above the mean.

### Example

Suppose a student's score is 85, the class mean is 75, and the population standard deviation is 5.

$$
z = \frac{85-75}{5}
$$

$$
z = 2
$$

The student's score is two standard deviations above the mean.

Z-scores are useful for comparing observations measured on different scales, although their interpretation depends on the underlying distribution and the standardization method.

## 12. Applications in Machine Learning

### 12.1 Feature Standardization

Standard deviation is used to scale features in many machine-learning workflows.

A common standardization formula is:

$$
z = \frac{x-\mu}{\sigma}
$$

This centers a feature around zero and expresses values in standard-deviation units, assuming the standard deviation is nonzero.

Standardization can be helpful for algorithms sensitive to feature scales, such as:

- Logistic regression with regularization.
- Linear regression with regularization.
- Support vector machines.
- K-nearest neighbors.
- Gradient-based optimization methods.

Standardization is not required for every algorithm. Tree-based models, for example, are generally less sensitive to monotonic changes in feature scale.

When preparing train and test datasets, calculate the scaling parameters using the training data only, then apply those same parameters to the validation and test data. This helps prevent data leakage.

### 12.2 Detecting Unusual Observations

Standard deviation can help identify observations that are far from the mean.

A standardized score is:

$$
z = \frac{x-\mu}{\sigma}
$$

An observation with a large absolute z-score may deserve investigation.

For example, a value with an absolute z-score greater than 3 is sometimes flagged for review under a normal-distribution assumption.

However, a large z-score does not automatically prove that an observation is an error or an outlier. The data distribution, sample size, and business context should also be considered.

### 12.3 Bias-Variance Trade-Off

In machine learning, model variance describes how much a model's predictions may change when the training data changes.

A high-variance model can fit training data closely but may generalize poorly to unseen examples.

Standard deviation is a measure of spread, while model variance is a concept describing sensitivity to changes in training data. These ideas are related but should not be confused.

### 12.4 Measuring Prediction Uncertainty

Some probabilistic models estimate a distribution of possible outcomes rather than producing only one prediction.

For a predictive distribution, standard deviation can summarize the spread of predicted outcomes when that quantity is defined.

A larger predictive standard deviation indicates a wider predicted distribution, but it does not by itself guarantee that the model is well calibrated.

### 12.5 Monitoring Data Drift

Standard deviation can be monitored over time to detect changes in a feature's spread.

For example, a sudden increase in the standard deviation of transaction amounts may indicate a change in customer behavior or data collection.

It is best to examine changes in the mean, standard deviation, distribution shape, and data quality together rather than relying on standard deviation alone.

## 13. Common Mistakes

### Mistake 1: Confusing Variance with Standard Deviation

Standard deviation is the square root of variance.

$$
\sigma = \sqrt{\sigma^2}
$$

Variance is expressed in squared units, while standard deviation is expressed in the original units.

### Mistake 2: Using the Wrong Denominator

Population variance divides by \(N\), while the usual sample variance estimator divides by \(n-1\).

Choose the formula based on whether you are describing the complete population or estimating population variance from a sample.

### Mistake 3: Assuming a Large Standard Deviation Is Always Bad

A large standard deviation indicates more spread, not necessarily poor data quality.

For example, incomes in a large population may naturally have a high standard deviation.

### Mistake 4: Assuming Standard Deviation Is Unaffected by Scaling

Multiplying all observations by a constant changes standard deviation by the absolute value of that constant.

$$
\mathrm{SD}(aX) = |a|\mathrm{SD}(X)
$$

### Mistake 5: Assuming the 68-95-99.7 Rule Applies to Every Dataset

The empirical rule is based on the normal distribution. It does not generally apply to highly skewed, multimodal, or otherwise non-normal distributions.

### Mistake 6: Treating Every Extreme Value as an Error

An observation far from the mean may be a valid and important data point. Investigate its context before removing it.

### Mistake 7: Calculating Feature Scaling Before the Train-Test Split

Calculating standardization parameters using the entire dataset can leak information from the test set into the training process.

Fit the scaler on the training data and use the same fitted scaler to transform other splits.

## 14. Common Interview Questions and Answers

### Q1. What is standard deviation?

**Answer:** Standard deviation is the square root of variance and measures how spread out values are around the mean.

$$
\sigma = \sqrt{\mathrm{Var}(X)}
$$

### Q2. Why is standard deviation useful?

**Answer:** It measures spread in the original units of the data, making it easier to interpret than variance in many practical situations.

### Q3. What is the difference between population and sample standard deviation?

**Answer:** Population standard deviation describes the complete population and uses \(N\) in the variance calculation. The usual sample standard deviation uses \(n-1\) in the sample variance estimator.

### Q4. Can standard deviation be negative?

**Answer:** No. Standard deviation is the square root of a nonnegative variance, so it is nonnegative.

### Q5. What does a standard deviation of zero mean?

**Answer:** It means all observations in the dataset are identical, or that the random variable is constant with probability one.

### Q6. What happens to standard deviation when a constant is added?

**Answer:** It remains unchanged.

$$
\mathrm{SD}(X+c) = \mathrm{SD}(X)
$$

### Q7. What happens to standard deviation when a variable is multiplied by a constant?

**Answer:** It is multiplied by the absolute value of that constant.

$$
\mathrm{SD}(aX) = |a|\mathrm{SD}(X)
$$

### Q8. What is the relationship between standard deviation and the normal distribution?

**Answer:** For a normal distribution, approximately 68%, 95%, and 99.7% of observations lie within one, two, and three standard deviations of the mean, respectively.

### Q9. What is a z-score?

**Answer:** A z-score expresses how many standard deviations an observation lies above or below the mean.

$$
z = \frac{x-\mu}{\sigma}
$$

### Q10. How is standard deviation used in machine learning?

**Answer:** It is used in feature standardization, anomaly investigation, predictive uncertainty estimation, and monitoring changes in data distributions.

### Q11. Do standard deviations add when independent random variables are summed?

**Answer:** Not directly. For independent variables with finite variances, their variances add. The standard deviation of the sum is the square root of the sum of their variances.

$$
\mathrm{SD}(X+Y) = \sqrt{\mathrm{Var}(X)+\mathrm{Var}(Y)}
$$

### Q12. Does a large standard deviation imply that data is normally distributed?

**Answer:** No. Standard deviation measures spread but does not determine the shape of a distribution.

## 15. Practice Problems

### Problem 1: Calculate Population Standard Deviation

Calculate the population standard deviation of:

$$
4,\ 4,\ 4,\ 4
$$

**Solution:**

The mean is:

$$
\mu = \frac{4+4+4+4}{4} = 4
$$

Every deviation from the mean is zero. Therefore:

$$
\sigma^2 = 0
$$

$$
\sigma = 0
$$

### Problem 2: Calculate Population Standard Deviation

Calculate the population standard deviation of:

$$
2,\ 4,\ 6
$$

**Solution:**

The population mean is:

$$
\mu = \frac{2+4+6}{3} = 4
$$

The population variance is:

$$
\sigma^2 = \frac{(2-4)^2+(4-4)^2+(6-4)^2}{3}
$$

$$
\sigma^2 = \frac{4+0+4}{3}
$$

$$
\sigma^2 = \frac{8}{3}
$$

The population standard deviation is:

$$
\sigma = \sqrt{\frac{8}{3}}
$$

$$
\sigma \approx 1.633
$$

### Problem 3: Calculate Sample Standard Deviation

Calculate the sample standard deviation of:

$$
2,\ 4,\ 6
$$

**Solution:**

The sample mean is:

$$
\bar{x} = 4
$$

The sample variance is:

$$
s^2 = \frac{(2-4)^2+(4-4)^2+(6-4)^2}{3-1}
$$

$$
s^2 = \frac{8}{2}
$$

$$
s^2 = 4
$$

Therefore:

$$
s = \sqrt{4}
$$

$$
s = 2
$$

### Problem 4: Calculate a Z-Score

A student scores 90 on an exam. The mean is 75 and the standard deviation is 5.

Calculate the z-score.

**Solution:**

$$
z = \frac{90-75}{5}
$$

$$
z = 3
$$

The score is three standard deviations above the mean.

### Problem 5: Effect of Scaling

Suppose a random variable has a standard deviation of 4. Define:

$$
Y = -3X + 5
$$

Calculate the standard deviation of \(Y\).

**Solution:**

$$
\mathrm{SD}(Y) = |-3|\mathrm{SD}(X)
$$

$$
\mathrm{SD}(Y) = 3(4)
$$

$$
\mathrm{SD}(Y) = 12
$$

Adding 5 does not affect standard deviation, and multiplying by -3 scales it by 3.

## 16. Final Summary

- Standard deviation measures the spread of values around their mean.
- It is the square root of variance.
- Population standard deviation uses the complete population and divides the sum of squared deviations by \(N\).
- The usual sample standard deviation uses the sample variance denominator \(n-1\).
- Standard deviation uses the same units as the original data.
- Adding a constant does not change standard deviation.
- Multiplying a variable by a constant changes standard deviation by the absolute value of that constant.
- The empirical rule applies approximately to normally distributed data, not every distribution.
- In machine learning, standard deviation is useful for feature scaling, data monitoring, and understanding uncertainty.

