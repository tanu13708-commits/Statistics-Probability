# Q17. What Are Mean, Median, and Mode?

## 1. Introduction

Mean, median, and mode are the three most common measures of central tendency in statistics. They help us understand the center or typical value of a dataset.

For example, suppose the marks obtained by five students are:

`10, 20, 20, 30, 70`

We can summarize these values in three different ways:

- **Mean:** The arithmetic average of all values.
- **Median:** The middle value when the data is arranged in order.
- **Mode:** The most frequently occurring value.

For this dataset:

- Mean = 30
- Median = 20
- Mode = 20

These measures describe the same dataset from different perspectives. Choosing the right one depends on the distribution of the data, the presence of outliers, and the problem we want to solve.

---

## 2. What Is the Mean?

### Definition

The **mean**, commonly called the arithmetic average, is calculated by adding all observations and dividing by the total number of observations.

### Formula

For a dataset containing \(n\) observations:

$$
\text{Mean} = \frac{\text{Sum of all observations}}{\text{Number of observations}}
$$

Using mathematical notation:

$$
\bar{x} = \frac{1}{n}\sum_{i=1}^{n}x_i
$$

Where:

- \(\bar{x}\) = sample mean
- \(x_i\) = the \(i\)-th observation
- \(n\) = number of observations
- \(\sum\) = summation over all observations

### Example

Suppose the salaries of five employees, in thousands of rupees, are:

`20, 25, 30, 35, 40`

Step 1: Add all the values.

$$
20 + 25 + 30 + 35 + 40 = 150
$$

Step 2: Divide by the number of observations.

$$
\text{Mean} = \frac{150}{5} = 30
$$

Therefore, the **mean salary is ₹30,000**.

### Important properties of the mean

1. It uses every observation in the dataset.
2. It is sensitive to extreme values, also called outliers.
3. The sum of deviations from the arithmetic mean is zero.

$$
\sum_{i=1}^{n}(x_i-\bar{x}) = 0
$$

4. It is useful for mathematical calculations, including variance, standard deviation, and many statistical models.
5. For a fixed dataset, the arithmetic mean is unique.

### When should we use the mean?

The mean is generally appropriate when:

- The data is numerical.
- The observations are reasonably representative of the distribution.
- Extreme values do not distort the summary too much.
- We need a measure that incorporates every observation.

Examples include average test scores, average daily temperature, and the average measurement of a physical quantity.

---

## 3. What Is the Median?

### Definition

The **median** is the middle value of a dataset after arranging all observations in ascending or descending order.

Unlike the mean, the median depends primarily on the order of observations rather than their exact magnitudes.

### Formula

First, sort the observations.

If the number of observations \(n\) is odd:

$$
\text{Median} = x_{\left(\frac{n+1}{2}\right)}
$$

If the number of observations \(n\) is even:

$$
\text{Median} =
\frac{
x_{\left(\frac{n}{2}\right)}
+
x_{\left(\frac{n}{2}+1\right)}
}{2}
$$

Here, \(x_{(k)}\) means the \(k\)-th observation in the sorted dataset.

### Example 1: Odd number of observations

Consider the dataset:

`10, 20, 30, 40, 50`

There are five observations, so the median is at position:

$$
\frac{n+1}{2} = \frac{5+1}{2} = 3
$$

The third value is 30.

Therefore:

$$
\text{Median} = 30
$$

### Example 2: Even number of observations

Consider the dataset:

`10, 20, 30, 40`

There are four observations. The two middle values are 20 and 30.

Therefore:

$$
\text{Median} = \frac{20+30}{2} = 25
$$

The median is 25, even though 25 does not appear in the dataset.

### Why is the median robust to outliers?

Consider two datasets:

Dataset A:

`10, 20, 30, 40, 50`

Dataset B:

`10, 20, 30, 40, 1000`

For Dataset A:

$$
\text{Mean} = \frac{150}{5} = 30
$$

For Dataset B:

$$
\text{Mean} = \frac{1100}{5} = 220
$$

The mean increases dramatically because of the extreme value 1000.

However, both datasets have the same median:

$$
\text{Median} = 30
$$

The median remains unchanged because the middle observation has not changed.

### Important properties of the median

1. It is less sensitive to extreme values than the mean.
2. It divides an ordered dataset into two halves, with at least half the observations at or below it and at least half at or above it.
3. It is useful for skewed distributions.
4. It can be used with ordinal data, where observations can be ranked but differences between values may not be meaningful.
5. It does not use the exact magnitudes of all observations in the same way as the mean.

