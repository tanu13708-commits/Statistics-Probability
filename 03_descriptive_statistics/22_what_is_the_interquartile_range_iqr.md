# 22. What Is the Interquartile Range (IQR)?

## 1. Introduction

The **Interquartile Range (IQR)** is a statistical measure that describes the spread of the middle 50% of a dataset.

It is calculated as the difference between the third quartile and the first quartile.

$$
\mathrm{IQR}=Q_3-Q_1
$$

Where:

- \(Q_1\) is the first quartile, corresponding to the 25th percentile.
- \(Q_3\) is the third quartile, corresponding to the 75th percentile.

The IQR tells us how widely the middle half of the observations is distributed, without relying directly on the minimum or maximum values.

For example, consider two datasets:

**Dataset A:**

$$
10,\ 12,\ 14,\ 16,\ 18,\ 20,\ 22
$$

**Dataset B:**

$$
10,\ 11,\ 12,\ 16,\ 20,\ 25,\ 40
$$

The datasets have different patterns of spread. The IQR helps quantify the spread of their central observations.

The IQR is especially useful when a dataset contains outliers or is strongly skewed because it is generally less sensitive to extreme observations than the range, variance, and standard deviation.

---

## 2. What Are Quartiles?

To understand the IQR, we first need to understand quartiles.

Quartiles divide an ordered dataset into four parts, each containing approximately 25% of the observations.

There are three main quartiles.

### First quartile (\(Q_1\))

The first quartile is associated with the 25th percentile.

Approximately 25% of observations lie at or below this value.

### Second quartile (\(Q_2\))

The second quartile is the median, corresponding to the 50th percentile.

It divides the ordered dataset into two halves under the chosen median convention.

### Third quartile (\(Q_3\))

The third quartile is associated with the 75th percentile.

Approximately 75% of observations lie at or below this value.

The relationship is:

$$
Q_1=P_{25}
$$

$$
Q_2=P_{50}=\mathrm{Median}
$$

$$
Q_3=P_{75}
$$

The IQR measures the numerical distance between \(Q_1\) and \(Q_3\).

**Important:** Quartile values can differ slightly depending on the calculation convention used by a textbook or software library. For consistency, always use one convention throughout a calculation.

---

## 3. Formula for the Interquartile Range

The formula for the IQR is:

$$
\mathrm{IQR}=Q_3-Q_1
$$

Where:

- \(\mathrm{IQR}\) = interquartile range
- \(Q_3\) = third quartile
- \(Q_1\) = first quartile

### Example

Suppose a dataset has:

$$
Q_1=20
$$

$$
Q_3=50
$$

Then:

$$
\mathrm{IQR}=50-20
$$

$$
\boxed{\mathrm{IQR}=30}
$$

This means that the middle 50% of the dataset spans an interval of 30 units.

The IQR is a measure of spread, not a count of observations.

---

## 4. Step-by-Step Example: Calculating the IQR

Consider the following sorted dataset:

$$
2,\ 4,\ 6,\ 8,\ 10,\ 12,\ 14,\ 16,\ 18
$$

We will use the **median-of-halves method**, excluding the overall median from the lower and upper halves when the dataset has an odd number of observations.

Other quartile conventions may give different answers for some datasets.

### Step 1: Find the median

There are nine observations, so the fifth observation is the median.

$$
Q_2=10
$$

### Step 2: Find the lower half

Exclude the median and take the values below it:

$$
2,\ 4,\ 6,\ 8
$$

The median of the lower half is the average of \(4\) and \(6\).

$$
Q_1=\frac{4+6}{2}
$$

$$
Q_1=5
$$

### Step 3: Find the upper half

Exclude the median and take the values above it:

$$
12,\ 14,\ 16,\ 18
$$

The median of the upper half is the average of \(14\) and \(16\).

$$
Q_3=\frac{14+16}{2}
$$

$$
Q_3=15
$$

