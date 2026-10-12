# 21. What Are Percentiles and Quartiles?

## 1. Introduction

Percentiles and quartiles are statistical measures used to understand the distribution of data. They describe the relative position of observations within a dataset and help us understand how data values are spread out.

They are useful for answering questions such as:

- What percentage of observations fall below a particular value?
- What score separates the lowest 25% of students from the rest?
- What is the median of a dataset?
- How can we identify unusually low or high observations?
- How can we summarize a dataset without relying only on its mean?
- How are percentiles and quartiles used in data analysis and machine learning?

For example, if a student's exam score is at the 90th percentile, the student performed at or above approximately 90% of the comparison group under a common percentile interpretation. The exact interpretation depends on the percentile convention and how ties are handled.

Percentiles and quartiles are closely related:

- **Percentiles** divide a distribution into 100 equal-proportion parts.
- **Quartiles** divide a distribution into four equal-proportion parts.

Both are positional measures that help describe the distribution of data.

---

## 2. What Is a Percentile?

A **percentile** is a value that indicates a position in a distribution. The \(p\)-th percentile is commonly interpreted as a value at or below which approximately \(p\%\) of the observations fall.

For example:

- The 10th percentile is a value below which approximately 10% of observations fall.
- The 25th percentile is a value below which approximately 25% of observations fall.
- The 50th percentile is the median.
- The 75th percentile is a value below which approximately 75% of observations fall.
- The 90th percentile is a value below which approximately 90% of observations fall.

The exact calculated percentile can vary depending on the convention used, particularly for small datasets.

### 2.1 Example

Suppose the sorted exam scores are:

$$
40,\ 50,\ 55,\ 60,\ 65,\ 70,\ 75,\ 80,\ 85,\ 90
$$

A percentile identifies a position in this distribution.

For example, the 50th percentile is the median. Because there are ten observations, the median is the average of the fifth and sixth observations:

$$
P_{50}=\frac{65+70}{2}=67.5
$$

Thus, the median is \(67.5\).

To calculate the 25th or 75th percentile, we must choose a percentile convention. Different software packages may return different values because they use different interpolation rules.

---

## 3. How to Calculate Percentiles

There is no single calculation convention used by every statistical tool. Several methods are common, so it is important to understand which method is being used.

One introductory method uses the following rank formula for a dataset sorted in ascending order:

$$
r=\frac{p}{100}(n+1)
$$

Where:

- \(r\) = rank or position
- \(p\) = desired percentile
- \(n\) = number of observations

This is one convention, not a universal percentile formula.

### 3.1 Steps for calculating a percentile

1. Sort the observations in ascending order.
2. Identify the number of observations, \(n\).
3. Choose the desired percentile, \(p\).
4. Calculate the rank using the selected convention.
5. If the rank is an integer, use the corresponding observation.
6. If the rank lies between two observations, interpolate according to the convention.

### 3.2 Example using the rank formula

Consider the sorted dataset:

$$
10,\ 20,\ 30,\ 40,\ 50,\ 60,\ 70,\ 80,\ 90
$$

There are nine observations.

Find the 25th percentile using:

$$
r=\frac{p}{100}(n+1)
$$

Substitute \(p=25\) and \(n=9\):

$$
r=\frac{25}{100}(9+1)
$$

$$
r=0.25\times10=2.5
$$

The rank is \(2.5\), halfway between the second and third observations.

The second observation is \(20\), and the third observation is \(30\).

Using linear interpolation:

$$
P_{25}=20+0.5(30-20)
$$

$$
P_{25}=20+5=25
$$

Therefore, under this convention:

$$
P_{25}=25
$$

**Important:** This result is specific to the \(r=(p/100)(n+1)\) convention. Other methods, including the default methods in some programming libraries, can produce different percentile values.

### 3.3 What if the rank is not an integer?

Suppose a calculation gives rank \(r=3.4\).

Under a linear-interpolation convention, this means moving 40% of the distance from the third observation to the fourth observation.

If those observations are \(x_3\) and \(x_4\), then:

$$
P=x_3+0.4(x_4-x_3)
$$

Interpolation estimates a percentile between observed values. It does not mean that the interpolated value must appear in the original dataset.

---

## 4. What Are Quartiles?

