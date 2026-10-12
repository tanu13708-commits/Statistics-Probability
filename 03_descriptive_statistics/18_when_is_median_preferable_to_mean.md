# Q18. When Is the Median Preferable to the Mean?

## 1. Introduction

The mean and median are two important measures of central tendency. Both describe the center of a dataset, but they respond differently to extreme values and skewed distributions.

- **Mean:** The sum of all observations divided by the number of observations.
- **Median:** The middle value after arranging observations in ascending or descending order.

The **median is generally preferable to the mean when a dataset contains extreme outliers, is strongly skewed, or when we want a robust measure of a typical observation.**

However, the median is not always the best choice. The appropriate measure depends on the data distribution, the objective of the analysis, and the consequences of different types of errors.

---

## 2. Mathematical Definitions

### Mean

For a dataset containing \(n\) observations:

$$
\bar{x} = \frac{1}{n}\sum_{i=1}^{n}x_i
$$

Where:

- \(\bar{x}\) is the arithmetic mean.
- \(x_i\) is the \(i\)-th observation.
- \(n\) is the total number of observations.

The mean uses the numerical value of every observation.

### Median

First, sort the observations in ascending order.

If \(n\) is odd:

$$
\text{Median} = x_{\left(\frac{n+1}{2}\right)}
$$

If \(n\) is even:

$$
\text{Median} =
\frac{x_{\left(\frac{n}{2}\right)}+
x_{\left(\frac{n}{2}+1\right)}}{2}
$$

Here, \(x_{(k)}\) represents the \(k\)-th observation in the sorted dataset.

The median depends on the ordering of observations and is much less sensitive to the magnitude of extreme values.

---

## 3. Situation 1: When the Dataset Contains Outliers

An **outlier** is an observation that lies unusually far from the other observations.

Because the mean uses every numerical value, an extreme observation can substantially change it. The median is usually more stable because it depends on the middle position of the sorted data.

### Example

Suppose the monthly salaries of five employees, in thousands of rupees, are:

`20, 25, 30, 35, 40`

The mean is:

$$
\text{Mean} = \frac{20+25+30+35+40}{5}
$$

$$
\text{Mean} = \frac{150}{5} = 30
$$

The median is the middle observation:

$$
\text{Median} = 30
$$

Now suppose the last salary is replaced with 500:

`20, 25, 30, 35, 500`

The new mean is:

$$
\text{Mean} = \frac{20+25+30+35+500}{5}
$$

$$
\text{Mean} = \frac{610}{5} = 122
$$

The new median remains:

$$
\text{Median} = 30
$$

| Measure | Original dataset | Dataset with extreme value |
|---|---:|---:|
| Mean | 30 | 122 |
| Median | 30 | 30 |

The extreme salary increases the mean from 30 to 122, while the median remains unchanged.

**Conclusion:** When a few extreme observations would distort the average, the median is often a better summary of the typical observation.

**Important:** An extreme observation is not automatically an error. Before removing an outlier, investigate whether it represents a valid observation, a measurement error, or a different population.

---

## 4. Situation 2: When the Distribution Is Skewed

A distribution is **skewed** when its values are not distributed symmetrically around the center.

### A. Right-skewed distribution

A right-skewed distribution has a long tail toward larger values.

Examples may include:

- Personal income
- House prices
- Insurance claim amounts
- Some customer spending distributions

Consider this dataset:

`10, 12, 13, 15, 50`

The mean is:

$$
\text{Mean} = \frac{10+12+13+15+50}{5}
$$

$$
\text{Mean} = \frac{100}{5} = 20
$$

The median is:

$$
\text{Median} = 13
$$

The mean is higher than the median because the large value 50 pulls the mean toward the right tail.

If the goal is to describe the middle or typical observation, the median may be more informative.

### B. Left-skewed distribution

A left-skewed distribution has a long tail toward smaller values.

Example:

`5, 40, 42, 44, 46`

The mean is:

$$
\text{Mean} = \frac{5+40+42+44+46}{5}
$$

$$
\text{Mean} = \frac{177}{5} = 35.4
$$

The median is:

$$
\text{Median} = 42
$$

The small value 5 pulls the mean downward.

In a strongly left-skewed dataset, the median can be a better description of the center when extreme low values are not representative of the typical observation.