### When should we use the median?

The median is often preferred when:

- The dataset contains extreme outliers.
- The distribution is strongly skewed.
- We want a robust summary of a typical observation.
- We are analyzing income, property prices, or waiting times with a long tail.

For example, median household income often describes a typical household more accurately than mean income when a small number of households earn exceptionally high incomes.

---

## 4. What Is the Mode?

### Definition

The **mode** is the value that occurs most frequently in a dataset.

Unlike the mean and median, the mode can be used for both numerical and categorical data.

### Example

Consider the dataset:

`10, 20, 20, 30, 40`

The value 20 occurs twice, while every other value occurs once.

Therefore:

$$
\text{Mode} = 20
$$

### Different types of mode

#### 1. Unimodal distribution

A dataset is unimodal when it has one mode.

Example:

`1, 2, 2, 3, 4`

Mode = 2.

#### 2. Bimodal distribution

A dataset is bimodal when it has two modes.

Example:

`1, 1, 2, 3, 3, 4`

The values 1 and 3 both occur twice.

Modes = 1 and 3.

#### 3. Multimodal distribution

A dataset is multimodal when it has more than two modes.

Example:

`1, 1, 2, 2, 3, 3, 4`

Modes = 1, 2, and 3.

#### 4. No unique mode

Some datasets have no single most frequent value.

Example:

`1, 2, 3, 4, 5`

Every value occurs once, so there is no unique mode.

For a finite dataset, if every observation occurs with the same frequency, there is no uniquely most frequent value.

### Mode for categorical data

Suppose a survey records people's preferred programming languages:

`Python, Java, Python, C++, Python, Java`

Python appears three times, Java appears twice, and C++ appears once.

Therefore:

**Mode = Python**

We cannot meaningfully calculate the arithmetic mean of programming-language names. This is one reason the mode is useful.

### Important properties of the mode

1. It can be used for categorical data.
2. A dataset may have one mode, multiple modes, or no unique mode.
3. It is not necessarily close to the mean or median.
4. It identifies the most frequently observed value or category.
5. It can be unstable in small datasets because a small change in observations may change the most frequent value.

### When should we use the mode?

The mode is useful when:

- We need the most common category.
- We are analyzing customer preferences.
- We want to identify the most frequently sold product size.
- We are studying the most common class in a classification dataset.
- We need a measure of central tendency for nominal categorical data.

---

## 5. Mean vs. Median vs. Mode

| Feature | Mean | Median | Mode |
|---|---|---|---|
| Meaning | Arithmetic average | Middle ordered value | Most frequent value |
| Uses all numerical magnitudes? | Yes | No, primarily uses order | No |
| Sensitive to outliers? | Yes | Much less sensitive | Depends on how frequencies change |
| Works with categorical data? | No | Only if categories are ordered | Yes |
| Can have multiple values? | No, for a fixed dataset | No, under the usual definition | Yes |
| Best known use | Average numerical value | Typical value with skew or outliers | Most common value or category |

### Quick example

Dataset:

`2, 3, 3, 4, 18`

Mean:

$$
\text{Mean} = \frac{2+3+3+4+18}{5} = 6
$$

Median:

$$
\text{Median} = 3
$$

Mode:

$$
\text{Mode} = 3
$$

The mean is larger than the median because the value 18 pulls the average upward.

This illustrates why choosing a measure based on the shape of the data is important.

---

## 6. Relationship Between Mean, Median, and Mode

The relationship between these measures depends on the distribution.

### A. Symmetric distribution

In many symmetric, unimodal distributions, the mean, median, and mode coincide or are close together.

For example, a perfectly symmetric normal distribution has:

$$
\text{Mean} = \text{Median} = \text{Mode}
$$

This is an important property of the normal distribution.

However, symmetry alone does not guarantee that a dataset has a unique mode or that all three measures are exactly equal.

### B. Right-skewed distribution

A right-skewed distribution has a long tail toward larger values.

A common pattern is:

$$
\text{Mode} < \text{Median} < \text{Mean}
$$

Example: personal income, where a small number of people earn much more than most others.

The large values pull the mean toward the right tail.

### C. Left-skewed distribution

A left-skewed distribution has a long tail toward smaller values.

A common pattern is:

$$
\text{Mean} < \text{Median} < \text{Mode}
$$

The unusually small values pull the mean toward the left tail.

**Important:** These orderings are useful rules of thumb for typical unimodal distributions, not universal laws. Real datasets may not follow them exactly.

---

## 7. Weighted Mean