**Quartiles divide an ordered dataset into four parts, each containing approximately 25% of the observations.**

There are three principal quartiles:

- **First quartile (\(Q_1\))**: the 25th percentile.
- **Second quartile (\(Q_2\))**: the 50th percentile, or median.
- **Third quartile (\(Q_3\))**: the 75th percentile.

These definitions describe their intended positions. The exact numerical values depend on the quartile calculation convention.

### 4.1 First quartile (\(Q_1\))

The first quartile is associated with the 25th percentile.

Approximately 25% of observations lie at or below \(Q_1\).

### 4.2 Second quartile (\(Q_2\))

The second quartile is the median, or 50th percentile.

It divides the ordered data into two halves under the chosen median convention.

### 4.3 Third quartile (\(Q_3\))

The third quartile is associated with the 75th percentile.

Approximately 75% of observations lie at or below \(Q_3\).

### 4.4 Visual interpretation

Imagine a dataset represented by a number line:

- The first quarter of the distribution lies below \(Q_1\).
- The next quarter lies between \(Q_1\) and \(Q_2\).
- The next quarter lies between \(Q_2\) and \(Q_3\).
- The final quarter lies above \(Q_3\).

The intervals do not necessarily have equal widths. Quartiles divide the data by relative position, not by equal numerical distances.

For example, if \(Q_1=20\), \(Q_2=30\), and \(Q_3=70\), the distance from \(Q_2\) to \(Q_3\) is much larger than the distance from \(Q_1\) to \(Q_2\). This indicates that the upper middle portion of the data spans a wider numerical range.

---

## 5. Relationship Between Percentiles and Quartiles

Quartiles are special percentiles.

| Quartile | Percentile | Interpretation |
|---|---:|---|
| \(Q_1\) | 25th percentile | Lower quarter boundary |
| \(Q_2\) | 50th percentile | Median |
| \(Q_3\) | 75th percentile | Upper quarter boundary |

The relationships are:

$$
Q_1=P_{25}
$$

$$
Q_2=P_{50}=\text{Median}
$$

$$
Q_3=P_{75}
$$

This means quartiles are not separate from percentiles. They are specific points in the percentile system.

### How many parts do they create?

- Percentiles use 99 internal cut points to create up to 100 percentile intervals.
- Quartiles use three internal cut points to create four quarters.

Ties and repeated values can mean that the groups do not contain exactly equal numbers of observations.

---

## 6. Step-by-Step Example: Calculate Quartiles

Consider the following sorted dataset:

$$
2,\ 4,\ 6,\ 8,\ 10,\ 12,\ 14,\ 16,\ 18
$$

There are nine observations.

For this example, we will use the **median-of-halves method**, excluding the overall median from each half when the number of observations is odd.

Other quartile conventions can produce different answers for some datasets.

### Step 1: Find the median (\(Q_2\))

There are nine observations, so the fifth observation is the median.

$$
Q_2=10
$$

### Step 2: Find the lower half

Exclude the median and take the observations below it:

$$
2,\ 4,\ 6,\ 8
$$

The lower half contains four observations.

Its median is the average of the second and third observations:

$$
Q_1=\frac{4+6}{2}
$$

$$
Q_1=5
$$

### Step 3: Find the upper half

Exclude the median and take the observations above it:

$$
12,\ 14,\ 16,\ 18
$$

The upper half also contains four observations.

Its median is:

$$
Q_3=\frac{14+16}{2}
$$

$$
Q_3=15
$$

### Final result

$$
Q_1=5,\qquad Q_2=10,\qquad Q_3=15
$$

Interpretation:

- \(Q_1=5\) is the lower quartile boundary.
- \(Q_2=10\) is the median.
- \(Q_3=15\) is the upper quartile boundary.

Under this method, the first and third quartiles are the medians of the lower and upper halves, respectively.

---

## 7. Quartiles for an Even Number of Observations

Consider the sorted dataset:

$$
3,\ 5,\ 7,\ 9,\ 11,\ 13,\ 15,\ 17
$$

There are eight observations.

For this example, use the median-of-halves method.

### Step 1: Find the overall median

The two middle observations are \(9\) and \(11\).

$$
Q_2=\frac{9+11}{2}=10
$$

### Step 2: Find the lower quartile

The lower half is:

$$
3,\ 5,\ 7,\ 9
$$

