# 20. What Are Variance and Standard Deviation?

## 1. Introduction

Variance and standard deviation are two fundamental statistical measures that describe the **spread or dispersion of data** around its mean.

The mean tells us the central or average value of a dataset. However, it does not tell us whether the observations are close to the mean or widely spread out.

Variance and standard deviation help answer questions such as:

- How much do the observations differ from the mean?
- Are the data points closely clustered or widely spread?
- Is a dataset more consistent than another dataset?
- How much uncertainty or variability exists in a random variable?
- How can we measure variability in machine learning models and datasets?

For example, consider these two datasets:

**Dataset A:**

$$
10,\ 10,\ 10,\ 10,\ 10
$$

**Dataset B:**

$$
2,\ 6,\ 10,\ 14,\ 18
$$

Both datasets have the same mean:

$$
\mu = 10
$$

However, Dataset A has no variation, while Dataset B contains values spread around the mean.

Variance and standard deviation quantify this difference.

---

## 2. What Is Variance?

**Variance is a measure of how far the observations in a dataset are spread out from their mean.**

It is calculated by finding the squared difference between each observation and the mean, then averaging those squared differences.

A small variance indicates that the observations are generally close to the mean.

A large variance indicates that the observations are more widely spread around the mean.

### 2.1 Population variance

When the dataset contains the entire population of interest, the population variance is calculated as:

$$
\sigma^2 = \frac{1}{N}\sum_{i=1}^{N}(x_i-\mu)^2
$$

Where:

- \(\sigma^2\) = population variance
- \(N\) = total number of observations in the population
- \(x_i\) = the \(i\)-th observation
- \(\mu\) = population mean
- \(\sum\) = summation over all observations

The formula can be understood in four steps:

1. Calculate the population mean.
2. Subtract the mean from each observation.
3. Square each difference.
4. Calculate the average of the squared differences.

### 2.2 Sample variance

When we have a sample from a larger population, sample variance is commonly calculated as:

$$
s^2 = \frac{1}{n-1}\sum_{i=1}^{n}(x_i-\bar{x})^2
$$

Where:

- \(s^2\) = sample variance
- \(n\) = number of observations in the sample
- \(x_i\) = the \(i\)-th sample observation
- \(\bar{x}\) = sample mean
- \(n-1\) = degrees of freedom

The denominator is \(n-1\), rather than \(n\), because using the sample mean tends to underestimate the population variance when we divide by \(n\). The \(n-1\) adjustment, called **Bessel's correction**, makes the sample variance an unbiased estimator of population variance when the observations are independently sampled from a population with finite variance.

### 2.3 Population variance vs. sample variance

| Feature | Population variance | Sample variance |
|---|---|---|
| Symbol | \(\sigma^2\) | \(s^2\) |
| Data used | Entire population | Sample from a population |
| Denominator | \(N\) | \(n-1\) |
| Main purpose | Describe population variability | Estimate population variability |
| Mean used | Population mean, \(\mu\) | Sample mean, \(\bar{x}\) |

**Important:** Use the population formula when you are describing the entire population of interest. Use the sample formula when estimating population variance from a sample under the usual sampling assumptions.

---

## 3. What Is Standard Deviation?

**Standard deviation is the positive square root of variance.**

It measures how spread out observations are around their mean, but it expresses the result in the same units as the original data.

### 3.1 Population standard deviation

$$
\sigma = \sqrt{\frac{1}{N}\sum_{i=1}^{N}(x_i-\mu)^2}
$$

### 3.2 Sample standard deviation

$$
s = \sqrt{\frac{1}{n-1}\sum_{i=1}^{n}(x_i-\bar{x})^2}
$$

Where:

- \(\sigma\) = population standard deviation
- \(s\) = sample standard deviation
- Variance is the square of the corresponding standard deviation.

$$
\sigma^2 = \mathrm{Var}(X)
$$

$$
\sigma = \sqrt{\mathrm{Var}(X)}
$$

For a sample, the equivalent relationship is:

$$
s = \sqrt{s^2}
$$

### 3.3 Why is standard deviation useful?

Suppose a dataset measures the heights of people in centimeters.

If the variance is \(100\text{ cm}^2\), the standard deviation is:

$$
\sigma = \sqrt{100} = 10\text{ cm}
$$

The standard deviation is easier to interpret because its unit is centimeters, the same as the original measurements.

Variance is expressed in squared units, such as \(\text{cm}^2\), \(\text{kg}^2\), or \(\text{dollars}^2\).

---

## 4. Why Do We Square the Differences from the Mean?

The variance formula squares each deviation:

$$
(x_i-\mu)^2
$$

There are several reasons for doing this.

### Reason 1: Positive and negative deviations would cancel out

Consider the observations:

$$
2,\ 4,\ 6
$$

Their mean is:

$$
\mu = \frac{2+4+6}{3}=4
$$

The deviations from the mean are:

$$
2-4=-2
$$

$$
4-4=0
$$

$$
6-4=2
$$

Their sum is:

$$
-2+0+2=0
$$

If we simply averaged the deviations, the result would always be zero when deviations are calculated from the arithmetic mean.

Squaring the deviations gives:

$$
(-2)^2=4,\quad 0^2=0,\quad 2^2=4
$$

The squared deviations are nonnegative and do not cancel each other out.

