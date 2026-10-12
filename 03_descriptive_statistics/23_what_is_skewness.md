# 23. What Is Skewness?

## 1. Introduction

**Skewness** is a statistical measure that describes the asymmetry of a probability distribution or dataset around its center.

It helps us understand whether the distribution is balanced or whether one tail extends farther than the other.

There are three main types of skewness:

1. **Zero skewness:** The distribution has zero skewness, often associated with a symmetric distribution.
2. **Positive skewness:** The distribution has a longer or heavier right tail.
3. **Negative skewness:** The distribution has a longer or heavier left tail.

Skewness is useful in descriptive statistics, exploratory data analysis, outlier investigation, financial analysis, and machine learning.

For example:

- Household income data often exhibit positive skewness because a small number of households have very high incomes.
- Some examination score distributions may exhibit negative skewness when most students score highly and only a few score poorly.
- An ideal normal distribution has zero skewness.

**Important:** Skewness describes asymmetry. It does not directly measure the overall spread of the data. Variance, standard deviation, and the interquartile range are measures of spread.

---

## 2. What Does a Distribution Look Like?

A distribution describes how observations or probabilities are spread across possible values.

The shape of a distribution can provide information about its center, spread, tails, and possible extreme observations.

Skewness focuses specifically on asymmetry.

### 2.1 Symmetric distribution

A symmetric distribution has approximately the same shape on both sides of its center.

<AsyncImage query="symmetric bell shaped probability distribution statistical graph labeled mean median mode" aspectRatio="5:3" width="100%" />

In a symmetric, unimodal distribution such as the normal distribution, the mean, median, and mode coincide.

$$
\mathrm{Mean}=\mathrm{Median}=\mathrm{Mode}
$$

This relationship is not guaranteed for every symmetric distribution, especially when the mode is not unique or the distribution is discrete.

### 2.2 Positively skewed distribution

A positively skewed distribution has a longer or heavier tail toward larger values.

<AsyncImage query="right positively skewed probability distribution histogram long tail to the right statistical graph" aspectRatio="5:3" width="100%" />

Examples may include:

- Household income
- Property prices in a mixed market
- Waiting times with occasional long delays
- Customer spending when a few customers spend much more than most

In many common positively skewed distributions, the mean is greater than the median.

$$
\mathrm{Mean}>\mathrm{Median}
$$

This is a useful pattern, not a universal rule for every distribution with positive skewness.

### 2.3 Negatively skewed distribution

A negatively skewed distribution has a longer or heavier tail toward smaller values.

<AsyncImage query="left negatively skewed probability distribution histogram long tail to the left statistical graph" aspectRatio="5:3" width="100%" />

Examples may include:

- An examination in which most students score highly but a few score poorly
- A satisfaction rating distribution concentrated near the highest rating
- A task with scores near the maximum and a few unusually low results

In many common negatively skewed distributions, the mean is less than the median.

$$
\mathrm{Mean}<\mathrm{Median}
$$

Again, this is a common pattern rather than a universal mathematical rule.

---

## 3. Types of Skewness

### 3.1 Zero skewness

A distribution has zero skewness when its third central moment is zero, provided the moment exists.

For a distribution with a finite, positive standard deviation:

$$
\gamma_1=0
$$

A symmetric distribution with a finite third moment has zero skewness.

However, zero skewness does not necessarily mean that a distribution is symmetric. Some asymmetric distributions can also have zero third standardized central moment.

### 3.2 Positive skewness

Positive skewness means that the third standardized central moment is positive.

$$
\gamma_1>0
$$

The distribution often has a longer or heavier right tail.

A few large observations can pull the mean upward, which is why the mean is often greater than the median in common right-skewed distributions.

### 3.3 Negative skewness

Negative skewness means that the third standardized central moment is negative.

$$
\gamma_1<0
$$

The distribution often has a longer or heavier left tail.

A few small observations can pull the mean downward, which is why the mean is often less than the median in common left-skewed distributions.

---

## 4. Formula for Skewness

There are multiple ways to measure skewness. The appropriate formula depends on whether we are describing a population, calculating a sample estimate, or using a simpler descriptive approximation.

### 4.1 Population skewness