Its median is:

$$
Q_1=\frac{5+7}{2}=6
$$

### Step 3: Find the upper quartile

The upper half is:

$$
11,\ 13,\ 15,\ 17
$$

Its median is:

$$
Q_3=\frac{13+15}{2}=14
$$

Therefore:

$$
Q_1=6,\qquad Q_2=10,\qquad Q_3=14
$$

---

## 8. What Is the Interquartile Range (IQR)?

The **interquartile range (IQR)** measures the spread of the middle 50% of the data.

It is the difference between the third quartile and the first quartile.

$$
\mathrm{IQR}=Q_3-Q_1
$$

Where:

- \(Q_1\) is the first quartile.
- \(Q_3\) is the third quartile.

The IQR excludes the lowest quarter and the highest quarter of the ordered data, focusing on the central half.

### Example

Suppose:

$$
Q_1=15
$$

$$
Q_3=35
$$

Then:

$$
\mathrm{IQR}=35-15=20
$$

The middle 50% of the data spans 20 units.

The IQR is often more robust to extreme observations than the range, variance, and standard deviation because it depends on the middle part of the distribution.

### Important distinction

The IQR measures the width of the central 50% of the distribution. It does not tell us the exact positions of all observations within that interval.

---

## 9. Detecting Potential Outliers Using Quartiles

Quartiles and the IQR are commonly used in the boxplot rule for flagging potential outliers.

First calculate:

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

Observations below \(L\) or above \(U\) are flagged as potential outliers under this rule.

### Example

Suppose:

$$
Q_1=20
$$

$$
Q_3=40
$$

Calculate the IQR:

$$
\mathrm{IQR}=40-20=20
$$

Calculate the lower fence:

$$
L=20-1.5(20)
$$

$$
L=20-30=-10
$$

Calculate the upper fence:

$$
U=40+1.5(20)
$$

$$
U=40+30=70
$$

Therefore:

- Values below \(-10\) are flagged as potential lower outliers.
- Values above \(70\) are flagged as potential upper outliers.

An observation equal to a fence is not beyond that fence, so it is not flagged by the strict rule.

### Are all flagged observations errors?

No. A flagged observation may be:

- A data-entry mistake
- A measurement error
- A rare but valid observation
- A member of a different population or subgroup
- A meaningful extreme event

The IQR rule is a screening technique, not proof that an observation is incorrect.

---

## 10. What Is a Box Plot?

A box plot, also called a box-and-whisker plot, summarizes a distribution using quartiles and related values.

A typical box plot displays:

1. The minimum or lower whisker endpoint, depending on the plotting convention
2. The first quartile (\(Q_1\))
3. The median (\(Q_2\))
4. The third quartile (\(Q_3\))
5. The maximum or upper whisker endpoint, depending on the plotting convention
6. Potential outliers as individual points in many implementations

The box extends from \(Q_1\) to \(Q_3\), and the line inside the box marks the median.

The box width in a horizontal box plot represents the IQR.

### How to interpret a box plot

- **Median position:** A median closer to one side of the box may indicate asymmetry in the middle 50% of the data.
- **Box length:** A longer box indicates a larger IQR.
- **Whisker length:** Unequal whiskers may indicate differences in the spread of the lower and upper portions.
- **Outlier markers:** Points beyond the whiskers may be flagged by the plotting rule.

Box plots are particularly useful for comparing distributions across categories.

### Important note about whiskers

In some common box plot implementations, whiskers extend to the most extreme observed points within the \(1.5\times\mathrm{IQR}\) fences, and observations beyond those fences are shown separately. In other plots, whiskers may extend to the minimum and maximum.

Always check the plotting convention before interpreting whisker endpoints.

---

## 11. Percentile Rank vs. Percentile Value

These terms are related but different.

### Percentile value

The percentile value is a data value associated with a specified percentile.

For example:

- The 90th percentile of exam scores may be 88.
- This means 88 is the value associated with the 90th percentile under the chosen calculation convention.

### Percentile rank

The percentile rank describes the relative standing of a particular observation in a reference distribution.

For example, a score of 88 might have a percentile rank near 90, depending on the other scores and the percentile-rank convention.

**Remember:**

- Asking “What is the 90th percentile?” asks for a value.
- Asking “What percentile rank does this score have?” asks about the position of a particular value.