### Reason 2: Larger deviations receive more weight

Squaring makes large deviations contribute disproportionately more to variance.

For example:

$$
2^2=4
$$

$$
5^2=25
$$

A deviation of \(5\) contributes more than six times as much squared deviation as a deviation of \(2\).

This makes variance sensitive to extreme values and outliers.

### Reason 3: Squared deviations have useful mathematical properties

Squared deviations work well in many statistical methods, including least-squares regression, probability theory, and optimization.

They also lead to convenient algebraic identities and decomposition formulas.

### Limitation

Because deviations are squared, variance can be strongly affected by outliers. Standard deviation is also sensitive to outliers because it is derived from variance.

---

## 5. Step-by-Step Example: Calculate Variance and Standard Deviation

Consider the dataset:

$$
2,\ 4,\ 6,\ 8,\ 10
$$

Assume these five observations represent the entire population.

We will calculate the population variance and population standard deviation.

### Step 1: Calculate the mean

$$
\mu = \frac{2+4+6+8+10}{5}
$$

$$
\mu = \frac{30}{5}=6
$$

### Step 2: Calculate the deviations from the mean

| Observation \(x_i\) | Mean \(\mu\) | Deviation \(x_i-\mu\) |
|---:|---:|---:|
| 2 | 6 | -4 |
| 4 | 6 | -2 |
| 6 | 6 | 0 |
| 8 | 6 | 2 |
| 10 | 6 | 4 |

### Step 3: Square each deviation

| Observation | Deviation | Squared deviation |
|---:|---:|---:|
| 2 | -4 | 16 |
| 4 | -2 | 4 |
| 6 | 0 | 0 |
| 8 | 2 | 4 |
| 10 | 4 | 16 |
| **Total** | **0** | **40** |

Therefore:

$$
\sum_{i=1}^{5}(x_i-\mu)^2=40
$$

### Step 4: Calculate the population variance

$$
\sigma^2=\frac{40}{5}
$$

$$
\boxed{\sigma^2=8}
$$

### Step 5: Calculate the population standard deviation

$$
\sigma=\sqrt{8}
$$

$$
\boxed{\sigma\approx 2.83}
$$

**Final answer:**

- Population mean = \(6\)
- Population variance = \(8\)
- Population standard deviation \(\approx 2.83\)

The variance is \(8\) squared units, while the standard deviation is approximately \(2.83\) units.

### What if the same five observations were a sample?

If the values were a sample from a larger population, we would divide by \(n-1=4\).

$$
s^2=\frac{40}{5-1}=\frac{40}{4}=10
$$

Then:

$$
s=\sqrt{10}\approx 3.16
$$

The sample variance is \(10\), and the sample standard deviation is approximately \(3.16\).

---

## 6. Example: Zero Variance

Consider the dataset:

$$
5,\ 5,\ 5,\ 5,\ 5
$$

The mean is:

$$
\mu = 5
$$

Every observation equals the mean. Therefore, every deviation is zero.

$$
x_i-\mu=0
$$

The population variance is:

$$
\sigma^2=\frac{0+0+0+0+0}{5}=0
$$

The standard deviation is:

$$
\sigma=\sqrt{0}=0
$$

**Interpretation:** There is no variation in the dataset. Every observation has the same value.

Zero variance does not mean that the mean is zero. It means that all observations are identical within the dataset being measured.

---

## 7. Example: Comparing Two Datasets

Consider two datasets with the same mean.

**Dataset A:**

$$
8,\ 9,\ 10,\ 11,\ 12
$$

**Dataset B:**

$$
2,\ 6,\ 10,\ 14,\ 18
$$

Both have mean \(10\).

### Dataset A

The deviations are:

$$
-2,\ -1,\ 0,\ 1,\ 2
$$

The squared deviations are:

$$
4,\ 1,\ 0,\ 1,\ 4
$$

Their sum is \(10\). Therefore, the population variance is:

$$
\sigma_A^2=\frac{10}{5}=2
$$

The standard deviation is:

$$
\sigma_A=\sqrt{2}\approx1.41
$$

### Dataset B

The deviations are:

$$
-8,\ -4,\ 0,\ 4,\ 8
$$

The squared deviations are:

$$
64,\ 16,\ 0,\ 16,\ 64
$$

Their sum is \(160\). Therefore, the population variance is:

$$
\sigma_B^2=\frac{160}{5}=32
$$

The standard deviation is:

$$
\sigma_B=\sqrt{32}\approx5.66
$$

### Comparison

| Measure | Dataset A | Dataset B |
|---|---:|---:|
| Mean | 10 | 10 |
| Population variance | 2 | 32 |
| Population standard deviation | 1.41 | 5.66 |
| Spread | Lower | Higher |

**Conclusion:** Both datasets have the same mean, but Dataset B has much greater variability.

This demonstrates why the mean alone is not sufficient to describe a dataset.

---

## 8. Variance and Standard Deviation of a Random Variable

Variance and standard deviation are also defined for random variables.

For a random variable \(X\), variance measures how much its possible values vary around its expected value.

The expected value is denoted by:

$$
\mu = \mathbb{E}[X]
$$

The variance is:

$$
\mathrm{Var}(X)=\mathbb{E}\left[(X-\mathbb{E}[X])^2\right]
$$

