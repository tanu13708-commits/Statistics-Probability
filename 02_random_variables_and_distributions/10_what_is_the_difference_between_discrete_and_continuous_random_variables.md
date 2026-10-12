# Q10. What Is the Difference Between Discrete and Continuous Random Variables?

## 1. Introduction

In probability and statistics, random variables are broadly classified into two main types:

1. **Discrete random variables**
2. **Continuous random variables**

Both represent numerical outcomes of random experiments, but they differ in the values they can take and how probabilities are assigned to those values.

A **discrete random variable** takes values from a finite or countably infinite set. A **continuous random variable** is commonly modeled using a probability density over a continuous range of values.

Understanding this distinction is important for selecting probability distributions, calculating probabilities, performing statistical analysis, and building machine-learning models.

## 2. What Is a Discrete Random Variable?

A discrete random variable takes values from a finite or countably infinite set.

Its possible values can be listed, even if the list contains infinitely many values.

### Examples

- Number of heads in a sequence of coin tosses.
- Number of customers arriving at a store in one hour.
- Number of defective products in a batch.
- Number of emails received in a day.
- Number of purchases made by a customer in one month.

These variables represent counts, so their possible values are usually nonnegative integers.

### Example: Number of Heads in Two Coin Tosses

Suppose a fair coin is tossed twice.

The sample space is:

$$
S = \{HH, HT, TH, TT\}
$$

Let \(X\) represent the number of heads.

| Outcome | Value of \(X\) |
|---|---:|
| HH | 2 |
| HT | 1 |
| TH | 1 |
| TT | 0 |

The possible values are:

$$
X \in \{0,1,2\}
$$

Since \(X\) takes only three possible values, it is a discrete random variable.

Each outcome is equally likely, so its probability distribution is:

| \(x\) | \(P(X=x)\) |
|---|---:|
| 0 | 0.25 |
| 1 | 0.50 |
| 2 | 0.25 |

The probabilities sum to one:

$$
\sum_x P(X=x)=1
$$

### Probability Mass Function (PMF)

A discrete random variable is described by a probability mass function (PMF).

The PMF gives the probability that the variable equals a specific value:

$$
p_X(x)=P(X=x)
$$

A valid PMF satisfies:

$$
P(X=x)\geq 0
$$

and

$$
\sum_x P(X=x)=1
$$

For a discrete random variable, the probability of a specific value can be greater than zero.

For example:

$$
P(X=1)=0.50
$$

This means there is a 50% probability of obtaining exactly one head in two fair coin tosses.

## 3. What Is a Continuous Random Variable?

A continuous random variable is commonly modeled as taking values over one or more continuous intervals of the real number line.

Unlike a count, a measurement can take fractional values at increasingly fine levels of precision.

### Examples

- Height of a person.
- Weight of a product.
- Time required to complete a task.
- Temperature at a location.
- Distance traveled by a vehicle.
- Amount of rainfall over a period.

For example, a task's completion time might be 4 seconds, 4.2 seconds, 4.25 seconds, or 4.251 seconds.

The values are not restricted to whole numbers.

### Probability Density Function (PDF)

A continuous random variable is commonly described by a probability density function (PDF), denoted by \(f_X(x)\).

A valid PDF satisfies:

$$
f_X(x)\geq 0
$$

and

$$
\int_{-\infty}^{\infty} f_X(x)\,dx=1
$$

The probability that \(X\) falls within an interval is calculated by integrating the PDF:

$$
P(a\leq X\leq b)=\int_a^b f_X(x)\,dx
$$

For a continuous random variable with a PDF, the probability of any individual exact value is zero:

$$
P(X=a)=0
$$

This does not mean that the value is impossible. It means that probability is measured over intervals rather than individual points.

Consequently:

$$
P(a\leq X\leq b)=P(a<X<b)
$$

because including or excluding the endpoints does not change the probability.

## 4. Key Differences Between Discrete and Continuous Random Variables