Sometimes, every observation does not contribute equally. In such cases, we may use a **weighted mean**.

### Formula

$$
\bar{x}_w = \frac{\sum_{i=1}^{n}w_i x_i}{\sum_{i=1}^{n}w_i}
$$

Where:

- \(x_i\) = observed value
- \(w_i\) = weight assigned to that value
- \(n\) = number of observations

### Example

Suppose a student's grades are:

- Assignment: 80, weight 20%
- Midterm: 70, weight 30%
- Final exam: 90, weight 50%

The weighted mean is:

$$
\bar{x}_w = 80(0.20) + 70(0.30) + 90(0.50)
$$

$$
\bar{x}_w = 16 + 21 + 45 = 82
$$

Therefore, the final weighted score is 82.

### Why is this important?

A simple average would incorrectly give all three assessments equal importance. The weighted mean accounts for their different contributions.

In machine learning and statistics, weighted averages can appear in sample weighting, ensemble predictions, and the calculation of certain evaluation metrics.

---

## 8. Mean, Median, and Mode in Machine Learning

These measures are useful during exploratory data analysis, feature preprocessing, and model evaluation.

### A. Handling missing values

Suppose a numerical feature contains missing values.

Common strategies include:

- **Mean imputation:** Replace missing values with the mean.
- **Median imputation:** Replace missing values with the median.
- **Mode imputation:** Replace missing values with the most frequent value or category.

Example:

Suppose an age feature contains:

`20, 22, 23, missing, 100`

The observed mean is:

$$
\text{Mean} = \frac{20+22+23+100}{4} = 41.25
$$

The observed median is:

$$
\text{Median} = \frac{22+23}{2} = 22.5
$$

If 100 is an unusual outlier, median imputation may better represent a typical observation than mean imputation.

However, the best imputation strategy depends on the data and the missingness mechanism. Imputation values should be learned from the training data and then applied to validation and test data to avoid data leakage.

### B. Detecting skewness and outliers

Comparing the mean and median can help identify potential skewness.

If the mean is substantially greater than the median, the data may be right-skewed. If the mean is substantially less than the median, the data may be left-skewed.

This is a diagnostic clue, not a complete test of skewness.

### C. Understanding categorical features

The mode can identify the most common category in a feature such as:

- Payment method
- Product category
- Device type
- Customer segment

The mode may also be used for imputing missing categorical values, although it can overrepresent the most common category.

### D. Comparing model errors

Suppose we analyze the absolute errors of a regression model.

- The mean absolute error summarizes the average absolute prediction error.
- The median absolute error summarizes the median absolute prediction error.

The mean absolute error is more affected by very large errors, while the median absolute error is more robust to them.

These are model evaluation metrics based on the mean and median, respectively.

---

## 9. Limitations and Common Mistakes

### Mistake 1: Assuming the mean always represents a typical observation

The mean can be misleading when the data contains extreme values or is strongly skewed.

**Better approach:** Examine the median, distribution, and outliers before choosing a summary.

### Mistake 2: Assuming the median is always the best measure

The median is robust, but it does not use all numerical magnitudes in the same way as the mean.

If every observation matters to a calculation, such as the sum of squared deviations, the mean may be the more relevant measure.

### Mistake 3: Assuming every dataset has exactly one mode

A dataset may have multiple modes or no unique mode.

**Better approach:** Examine the frequencies rather than assuming a single most common value exists.

### Mistake 4: Confusing the mode with the maximum value

The mode is the most frequent value, not the largest value.

Example:

`2, 2, 2, 5, 9`

Mode = 2, while maximum = 9.

### Mistake 5: Confusing the mean with the median

The mean is calculated using the sum of observations. The median is calculated from the middle position after sorting.

They are not generally equal.

### Mistake 6: Using mean imputation without checking the distribution

Mean imputation can be influenced by outliers and may reduce the apparent variability of a feature.

**Better approach:** Compare possible strategies and fit preprocessing steps only on the training data.

---

## 10. Common Interview Questions and Answers

### Q1. What is the difference between mean, median, and mode?

**Answer:** The mean is the arithmetic average, the median is the middle value after sorting the observations, and the mode is the most frequently occurring value.

### Q2. Which measure is most sensitive to outliers?

**Answer:** The mean is generally the most sensitive because extreme values directly affect the sum. The median is more robust to extreme magnitudes.

### Q3. When would you use the median instead of the mean?

**Answer:** I would generally consider the median when the data is strongly skewed or contains extreme outliers, such as income or property-price data.

### Q4. Can a dataset have more than one mode?