### Step 4: Calculate the IQR

$$
\mathrm{IQR}=Q_3-Q_1
$$

$$
\mathrm{IQR}=15-5
$$

$$
\boxed{\mathrm{IQR}=10}
$$

**Final answer:** The interquartile range is \(10\).

Interpretation: The middle 50% of the dataset spans 10 units, from \(Q_1=5\) to \(Q_3=15\).

---

## 5. Example with an Even Number of Observations

Consider the sorted dataset:

$$
3,\ 5,\ 7,\ 9,\ 11,\ 13,\ 15,\ 17
$$

There are eight observations.

We will again use the median-of-halves method.

### Step 1: Find the lower half

$$
3,\ 5,\ 7,\ 9
$$

The lower quartile is:

$$
Q_1=\frac{5+7}{2}=6
$$

### Step 2: Find the upper half

$$
11,\ 13,\ 15,\ 17
$$

The upper quartile is:

$$
Q_3=\frac{13+15}{2}=14
$$

### Step 3: Calculate the IQR

$$
\mathrm{IQR}=14-6
$$

$$
\boxed{\mathrm{IQR}=8}
$$

The middle 50% of the dataset spans 8 units.

---

## 6. Why Is the IQR Important?

The IQR is useful because it focuses on the central portion of the data rather than the extremes.

### 6.1 It is less sensitive to outliers

Consider the datasets:

**Dataset A:**

$$
10,\ 12,\ 14,\ 16,\ 18
$$

**Dataset B:**

$$
10,\ 12,\ 14,\ 16,\ 100
$$

The maximum value in Dataset B is much larger than the other observations.

This causes the range to increase dramatically.

However, the IQR focuses on the first and third quartiles, so it is generally less affected by extreme minimum or maximum values than the range.

### 6.2 It describes the spread of the middle 50%

The range describes the distance between the minimum and maximum values.

The IQR describes the distance between the first and third quartiles.

This makes the IQR useful when the goal is to understand the spread of typical central observations without allowing the extremes to dominate the summary.

### 6.3 It works well for skewed data

For strongly skewed distributions, the mean and standard deviation may be heavily influenced by extreme values.

The median and IQR often provide a more robust summary of central position and spread.

However, the IQR does not describe the entire distribution. Tail behavior and extreme values may still require separate analysis.

---

## 7. IQR vs. Range

The range and IQR both measure spread, but they use different parts of the dataset.

### Range

The range is the maximum minus the minimum.

$$
\mathrm{Range}=x_{\max}-x_{\min}
$$

### Interquartile range

The IQR is the third quartile minus the first quartile.

$$
\mathrm{IQR}=Q_3-Q_1
$$

### Comparison

| Feature | Range | IQR |
|---|---|---|
| Formula | Maximum minus minimum | Third quartile minus first quartile |
| Data used | Two extreme observations | Central quartile boundaries |
| Sensitivity to outliers | High | Generally lower |
| What it describes | Full observed span | Spread of the middle 50% |
| Main limitation | Can be dominated by extremes | Does not describe the tails fully |

### Example

Consider:

$$
1,\ 2,\ 3,\ 4,\ 5,\ 6,\ 7,\ 100
$$

The range is:

$$
\mathrm{Range}=100-1=99
$$

The range is dominated by the extreme value \(100\).

The IQR focuses on the middle of the distribution and is less directly affected by this maximum.

The exact numerical IQR depends on the quartile convention used.

---

## 8. IQR vs. Variance and Standard Deviation

Variance and standard deviation are also measures of spread, but they differ from the IQR in important ways.

| Feature | IQR | Variance | Standard deviation |
|---|---|---|---|
| Based on | First and third quartiles | Squared deviations from the mean | Square root of variance |
| Units | Original units | Squared original units | Original units |
| Sensitivity to outliers | Generally lower | High | High |
| Measures | Width of the middle 50% | Average squared deviation, using the appropriate denominator | Spread in original units |
| Common uses | Robust summaries and outlier screening | Statistical calculations and modeling | Descriptive statistics and modeling |