For a random variable \(X\) with mean \(\mu\) and standard deviation \(\sigma\), the moment-based population skewness is:

$$
\gamma_1=\frac{E[(X-\mu)^3]}{\sigma^3}
$$

Where:

- \(\gamma_1\) = population skewness
- \(X\) = random variable
- \(\mu\) = population mean
- \(\sigma\) = population standard deviation
- \(E[\cdot]\) = expected value

The numerator measures the average cubed deviation from the mean.

The denominator standardizes the result so that skewness is dimensionless.

### 4.2 Population skewness for a finite dataset

If we treat a complete finite dataset as the population, a common empirical moment formula is:

$$
g_1=\frac{\frac{1}{N}\sum_{i=1}^{N}(x_i-\bar{x})^3}{\left(\frac{1}{N}\sum_{i=1}^{N}(x_i-\bar{x})^2\right)^{3/2}}
$$

Where:

- \(N\) = number of observations
- \(x_i\) = observation \(i\)
- \(\bar{x}\) = arithmetic mean

This formula uses the second and third central moments calculated with denominator \(N\).

### 4.3 Sample skewness

When observations come from a sample, the sample skewness estimator may use a bias correction.

One common adjusted Fisher-Pearson sample skewness is:

$$
G_1=\frac{n}{(n-1)(n-2)}\sum_{i=1}^{n}\left(\frac{x_i-\bar{x}}{s}\right)^3
$$

Where:

- \(n\) = sample size
- \(\bar{x}\) = sample mean
- \(s\) = sample standard deviation calculated using denominator \(n-1\)

This estimator is commonly used when estimating population skewness from sample data.

Different software packages can use different conventions, so exact numerical results may vary.

### 4.4 A simpler descriptive formula: Pearson's second coefficient

A commonly taught descriptive measure of skewness is Pearson's second coefficient:

$$
\mathrm{Skewness}_{P}=\frac{3(\mathrm{Mean}-\mathrm{Median})}{\mathrm{Standard\ Deviation}}
$$

This is a useful approximation for describing the direction of skewness.

It is not the same as the moment-based skewness formula. The two methods can produce different magnitudes and, in some cases, different signs.

Use the formula requested in the question or the convention specified by your software.

---

## 5. Why Are Deviations Cubed?

The moment-based skewness formula uses cubed deviations from the mean.

$$
(X-\mu)^3
$$

There are several reasons for using the third power.

### 5.1 Positive and negative deviations remain distinguishable

If deviations were squared, both positive and negative deviations would become nonnegative.

For example:

$$
(-2)^2=4
$$

$$
2^2=4
$$

Squaring therefore loses the sign of the deviation.

Cubing preserves it:

$$
(-2)^3=-8
$$

$$
2^3=8
$$

This allows the third central moment to reflect the direction of asymmetry.

### 5.2 Larger deviations receive more weight

Cubing makes large deviations contribute disproportionately.

For example:

$$
2^3=8
$$

$$
5^3=125
$$

A large positive deviation can contribute strongly to positive skewness, while a large negative deviation can contribute strongly to negative skewness.

This also makes moment-based skewness sensitive to extreme observations.

### 5.3 Standardization makes the measure unitless

The third central moment has units cubed. Dividing it by the standard deviation cubed removes those units.

$$
\gamma_1=\frac{\mu_3}{\sigma^3}
$$

Here, \(\mu_3\) is the third central moment.

As a result, skewness can be compared across variables measured in different units, although differences in distribution shape and estimation methods still matter.

---

## 6. Step-by-Step Example: Calculating Skewness

Consider the dataset:

$$
1,\ 2,\ 3,\ 4,\ 10
$$

We will calculate the empirical moment skewness using denominator \(n\) for the second and third central moments.

### Step 1: Calculate the mean

$$
\bar{x}=\frac{1+2+3+4+10}{5}
$$

$$
\bar{x}=\frac{20}{5}=4
$$

### Step 2: Calculate deviations from the mean

| Observation \(x_i\) | Deviation \(x_i-\bar{x}\) |
|---:|---:|
| 1 | -3 |
| 2 | -2 |
| 3 | -1 |
| 4 | 0 |
| 10 | 6 |

### Step 3: Calculate squared deviations