An equivalent formula is:

$$
\mathrm{Var}(X)=\mathbb{E}[X^2]-(\mathbb{E}[X])^2
$$

The standard deviation is:

$$
\mathrm{SD}(X)=\sqrt{\mathrm{Var}(X)}
$$

Here, \(\mathbb{E}[X]\) denotes the expected value of \(X\), and \(\mathbb{E}[X^2]\) denotes the expected value of its square.

### 8.1 Discrete random variable

For a discrete random variable with possible values \(x_1,x_2,\ldots,x_k\) and corresponding probabilities \(p_1,p_2,\ldots,p_k\), where the probabilities sum to one:

$$
\sum_{i=1}^{k}p_i=1
$$

The expected value is:

$$
\mathbb{E}[X]=\sum_{i=1}^{k}x_i p_i
$$

The variance is:

$$
\mathrm{Var}(X)=\sum_{i=1}^{k}(x_i-\mu)^2p_i
$$

Where:

$$
\mu=\mathbb{E}[X]
$$

Each squared deviation is weighted by the probability of that outcome.

### 8.2 Example: Fair six-sided die

Let \(X\) be the result of rolling a fair six-sided die.

Possible outcomes are:

$$
1,\ 2,\ 3,\ 4,\ 5,\ 6
$$

Each outcome has probability \(1/6\).

The expected value is:

$$
\mathbb{E}[X]=\frac{1+2+3+4+5+6}{6}
$$

$$
\mathbb{E}[X]=3.5
$$

To calculate variance, first find the expected value of \(X^2\):

$$
\mathbb{E}[X^2]=\frac{1^2+2^2+3^2+4^2+5^2+6^2}{6}
$$

$$
\mathbb{E}[X^2]=\frac{91}{6}
$$

Use the computational formula:

$$
\mathrm{Var}(X)=\mathbb{E}[X^2]-(\mathbb{E}[X])^2
$$

$$
\mathrm{Var}(X)=\frac{91}{6}-(3.5)^2
$$

$$
\mathrm{Var}(X)=\frac{35}{12}\approx2.92
$$

The standard deviation is:

$$
\mathrm{SD}(X)=\sqrt{\frac{35}{12}}\approx1.71
$$

**Interpretation:** A fair die has an expected outcome of \(3.5\), a variance of approximately \(2.92\), and a standard deviation of approximately \(1.71\).

The expected value does not need to be an outcome that the random variable can actually take. A die cannot show \(3.5\), but its expected value is \(3.5\).

---

## 9. The Computational Formula for Variance

Calculating deviations from the mean is intuitive, but another formula can make variance easier to compute.

For a population or random variable:

$$
\mathrm{Var}(X)=\mathbb{E}[X^2]-(\mathbb{E}[X])^2
$$

For a finite population of \(N\) values:

$$
\sigma^2=\frac{\sum_{i=1}^{N}x_i^2}{N}-\mu^2
$$

For a sample, the corresponding computational identity is:

$$
s^2=\frac{\sum_{i=1}^{n}x_i^2-n\bar{x}^2}{n-1}
$$

These formulas are algebraically equivalent to their respective deviation-based variance formulas.

### Why does this formula work?

Start with the variance definition for a random variable:

$$
\mathrm{Var}(X)=\mathbb{E}[(X-\mu)^2]
$$

Expand the square:

$$
\mathrm{Var}(X)=\mathbb{E}[X^2-2\mu X+\mu^2]
$$

Using the linearity of expectation and the fact that \(\mu\) is a constant:

$$
\mathrm{Var}(X)=\mathbb{E}[X^2]-2\mu\mathbb{E}[X]+\mu^2
$$

Since \(\mathbb{E}[X]=\mu\):

$$
\mathrm{Var}(X)=\mathbb{E}[X^2]-2\mu^2+\mu^2
$$

Therefore:

$$
\boxed{\mathrm{Var}(X)=\mathbb{E}[X^2]-\mu^2}
$$

This is often stated as:

**Variance = expected square minus square of the expectation.**

### Important numerical caution

The computational formula can suffer from floating-point cancellation when values are very large relative to their variance. For numerical work, stable algorithms such as Welford's online variance algorithm can be preferable.

---

## 10. Important Properties of Variance and Standard Deviation

These properties are useful in statistical calculations, probability theory, and machine learning.

### Property 1: Variance is always nonnegative

$$
\mathrm{Var}(X)\geq0
$$

This is because variance is based on squared deviations, which cannot be negative.

Standard deviation is also nonnegative:

$$
\mathrm{SD}(X)\geq0
$$

### Property 2: Adding a constant does not change variance

If a constant \(c\) is added to every observation:

$$
\mathrm{Var}(X+c)=\mathrm{Var}(X)
$$

The standard deviation is also unchanged:

$$
\mathrm{SD}(X+c)=\mathrm{SD}(X)
$$

**Why?**

Adding a constant shifts every value and the mean by the same amount. The deviations from the mean therefore remain unchanged.

For example, compare:

$$
2,\ 4,\ 6
$$

with:

$$
12,\ 14,\ 16
$$

The second dataset is shifted upward by \(10\), but the spread remains the same.

### Property 3: Multiplying by a constant changes variance by its square

If every observation is multiplied by a constant \(a\):