### Example

Suppose a dataset has a large extreme value.

Variance and standard deviation may increase substantially because the extreme value can contribute a large squared deviation from the mean.

The IQR may change little if the extreme value does not materially affect the quartile boundaries.

This is why the IQR is often preferred alongside the median when summarizing skewed data.

---

## 9. Using the IQR to Detect Potential Outliers

A common method for identifying potential outliers is the **1.5 times IQR rule**.

First, calculate:

$$
\mathrm{IQR}=Q_3-Q_1
$$

Then calculate the lower fence:

$$
L=Q_1-1.5(\mathrm{IQR})
$$

And the upper fence:

$$
U=Q_3+1.5(\mathrm{IQR})
$$

Observations below the lower fence or above the upper fence are flagged as potential outliers.

### Step-by-step example

Suppose:

$$
Q_1=20
$$

$$
Q_3=40
$$

### Step 1: Calculate the IQR

$$
\mathrm{IQR}=40-20=20
$$

### Step 2: Calculate the lower fence

$$
L=20-1.5(20)
$$

$$
L=20-30=-10
$$

### Step 3: Calculate the upper fence

$$
U=40+1.5(20)
$$

$$
U=40+30=70
$$

### Step 4: Interpret the fences

The fences are:

$$
L=-10,\qquad U=70
$$

Therefore:

- An observation below \(-10\) is flagged as a potential lower outlier.
- An observation above \(70\) is flagged as a potential upper outlier.
- An observation equal to a fence is not beyond it.

### Important distinction: Fences vs. whiskers

The lower and upper fences are thresholds, not necessarily observed data values.

In a common box plot convention, the whiskers extend to the most extreme observed values that remain within the fences. Values beyond the fences are shown separately as potential outliers.

Other plotting conventions may use different whisker definitions.

### Are potential outliers always errors?

No. An observation outside an IQR fence may be:

- A data-entry error
- A measurement error
- A rare but valid event
- A member of a different population
- An important extreme observation

The IQR rule is a screening tool. Investigate the data before removing or changing observations.

---

## 10. The IQR and Box Plots

A box plot, or box-and-whisker plot, is a graphical representation of a distribution using quartiles.

A typical box plot contains:

- First quartile, \(Q_1\)
- Median, \(Q_2\)
- Third quartile, \(Q_3\)
- A box extending from \(Q_1\) to \(Q_3\)
- Whiskers that follow the selected plotting convention
- Individual markers for potential outliers in many implementations

The box length represents the IQR.

$$
\mathrm{Box\ length}=Q_3-Q_1=\mathrm{IQR}
$$

### How to interpret a box plot

**Long box:** The middle 50% of the data is spread across a wider interval.

**Short box:** The middle 50% is concentrated within a narrower interval.

**Median near the center of the box:** The two halves of the middle 50% have similar numerical widths.

**Median closer to one edge:** The middle portions may have different spreads, suggesting asymmetry.

**Long whiskers:** The observations beyond the quartile boundaries extend farther under the chosen whisker convention.

Box plots are especially useful when comparing the spread of several groups, such as exam scores across classes or response times across servers.

---

## 11. Relationship Between the IQR and Percentiles

The IQR is based on two percentiles:

$$
Q_1=P_{25}
$$

$$
Q_3=P_{75}
$$

Therefore:

$$
\mathrm{IQR}=P_{75}-P_{25}
$$

The IQR is the difference between the 75th and 25th percentile values.

It describes the numerical width of the central half of the distribution.

### Example

Suppose:

$$
P_{25}=35
$$

$$
P_{75}=65
$$

Then:

$$
\mathrm{IQR}=65-35=30
$$

The middle 50% spans 30 units.

### Does the IQR tell us where the data are centered?