| Feature | Discrete Random Variable | Continuous Random Variable |
|---|---|---|
| Possible values | Finite or countably infinite | Usually values throughout continuous intervals |
| Typical examples | Number of calls, defects, purchases | Height, weight, time, temperature |
| Common probability representation | PMF | PDF |
| Probability of an exact value | Can be greater than zero | Zero when the variable has a PDF |
| Probability calculation | Sum probabilities of relevant values | Integrate density over an interval |
| Total probability | Sum over all possible values equals 1 | Integral of the PDF over its domain equals 1 |
| Typical distributions | Bernoulli, Binomial, Poisson | Normal, Exponential, Uniform |
| Common data type | Counts | Measurements |

**Important:** These are common patterns, not absolute rules for every application. A variable describing a measurement rounded to whole numbers can be discrete in the recorded dataset even when the underlying physical quantity is modeled as continuous.

## 5. Example: Comparing Discrete and Continuous Variables

Consider a factory that manufactures products.

### Case A: Number of Defective Products

Let \(X\) be the number of defective products in a batch of 10 products.

Possible values are:

$$
X\in\{0,1,2,\ldots,10\}
$$

The number of defective products must be a whole number. It cannot be 2.5 defective products.

Therefore, \(X\) is a discrete random variable.

If the probability of a product being defective is \(p\), and defects occur independently across products, then \(X\) can be modeled using a Binomial distribution:

$$
X\sim\operatorname{Binomial}(n=10,p)
$$

The probability of exactly \(k\) defective products is:

$$
P(X=k)=\binom{10}{k}p^k(1-p)^{10-k}
$$

Here:

- \(n=10\) is the number of products.
- \(k\) is the number of defective products.
- \(p\) is the probability that an individual product is defective.

### Case B: Weight of a Product

Let \(Y\) be the weight of a randomly selected product, measured in kilograms.

Its underlying weight could be 1.502 kg, 1.5024 kg, or another value within the physically possible range.

If weight is modeled as a continuous random variable, probabilities are calculated over intervals.

For example:

$$
P(1.5\leq Y\leq 1.6)
$$

If the weight has PDF \(f_Y(y)\), then:

$$
P(1.5\leq Y\leq 1.6)=\int_{1.5}^{1.6}f_Y(y)\,dy
$$

The probability of the exact weight being 1.5 kg is:

$$
P(Y=1.5)=0
$$

under the continuous model.

### Main Lesson

- Counting defective products produces a discrete random variable.
- Measuring product weight is commonly modeled using a continuous random variable.

The distinction depends on what is being measured and how the variable is defined.

## 6. Example: Discrete Probability Versus Continuous Probability

Suppose a fair six-sided die is rolled once.

Let \(X\) be the number shown.

The probability of rolling exactly 4 is:

$$
P(X=4)=\frac{1}{6}
$$

This is a discrete random variable, so an exact value can have positive probability.

Now suppose \(Y\) is a continuous random variable representing a person's height in meters.

Even if a height of 1.70 meters is possible:

$$
P(Y=1.70)=0
$$

under a continuous probability model.

However, an interval can have positive probability:

$$
P(1.69\leq Y\leq 1.71)
$$

If \(f_Y(y)\) is the height's probability density function, then:

$$
P(1.69\leq Y\leq 1.71)
=
\int_{1.69}^{1.71}f_Y(y)\,dy
$$

This illustrates a fundamental distinction:

- Discrete probability assigns probability to individual values.
- Continuous probability assigns probability to intervals through integration.

## 7. Cumulative Distribution Function (CDF)

Both discrete and continuous random variables can be described using a cumulative distribution function (CDF).

The CDF is defined as:

$$
F_X(x)=P(X\leq x)
$$

### For a Discrete Random Variable

The CDF is obtained by adding the probabilities of all possible values less than or equal to \(x\).

For the number of heads in two fair coin tosses:

$$
P(X=0)=0.25
$$

$$
P(X=1)=0.50
$$

$$
P(X=2)=0.25
$$

Therefore:

$$
F_X(0)=0.25
$$

$$
F_X(1)=0.75
$$

$$
F_X(2)=1
$$

