# Q19. What Is Range in Statistics?

## 1. Introduction

In statistics, **range is a measure of dispersion that describes the difference between the largest and smallest values in a dataset.**

It gives us a quick understanding of how far apart the extreme observations are.

For example, consider the dataset:

`10, 20, 30, 40, 50`

The smallest value is 10, and the largest value is 50.

Therefore, the range is:

$$
\text{Range} = 50 - 10 = 40
$$

This means the difference between the largest and smallest observations is 40.

Range is one of the simplest measures of variability and is often used during exploratory data analysis.

---

## 2. Definition of Range

The range is defined as the difference between the maximum and minimum observations in a dataset.

### Formula

$$
\text{Range} = X_{\max} - X_{\min}
$$

Where:

- \(X_{\max}\) = maximum value in the dataset
- \(X_{\min}\) = minimum value in the dataset

The range is expressed in the same units as the original data.

For example, if the observations represent temperatures in degrees Celsius, the range is also expressed in degrees Celsius.

---

## 3. How to Calculate Range

To calculate the range, follow these steps:

1. Identify all observations in the dataset.
2. Find the minimum value.
3. Find the maximum value.
4. Subtract the minimum value from the maximum value.

### Example 1: Simple numerical dataset

Consider:

`5, 8, 12, 15, 20`

Minimum = 5

Maximum = 20

$$
\text{Range} = 20 - 5
$$

$$
\boxed{\text{Range} = 15}
$$

The range is 15.

### Example 2: Dataset with negative values

Consider:

`-10, -5, 0, 5, 15`

Minimum = -10

Maximum = 15

$$
\text{Range} = 15 - (-10)
$$

$$
\text{Range} = 15 + 10 = 25
$$

The range is 25.

**Important:** Subtracting a negative minimum means adding its absolute value.

### Example 3: Dataset with repeated values

Consider:

`4, 4, 4, 4, 4`

Minimum = 4

Maximum = 4

$$
\text{Range} = 4 - 4 = 0
$$

The range is zero because every observation has the same value.

### Example 4: Unsorted dataset

Consider:

`25, 10, 45, 15, 30`

The observations do not need to be sorted before calculating the range.

Minimum = 10

Maximum = 45

$$
\text{Range} = 45 - 10 = 35
$$

The range is 35.

---

## 4. What Does Range Tell Us?

Range provides a basic indication of the spread of a dataset.

### Small range

A small range means the minimum and maximum observations are relatively close together.

Example:

`48, 49, 50, 51, 52`

$$
\text{Range} = 52 - 48 = 4
$$

The extreme values differ by only 4 units.

### Large range

A large range means the minimum and maximum observations are far apart.

Example:

`10, 20, 30, 40, 100`

$$
\text{Range} = 100 - 10 = 90
$$

The extreme values differ by 90 units.

### Important limitation

A large range does not necessarily mean that most observations are widely spread out.

For example:

`10, 11, 12, 13, 100`

The range is 90, even though four of the five observations are close together.

Therefore, range describes the distance between the two extremes, not the overall distribution of every observation.

---

## 5. Range and Outliers

One of the most important limitations of range is that it is highly sensitive to outliers.

An outlier is an observation that lies unusually far from the rest of the data.

### Example

Dataset A:

`10, 20, 30, 40, 50`

The range is:

$$
\text{Range}_A = 50 - 10 = 40
$$

Now suppose the last value changes from 50 to 500.

Dataset B:

`10, 20, 30, 40, 500`

The new range is:

$$
\text{Range}_B = 500 - 10 = 490
$$

| Measure | Dataset A | Dataset B |
|---|---:|---:|
| Minimum | 10 | 10 |
| Maximum | 50 | 500 |
| Range | 40 | 490 |

Changing just one observation increases the range from 40 to 490.

This illustrates why range is not a robust measure of dispersion.

### Interview takeaway

**Range is highly sensitive to outliers because it depends entirely on the minimum and maximum values.**

When extreme observations are present, the interquartile range (IQR) may provide a more representative measure of the spread of the middle portion of the data.

---

## 6. Range vs. Interquartile Range (IQR)