Not by itself.

Two datasets may have the same IQR but different medians.

For example:

- Dataset A may have \(Q_1=10\), median \(20\), and \(Q_3=30\).
- Dataset B may have \(Q_1=100\), median \(110\), and \(Q_3=120\).

Both have:

$$
\mathrm{IQR}=20
$$

However, Dataset B is located much higher on the number line.

For a fuller summary, report the median and IQR together.

---

## 12. Applications of the IQR in Machine Learning

The IQR is useful in several machine learning and data analysis tasks.

### 12.1 Exploratory data analysis

The IQR helps describe numerical features during initial data exploration.

Analysts often inspect:

- Minimum and maximum
- Mean and median
- First and third quartiles
- IQR
- Variance and standard deviation
- Potential outliers

This helps identify skewness, spread, unusual observations, and possible data-quality issues.

### 12.2 Robust feature scaling

Standard scaling commonly uses the mean and standard deviation.

However, those statistics can be influenced by extreme observations.

A robust scaling transformation uses the median and IQR:

$$
x_{\mathrm{scaled}}=\frac{x-\mathrm{Median}(X)}{\mathrm{IQR}(X)}
$$

Equivalently:

$$
x_{\mathrm{scaled}}=\frac{x-Q_2}{Q_3-Q_1}
$$

This centers the feature around its median and scales it using the middle 50% spread.

It can be useful when features contain extreme values.

**Important:** If the IQR is zero, this transformation involves division by zero. A preprocessing pipeline must handle such features explicitly.

### 12.3 Outlier screening

The IQR rule can flag extreme feature values before modeling.

Potentially unusual values can then be investigated to determine whether they represent data errors or legitimate behavior.

Automatically removing every flagged value is not recommended because unusual observations may contain useful information.

### 12.4 Comparing distributions across groups

The IQR can be used to compare features across customer groups, product categories, or model classes.

For example, comparing the IQR of transaction values between two customer groups can show which group has a wider spread in its middle 50%.

### 12.5 Monitoring model errors

The IQR of prediction errors can help summarize how widely the middle half of errors is distributed.

For absolute errors, a high IQR indicates that the middle 50% of absolute errors spans a wider range.

It should be interpreted alongside measures such as median absolute error, mean absolute error, and tail percentiles.

### 12.6 Monitoring system latency

In production systems, the IQR of response times can indicate how variable the central portion of request latency is.

However, high-percentile latency, such as the 95th or 99th percentile, should also be monitored because the IQR alone does not describe the extreme slow tail.

### 12.7 Avoiding data leakage

If IQR-based scaling is used in a predictive model, estimate the median and IQR from the training data only.

Then apply the same learned values to validation and test data.

Calculating preprocessing statistics from the entire dataset can leak information from evaluation data into the training process.

---

## 13. Limitations of the IQR

Although the IQR is useful, it has several limitations.

### 13.1 It ignores the outer 50% when measuring spread

The IQR focuses on the middle 50% of observations.

It does not directly describe how widely the lowest 25% or highest 25% are distributed.

### 13.2 It does not describe the entire distribution

Two datasets can have the same IQR but differ in skewness, clustering, and tail behavior.

Therefore, the IQR should not be used as the only measure of distribution shape.

### 13.3 It depends on the quartile convention

Different quartile algorithms can return different \(Q_1\) and \(Q_3\) values, especially for small datasets.

Consequently, the calculated IQR can also differ.

### 13.4 It can be zero for a variable that is not constant

If many observations have the same value, both quartiles may be equal even though some observations differ.

For example, a dataset containing many zeros and a few large positive values can have:

$$
Q_1=Q_3=0
$$

Therefore:

$$
\mathrm{IQR}=0
$$

This does not necessarily mean that every observation is identical.

### 13.5 The IQR rule may flag valid observations

The \(1.5\times\mathrm{IQR}\) rule is a convention for screening potential outliers. It is not a formal guarantee that all flagged observations are erroneous.