| Observation | Deviation | Squared deviation |
|---:|---:|---:|
| 1 | -3 | 9 |
| 2 | -2 | 4 |
| 3 | -1 | 1 |
| 4 | 0 | 0 |
| 10 | 6 | 36 |

The sum of squared deviations is:

$$
9+4+1+0+36=50
$$

The empirical second central moment is:

$$
m_2=\frac{50}{5}=10
$$

The corresponding population-style standard deviation is:

$$
\sigma_n=\sqrt{10}\approx3.1623
$$

### Step 4: Calculate cubed deviations

| Observation | Deviation | Cubed deviation |
|---:|---:|---:|
| 1 | -3 | -27 |
| 2 | -2 | -8 |
| 3 | -1 | -1 |
| 4 | 0 | 0 |
| 10 | 6 | 216 |

The sum of cubed deviations is:

$$
-27-8-1+0+216=180
$$

The empirical third central moment is:

$$
m_3=\frac{180}{5}=36
$$

### Step 5: Calculate skewness

Using the empirical moment formula:

$$
g_1=\frac{m_3}{m_2^{3/2}}
$$

Substitute the values:

$$
g_1=\frac{36}{10^{3/2}}
$$

Since:

$$
10^{3/2}=10\sqrt{10}\approx31.6228
$$

We obtain:

$$
g_1\approx\frac{36}{31.6228}
$$

$$
\boxed{g_1\approx1.138}
$$

### Interpretation

The empirical moment skewness is positive.

The observation \(10\) lies well above the other values and contributes a large positive cubed deviation.

This example illustrates how a relatively small number of large observations can influence skewness.

**Note:** A bias-corrected sample skewness formula would give a different numerical result for this dataset.

---

## 7. Mean, Median, and Mode in Skewed Distributions

The mean, median, and mode describe different aspects of a distribution.

- **Mean:** Arithmetic average of the observations.
- **Median:** Middle value of the ordered observations, or the average of the two middle values for an even-sized dataset.
- **Mode:** Most frequent value or a location of a peak in a distribution.

In many common unimodal distributions, their relative positions follow familiar patterns.

### 7.1 Symmetric, unimodal distribution

A common pattern is:

$$
\mathrm{Mean}=\mathrm{Median}=\mathrm{Mode}
$$

The normal distribution is a standard example.

### 7.2 Positively skewed, unimodal distribution

A common pattern is:

$$
\mathrm{Mode}<\mathrm{Median}<\mathrm{Mean}
$$

The right tail can pull the mean toward larger values.

### 7.3 Negatively skewed, unimodal distribution

A common pattern is:

$$
\mathrm{Mean}<\mathrm{Median}<\mathrm{Mode}
$$

The left tail can pull the mean toward smaller values.

**Important:** These are useful introductory patterns, not universal laws. The ordering may differ for multimodal distributions, unusual shapes, or particular discrete datasets.

The mean-median relationship alone is not a definitive measure of moment-based skewness.

---

## 8. Skewness vs. Symmetry

A distribution is symmetric if reflecting it around its center leaves its shape unchanged.

For a symmetric distribution with a finite third moment, moment-based skewness is zero.

However, the reverse is not always true.

A distribution can have zero third standardized central moment while still being asymmetric.

Therefore:

- Symmetry with a finite third moment implies zero moment skewness.
- Zero moment skewness does not prove symmetry.

This distinction is important in statistics interviews because skewness summarizes one aspect of distribution shape rather than fully describing the distribution.

---

## 9. Skewness vs. Kurtosis

Skewness and kurtosis are both measures related to distribution shape, but they focus on different characteristics.

| Feature | Skewness | Kurtosis |
|---|---|---|
| Main focus | Asymmetry | Tail behavior and concentration relative to a reference distribution |
| Common moment | Third central moment | Fourth central moment |
| Standardized formula | Third central moment divided by standard deviation cubed | Fourth central moment divided by standard deviation to the fourth power |
| Sign or interpretation | Positive, negative, or zero | Raw kurtosis is at least 1 for a nondegenerate distribution with a finite fourth moment; excess kurtosis can be positive, negative, or zero |
| Common use | Describing directional asymmetry | Describing tail weight and distribution shape |