Percentile ranks can differ depending on how ties and boundary values are handled.

---

## 12. Percentiles in Real-World Applications

Percentiles are useful in many domains because they describe relative position without requiring the data to follow a normal distribution.

### 12.1 Education and examinations

Exam results may be reported using percentile ranks.

A student at a high percentile performed better than a large proportion of the reference group.

Percentiles can help compare performance when the reference group and scoring method are clearly defined.

### 12.2 Healthcare and growth charts

Growth charts may use percentiles to compare a child's height or weight with reference populations of similar age and sex.

A percentile indicates relative position within the reference distribution. It is not, by itself, a diagnosis.

Interpretation depends on the relevant reference population, measurement accuracy, and clinical context.

### 12.3 Income distribution

Economists and analysts use percentiles to describe income distribution.

For example, the 90th percentile of income is a threshold near the upper end of the distribution.

Percentiles can help compare income levels without being dominated solely by the mean.

### 12.4 Customer analytics

Businesses can use percentiles to understand:

- Spending behavior
- Purchase frequency
- Customer lifetime value
- Order sizes
- Delivery times

For example, the 95th percentile of order value helps describe the upper end of typical order values, although the precise interpretation depends on the percentile method.

### 12.5 Performance monitoring

Percentiles are often used to report response times in software systems.

For example, the 95th-percentile response time is a threshold below which approximately 95% of measured response times fall under the chosen convention.

This is useful because averages can hide slow requests in the tail of a distribution.

### 12.6 Data analysis

Percentiles help analysts summarize skewed data, compare observations with a reference group, and describe the tails of a distribution.

They are also useful for identifying threshold values for further investigation.

---

## 13. Quartiles and Percentiles in Machine Learning

Percentiles and quartiles are useful in data preprocessing, exploratory analysis, anomaly screening, and model evaluation.

### 13.1 Exploratory data analysis

Quartiles help summarize a feature's distribution.

For each numerical feature, an analyst may inspect:

- Minimum and maximum
- First quartile
- Median
- Third quartile
- IQR
- Potential outliers

This helps reveal skewness, spread, unusual values, and differences between groups.

### 13.2 Robust outlier screening

The IQR rule can flag unusually low or high feature values.

For a feature \(X\):

$$
\mathrm{IQR}(X)=Q_3(X)-Q_1(X)
$$

The common lower and upper fences are:

$$
L=Q_1(X)-1.5\mathrm{IQR}(X)
$$

$$
U=Q_3(X)+1.5\mathrm{IQR}(X)
$$

Observations outside these fences can be reviewed.

In machine learning, do not automatically remove every flagged observation. Extreme observations may represent important patterns, rare events, or the class of interest.

### 13.3 Robust scaling

Some preprocessing methods use the median and IQR instead of the mean and standard deviation.

A simple robust scaling transformation is:

$$
x_{\mathrm{scaled}}=\frac{x-Q_2}{Q_3-Q_1}
$$

Where:

- \(Q_2\) is the median.
- \(Q_3-Q_1\) is the IQR.

This transformation centers values around the median and scales them by the IQR.

It is less sensitive to extreme observations than standardization based on the mean and standard deviation, although it does not remove all effects of outliers.

If the IQR is zero, this formula involves division by zero. The feature then requires special handling, such as leaving it unchanged or using a suitable scaling rule.

### 13.4 Quantile-based discretization

Percentiles can be used to divide a numerical feature into bins.

For example, quartile-based binning attempts to create four groups with roughly equal numbers of observations.

This can be useful for exploratory analysis or certain modeling approaches.

However, repeated values may make it impossible to create four distinct intervals containing exactly equal numbers of observations.

### 13.5 Evaluating prediction latency

For a deployed machine learning system, percentile latency can help monitor user experience.

Examples include:

- Median latency
- 90th-percentile latency
- 95th-percentile latency
- 99th-percentile latency

The 99th percentile focuses on the slow tail of response times and can reveal problems that the average hides.

### 13.6 Understanding prediction errors

Percentiles of absolute prediction errors can help summarize typical and extreme model performance.

For instance, the 90th percentile of absolute errors describes a threshold below which approximately 90% of those errors fall.