### 13.6 It is not a measure of variability in squared units

Unlike variance, the IQR is measured in the same units as the original data.

This is often an advantage for interpretation, but the IQR does not replace variance in calculations that specifically require squared deviations.

---

## 14. Common Mistakes

### Mistake 1: Reversing the quartiles

The correct formula is:

$$
\mathrm{IQR}=Q_3-Q_1
$$

Since \(Q_3\) is at or above \(Q_1\), the IQR should be nonnegative.

### Mistake 2: Confusing the IQR with the range

The range is maximum minus minimum, while the IQR is third quartile minus first quartile.

$$
\mathrm{Range}=x_{\max}-x_{\min}
$$

$$
\mathrm{IQR}=Q_3-Q_1
$$

### Mistake 3: Assuming the IQR is the middle 50% of observations

The IQR is the numerical width of the interval from \(Q_1\) to \(Q_3\). The observations between those quartiles constitute approximately the middle 50%.

### Mistake 4: Assuming the IQR must be positive

The IQR cannot be negative, but it can be zero when the first and third quartiles are equal.

### Mistake 5: Treating IQR fences as actual data values

Fences are calculated thresholds. They do not have to match any observed value.

### Mistake 6: Removing all observations beyond the fences

Values beyond the fences are potential outliers, not automatically errors. Review them in context.

### Mistake 7: Ignoring the quartile convention

For exact numerical answers, use the requested quartile method. Different methods may produce different values.

### Mistake 8: Assuming the IQR reveals skewness by itself

A large or small IQR indicates spread, not necessarily skewness. Compare the median's position within the quartiles, inspect the tails, or use a plot to assess distribution shape.

### Mistake 9: Using IQR scaling without handling zero IQR

If \(Q_3=Q_1\), dividing by the IQR is undefined. Handle the feature appropriately in preprocessing.

### Mistake 10: Calculating IQR-based preprocessing statistics before splitting the data

Fit the median and IQR on the training data only, then reuse those values for validation and test data.

---

## 15. Frequently Asked Interview Questions

### Q1. What is the interquartile range?

The IQR is a measure of spread that describes the width of the middle 50% of a dataset.

$$
\mathrm{IQR}=Q_3-Q_1
$$

### Q2. What do \(Q_1\) and \(Q_3\) represent?

\(Q_1\) is the first quartile, associated with the 25th percentile. \(Q_3\) is the third quartile, associated with the 75th percentile.

### Q3. Why is the IQR useful?

It provides a summary of the central spread that is generally less sensitive to extreme observations than the range, variance, and standard deviation.

### Q4. Can the IQR be negative?

No. Under a consistently defined quartile method, \(Q_3\) is at or above \(Q_1\), so the IQR is nonnegative.

### Q5. Can the IQR be zero?

Yes. If \(Q_1=Q_3\), then the IQR is zero. Some observations may still differ if the distribution contains many tied values.

### Q6. How is the IQR used to identify potential outliers?

Calculate the lower and upper fences:

$$
L=Q_1-1.5\mathrm{IQR}
$$

$$
U=Q_3+1.5\mathrm{IQR}
$$

Observations outside the fences are flagged for further investigation.

### Q7. Is the IQR better than standard deviation?

Neither measure is universally better. The IQR is often more robust to extreme values, while standard deviation is useful for mathematical modeling and distributions where squared deviations are relevant.

### Q8. What is the difference between IQR and range?

The range uses the minimum and maximum. The IQR uses the first and third quartiles and measures the spread of the middle 50%.

### Q9. How does the IQR relate to percentiles?

The IQR is the difference between the 75th and 25th percentile values.

$$
\mathrm{IQR}=P_{75}-P_{25}
$$

### Q10. Can two datasets have the same IQR but different distributions?

Yes. The IQR summarizes only the width of the middle 50%. It does not uniquely determine the distribution's shape or tails.