$$
\mathrm{Var}(aX)=a^2\mathrm{Var}(X)
$$

Standard deviation changes by the absolute value of the multiplier:

$$
\mathrm{SD}(aX)=|a|\mathrm{SD}(X)
$$

**Why does variance change quadratically?**

Multiplying the observations by \(a\) also multiplies each deviation from the mean by \(a\). Squaring those deviations introduces the factor \(a^2\).

For example, if the original variance is \(4\) and all values are multiplied by \(3\):

$$
\mathrm{Var}(3X)=3^2\times4=36
$$

The original standard deviation is \(2\), so the new standard deviation is:

$$
\mathrm{SD}(3X)=|3|\times2=6
$$

If \(a=-3\), the variance is still multiplied by \(9\), and standard deviation is multiplied by \(3\).

### Property 4: Variance of a shifted and scaled random variable

Combining the previous two properties gives:

$$
\mathrm{Var}(aX+b)=a^2\mathrm{Var}(X)
$$

And:

$$
\mathrm{SD}(aX+b)=|a|\mathrm{SD}(X)
$$

Adding \(b\) does not affect spread, while multiplying by \(a\) scales the spread.

### Property 5: Variance of a sum

For two random variables \(X\) and \(Y\):

$$
\mathrm{Var}(X+Y)=\mathrm{Var}(X)+\mathrm{Var}(Y)+2\mathrm{Cov}(X,Y)
$$

For their difference:

$$
\mathrm{Var}(X-Y)=\mathrm{Var}(X)+\mathrm{Var}(Y)-2\mathrm{Cov}(X,Y)
$$

Here, \(\mathrm{Cov}(X,Y)\) is the covariance between the two variables.

If \(X\) and \(Y\) are independent and have finite variances, their covariance is zero. Therefore:

$$
\mathrm{Var}(X+Y)=\mathrm{Var}(X)+\mathrm{Var}(Y)
$$

For independent random variables, the variance of a sum is the sum of the variances.

**Important:** Independence is sufficient for zero covariance, but zero covariance alone does not generally imply independence.

### Property 6: Variance of a difference between independent variables

If \(X\) and \(Y\) are independent:

$$
\mathrm{Var}(X-Y)=\mathrm{Var}(X)+\mathrm{Var}(Y)
$$

Although the variables are subtracted, their variances add when the variables are independent.

This follows because subtracting \(Y\) changes the covariance term's sign, but independence makes that term zero.

### Property 7: Variance of a sum with constants

For constants \(a\), \(b\), and random variables \(X\), \(Y\):

$$
\mathrm{Var}(aX+bY)=a^2\mathrm{Var}(X)+b^2\mathrm{Var}(Y)+2ab\mathrm{Cov}(X,Y)
$$

If \(X\) and \(Y\) are independent, this simplifies to:

$$
\mathrm{Var}(aX+bY)=a^2\mathrm{Var}(X)+b^2\mathrm{Var}(Y)
$$

### Property 8: Standard deviation is not generally additive

In general:

$$
\mathrm{SD}(X+Y)\neq\mathrm{SD}(X)+\mathrm{SD}(Y)
$$

The relationship between the spread of a sum and the spread of its components depends on their covariance.

When variables are independent:

$$
\mathrm{SD}(X+Y)=\sqrt{\mathrm{Var}(X)+\mathrm{Var}(Y)}
$$

It is the variances that add under independence, not the standard deviations.

### Property 9: Zero variance means a constant value

For a random variable with finite variance:

$$
\mathrm{Var}(X)=0
$$

implies that \(X\) equals a constant with probability \(1\).

For a finite dataset, variance is zero exactly when all observations are identical.

### Property 10: Variance depends on the unit of measurement

If a measurement is expressed in meters and converted to centimeters, the values are multiplied by \(100\).

The variance is therefore multiplied by:

$$
100^2=10000
$$

The standard deviation is multiplied by \(100\).

This is why variance is expressed in squared units, while standard deviation uses the original unit.

---

## 11. Variance vs. Standard Deviation

Although closely related, variance and standard deviation are not identical.

| Feature | Variance | Standard deviation |
|---|---|---|
| Meaning | Average squared deviation, using the appropriate population or sample denominator | Square root of variance |
| Population symbol | \(\sigma^2\) | \(\sigma\) |
| Sample symbol | \(s^2\) | \(s\) |
| Units | Squared original units | Original units |
| Can it be negative? | No | No |
| Effect of outliers | Sensitive | Sensitive |
| Main interpretation | Mathematical measure of dispersion | More directly interpretable measure of dispersion |

### Example

Suppose population variance is:

$$
\sigma^2=25
$$

Then the population standard deviation is:

$$
\sigma=\sqrt{25}=5
$$

If the original observations are measured in kilograms, the variance is \(25\text{ kg}^2\), and the standard deviation is \(5\text{ kg}\).

### Which one should we use?

- Use **variance** when performing mathematical calculations, comparing model objectives based on squared error, or working with probability distributions.
- Use **standard deviation** when describing variability in the same units as the data.
- Use both when a complete statistical description is needed.

---

## 12. Variance and Standard Deviation in the Normal Distribution

The normal distribution is described by two parameters: its mean and standard deviation, or equivalently, its mean and variance.

For a normal random variable:

$$
X\sim\mathcal{N}(\mu,\sigma^2)
$$

Where:

- \(\mu\) = mean, which determines the center
- \(\sigma^2\) = variance, which controls the squared spread
- \(\sigma\) = standard deviation, which controls the spread in the original units

The probability density function is:

$$
f(x)=\frac{1}{\sigma\sqrt{2\pi}}
\exp\left(-\frac{(x-\mu)^2}{2\sigma^2}\right)
$$

Here, \(\sigma>0\).

### Effect of the standard deviation

- A smaller standard deviation produces a narrower, more concentrated normal distribution.
- A larger standard deviation produces a wider, more dispersed normal distribution.
- Changing the mean shifts the distribution without changing its spread.

### The empirical rule

For a normally distributed variable, approximately:

- \(68\%\) of observations lie within one standard deviation of the mean.
- \(95\%\) lie within two standard deviations of the mean.
- \(99.7\%\) lie within three standard deviations of the mean.

These intervals are:

$$
[\mu-\sigma,\ \mu+\sigma]
$$

$$
[\mu-2\sigma,\ \mu+2\sigma]
$$

$$
[\mu-3\sigma,\ \mu+3\sigma]
$$

These percentages are approximate and rely on the normal distribution assumption. They are not universal rules for arbitrary datasets.

---

## 13. Z-Scores and Standardization

A z-score describes how many standard deviations an observation lies above or below the mean.

For a population distribution:

$$
z=\frac{x-\mu}{\sigma}
$$

When standardizing a sample using its sample mean and sample standard deviation, the corresponding expression is:

$$
z=\frac{x-\bar{x}}{s}
$$

A positive z-score means the observation is above the mean.

A negative z-score means it is below the mean.

A z-score of zero means it equals the mean.

### Example

Suppose exam scores have a mean of \(70\) and a standard deviation of \(10\).

A student scores \(85\).

$$
z=\frac{85-70}{10}
$$

$$
z=1.5
$$

The score is \(1.5\) standard deviations above the mean.

### Standardization in machine learning

A common feature-standardization transformation is:

$$
z=\frac{x-\mu}{\sigma}
$$

In practice, \(\mu\) and \(\sigma\) are usually estimated from the training dataset.

The transformation centers the feature around zero and scales it by its standard deviation.

**Important:** Fit the standardization parameters on the training data only, then apply those same parameters to validation and test data. Fitting the scaler on the entire dataset can leak information from the validation or test set into training.

---

## 14. Applications of Variance and Standard Deviation in Machine Learning

Variance and standard deviation are widely used in machine learning and data science.

### 14.1 Feature scaling and standardization

Features can have very different scales.

For example:

- Age may range from \(18\) to \(90\).
- Income may range from thousands to millions.
- A test score may range from \(0\) to \(100\).

Some algorithms are sensitive to feature scales. Standardization can help prevent features with large numerical scales from dominating distance calculations or optimization.

Commonly affected methods include:

- Logistic regression with regularization
- Linear regression with regularization
- Support vector machines
- K-nearest neighbors
- K-means clustering
- Principal component analysis
- Neural networks, depending on architecture and optimization setup

Tree-based models such as decision trees and random forests generally do not require standardization for their usual split-based training procedures.

### 14.2 Detecting unusual observations

An observation far from the mean may be an outlier or an unusual data point.

A z-score can be used as a screening measure:

$$
z=\frac{x-\mu}{\sigma}
$$

For example, a value with an absolute z-score greater than \(3\) is sometimes flagged for investigation.

However, this is a heuristic rather than a universal outlier rule. It can be unreliable for skewed distributions, heavy-tailed distributions, small samples, or datasets containing multiple groups.

An unusual value is not automatically an error. It should be investigated using the context of the data.

### 14.3 Gaussian Naive Bayes

Gaussian Naive Bayes models a continuous feature within each class using a Gaussian distribution.

For a feature \(X_j\) and class \(C_k\), the model estimates a class-specific mean and variance:

$$
X_j\mid C_k\sim\mathcal{N}(\mu_{jk},\sigma_{jk}^2)
$$

The variance helps determine the width of the feature distribution for that class.

A class with a small variance has values concentrated near its class-specific mean. A class with a larger variance has more spread.

### 14.4 Bias-variance trade-off

The bias-variance trade-off is a central concept in supervised learning.

- **Bias** is associated with errors caused by simplifying assumptions that prevent a model from capturing the underlying relationship.
- **Variance** describes how much a fitted model's predictions can change when the training dataset changes.

A high-variance model may fit the training data very closely but perform poorly on unseen data. This is commonly associated with overfitting.

A high-bias model may be too simple to capture important patterns. This is commonly associated with underfitting.

The objective is not simply to minimize variance. It is to find an appropriate balance that improves generalization.

### 14.5 Principal component analysis

Principal component analysis (PCA) identifies directions in the data that explain large amounts of variance.

The covariance matrix contains variances on its diagonal and covariances off its diagonal.

The eigenvectors of the covariance matrix identify principal directions, and their corresponding eigenvalues describe the variance along those directions.

PCA often retains components with large eigenvalues and discards components with smaller eigenvalues.

This can reduce dimensionality, although a low-variance component can still contain useful predictive information.

### 14.6 Measuring model and data stability

Variance can help compare the stability of measurements, model predictions, or estimates across repeated samples.