Both range and interquartile range measure dispersion, but they describe different parts of a dataset.

### Range

The range uses the two extreme observations.

$$
\text{Range} = X_{\max} - X_{\min}
$$

### Interquartile range

The interquartile range measures the spread of the middle 50% of the observations.

$$
\text{IQR} = Q_3 - Q_1
$$

Where:

- \(Q_1\) = first quartile, or 25th percentile
- \(Q_3\) = third quartile, or 75th percentile

### Example

Consider:

`1, 2, 3, 4, 5, 6, 7, 8, 100`

The range is:

$$
\text{Range} = 100 - 1 = 99
$$

Using the common method that excludes the overall median when finding the medians of the lower and upper halves:

- Lower half: `1, 2, 3, 4`
- Upper half: `6, 7, 8, 100`

Therefore:

$$
Q_1 = \frac{2+3}{2} = 2.5
$$

$$
Q_3 = \frac{7+8}{2} = 7.5
$$

The IQR is:

$$
\text{IQR} = 7.5 - 2.5 = 5
$$

The range is 99, while the IQR is 5.

The large difference occurs because the range includes the extreme value 100, while the IQR describes the spread of the middle half of the data.

**Note:** Different statistical software packages may use different quartile calculation conventions, so IQR values can differ slightly for small datasets.

---

## 7. Range vs. Variance and Standard Deviation

Range, variance, and standard deviation are all measures of dispersion, but they summarize variability differently.

### Range

Measures the difference between the maximum and minimum observations.

$$
\text{Range} = X_{\max} - X_{\min}
$$

### Population variance

Measures the average squared deviation from the population mean.

$$
\sigma^2 = \frac{1}{N}\sum_{i=1}^{N}(x_i-\mu)^2
$$

Where:

- \(\sigma^2\) = population variance
- \(N\) = population size
- \(x_i\) = individual observation
- \(\mu\) = population mean

### Population standard deviation

Is the square root of population variance.

$$
\sigma = \sqrt{\frac{1}{N}\sum_{i=1}^{N}(x_i-\mu)^2}
$$

### Comparison

| Feature | Range | Variance | Standard deviation |
|---|---|---|---|
| What it measures | Distance between extremes | Average squared deviation from the mean | Typical scale of deviation from the mean |
| Uses all observations? | No, only minimum and maximum | Yes | Yes |
| Sensitive to outliers? | Yes | Yes | Yes |
| Units | Original units | Squared units | Original units |
| Computational complexity | Very low | Higher | Higher |

Range is easy to calculate, but variance and standard deviation use information from every observation.

**Important:** Standard deviation is not literally the average absolute distance from the mean. It is based on squared deviations.

---

## 8. Range in Real-World Applications

### A. Weather analysis

Suppose the temperatures recorded during a day are:

- Minimum temperature: 18°C
- Maximum temperature: 32°C

The temperature range is:

$$
\text{Range} = 32 - 18 = 14^\circ C
$$

The temperature varied across an interval of 14°C between the day's minimum and maximum.

### B. Business analysis

Suppose the daily sales of a shop over five days are:

`₹5,000, ₹6,000, ₹7,000, ₹8,000, ₹12,000`

The range is:

$$
\text{Range} = 12000 - 5000
$$

$$
\text{Range} = ₹7,000
$$

This provides a quick summary of the difference between the highest and lowest daily sales.

However, it does not tell us how sales varied on the other days.

### C. Quality control

In manufacturing, range can be used to monitor variation in repeated measurements.

Suppose five components have measured lengths, in millimeters:

`10.1, 10.2, 10.2, 10.3, 10.4`

The range is:

$$
\text{Range} = 10.4 - 10.1 = 0.3\text{ mm}
$$

A small range may indicate that measurements are close together, although determining whether the variation is acceptable requires product specifications and an appropriate quality-control method.

### D. Financial analysis

Range can describe the difference between the highest and lowest recorded stock prices over a specified period.

For example, if a stock's lowest price is ₹100 and its highest price is ₹130:

$$
\text{Range} = 130 - 100 = ₹30
$$