### Q11. Why is the IQR used in box plots?

The box in a standard box plot extends from \(Q_1\) to \(Q_3\), so its length represents the IQR. The plot also displays the median and often marks potential outliers.

### Q12. How is the IQR used in robust scaling?

A feature can be centered by its median and divided by its IQR:

$$
x_{\mathrm{scaled}}=\frac{x-\mathrm{Median}(X)}{\mathrm{IQR}(X)}
$$

This makes the transformation less sensitive to extreme observations than scaling based on the mean and standard deviation.

### Q13. Are all observations outside the IQR fences errors?

No. They are flagged as potential outliers and require investigation.

### Q14. Why might different libraries calculate different IQR values?

They may use different quartile or percentile conventions, particularly for small datasets.

### Q15. Does the IQR measure the full spread of a dataset?

No. It measures the spread between the first and third quartiles, covering the middle 50%. It does not directly describe the full range or tail spread.

### Q16. How is IQR useful in machine learning?

It is useful for exploratory analysis, robust scaling, potential outlier screening, distribution comparisons, and monitoring the spread of prediction errors.

### Q17. What happens to the IQR if a constant is added to every observation?

Both quartiles increase by that constant, so their difference remains unchanged.

If \(Y=X+c\), then:

$$
\mathrm{IQR}(Y)=\mathrm{IQR}(X)
$$

### Q18. What happens to the IQR if every observation is multiplied by a constant?

For a constant \(a\):

$$
\mathrm{IQR}(aX)=|a|\mathrm{IQR}(X)
$$

Multiplication by a negative constant reverses the ordering, which is why the absolute value appears.

### Q19. Is the IQR affected by the units of measurement?

Yes, it scales with the units. Converting meters to centimeters multiplies the IQR by \(100\).

### Q20. What should you check before using IQR-based scaling?

Check whether the IQR is zero or very small, choose an appropriate preprocessing strategy, and fit the median and IQR on the training data only.

---

## 16. Practice Problems

Try solving these problems before reading the answers.

### Problem 1: Calculate the IQR

Suppose:

$$
Q_1=18,\qquad Q_3=42
$$

Calculate the IQR.

### Problem 2: Calculate the fences

Suppose:

$$
Q_1=15,\qquad Q_3=35
$$

Calculate the lower and upper fences using the \(1.5\times\mathrm{IQR}\) rule.

### Problem 3: Identify potential outliers

Using the fences from Problem 2, determine whether \(70\) is flagged as a potential outlier.

### Problem 4: Interpret the IQR

A dataset has an IQR of \(12\). What does this tell you about the middle 50% of the data?

### Problem 5: Compare two datasets

Dataset A has an IQR of \(5\), and Dataset B has an IQR of \(20\). Which dataset has the wider central 50% spread?

### Problem 6: Effect of adding a constant

If the IQR of \(X\) is \(8\), what is the IQR of \(Y=X+100\)?

### Problem 7: Effect of scaling

If the IQR of \(X\) is \(6\), calculate the IQR of \(Y=3X\).

### Problem 8: Negative scaling

If the IQR of \(X\) is \(10\), calculate the IQR of \(Y=-2X+5\).

### Problem 9: IQR vs. range

Why can a dataset have a very large range but a relatively small IQR?

### Problem 10: Robust scaling

A feature has a median of \(40\), first quartile of \(30\), third quartile of \(50\), and observation \(x=60\).

Calculate its median-and-IQR scaled value.

### Problem 11: Zero IQR

Can a dataset have an IQR of zero while still containing different values? Explain briefly.

### Problem 12: Machine learning workflow

You want to use median-and-IQR scaling before training a model. When should you estimate the median and IQR to avoid data leakage?

---

## 17. Practice Problem Answers

### Answer 1

$$
\mathrm{IQR}=Q_3-Q_1
$$