This is often easier to interpret than looking only at mean squared error, especially when the goal is to understand the distribution of prediction errors.

### 13.7 Avoiding data leakage

When percentile thresholds, quartiles, or IQR values are used as preprocessing parameters in a predictive model, estimate them using the training data only.

Then apply the same learned thresholds or scaling parameters to validation and test data.

Calculating them using the full dataset can leak information from evaluation data into the training pipeline.

---

## 14. Limitations of Percentiles and Quartiles

### 14.1 Different conventions can produce different values

Several percentile and quartile algorithms are used in statistics and software libraries.

For small datasets, these methods can produce noticeably different results.

Always state the convention when exact reproducibility matters.

### 14.2 Quartiles do not describe every aspect of a distribution

Two datasets can have the same quartiles but very different shapes, clusters, or tail behavior.

Quartiles summarize important positions, but they do not describe the entire distribution.

### 14.3 Repeated values can create ties

When many observations are identical, a percentile boundary may not divide the observations into groups containing exactly the intended percentages.

### 14.4 Interpolation can produce values not observed in the data

Some methods estimate percentiles by interpolating between adjacent observations.

The resulting percentile may not be an actual observed value. This is normal for interpolation-based methods.

### 14.5 Percentiles depend on the reference group

A percentile rank has meaning relative to the group being used for comparison.

The same observation may have a different percentile rank in different populations.

### 14.6 Outlier rules are not universal

The \(1.5\times\mathrm{IQR}\) rule is a common screening technique, but it does not establish that a value is wrong or statistically impossible.

### 14.7 Quartiles can hide important tail behavior

Quartiles focus on the middle of the distribution. When rare extreme values matter, inspect tail percentiles, plots, and the underlying observations as well.

---

## 15. Common Mistakes

### Mistake 1: Confusing percentile value with percentile rank

A percentile value is a data threshold. Percentile rank describes the relative position of an observation.

### Mistake 2: Assuming the 50th percentile is always an observed value

For an even-sized dataset, the median may be the average of two middle observations. Other percentiles may also be interpolated.

### Mistake 3: Assuming all percentile methods give identical results

Different conventions can yield different numerical answers, especially for small datasets.

### Mistake 4: Forgetting to sort the data

Percentiles and quartiles are positional measures. The data generally need to be ordered before applying rank-based calculations.

### Mistake 5: Confusing the IQR with the full range

The range is maximum minus minimum. The IQR is third quartile minus first quartile.

$$
\mathrm{Range}=x_{\max}-x_{\min}
$$

$$
\mathrm{IQR}=Q_3-Q_1
$$

### Mistake 6: Assuming each quartile contains exactly 25% of the observations

Quartiles describe boundaries for equal-proportion parts in an idealized distribution. Ties and discrete values can prevent exact separation into equal-sized groups.

### Mistake 7: Removing every observation beyond an IQR fence

A potential outlier is not automatically a bad observation. Investigate its source and relevance before deciding how to handle it.

### Mistake 8: Treating a percentile as a probability for an individual

A percentile describes a position in a reference distribution. It does not necessarily mean that a particular observation has that probability of occurring.

### Mistake 9: Calculating preprocessing percentiles on the entire dataset

In a predictive modeling workflow, fit percentile-based transformations on training data only to avoid leakage.

### Mistake 10: Assuming a high percentile always means a good outcome

A high percentile is not inherently desirable. A high exam score may be good, but a high error rate or response time may be undesirable.

---

## 16. Frequently Asked Interview Questions

### Q1. What is a percentile?

A percentile is a value associated with a specified relative position in an ordered distribution. The \(p\)-th percentile is commonly interpreted as a threshold at or below which approximately \(p\%\) of observations fall.

### Q2. What are quartiles?

Quartiles divide an ordered distribution into four parts. The first quartile corresponds to the 25th percentile, the second to the 50th percentile, and the third to the 75th percentile.

### Q3. What is the difference between percentiles and quartiles?

Percentiles describe positions on a 100-part scale. Quartiles are specific percentile boundaries that divide the distribution into four parts.

### Q4. What is the second quartile?

The second quartile, \(Q_2\), is the median and corresponds to the 50th percentile.

### Q5. What is the interquartile range?

The IQR measures the width of the middle 50% of the data.

$$
\mathrm{IQR}=Q_3-Q_1
$$