### Moment-based kurtosis

For a random variable with a finite, positive standard deviation and finite fourth moment, raw kurtosis is:

$$
\beta_2=\frac{E[(X-\mu)^4]}{\sigma^4}
$$

Excess kurtosis subtracts 3:

$$
\mathrm{Excess\ Kurtosis}=\beta_2-3
$$

The normal distribution has raw kurtosis 3 and excess kurtosis 0.

Skewness and kurtosis provide different information. A distribution can have zero skewness and nonzero excess kurtosis.

---

## 10. Skewness vs. Variance and Standard Deviation

Variance and standard deviation measure spread, while skewness measures asymmetry.

| Feature | Variance | Standard deviation | Skewness |
|---|---|---|---|
| Purpose | Measures squared spread around the mean | Measures spread in original units | Measures asymmetry |
| Based on | Squared deviations | Square root of variance | Cubed deviations, standardized by spread |
| Units | Squared data units | Original data units | No units |
| Sensitive to extremes | Often highly sensitive | Often highly sensitive | Can be highly sensitive |
| Can be negative? | No | No | Yes, no, or positive |

Two datasets can have the same standard deviation but different skewness.

For example, one dataset may be roughly symmetric, while another contains a long right tail. Their spreads may be similar even though their shapes differ.

Likewise, two datasets can have the same skewness but different variances.

---

## 11. Is Skewness Affected by Outliers?

Yes. Moment-based skewness can be strongly affected by extreme observations because it uses cubed deviations.

A very large positive deviation contributes a large positive value to the third central moment.

A very large negative deviation contributes a large negative value.

This means that:

- A large high-end observation can increase positive skewness.
- A large low-end observation can increase negative skewness in magnitude.
- A few extreme observations can substantially change the skewness estimate.

However, an extreme observation does not guarantee a particular skewness value because skewness depends on all observations, the mean, and the standard deviation.

When data contain extreme values, consider examining:

- A histogram
- A box plot
- The median and IQR
- The range and standard deviation
- The underlying observations and their context

Do not automatically remove extreme values solely because they change skewness.

---

## 12. Skewness and Data Transformation

Skewed data sometimes benefit from transformations, depending on the purpose of the analysis and the model being used.

### 12.1 Log transformation

For strictly positive values, a logarithmic transformation can reduce right skewness in some datasets.

$$
Y=\log(X)
$$

For nonnegative values that include zero, a common alternative is:

$$
Y=\log(1+X)
$$

The effect depends on the data. A log transformation does not guarantee a symmetric distribution.

### 12.2 Square-root transformation

For nonnegative data, a square-root transformation may reduce positive skewness in some situations.

$$
Y=\sqrt{X}
$$

It is often considered for count data, although the best transformation depends on the statistical problem.

### 12.3 Box-Cox transformation

The Box-Cox family provides a parameterized power transformation for strictly positive observations.

For transformation parameter \(\lambda\):

$$
Y=
\begin{cases}
\frac{X^\lambda-1}{\lambda}, & \lambda\ne0 \\
\log(X), & \lambda=0
\end{cases}
$$

The parameter is selected according to a specified criterion, such as improving the fit to a model's assumptions.

Box-Cox requires strictly positive inputs in its standard form. Variants such as the Yeo-Johnson transformation can accommodate zero and negative values.

### 12.4 Important precautions

Before transforming a feature:

1. Inspect its distribution and understand why it is skewed.
2. Consider whether the transformation makes sense for the variable.
3. Remember that transformations change the interpretation of values.
4. Fit transformation parameters using training data only in a machine learning workflow.
5. Evaluate model performance and relevant assumptions after transformation.

Not every machine learning algorithm requires normally distributed features. Transformations should be chosen based on the modeling goal, not applied automatically whenever skewness is present.

---

## 13. Applications of Skewness in Machine Learning

Skewness can be useful in data analysis and machine learning, especially during data exploration and preprocessing.

### 13.1 Exploratory data analysis

Skewness helps identify whether a numerical feature is asymmetric.

This can guide further investigation of:

- Extreme values
- Long tails
- Concentration of observations
- Suitable descriptive statistics
- Potential transformations

### 13.2 Feature preprocessing