The range provides a simple measure of price movement over that period. It does not, by itself, describe the sequence of prices, volatility over time, or investment risk.

---

## 9. Range in Machine Learning

Range can be useful during exploratory data analysis and feature preprocessing.

### A. Understanding feature variability

Suppose a dataset contains two features:

- Age: minimum 18, maximum 65
- Annual income: minimum ₹100,000, maximum ₹2,000,000

Their ranges are:

$$
\text{Age Range} = 65 - 18 = 47
$$

$$
\text{Income Range} = 2000000 - 100000 = 1900000
$$

The ranges are very different because the features use different scales and units.

A large numerical range does not automatically mean that a feature is more important to a machine learning model.

### B. Min-max scaling

Min-max scaling transforms a numerical feature into a specified interval, commonly from 0 to 1.

The formula is:

$$
x' = \frac{x-x_{\min}}{x_{\max}-x_{\min}}
$$

Where:

- \(x\) = original feature value
- \(x_{\min}\) = minimum value used for scaling
- \(x_{\max}\) = maximum value used for scaling
- \(x'\) = scaled value

### Example

Suppose the minimum age is 20 and the maximum age is 60.

For an age of 40:

$$
x' = \frac{40-20}{60-20}
$$

$$
x' = \frac{20}{40} = 0.5
$$

The scaled value is 0.5.

The original value 40 is halfway between the minimum and maximum, so it maps to the midpoint of the interval from 0 to 1.

### C. A limitation of min-max scaling

Min-max scaling depends on the minimum and maximum values. If an extreme outlier is present, it can compress most other observations into a narrow portion of the scaled interval.

For example, if most incomes fall between ₹100,000 and ₹500,000 but one income is ₹10,000,000, the extreme value can make the scaled values of ordinary incomes very small.

Possible responses include investigating the outlier, using a suitable transformation, or considering a robust scaling method when appropriate.

### D. Avoiding data leakage

When training a machine learning model, learn the minimum and maximum values from the training dataset only. Then apply those same fitted scaling parameters to validation and test data.

Do not independently fit the scaler on the test data, because that allows information from the test distribution to influence preprocessing.

### Important distinction

**Range is a descriptive statistic. Min-max scaling uses the range to transform feature values, but range itself is not a scaling algorithm.**

---

## 10. Advantages of Range

1. **Simple to calculate:** Only the minimum and maximum are required.
2. **Easy to interpret:** It directly describes the difference between the two extremes.
3. **Fast to compute:** It is useful for quick exploratory analysis.
4. **Useful in quality control:** It can help summarize the spread of repeated measurements.
5. **Helps identify potential extreme observations:** An unexpectedly large range can motivate further investigation.

---

## 11. Limitations of Range

1. **Sensitive to outliers:** A single extreme observation can change the range substantially.
2. **Ignores most observations:** It does not describe how the remaining data is distributed.
3. **Does not describe the center:** It cannot tell us the mean or median.
4. **Cannot reveal distribution shape:** Two datasets can have the same range but very different distributions.
5. **Depends on sample size:** Larger samples may have more extreme minimum or maximum values, increasing the range even if the underlying distribution has not changed.
6. **Not a complete measure of variability:** It is often useful to examine the IQR, variance, standard deviation, and visualizations as well.

---

## 12. Common Interview Questions and Answers

### Q1. What is range in statistics?

**Answer:** Range is the difference between the maximum and minimum values in a dataset.

$$
\text{Range} = X_{\max} - X_{\min}
$$

### Q2. Is range a measure of central tendency or dispersion?

**Answer:** Range is a measure of dispersion because it describes the spread between the extreme observations.

### Q3. Why is range sensitive to outliers?

**Answer:** Range depends only on the minimum and maximum values. An extreme observation can change either of these values and substantially increase or decrease the range.

### Q4. Can the range be zero?

**Answer:** Yes. If every observation has the same value, the maximum equals the minimum, so the range is zero.

### Q5. Can range be negative?

**Answer:** No. The maximum value is always greater than or equal to the minimum value, so the range is always nonnegative for a nonempty dataset of numerical observations.

### Q6. What is the difference between range and IQR?

**Answer:** Range measures the difference between the maximum and minimum. IQR measures the difference between the third and first quartiles and describes the spread of the middle 50% of observations.

### Q7. What is the relationship between range and min-max scaling?

**Answer:** Min-max scaling uses the difference between the maximum and minimum values as its denominator to transform feature values into a specified interval.

### Q8. Why is range not sufficient for understanding a distribution?

**Answer:** It uses only the two extreme values and ignores the positions and frequencies of the remaining observations.

### Q9. Can two datasets have the same range but different variability?

**Answer:** Yes. For example, `0, 1, 2, 9, 10` and `0, 5, 5, 5, 10` both have a range of 10, but their internal distributions differ.

### Q10. When should range be preferred over standard deviation?

**Answer:** Range can be useful when a quick, simple description of the extreme spread is needed. Standard deviation is usually more informative when we want a measure based on deviations of all observations from the mean.

---

## 13. Practice Problems

Try to solve these questions before checking the answers.

### Problem 1

Calculate the range of:

`5, 10, 15, 20, 25`

### Problem 2

Calculate the range of:

`-15, -5, 0, 10, 20`

### Problem 3

A dataset contains:

`7, 7, 7, 7, 7`

What is its range?

### Problem 4

The daily temperatures recorded in a city are:

`22, 25, 28, 30, 35`

Calculate the temperature range.

### Problem 5

Dataset A is:

`10, 20, 30, 40, 50`

Dataset B is:

`10, 20, 30, 40, 500`

Calculate the range of both datasets. Explain the difference.

### Problem 6

Two datasets have the same minimum and maximum values. Must they have the same standard deviation?

Explain your answer.

### Problem 7

A feature has a minimum value of 10 and a maximum value of 50. Use min-max scaling to transform the value 30 into the interval from 0 to 1.

### Problem 8

Why might the IQR be preferred over range when a dataset contains extreme outliers?

---

## 14. Practice Problem Answers

### Answer 1

Minimum = 5

Maximum = 25

$$
\text{Range} = 25 - 5 = 20
$$

### Answer 2

Minimum = -15

Maximum = 20

$$
\text{Range} = 20 - (-15) = 35
$$

### Answer 3

Minimum = 7

Maximum = 7

$$
\text{Range} = 7 - 7 = 0
$$

### Answer 4

Minimum temperature = 22°C

Maximum temperature = 35°C

$$
\text{Range} = 35 - 22 = 13^\circ C
$$

### Answer 5

Dataset A:

$$
\text{Range}_A = 50 - 10 = 40
$$

Dataset B:

$$
\text{Range}_B = 500 - 10 = 490
$$

The range increases from 40 to 490 because the maximum value changes from 50 to 500.

### Answer 6

No. The minimum and maximum values determine the range, but the standard deviation depends on all observations and their deviations from the mean.

Two datasets can have the same minimum and maximum values but different standard deviations.

### Answer 7

The min-max scaling formula is:

$$
x' = \frac{x-x_{\min}}{x_{\max}-x_{\min}}
$$

Substituting the values:

$$
x' = \frac{30-10}{50-10}
$$

$$
x' = \frac{20}{40} = 0.5
$$

The scaled value is 0.5.

### Answer 8

The IQR focuses on the middle 50% of the observations and is less sensitive to extreme minimum or maximum values. It can therefore provide a more robust description of the spread of the central part of a dataset.

---

## 15. Key Takeaways

- Range is the difference between the maximum and minimum observations.
- The formula is:

$$
\text{Range} = X_{\max} - X_{\min}
$$

- Range is a measure of dispersion, not central tendency.
- It is easy to calculate but highly sensitive to outliers.
- A range of zero means all observations have the same value.
- The IQR describes the spread of the middle 50% and is more robust to extreme values.
- Variance and standard deviation use information from all observations.
- In machine learning, the range is used in min-max scaling.
- Extreme values can strongly affect min-max scaling, so investigate outliers and fit preprocessing steps on training data only.
- **Interview rule:** Use range for a quick summary of extreme spread, but do not rely on it alone to understand the full variability of a dataset.