For example, if a model is trained on multiple resampled datasets, variation in its predictions may provide insight into model sensitivity.

This is one reason resampling approaches such as bootstrap analysis are useful.

### 14.7 Quality control and monitoring

Variance and standard deviation can help identify changes in production measurements, sensor readings, transaction values, and system performance.

An unexpected increase in variability may indicate:

- A change in the data-generating process
- Measurement problems
- A process becoming less consistent
- An unusual operating condition

The interpretation depends on the application and should account for normal variation.

---

## 15. Limitations of Variance and Standard Deviation

Variance and standard deviation are useful, but they have limitations.

### 15.1 Sensitivity to outliers

Because variance squares deviations, large deviations have a disproportionate effect.

For example, compare:

$$
10,\ 11,\ 12,\ 13,\ 14
$$

with:

$$
10,\ 11,\ 12,\ 13,\ 100
$$

The value \(100\) substantially increases both variance and standard deviation.

If a dataset is highly skewed or contains influential outliers, consider also reporting the median and interquartile range.

### 15.2 Variance uses squared units

A variance of \(100\text{ cm}^2\) is less intuitive than a standard deviation of \(10\text{ cm}\).

This is one reason standard deviation is often preferred for descriptive reporting.

### 15.3 Standard deviation does not describe the entire distribution

Two datasets can have the same mean and standard deviation but have different shapes.

They may differ in skewness, number of modes, tail behavior, or the presence of clusters.

Therefore, variance and standard deviation should not be treated as complete descriptions of a distribution.

### 15.4 The mean may be unrepresentative for skewed data

Variance and standard deviation are calculated around the mean.

If a dataset is strongly skewed, the mean may not represent a typical observation well. In such cases, the median and interquartile range may provide a more robust summary.

### 15.5 Standard deviation does not always imply a normal distribution

A standard deviation of \(5\) does not mean that \(68\%\) of the data must lie within \(5\) units of the mean.

That approximate \(68\%\) rule applies to normal distributions. For arbitrary distributions, the proportion can be different.

---

## 16. Variance vs. Range vs. Interquartile Range

These are different measures of spread.

| Measure | Definition | Main strength | Main limitation |
|---|---|---|---|
| Range | Maximum minus minimum | Simple and easy to calculate | Depends only on two observations |
| Variance | Average squared deviation, using the appropriate denominator | Useful for probability and mathematical analysis | Squared units; sensitive to outliers |
| Standard deviation | Square root of variance | Expressed in the original units | Sensitive to outliers |
| Interquartile range | Third quartile minus first quartile | Robust to extreme values | Does not describe tail spread in detail |

The interquartile range is:

$$
\mathrm{IQR}=Q_3-Q_1
$$

Where:

- \(Q_1\) is the first quartile.
- \(Q_3\) is the third quartile.

Use measures of spread that fit the distribution and the question being asked. For approximately symmetric, well-behaved data, standard deviation is often informative. For strongly skewed data, median and IQR may be more appropriate.

---

## 17. Common Mistakes

### Mistake 1: Dividing by \(n\) instead of \(n-1\) for sample variance

For the usual unbiased sample-variance estimator, divide the sum of squared deviations from the sample mean by \(n-1\).

$$
s^2=\frac{\sum_{i=1}^{n}(x_i-\bar{x})^2}{n-1}
$$

Divide by \(N\) when calculating the variance of the complete population.

### Mistake 2: Forgetting to square the deviations

Variance uses squared deviations, not absolute deviations.

$$
(x_i-\mu)^2
$$

Using absolute deviations instead produces a different measure: the mean absolute deviation when averaged in the usual way.

### Mistake 3: Confusing variance with standard deviation

Variance is the squared spread measure. Standard deviation is its square root.

If variance is \(36\), standard deviation is \(6\), not \(36\).

### Mistake 4: Assuming a larger standard deviation means a larger mean

Mean and standard deviation describe different properties.

A dataset can have a high mean and low standard deviation, or a low mean and high standard deviation.

### Mistake 5: Adding standard deviations for independent variables

For independent \(X\) and \(Y\), variances add:

$$
\mathrm{Var}(X+Y)=\mathrm{Var}(X)+\mathrm{Var}(Y)
$$

Standard deviations do not generally add directly.

### Mistake 6: Assuming every value within three standard deviations is guaranteed to occur

The empirical rule is approximate and depends on normality. It does not guarantee that every observation will lie within three standard deviations.

### Mistake 7: Ignoring units

If the original measurement is in meters, variance is in square meters, while standard deviation is in meters.

### Mistake 8: Treating every unusual observation as an error

An outlier may be a genuine observation, a measurement error, or evidence of a different process. Investigate before removing it.

### Mistake 9: Standardizing before splitting the data

When evaluating a machine learning model, fit preprocessing parameters on the training set only. Apply the learned transformation to validation and test data.

### Mistake 10: Assuming zero covariance means independence

Zero covariance is enough for the variance-of-a-sum simplification, but it does not generally prove that two random variables are independent.

---

## 18. Frequently Asked Interview Questions

### Q1. What is variance?

Variance measures the average squared deviation of observations from their mean, using the appropriate population or sample formula.

For a population:

$$
\sigma^2=\frac{1}{N}\sum_{i=1}^{N}(x_i-\mu)^2
$$