A strongly right-skewed feature may contain many small values and a small number of very large values.

A transformation may make its distribution more compact and can sometimes improve the behavior of models that are sensitive to scale or functional form.

However, tree-based models often handle monotonic transformations differently from linear or distance-based models. A transformation is not automatically beneficial for every model.

### 13.3 Linear regression

Skewness can matter when examining predictors and residuals, but ordinary least squares regression does not require every predictor to be normally distributed.

For classical inference under common regression assumptions, the distribution of the errors is more relevant to exact small-sample inference than the marginal distribution of the predictors.

Transforming a variable may be useful if it improves the relationship with the response, residual behavior, or interpretation.

### 13.4 Distance-based algorithms

Algorithms such as k-nearest neighbors and k-means can be affected by feature scales and the geometry of the data.

A skewed feature with extreme values may dominate distances.

A suitable transformation or scaling method can sometimes help, but the choice should be validated.

### 13.5 Outlier analysis

Skewness can alert an analyst to an asymmetric tail, but it does not identify individual outliers by itself.

Combine it with plots, quantiles, domain knowledge, and appropriate screening methods.

### 13.6 Monitoring operational data

Skewness can help describe changes in response times, transaction amounts, error magnitudes, and other operational metrics.

For example, a growing right tail in latency may indicate occasional slow requests even when the median remains stable.

Monitor tail percentiles as well as skewness because one summary statistic cannot fully describe tail behavior.

### 13.7 Data leakage prevention

If transformation parameters are selected or estimated during preprocessing, fit them on the training split only.

Apply the fitted transformation to validation and test data without estimating new parameters from those sets.

---

## 14. Limitations of Skewness

Skewness is useful, but it has several limitations.

### 14.1 Sensitivity to extreme values

Moment-based skewness uses cubed deviations, so extreme observations can strongly influence it.

### 14.2 It does not fully describe distribution shape

Two distributions can have the same skewness but different modes, tails, or concentrations.

### 14.3 It can be unstable for small samples

With few observations, one value can substantially affect the estimate. Sample skewness should be interpreted with caution when the sample size is small.

### 14.4 Estimators differ

Population moment skewness, empirical moment skewness, bias-corrected sample skewness, and Pearson's coefficient are not identical.

When reporting a value, identify the formula or software convention if precision matters.

### 14.5 Zero skewness does not prove symmetry

An asymmetric distribution can have zero third central moment.

### 14.6 It may not exist

The theoretical moment-based skewness requires a finite, positive standard deviation and a finite third absolute moment.

Some heavy-tailed distributions do not have a finite third moment, so their theoretical moment skewness is undefined.

### 14.7 It does not directly measure spread

A distribution can have strong skewness but small variance, or weak skewness but large variance. Skewness should be considered alongside measures of spread.

---

## 15. Common Mistakes

### Mistake 1: Confusing positive skewness with a concentration of high values

Positive skewness generally refers to a longer or heavier right tail. Many observations may still be concentrated at relatively low values.

### Mistake 2: Assuming the mean-median relationship always determines skewness

The mean being greater than the median is common in right-skewed distributions, but it is not a universal definition of positive moment skewness.

### Mistake 3: Assuming zero skewness proves symmetry

Zero third standardized central moment does not guarantee a symmetric distribution.

### Mistake 4: Confusing skewness with spread

Variance and standard deviation measure spread. Skewness measures asymmetry.

### Mistake 5: Ignoring the formula used

Different skewness estimators can return different results. State which method is being used when necessary.

### Mistake 6: Assuming a normal distribution has positive skewness

An ideal normal distribution is symmetric and has zero skewness.

### Mistake 7: Removing all extreme values

Extreme values may be valid observations. Investigate their source before deciding how to handle them.

### Mistake 8: Assuming every feature must be normally distributed for machine learning

Many algorithms do not require normally distributed input features. Preprocessing should depend on the algorithm and task.

### Mistake 9: Applying transformations without checking their assumptions

For example, the standard Box-Cox transformation requires strictly positive values.

### Mistake 10: Treating skewness as a complete description of the distribution

Skewness is only one summary. Use plots, quantiles, and other statistics for a fuller picture.

---