The CDF increases in steps.

### For a Continuous Random Variable

For a continuous random variable with PDF \(f_X(x)\):

$$
F_X(x)=\int_{-\infty}^{x}f_X(t)\,dt
$$

The CDF is continuous when the distribution has a PDF. It accumulates probability as \(x\) increases.

Unlike a PMF, a PDF does not directly give the probability of an exact value.

## 8. Expected Value and Variance

Both discrete and continuous random variables can have an expected value and variance.

The formulas differ according to how their probability distributions are represented.

### 8.1 Expected Value of a Discrete Random Variable

For a discrete random variable:

$$
E[X]=\sum_x xP(X=x)
$$

Multiply each possible value by its probability and add the results.

### 8.2 Expected Value of a Continuous Random Variable

For a continuous random variable with PDF \(f_X(x)\):

$$
E[X]=\int_{-\infty}^{\infty}xf_X(x)\,dx
$$

This integral gives the probability-weighted average over the distribution, when the expectation exists.

### 8.3 Variance

For either type of random variable, variance can be defined as:

$$
\mathrm{Var}(X)=E[(X-E[X])^2]
$$

When the second moment is finite, an equivalent expression is:

$$
\mathrm{Var}(X)=E[X^2]-(E[X])^2
$$

For a discrete random variable:

$$
\mathrm{Var}(X)=\sum_x (x-E[X])^2P(X=x)
$$

For a continuous random variable with PDF \(f_X(x)\):

$$
\mathrm{Var}(X)=\int_{-\infty}^{\infty}(x-E[X])^2f_X(x)\,dx
$$

Variance measures spread around the mean, while standard deviation is the square root of variance.

## 9. Common Probability Distributions

Different probability distributions are useful for modeling different kinds of random variables.

### 9.1 Common Discrete Distributions

**Bernoulli distribution**

Models one trial with two possible outcomes, often represented as 0 and 1.

Example: Whether a customer purchases a product.

$$
X\sim\operatorname{Bernoulli}(p)
$$

**Binomial distribution**

Models the number of successes in a fixed number of independent Bernoulli trials with the same success probability.

Example: Number of defective products in a fixed batch, under the required independence and equal-probability assumptions.

$$
X\sim\operatorname{Binomial}(n,p)
$$

**Poisson distribution**

Models a nonnegative integer count and is commonly used for the number of events occurring within a fixed interval under suitable assumptions.

Example: Number of customer arrivals in an hour.

$$
X\sim\operatorname{Poisson}(\lambda)
$$

### 9.2 Common Continuous Distributions

**Normal distribution**

A symmetric, bell-shaped distribution commonly used to model measurements and errors in suitable settings.

$$
X\sim N(\mu,\sigma^2)
$$

Here, \(\mu\) is the mean and \(\sigma^2\) is the variance.

**Uniform distribution**

A continuous uniform distribution assigns a constant density across a specified interval.

For example, if \(X\) is uniform between \(a\) and \(b\):

$$
f_X(x)=\frac{1}{b-a}
\quad \text{for } a\leq x\leq b
$$

**Exponential distribution**

Often used to model waiting times under suitable assumptions, such as a constant event rate in a Poisson process.

$$
X\sim\operatorname{Exponential}(\lambda)
$$

Here, \(\lambda>0\) is the rate parameter.

The distribution used should be chosen based on the variable, the data, and the assumptions of the problem.

## 10. Applications in Machine Learning

Understanding the distinction between discrete and continuous random variables helps in choosing appropriate statistical models, likelihood functions, and evaluation methods.

### 10.1 Classification

In classification, the target variable is often discrete.

For example, a spam classifier may define its target as:

$$
Y\in\{0,1\}
$$

where:

- \(Y=1\) means spam.
- \(Y=0\) means not spam.

A probabilistic classifier estimates:

$$
P(Y=1\mid X=x)
$$

For a multiclass problem, the target may take one of several categorical values.

Models such as logistic regression and Naive Bayes can be used for classification, with their specific assumptions and implementations determining how the probabilities are estimated.