$$
\mathrm{IQR}=42-18=24
$$

### Answer 2

First calculate the IQR:

$$
\mathrm{IQR}=35-15=20
$$

Lower fence:

$$
L=15-1.5(20)=-15
$$

Upper fence:

$$
U=35+1.5(20)=65
$$

### Answer 3

The value \(70\) is greater than the upper fence of \(65\).

Therefore, it is flagged as a potential outlier by the \(1.5\times\mathrm{IQR}\) rule.

### Answer 4

The middle 50% of observations spans an interval of 12 units between the first and third quartiles.

### Answer 5

Dataset B has the wider central spread because its IQR is \(20\), compared with \(5\) for Dataset A.

### Answer 6

Adding a constant shifts both quartiles by the same amount, leaving their difference unchanged.

$$
\mathrm{IQR}(X+100)=\mathrm{IQR}(X)=8
$$

### Answer 7

For a positive scaling factor \(a\):

$$
\mathrm{IQR}(aX)=|a|\mathrm{IQR}(X)
$$

Therefore:

$$
\mathrm{IQR}(3X)=3\times6=18
$$

### Answer 8

For a transformation \(Y=aX+b\):

$$
\mathrm{IQR}(aX+b)=|a|\mathrm{IQR}(X)
$$

Here, \(a=-2\).

$$
\mathrm{IQR}(Y)=|-2|\times10=20
$$

Adding \(5\) does not change the IQR.

### Answer 9

The range depends only on the minimum and maximum, so a single extreme observation can make it very large. The IQR focuses on the central 50% and is less sensitive to extreme values outside that region.

### Answer 10

Calculate the IQR:

$$
\mathrm{IQR}=50-30=20
$$

Apply median-and-IQR scaling:

$$
x_{\mathrm{scaled}}=\frac{60-40}{20}
$$

$$
x_{\mathrm{scaled}}=1
$$

### Answer 11

Yes. If many observations have the same value, both quartiles may equal that value even though some observations in the tails differ.

For example, a dataset with many zeros and a few large positive values can have an IQR of zero, depending on the quartile convention.

### Answer 12

Estimate the median and IQR using the training data only. Apply the same learned values to validation and test data.

---

## 18. Quick Revision Notes

- IQR stands for **Interquartile Range**.
- It measures the spread of the middle 50% of a dataset.
- The formula is \(Q_3-Q_1\).
- \(Q_1\) corresponds to the 25th percentile.
- \(Q_3\) corresponds to the 75th percentile.
- The IQR is nonnegative and can equal zero.
- It is generally less sensitive to outliers than range, variance, and standard deviation.
- The common outlier fences are \(Q_1-1.5\mathrm{IQR}\) and \(Q_3+1.5\mathrm{IQR}\).
- Observations beyond those fences are potential outliers, not necessarily errors.
- The IQR is the width of the box in a standard box plot.
- Median-and-IQR scaling can help when features contain extreme values.
- Adding a constant does not change the IQR.
- Multiplying by \(a\) changes the IQR by a factor of \(|a|\).
- In machine learning, fit preprocessing statistics on training data only.
- Quartile conventions can affect exact calculations.

---

## 19. Final Summary

The interquartile range is a robust measure of spread that describes the numerical width of the middle 50% of a dataset.

Its main formula is:

$$
\mathrm{IQR}=Q_3-Q_1
$$

The IQR is useful for describing central variability, comparing distributions, constructing box plots, screening for potential outliers, and performing robust feature scaling.

The commonly used outlier fences are:

$$
L=Q_1-1.5\mathrm{IQR}
$$

$$
U=Q_3+1.5\mathrm{IQR}
$$

Observations beyond these fences should be investigated rather than automatically removed.

For statistics interviews, remember the key distinction: **the range measures the full observed span, while the IQR measures the spread between the first and third quartiles.** The IQR is generally less sensitive to extreme values and is especially useful when summarizing skewed data.