### Q2. What is standard deviation?

Standard deviation is the positive square root of variance. It measures dispersion in the same units as the original data.

$$
\sigma=\sqrt{\sigma^2}
$$

### Q3. What is the difference between variance and standard deviation?

Variance uses squared deviations and has squared units. Standard deviation is the square root of variance and uses the original units, making it easier to interpret.

### Q4. Why is sample variance divided by \(n-1\)?

When estimating population variance, the sample mean is calculated from the same observations. This uses one degree of freedom and tends to make the version divided by \(n\) underestimate population variance. Dividing by \(n-1\) gives the usual unbiased sample-variance estimator.

### Q5. Can variance be negative?

No. Variance is based on squared deviations, which are nonnegative.

$$
\mathrm{Var}(X)\geq0
$$

### Q6. What does zero variance mean?

It means all observations in a finite dataset are identical. For a random variable with finite variance, it means the variable is constant with probability \(1\).

### Q7. Can two datasets have the same mean but different variance?

Yes. The mean measures the center, while variance measures the spread. Two datasets can have the same mean but different amounts of dispersion.

### Q8. Why is standard deviation often easier to interpret than variance?

Standard deviation is expressed in the same units as the original data. Variance is expressed in squared units.

### Q9. How does multiplying all observations by a constant affect variance?

If every value is multiplied by \(a\), variance is multiplied by \(a^2\).

$$
\mathrm{Var}(aX)=a^2\mathrm{Var}(X)
$$

### Q10. How does adding a constant affect variance?

Adding a constant shifts the data without changing its spread.

$$
\mathrm{Var}(X+c)=\mathrm{Var}(X)
$$

### Q11. Why is variance sensitive to outliers?

Because deviations from the mean are squared, a large deviation contributes disproportionately to the total.

### Q12. What is the relationship between variance and covariance?

For two random variables:

$$
\mathrm{Var}(X+Y)=\mathrm{Var}(X)+\mathrm{Var}(Y)+2\mathrm{Cov}(X,Y)
$$

Covariance accounts for how the two variables vary together.

### Q13. What happens to the variance when the units change?

If all values are multiplied by a conversion factor \(a\), variance is multiplied by \(a^2\), and standard deviation is multiplied by \(|a|\).

### Q14. How are variance and standard deviation used in machine learning?

They are used in feature standardization, Gaussian Naive Bayes, PCA, anomaly screening, model stability analysis, and the bias-variance trade-off.

### Q15. Does a high variance always indicate a bad model?

No. The meaning depends on context. High variance in a fitted model's predictions across training samples can suggest instability or overfitting, but high variance in a feature may be meaningful and useful.

### Q16. Does a low variance always indicate good data?

No. A low-variance feature may be stable, but it may also carry little useful information. Whether low variance is desirable depends on the task.

### Q17. Is standard deviation affected by a shift in the mean?

No. Adding a constant to all observations changes the mean but leaves standard deviation unchanged.

### Q18. What is the computational formula for variance?

For a random variable:

$$
\mathrm{Var}(X)=\mathbb{E}[X^2]-(\mathbb{E}[X])^2
$$

### Q19. What is the difference between population and sample variance?

Population variance describes the entire population and divides by \(N\). Sample variance usually estimates population variance and divides the squared deviations from the sample mean by \(n-1\).

### Q20. Can two distributions have the same variance but different shapes?

Yes. Variance describes one aspect of spread, not the entire distribution. Different distributions can have the same mean and variance while differing in skewness, tails, or modality.

---

## 19. Practice Problems

Try solving these problems before checking the answers.

### Problem 1: Population variance and standard deviation

Calculate the population variance and standard deviation for:

$$
4,\ 4,\ 4,\ 4
$$

### Problem 2: Population variance

Calculate the population variance for:

$$
1,\ 3,\ 5
$$

### Problem 3: Sample variance

Calculate the sample variance for:

$$
2,\ 4,\ 6
$$

### Problem 4: Scaling property

A random variable \(X\) has variance \(5\). Find the variance of \(Y=4X\).

### Problem 5: Shift property

A random variable \(X\) has variance \(12\). Find the variance of \(Y=X+100\).

### Problem 6: Standard deviation

If a population variance is \(49\), what is its standard deviation?

### Problem 7: Sum of independent variables

Suppose \(X\) and \(Y\) are independent, with:

$$
\mathrm{Var}(X)=4
$$

$$
\mathrm{Var}(Y)=9
$$

Calculate the variance and standard deviation of \(X+Y\).

### Problem 8: Interpret the spread

Dataset A has standard deviation \(2\), and Dataset B has standard deviation \(8\). What can you conclude if both datasets use the same measurement units?

### Problem 9: Z-score

A student scores \(90\) on a test with mean \(75\) and standard deviation \(5\). Calculate the z-score.

### Problem 10: Sample vs. population variance

A dataset contains all five members of a small group, and you want to describe variability within that group. Should you use the population or sample variance formula?

### Problem 11: Variance of a difference

Suppose \(X\) and \(Y\) are independent, with variances \(7\) and \(3\). Calculate:

$$
\mathrm{Var}(X-Y)
$$

### Problem 12: Variance under a transformation

A random variable \(X\) has variance \(6\). Define:

$$
Y=-2X+5
$$

Find the variance and standard deviation of \(Y\) in terms of the given variance and standard deviation of \(X\).

---

## 20. Practice Problem Answers

### Answer 1

All observations are equal to \(4\), so every deviation is zero.

$$
\sigma^2=0
$$

$$
\sigma=0
$$

### Answer 2

The mean is:

$$
\mu=\frac{1+3+5}{3}=3
$$

Squared deviations:

$$
(1-3)^2=4,\quad (3-3)^2=0,\quad (5-3)^2=4
$$

Population variance:

$$
\sigma^2=\frac{4+0+4}{3}=\frac{8}{3}
$$

Therefore:

$$
\boxed{\sigma^2\approx2.67}
$$

### Answer 3

The sample mean is:

$$
\bar{x}=\frac{2+4+6}{3}=4
$$

The sum of squared deviations is:

$$
(2-4)^2+(4-4)^2+(6-4)^2=8
$$

Sample variance:

$$
s^2=\frac{8}{3-1}=4
$$

### Answer 4

Use the scaling property:

$$
\mathrm{Var}(4X)=4^2\mathrm{Var}(X)
$$

$$
\mathrm{Var}(Y)=16\times5=80
$$

### Answer 5

Adding a constant does not change variance:

$$
\mathrm{Var}(X+100)=\mathrm{Var}(X)
$$

Therefore:

$$
\mathrm{Var}(Y)=12
$$

### Answer 6

$$
\sigma=\sqrt{49}=7
$$

### Answer 7

Because \(X\) and \(Y\) are independent:

$$
\mathrm{Var}(X+Y)=4+9=13
$$

The standard deviation is:

$$
\mathrm{SD}(X+Y)=\sqrt{13}\approx3.61
$$

### Answer 8

Dataset B has greater dispersion than Dataset A, because its standard deviation is larger.

The ratio of their standard deviations is:

$$
\frac{8}{2}=4
$$

Dataset B's standard deviation is four times Dataset A's. This does not imply that every observation in Dataset B is farther from its mean than every observation in Dataset A.

### Answer 9

$$
z=\frac{90-75}{5}=3
$$

The score is three standard deviations above the mean.

### Answer 10

Use the population variance formula because the data include the entire group of interest.

$$
\sigma^2=\frac{1}{N}\sum_{i=1}^{N}(x_i-\mu)^2
$$

If the goal were to use those observations to estimate the variance of a larger population, the sample variance formula would generally be appropriate instead.

### Answer 11

Independence implies zero covariance, so:

$$
\mathrm{Var}(X-Y)=\mathrm{Var}(X)+\mathrm{Var}(Y)
$$

$$
\mathrm{Var}(X-Y)=7+3=10
$$

### Answer 12

For \(Y=aX+b\):

$$
\mathrm{Var}(aX+b)=a^2\mathrm{Var}(X)
$$

Here, \(a=-2\) and \(b=5\).

$$
\mathrm{Var}(Y)=(-2)^2\times6=24
$$

The standard deviation scales by the absolute value of the multiplier:

$$
\mathrm{SD}(Y)=|-2|\mathrm{SD}(X)
$$

Since \(\mathrm{SD}(X)=\sqrt{6}\):

$$
\mathrm{SD}(Y)=2\sqrt{6}\approx4.90
$$

---

## 21. Quick Revision Notes

- **Variance** measures dispersion using squared deviations from the mean.
- **Standard deviation** is the positive square root of variance.
- Population variance divides by \(N\).
- The usual unbiased sample variance divides by \(n-1\).
- Variance is always nonnegative.
- Zero variance means no variation in a finite dataset.
- Adding a constant does not change variance or standard deviation.
- Multiplying observations by \(a\) multiplies variance by \(a^2\) and standard deviation by \(|a|\).
- Variances of independent random variables add when the variables are summed or subtracted.
- Standard deviations do not generally add.
- Variance uses squared units; standard deviation uses the original units.
- Outliers can strongly affect both variance and standard deviation.
- The empirical rule applies approximately to normally distributed data.
- Machine learning applications include standardization, PCA, Gaussian Naive Bayes, anomaly screening, and model stability analysis.

## 22. Final Summary

Variance and standard deviation describe how observations are distributed around their mean.

Variance measures the average squared deviation, while standard deviation takes the square root of variance to express the spread in the original units.

The most important formulas to remember are:

**Population variance**

$$
\sigma^2=\frac{1}{N}\sum_{i=1}^{N}(x_i-\mu)^2
$$

**Sample variance**

$$
s^2=\frac{1}{n-1}\sum_{i=1}^{n}(x_i-\bar{x})^2
$$

**Population standard deviation**

$$
\sigma=\sqrt{\sigma^2}
$$

**Sample standard deviation**

$$
s=\sqrt{s^2}
$$

**Computational formula for variance**

$$
\mathrm{Var}(X)=\mathbb{E}[X^2]-(\mathbb{E}[X])^2
$$

**Scaling and shifting**

$$
\mathrm{Var}(aX+b)=a^2\mathrm{Var}(X)
$$

$$
\mathrm{SD}(aX+b)=|a|\mathrm{SD}(X)
$$

Understanding these concepts is essential for descriptive statistics, probability, statistical inference, data analysis, and machine learning.