**Interview takeaway:** The median is often preferred for skewed data because it is less influenced by the long tail.

---

## 5. Situation 3: When Analyzing Income and Wealth

Income and wealth distributions are often right-skewed. A relatively small number of people may have exceptionally high incomes or large amounts of wealth.

Consider five annual incomes, in lakhs of rupees:

`3, 4, 5, 6, 42`

The mean income is:

$$
\text{Mean} = \frac{3+4+5+6+42}{5}
$$

$$
\text{Mean} = \frac{60}{5} = 12
$$

The median income is:

$$
\text{Median} = 5
$$

The mean income is ₹12 lakh, while the median income is ₹5 lakh.

The mean is mathematically correct, but it is substantially affected by the highest income. The median tells us that the middle person in this small ordered group earns ₹5 lakh.

### Why is the median useful here?

- It is less influenced by a few very high incomes.
- It can better represent the middle person or household.
- It is useful when comparing typical income levels across groups with different degrees of inequality.

However, the mean remains important when estimating total income divided by the number of people, calculating aggregate resources per person, or studying total economic output.

**The best measure depends on the question being asked.**

---

## 6. Situation 4: When You Need a Robust Summary

A **robust statistic** is a statistic that is relatively insensitive to small changes in the data, especially changes involving extreme observations.

The median is considered a robust measure of central tendency.

For example:

Dataset A:

`1, 2, 3, 4, 5`

Dataset B:

`1, 2, 3, 4, 100000`

The median of both datasets is 3.

However, the mean of Dataset A is:

$$
\text{Mean}_A = \frac{1+2+3+4+5}{5} = 3
$$

The mean of Dataset B is:

$$
\text{Mean}_B = \frac{1+2+3+4+100000}{5}
$$

$$
\text{Mean}_B = 20002
$$

The median is unaffected by this change because the middle observation remains 3.

### Breakdown point intuition

The median has a breakdown point of approximately 50%, meaning that nearly half the observations must be contaminated with arbitrarily extreme values before the median can be driven arbitrarily far away.

The arithmetic mean has a breakdown point of 0%: even one observation can make it arbitrarily large or small if that observation is allowed to become sufficiently extreme.

This is one reason the median is widely used in robust statistics.

---

## 7. Situation 5: When Working With Noisy Real-World Data

Real-world datasets can contain measurement errors, unusual observations, and natural variation.

Examples include:

- Sensor readings
- Website response times
- Delivery durations
- Customer purchase amounts
- Property prices

Suppose a website's response times, in milliseconds, are:

`100, 105, 110, 115, 900`

The mean is:

$$
\text{Mean} = \frac{100+105+110+115+900}{5}
$$

$$
\text{Mean} = \frac{1330}{5} = 266
$$

The median is:

$$
\text{Median} = 110
$$

If the goal is to describe a typical response time, the median may be more useful because one unusually slow response has a large effect on the mean.

However, if the goal is to estimate the average amount of time users experience across all requests, the mean may also be important. The slow request still contributes to the actual workload and user experience.

In performance analysis, it is often useful to report both the median and upper percentiles, such as the 90th or 99th percentile, because the typical response and the slowest experiences answer different questions.

---

## 8. Median vs. Mean in Machine Learning

The choice between mean and median matters during data preprocessing, feature analysis, and model evaluation.

### A. Missing-value imputation

Suppose a numerical feature contains:

`18, 20, 22, 24, missing, 200`

The observed mean is:

$$
\text{Mean} = \frac{18+20+22+24+200}{5}
$$

$$
\text{Mean} = \frac{284}{5} = 56.8
$$

The observed median is the middle value of the sorted observations:

`18, 20, 22, 24, 200`

$$
\text{Median} = 22
$$

If 200 is an unusual but valid extreme value, using 22 as the imputation value may better represent a typical observation than using 56.8.

Median imputation is therefore often considered for numerical features with substantial skewness or outliers.

However, imputation can distort the distribution and reduce apparent variability. The choice should be evaluated in the context of the dataset and model.

**Important machine learning practice:** Fit the imputer using the training data only, then apply the fitted imputer to validation and test data. This prevents information from those datasets from leaking into the preprocessing process.

### B. Regression with outliers

In regression, the mean and median are also connected to different loss functions.

For a target value \(y\) and prediction \(\hat{y}\), the squared-error loss is:

$$
L(y,\hat{y}) = (y-\hat{y})^2
$$

Minimizing the sum of squared errors tends to produce the conditional mean as the optimal prediction, assuming the relevant expectation exists.

The absolute-error loss is:

$$
L(y,\hat{y}) = |y-\hat{y}|
$$

Minimizing the expected absolute error tends to produce a conditional median as the optimal prediction.

This is a fundamental connection between measures of central tendency and machine learning.

### C. Evaluating model errors

The mean absolute error (MAE) is:

$$
\text{MAE} = \frac{1}{n}\sum_{i=1}^{n}|y_i-\hat{y}_i|
$$

The median absolute error is the median of the absolute prediction errors:

$$
\text{MedAE} =
\text{Median}\left(|y_i-\hat{y}_i|\right)
$$

MAE summarizes the average absolute error. Median absolute error summarizes the middle absolute error and is less sensitive to a few very large errors.

Neither metric is universally better. If large errors are especially costly, a mean-based metric or another tail-sensitive metric may be essential.

---

## 9. When Is the Mean Preferable to the Median?

The median is not always the right choice. The mean may be preferable when:

1. The numerical data is reasonably symmetric and does not contain influential outliers.
2. We need the arithmetic average of all observations.
3. We are calculating variance or standard deviation in the usual way.
4. We need to calculate a total by multiplying the average by the number of observations.
5. The objective or loss function specifically targets the mean.

For example, if five equally weighted measurements are `10, 20, 30, 40, 50`, the mean is 30. It provides the arithmetic average and uses all the measurements.

In contrast, the median also equals 30 in this example, but that agreement is not guaranteed for other datasets.

### A useful decision rule

- Choose the **mean** when the arithmetic average is the quantity of interest and extreme values are not unduly distorting the result.
- Choose the **median** when the middle observation or a robust measure of the center is more relevant.
- Consider reporting **both** when the data may be skewed or contain outliers.

Always consider the distribution and the purpose of the analysis before choosing.

---

## 10. Limitations of the Median

Although the median is robust, it has limitations.

### 1. It does not reflect the magnitude of every observation

The median of `1, 2, 3, 4, 100` is 3. The median of `1, 2, 3, 4, 100000` is also 3.

The two datasets have very different extreme values, but their medians are identical.

### 2. It may not be suitable for every statistical calculation

Many formulas and statistical procedures are based on the mean, including the conventional calculation of variance and standard deviation.

### 3. It can hide important tail behavior

If extreme values are important for risk, safety, or business costs, the median alone may conceal them.

For example, a median delivery time of 30 minutes does not reveal whether a small percentage of deliveries take several hours.

### 4. It may discard useful information about the overall magnitude

Two groups can have the same median but very different means, ranges, or distributions.

**Best practice:** Use the median with additional summaries, such as the interquartile range, percentiles, a histogram, or a box plot, when understanding the distribution matters.

---

## 11. Common Interview Questions and Answers

### Q1. When is the median preferable to the mean?

**Answer:** The median is generally preferable when the data is strongly skewed, contains influential outliers, or requires a robust summary of the typical observation.

### Q2. Why is the median robust to outliers?

**Answer:** The median depends on the middle position of the ordered observations, not on the magnitude of every value. An extreme value often has little effect unless it changes the middle position.

### Q3. Give an example where the median is better than the mean.

**Answer:** Income is a common example. A small number of very high incomes can pull the mean upward, while the median often better describes the income of a person in the middle of the distribution.

### Q4. Is the median always better than the mean?

**Answer:** No. The mean is appropriate when the arithmetic average is important and extreme values do not create a problem. The choice depends on the data and the purpose of the analysis.

### Q5. How does the median help in machine learning?

**Answer:** The median can be used for robust numerical imputation, exploratory data analysis, and median-based evaluation metrics. It is also linked to minimizing absolute-error loss.

### Q6. What is the difference between mean absolute error and median absolute error?

**Answer:** Mean absolute error averages the absolute prediction errors, while median absolute error takes their median. The median-based metric is less sensitive to a few very large errors.

### Q7. Why might a business report both mean and median?

**Answer:** The mean captures the arithmetic average, while the median describes the middle observation. A large gap between them can reveal skewness or influential extreme values.

### Q8. What is the breakdown point of the median?