### Q6. Why is the IQR useful?

The IQR is less sensitive to extreme observations than the range, variance, and standard deviation. It is useful for describing the spread of the central portion of a dataset.

### Q7. How are quartiles used to detect outliers?

Calculate the IQR, then define the common lower and upper fences:

$$
L=Q_1-1.5\mathrm{IQR}
$$

$$
U=Q_3+1.5\mathrm{IQR}
$$

Observations outside these fences are flagged as potential outliers.

### Q8. Is the 50th percentile always the mean?

No. The 50th percentile is the median. The mean and median may differ, especially in skewed distributions.

### Q9. Can the 25th percentile be greater than the 50th percentile?

For a consistently defined percentile function, percentile values are nondecreasing as the percentile level increases. Therefore, \(P_{25}\) cannot be greater than \(P_{50}\).

### Q10. Can quartiles have the same value?

Yes. In datasets with many repeated values or discrete measurements, two or more quartiles can have the same value.

### Q11. Why do percentile calculations differ between software libraries?

Different implementations may use different rank formulas, interpolation methods, or quantile definitions.

### Q12. What is the difference between range and IQR?

The range uses the minimum and maximum. The IQR uses the third and first quartiles and therefore focuses on the middle 50% of the data.

### Q13. How are percentiles used in machine learning?

They support exploratory analysis, robust scaling, quantile-based binning, anomaly screening, and evaluation of prediction errors and latency.

### Q14. What is robust scaling?

Robust scaling transforms a feature using statistics such as the median and IQR rather than the mean and standard deviation.

One common form is:

$$
x_{\mathrm{scaled}}=\frac{x-\mathrm{Median}(X)}{\mathrm{IQR}(X)}
$$

### Q15. Does the 90th percentile mean that 90% of observations are strictly below the value?

Not necessarily. Depending on the data and percentile convention, some observations may equal the percentile value. It is generally interpreted using an at-or-below convention or an approximate cumulative proportion.

### Q16. What does a high IQR indicate?

A high IQR indicates that the middle 50% of the data spans a relatively wide interval, in the units of the feature.

### Q17. Can a percentile be a decimal value not found in the dataset?

Yes. Interpolation-based methods can produce percentile values between observed data points.

### Q18. Why are percentiles useful for response times?

They reveal the slow tail of a latency distribution. High-percentile response times can expose performance problems hidden by the average.

### Q19. Are outliers always bad data?

No. Outliers may be errors, rare but valid observations, or meaningful events. Their treatment depends on context.

### Q20. What should be specified when reporting quartiles?

When exact reproducibility matters, state the quartile or percentile convention, especially when the dataset is small or when comparing software implementations.

---

## 17. Practice Problems

Try to solve the problems before checking the answers.

### Problem 1: Identify the quartiles

For the sorted dataset:

$$
2,\ 4,\ 6,\ 8,\ 10,\ 12,\ 14,\ 16,\ 18
$$

Using the median-of-halves method, calculate \(Q_1\), \(Q_2\), and \(Q_3\), excluding the overall median from each half.

### Problem 2: Calculate the IQR

Suppose:

$$
Q_1=12,\qquad Q_3=32
$$

Calculate the IQR.

### Problem 3: Identify potential outliers

Suppose:

$$
Q_1=10,\qquad Q_3=30
$$

Calculate the lower and upper fences using the \(1.5\times\mathrm{IQR}\) rule.

### Problem 4: Interpret a percentile

A student's score is at the 80th percentile of a defined reference group. What does this indicate?

### Problem 5: Quartile relationships

Complete the relationships:

$$
Q_1=P_{\_\_}
$$

$$
Q_2=P_{\_\_}
$$

$$
Q_3=P_{\_\_}
$$

### Problem 6: Find the median

For the sorted dataset:

$$
5,\ 10,\ 15,\ 20,\ 25,\ 30
$$

Calculate the median.

### Problem 7: Compare IQR and range

Consider:

$$
1,\ 2,\ 3,\ 4,\ 5,\ 6,\ 7,\ 100
$$

Explain why the range may be more affected by the extreme value than the IQR.

### Problem 8: Robust scaling

A feature has median \(20\), first quartile \(10\), third quartile \(30\), and observation \(x=35\).