## 16. Frequently Asked Interview Questions

### Q1. What is skewness?

Skewness is a statistical measure that describes the asymmetry of a distribution around its center.

### Q2. What are the three types of skewness?

- Zero skewness: the third standardized central moment is zero.
- Positive skewness: the third standardized central moment is positive.
- Negative skewness: the third standardized central moment is negative.

### Q3. What is the formula for population skewness?

$$
\gamma_1=\frac{E[(X-\mu)^3]}{\sigma^3}
$$

### Q4. Why are deviations cubed in the skewness formula?

Cubing preserves the sign of deviations and gives larger deviations disproportionate influence, allowing the formula to reflect asymmetry.

### Q5. What is the common mean-median-mode pattern for positive skewness?

For many common unimodal right-skewed distributions:

$$
\mathrm{Mode}<\mathrm{Median}<\mathrm{Mean}
$$

This is a common pattern, not a universal rule.

### Q6. What is the common mean-median-mode pattern for negative skewness?

For many common unimodal left-skewed distributions:

$$
\mathrm{Mean}<\mathrm{Median}<\mathrm{Mode}
$$

Again, this is not a universal rule.

### Q7. Can skewness be negative?

Yes. Negative skewness indicates a negative third standardized central moment and often corresponds to a longer or heavier left tail.

### Q8. Can skewness be zero for an asymmetric distribution?

Yes. Zero moment-based skewness does not necessarily imply symmetry.

### Q9. Is skewness affected by outliers?

Yes. Moment-based skewness can be strongly affected by extreme observations because it uses cubed deviations from the mean.

### Q10. What is the difference between skewness and kurtosis?

Skewness measures asymmetry. Kurtosis is based on the fourth standardized central moment and provides information about tail behavior and concentration relative to a reference distribution.

### Q11. Is skewness unitless?

Yes. Moment-based skewness is standardized by the standard deviation cubed, so the measurement units cancel.

### Q12. Can two datasets have the same skewness but different variances?

Yes. Skewness describes asymmetry rather than the magnitude of spread.

### Q13. Does a positively skewed distribution always have its mean above its median?

No. This relationship is common in many right-skewed distributions, but it is not a universal property of every distribution with positive moment skewness.

### Q14. Why might sample skewness differ between software packages?

Packages may use different formulas, denominators, and bias corrections.

### Q15. How can skewness be reduced?

Transformations such as logarithmic, square-root, or power transformations may reduce skewness in some datasets. Their effects must be checked rather than assumed.

### Q16. Do machine learning features need to be normally distributed?

No. Many algorithms do not require normally distributed input features. The importance of skewness depends on the model, assumptions, and task.

### Q17. How does skewness differ from IQR?

Skewness describes asymmetry, while the IQR measures the numerical width of the middle 50% of a dataset.

### Q18. Does positive skewness mean that most values are large?

No. A right-skewed distribution often has many relatively small values and a smaller number of large values extending the right tail.

### Q19. When is Pearson's second coefficient useful?

It is a simple descriptive approximation based on the mean, median, and standard deviation. It should not be confused with moment-based skewness.

### Q20. What is one limitation of skewness?

It is sensitive to extreme values and does not fully describe a distribution's shape.

---

## 17. Practice Problems

Try solving these before reading the answers.

### Problem 1: Identify the skewness direction

A dataset contains many low values and a small number of very high values. What type of skewness might it have?

### Problem 2: Identify the skewness direction

A test is relatively easy. Most students score near the maximum, while a few students receive very low scores. What type of skewness might this represent?

### Problem 3: Interpret a skewness value

A dataset has a moment-based skewness estimate of \(1.4\). What does the positive sign indicate?

### Problem 4: Zero skewness

Does a skewness value of zero prove that a distribution is symmetric?

### Problem 5: Understand the formula

Why does the moment-based skewness formula divide the third central moment by the standard deviation cubed?

### Problem 6: Compare measures

Which measure describes asymmetry: variance, standard deviation, IQR, or skewness?

### Problem 7: Outlier sensitivity

Why can one very large observation strongly affect moment-based skewness?

### Problem 8: Mean and median

A dataset has a mean of \(80\) and a median of \(60\). What might this suggest about its distribution? Why is this not definitive proof of positive moment skewness?