**Answer:** The median has a breakdown point of approximately 50%. Roughly half the observations must be contaminated with extreme values before the median can be driven arbitrarily far away.

### Q9. Can a median hide a serious problem?

**Answer:** Yes. A median can look acceptable even when a small fraction of observations have extremely large values. Percentiles and tail summaries may be needed to reveal those cases.

### Q10. Which measure is associated with squared-error and absolute-error optimization?

**Answer:** Under standard conditions, squared-error optimization targets the conditional mean, while absolute-error optimization targets the conditional median.

---

## 12. Practice Problems

### Problem 1

Consider the dataset:

`10, 12, 15, 18, 100`

Calculate the mean and median. Which is a more robust summary of the center?

### Problem 2

The monthly incomes, in thousands of rupees, of five people are:

`20, 25, 30, 35, 200`

Calculate the mean and median.

### Problem 3

Why might median imputation be preferred to mean imputation for a numerical feature with extreme outliers?

### Problem 4

A website records these response times, in milliseconds:

`90, 95, 100, 105, 800`

If you want to describe a typical response time, which measure would you choose and why?

### Problem 5

What is the relationship between absolute-error loss and the median?

### Problem 6

A model has absolute prediction errors:

`1, 2, 2, 3, 100`

Calculate the mean absolute error and median absolute error.

### Problem 7

Can two datasets have the same median but very different means? Explain with an example.

---

## 13. Practice Problem Answers

### Answer 1

Mean:

$$
\text{Mean} = \frac{10+12+15+18+100}{5}
$$

$$
\text{Mean} = \frac{155}{5} = 31
$$

Median = 15.

The median is a more robust summary of the center because the extreme value 100 raises the mean.

### Answer 2

Mean:

$$
\text{Mean} = \frac{20+25+30+35+200}{5}
$$

$$
\text{Mean} = \frac{310}{5} = 62
$$

Median = 30.

The mean is 62 thousand rupees, while the median is 30 thousand rupees. The median is less affected by the high income of 200 thousand rupees.

### Answer 3

Median imputation is less influenced by the magnitudes of extreme values. It can therefore provide a more representative central value when the feature is strongly skewed or contains influential outliers.

### Answer 4

The median is 100 milliseconds, while the mean is:

$$
\text{Mean} = \frac{90+95+100+105+800}{5}
$$

$$
\text{Mean} = \frac{1190}{5} = 238
$$

The median is a better description of a typical response in this example because the 800-millisecond observation strongly increases the mean.

However, the unusually slow response should not be ignored if the goal is to understand worst-case performance.

### Answer 5

Minimizing expected absolute-error loss generally produces a conditional median as the optimal prediction. This differs from squared-error loss, which targets the conditional mean under standard conditions.

### Answer 6

The absolute errors are:

`1, 2, 2, 3, 100`

Mean absolute error:

$$
\text{MAE} = \frac{1+2+2+3+100}{5}
$$

$$
\text{MAE} = \frac{108}{5} = 21.6
$$

Median absolute error:

$$
\text{MedAE} = 2
$$

The mean absolute error is much larger because the error of 100 strongly influences the average.

### Answer 7

Yes.

Dataset A:

`1, 2, 3, 4, 5`

Dataset B:

`1, 2, 3, 4, 1000`

Both datasets have a median of 3, but their means are different.

$$
\text{Mean}_A = 3
$$

$$
\text{Mean}_B = \frac{1010}{5} = 202
$$

This shows that the median can remain unchanged even when an extreme observation substantially changes the mean.

---

## 14. Key Takeaways

- The median is generally preferable when data is strongly skewed or contains influential outliers.
- The mean is sensitive to extreme values because it uses the numerical magnitude of every observation.
- The median is a robust measure of central tendency and has a breakdown point of approximately 50%.
- Income, property prices, response times, and customer spending are examples where the median can be useful.
- In machine learning, median imputation can help with skewed numerical features, while median absolute error offers a robust summary of prediction errors.
- Squared-error optimization targets the conditional mean under standard conditions; absolute-error optimization targets the conditional median.
- The median does not reveal all aspects of a distribution, especially extreme tail behavior.
- The mean and median often work best together, supported by measures of spread and visualizations.
- **Interview rule:** Use the median for a robust description of the center; use the mean when the arithmetic average is the quantity of interest.