Calculate the scaled value using median and IQR scaling.

### Problem 9: Percentile conventions

Why might two software libraries return different values for the 25th percentile of the same small dataset?

### Problem 10: Machine learning data leakage

You are training a model and want to use the IQR to scale a feature. Should you calculate the median and IQR using the entire dataset before splitting it, or fit them on the training data only?

---

## 18. Practice Problem Answers

### Answer 1

The median is:

$$
Q_2=10
$$

The lower half is \(2,4,6,8\), so:

$$
Q_1=\frac{4+6}{2}=5
$$

The upper half is \(12,14,16,18\), so:

$$
Q_3=\frac{14+16}{2}=15
$$

Therefore:

$$
Q_1=5,\qquad Q_2=10,\qquad Q_3=15
$$

### Answer 2

$$
\mathrm{IQR}=Q_3-Q_1
$$

$$
\mathrm{IQR}=32-12=20
$$

### Answer 3

First calculate the IQR:

$$
\mathrm{IQR}=30-10=20
$$

Lower fence:

$$
L=10-1.5(20)=-20
$$

Upper fence:

$$
U=30+1.5(20)=60
$$

Values below \(-20\) or above \(60\) are flagged as potential outliers by this rule.

### Answer 4

The score is at or above approximately 80% of the scores in the reference group, depending on the percentile-rank convention and how ties are handled.

### Answer 5

$$
Q_1=P_{25}
$$

$$
Q_2=P_{50}
$$

$$
Q_3=P_{75}
$$

### Answer 6

There are six observations. The two middle values are \(15\) and \(20\).

$$
\mathrm{Median}=\frac{15+20}{2}=17.5
$$

### Answer 7

The range uses the maximum and minimum, so:

$$
\mathrm{Range}=100-1=99
$$

The value \(100\) makes the range much larger than the span of the other observations. The IQR focuses on the middle 50% and is therefore less directly affected by that extreme maximum. Its exact value depends on the quartile convention.

### Answer 8

First calculate the IQR:

$$
\mathrm{IQR}=30-10=20
$$

Then apply median and IQR scaling:

$$
x_{\mathrm{scaled}}=\frac{35-20}{20}
$$

$$
x_{\mathrm{scaled}}=\frac{15}{20}=0.75
$$

### Answer 9

The libraries may use different rank formulas or interpolation methods. The differences are often more visible with small datasets.

### Answer 10

Fit the median and IQR on the training data only, then apply those learned parameters to validation and test data. This avoids leakage from evaluation data.

---

## 19. Quick Revision Notes

- A percentile describes a relative position in an ordered distribution.
- The 50th percentile is the median.
- Quartiles divide the distribution into four parts.
- \(Q_1=P_{25}\).
- \(Q_2=P_{50}=\text{Median}\).
- \(Q_3=P_{75}\).
- Percentile and quartile values can depend on the calculation convention.
- The IQR measures the width of the middle 50% of the data.
- The IQR is calculated as \(Q_3-Q_1\).
- The common IQR outlier fences are \(Q_1-1.5\mathrm{IQR}\) and \(Q_3+1.5\mathrm{IQR}\).
- A potential outlier is not necessarily an error.
- Percentiles are useful for exam scores, income distributions, healthcare reference charts, response-time monitoring, and machine learning.
- Median-and-IQR scaling can be more robust to extreme values than mean-and-standard-deviation scaling.
- In machine learning, fit preprocessing statistics on training data only.

---

## 20. Final Summary

Percentiles and quartiles describe the relative positions of observations within a distribution.

Percentiles divide a distribution into 100 equal-proportion parts, while quartiles divide it into four parts. The three main quartiles correspond to the 25th, 50th, and 75th percentiles.

The most important relationships are:

$$
Q_1=P_{25}
$$

$$
Q_2=P_{50}=\mathrm{Median}
$$

$$
Q_3=P_{75}
$$

The interquartile range is:

$$
\mathrm{IQR}=Q_3-Q_1
$$

The common lower and upper fences for potential outlier screening are:

$$
L=Q_1-1.5\mathrm{IQR}
$$

$$
U=Q_3+1.5\mathrm{IQR}
$$

These concepts are essential for descriptive statistics, exploratory data analysis, robust data summaries, outlier screening, and machine learning preprocessing.