### 10.2 Regression

In regression, the target is often a continuous quantity.

Examples include:

- Predicting house prices.
- Estimating delivery time.
- Predicting temperature.
- Forecasting product demand when demand is measured on a continuous scale.

A regression model might estimate the conditional mean:

$$
E[Y\mid X=x]
$$

Some regression tasks instead predict counts or other discrete outcomes. Therefore, regression does not always imply a continuous target.

### 10.3 Choosing a Likelihood Function

The type of target variable often influences the likelihood function used during model training.

Examples:

- Binary outcomes can be modeled with a Bernoulli distribution.
- Counts can be modeled with a Poisson distribution when its assumptions are appropriate.
- Continuous measurements can be modeled with a Normal distribution in suitable settings.

The likelihood should match the nature of the target and the modeling assumptions.

### 10.4 Data Preprocessing

The distinction also matters when preparing data.

For example:

- A count such as the number of purchases is naturally discrete.
- A measurement such as temperature is often modeled as continuous.
- A rounded or binned measurement may be recorded as discrete even if the underlying quantity is continuous.

Correctly identifying the variable helps determine which transformations, summary statistics, and modeling approaches are appropriate.

## 11. Common Mistakes

### Mistake 1: Assuming Discrete Variables Must Have Only a Few Values

A discrete random variable can have infinitely many possible values, as long as they are countable.

For example, a count variable could take any nonnegative integer:

$$
X\in\{0,1,2,3,\ldots\}
$$

### Mistake 2: Assuming Continuous Variables Must Be Normally Distributed

A continuous random variable can follow many different distributions, including uniform, exponential, and normal distributions.

The type of random variable does not uniquely determine its distribution.

### Mistake 3: Treating a PDF Value as an Exact Probability

For a continuous random variable with a PDF:

$$
P(X=a)=0
$$

The PDF value \(f_X(a)\) is a density, not the probability that \(X=a\).

### Mistake 4: Assuming Measurements Are Always Continuous in Recorded Data

A measurement may be rounded to a fixed precision.

For example, height recorded to the nearest centimeter takes values from a discrete set in the recorded dataset, even if underlying height is modeled as continuous.

### Mistake 5: Assuming Every Regression Target Is Continuous

Regression often predicts continuous values, but count regression can predict discrete outcomes.

The target type and the model's assumptions should guide the choice of statistical method.

### Mistake 6: Confusing a Count with a Measurement

The number of customers is a count, while the time customers spend in a store is a measurement.

The first is naturally discrete; the second is commonly modeled as continuous.

## 12. Common Interview Questions and Answers

### Q1. What is the main difference between discrete and continuous random variables?

**Answer:** A discrete random variable takes values from a finite or countably infinite set. A continuous random variable is commonly modeled as taking values throughout continuous intervals and is described using a probability density function when it has a density.

### Q2. Can a discrete random variable have infinitely many values?

**Answer:** Yes. A discrete random variable can have countably infinitely many values, such as the nonnegative integers.

### Q3. Why is the probability of an exact value zero for a continuous random variable with a PDF?

**Answer:** Probability is calculated by integrating the density over an interval. A single point has zero width, so its integral is zero. This does not mean that the value is impossible.

### Q4. What is the difference between a PMF and a PDF?

**Answer:** A PMF directly gives the probability of each possible value of a discrete random variable. A PDF gives probability density, and probabilities for continuous random variables are calculated by integrating the PDF over intervals.

### Q5. Can both discrete and continuous random variables have a CDF?

**Answer:** Yes. The CDF is defined for any random variable as:

$$
F_X(x)=P(X\leq x)
$$

For a discrete variable, it generally has jumps. For a variable with a continuous PDF, it is continuous.

### Q6. Is height a discrete or continuous random variable?

**Answer:** Height is commonly modeled as a continuous random variable. However, if height is recorded only to the nearest centimeter, the recorded values form a discrete set.

### Q7. Is the number of customer purchases discrete or continuous?

**Answer:** It is discrete because it is a count that takes nonnegative integer values.