### Problem 9: Transformation

A strictly positive feature has a long right tail. Name one transformation that might reduce its skewness.

### Problem 10: Machine learning

Do all machine learning algorithms require normally distributed input features?

### Problem 11: Sample estimators

Why might a bias-corrected sample skewness estimate differ from empirical moment skewness?

### Problem 12: Formula calculation

For a dataset, suppose the empirical second central moment is \(m_2=4\) and the empirical third central moment is \(m_3=16\).

Calculate the empirical moment skewness.

---

## 18. Practice Problem Answers

### Answer 1

The dataset may be positively skewed because a small number of large values extend the right tail.

### Answer 2

The dataset may be negatively skewed because a small number of low scores extend the left tail.

### Answer 3

The positive sign indicates positive moment-based skewness. The distribution may have a longer or heavier right tail, but the exact shape cannot be determined from skewness alone.

### Answer 4

No. A zero third standardized central moment does not guarantee symmetry.

### Answer 5

The third central moment has units cubed. Dividing by the standard deviation cubed removes the units, making skewness dimensionless.

### Answer 6

Skewness describes asymmetry. Variance, standard deviation, and IQR measure spread in different ways.

### Answer 7

Cubing gives large deviations disproportionate influence. A very large observation can contribute substantially to the third central moment and also affect the mean and standard deviation.

### Answer 8

The mean being greater than the median may suggest positive skewness, especially for a common unimodal distribution. However, mean-median ordering alone does not determine the third standardized central moment for every possible distribution.

### Answer 9

A logarithmic transformation may help:

$$
Y=\log(X)
$$

Its effectiveness depends on the data.

### Answer 10

No. Many algorithms do not require normally distributed input features. Whether transformation is useful depends on the model and task.

### Answer 11

A bias-corrected estimator adjusts the empirical moment estimate for finite-sample bias. Because the formulas differ, their numerical values may differ.

### Answer 12

Use the empirical moment formula:

$$
g_1=\frac{m_3}{m_2^{3/2}}
$$

Substitute the values:

$$
g_1=\frac{16}{4^{3/2}}
$$

Since:

$$
4^{3/2}=8
$$

The result is:

$$
\boxed{g_1=2}
$$

The empirical moment skewness is positive.

---

## 19. Quick Revision Notes

- Skewness measures the asymmetry of a distribution.
- Positive skewness often corresponds to a longer or heavier right tail.
- Negative skewness often corresponds to a longer or heavier left tail.
- Zero moment skewness does not guarantee symmetry.
- Population moment skewness is the third central moment divided by the standard deviation cubed.
- Sample skewness estimators may include bias corrections.
- Pearson's second coefficient is a separate descriptive measure.
- Cubing deviations preserves their signs and gives extreme deviations more influence.
- Moment-based skewness is unitless.
- Skewness can be sensitive to outliers.
- The mean, median, and mode follow familiar ordering patterns in many common unimodal distributions, but these patterns are not universal.
- Skewness and kurtosis describe different aspects of distribution shape.
- Transformations may reduce skewness, but their usefulness depends on the data and model.
- Many machine learning algorithms do not require normally distributed input features.
- Use skewness alongside histograms, box plots, quantiles, and measures of spread.

---

## 20. Final Summary

Skewness is a statistical measure that describes the asymmetry of a distribution.

The population moment-based formula is:

$$
\gamma_1=\frac{E[(X-\mu)^3]}{\sigma^3}
$$

Positive skewness indicates a positive third standardized central moment, while negative skewness indicates a negative one. Zero skewness means the third standardized central moment is zero, but it does not necessarily prove symmetry.

Skewness is useful for exploratory data analysis, investigating long tails, understanding potential outlier influence, and evaluating whether a transformation might be appropriate.

For machine learning, skewness can help guide feature exploration and preprocessing, but not every model requires normally distributed features. Any transformation should be chosen based on the data, modeling assumptions, and validation results.

**Key interview takeaway:** Skewness measures asymmetry, while variance, standard deviation, and the IQR measure spread. Always distinguish the moment-based skewness formula from simpler descriptive coefficients and identify the estimator when exact calculations matter.