**Answer:** Yes. A dataset can be bimodal or multimodal if multiple values share the highest frequency.

### Q5. Can a dataset have no unique mode?

**Answer:** Yes. If all values occur with equal frequency, there is no uniquely most frequent value.

### Q6. Can the median be a value that does not occur in the dataset?

**Answer:** Yes. With an even number of observations, the median is usually the average of the two middle values. For example, the median of 10 and 20 is 15.

### Q7. Can the mean be greater than the maximum observation?

**Answer:** No. For a nonempty dataset of finite numerical observations, the arithmetic mean must lie between the minimum and maximum values.

### Q8. Which measure can be used for nominal categorical data?

**Answer:** The mode is appropriate because nominal categories have no required numerical ordering. The mean is not meaningful for such categories.

### Q9. Why is the median useful for income analysis?

**Answer:** Income distributions often contain a small number of very high values. These values can raise the mean substantially, while the median is less affected by their magnitudes.

### Q10. How are the mean and median used in machine learning?

**Answer:** They are used in exploratory data analysis, missing-value imputation, distribution analysis, and evaluation metrics. The mean is used in mean absolute error, while the median can be used in median absolute error.

### Q11. What is a weighted mean?

**Answer:** A weighted mean assigns different levels of importance to observations. It is calculated by multiplying each value by its weight, adding the products, and dividing by the sum of the weights.

### Q12. Are mean, median, and mode always equal in a normal distribution?

**Answer:** Yes. In an ideal normal distribution, the mean, median, and mode coincide at the center of the distribution.

---

## 11. Practice Problems

Try solving these problems before checking the answers.

### Problem 1

Find the mean, median, and mode of:

`4, 6, 6, 8, 11`

### Problem 2

Find the median of:

`10, 15, 20, 25, 30, 35`

### Problem 3

A dataset contains:

`5, 5, 10, 10, 15, 15`

Does it have a unique mode?

### Problem 4

The monthly incomes of five people, in thousands of rupees, are:

`15, 20, 25, 30, 110`

Calculate the mean and median. Which is a more robust summary of a typical income?

### Problem 5

A student receives the following scores:

- Quiz: 70, weight 20%
- Midterm: 80, weight 30%
- Final: 90, weight 50%

Calculate the weighted mean.

### Problem 6

A categorical feature contains:

`Mobile, Desktop, Mobile, Tablet, Mobile, Desktop`

Find the mode.

### Problem 7

Explain why the median may be preferred over the mean when a dataset contains extreme outliers.

---

## 12. Practice Problem Answers

### Answer 1

Dataset:

`4, 6, 6, 8, 11`

Mean:

$$
\text{Mean} = \frac{4+6+6+8+11}{5} = 7
$$

Median = 6.

Mode = 6.

### Answer 2

Dataset:

`10, 15, 20, 25, 30, 35`

The middle values are 20 and 25.

$$
\text{Median} = \frac{20+25}{2} = 22.5
$$

### Answer 3

Each of the values 5, 10, and 15 occurs twice.

There is no unique mode; all three values share the highest frequency.

### Answer 4

Mean:

$$
\text{Mean} = \frac{15+20+25+30+110}{5}
$$

$$
\text{Mean} = \frac{200}{5} = 40
$$

Median = 25.

The median is generally a more robust summary of a typical income here because the value 110 pulls the mean upward.

### Answer 5

$$
\text{Weighted Mean} = 70(0.20)+80(0.30)+90(0.50)
$$

$$
\text{Weighted Mean} = 14+24+45 = 83
$$

The weighted mean is 83.

### Answer 6

Mobile occurs three times, Desktop occurs twice, and Tablet occurs once.

Mode = Mobile.

### Answer 7

The median depends on the ordered position of the observations and is less affected by the magnitude of an extreme value. Therefore, it often provides a more representative center for skewed data.

---

## 13. Key Takeaways

- **Mean:** The arithmetic average of all observations.
- **Median:** The middle value after sorting the data.
- **Mode:** The most frequently occurring value or category.
- The mean is sensitive to outliers, while the median is more robust to extreme magnitudes.
- The mode is useful for categorical data and may have multiple values.
- For a symmetric, unimodal normal distribution, mean = median = mode.
- In right-skewed data, the mean is often greater than the median; in left-skewed data, it is often smaller.
- Weighted means are useful when observations have different levels of importance.
- In machine learning, these measures support data exploration, missing-value imputation, and model evaluation.
- Always inspect the distribution and understand the problem before deciding which measure of central tendency to use.