### Q8. Which distributions are commonly used for discrete random variables?

**Answer:** Common examples include the Bernoulli, Binomial, and Poisson distributions. The appropriate choice depends on the data and the assumptions.

### Q9. Which distributions are commonly used for continuous random variables?

**Answer:** Common examples include the Normal, Uniform, and Exponential distributions. Other continuous distributions may be more suitable depending on the problem.

### Q10. Why is this distinction important in machine learning?

**Answer:** It influences how we represent target variables, choose probability distributions and likelihood functions, calculate probabilities, and interpret model predictions.

## 13. Key Takeaways

- Discrete random variables take values from finite or countably infinite sets.
- Continuous random variables are commonly modeled over continuous intervals.
- Discrete distributions are described using PMFs.
- Continuous distributions with densities are described using PDFs.
- For discrete variables, an exact value can have positive probability.
- For continuous variables with a PDF, the probability of an exact point is zero.
- CDFs can describe both discrete and continuous random variables.
- Expected value and variance can be defined for both types, subject to the relevant existence conditions.
- The distinction helps guide statistical modeling and machine-learning decisions.

## 14. Practice Problems

### Problem 1: Classify the Variables

Classify each variable as discrete or continuous under its natural modeling interpretation.

1. Number of calls received by a call center in one hour.
2. Time taken to complete a delivery.
3. Number of defective products in a batch.
4. Temperature measured at noon.
5. Number of purchases made by a customer in one week.
6. Weight of a randomly selected package.

#### Solution

| Variable | Classification | Reason |
|---|---|---|
| Number of calls | Discrete | It is a count |
| Delivery time | Continuous | It is a measurement |
| Number of defective products | Discrete | It is a count |
| Temperature | Continuous | It is commonly modeled as a measurement |
| Number of purchases | Discrete | It is a count |
| Package weight | Continuous | It is commonly modeled as a measurement |

Recorded values may have different properties if they are rounded or grouped.

### Problem 2: Discrete Probability

A fair coin is tossed twice. Let \(X\) be the number of heads.

Calculate:

1. \(P(X=0)\)
2. \(P(X=1)\)
3. \(P(X=2)\)

#### Solution

The sample space is:

$$
S=\{HH,HT,TH,TT\}
$$

There is one outcome with zero heads:

$$
P(X=0)=\frac{1}{4}=0.25
$$

There are two outcomes with one head:

$$
P(X=1)=\frac{2}{4}=0.50
$$

There is one outcome with two heads:

$$
P(X=2)=\frac{1}{4}=0.25
$$

The probabilities sum to one:

$$
0.25+0.50+0.25=1
$$

### Problem 3: Continuous Probability

Suppose \(X\) is uniformly distributed between 0 and 10.

Calculate:

1. \(P(2\leq X\leq 5)\)
2. \(P(X=3)\)

#### Solution

The PDF is:

$$
f_X(x)=\frac{1}{10}
\quad \text{for } 0\leq x\leq 10
$$

The probability of the interval is:

$$
P(2\leq X\leq 5)=\int_2^5 \frac{1}{10}\,dx
$$

$$
P(2\leq X\leq 5)=\frac{5-2}{10}=0.3
$$

Since \(X\) is continuous:

$$
P(X=3)=0
$$

The value 3 is possible, but its exact point probability is zero.

### Problem 4: Interview Challenge

A dataset contains two variables:

- \(X\): Number of products purchased by a customer.
- \(Y\): Total amount paid by the customer, recorded to the nearest cent.

Which variable is discrete and which is continuous?

#### Solution

The number of products \(X\) is discrete because it is a count.

The total amount paid \(Y\), as recorded to the nearest cent, takes values on a discrete grid of monetary amounts. Therefore, its recorded representation is discrete, although a continuous approximation may sometimes be useful for statistical modeling.

This example demonstrates that the distinction depends not only on the real-world concept but also on how the variable is represented and modeled.

---

**Final reminder:** Discrete variables are associated with countable values and PMFs, while continuous variables are commonly associated with measurements, densities, and integration over intervals.
