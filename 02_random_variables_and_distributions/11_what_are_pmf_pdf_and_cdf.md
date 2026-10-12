# Q11. What Are PMF, PDF, and CDF?

## 1. Introduction

In probability and statistics, PMF, PDF, and CDF are three important concepts used to describe probability distributions.

- **PMF (Probability Mass Function):** Gives the probability of each possible value of a discrete random variable.
- **PDF (Probability Density Function):** Describes probability density for a continuous random variable that has a density.
- **CDF (Cumulative Distribution Function):** Gives the probability that a random variable is less than or equal to a specified value.

The PMF and PDF describe probability in different ways, while the CDF can be used for discrete, continuous, and mixed random variables.

These concepts are essential for probability calculations, statistical analysis, and machine-learning interviews.

## 2. What Is a PMF?

A **Probability Mass Function (PMF)** gives the probability that a discrete random variable equals a particular value.

Its definition is:

$$
p_X(x) = P(X = x)
$$

Here:

- \(X\) is a discrete random variable.
- \(x\) is one of its possible values.
- \(P(X=x)\) is the probability that \(X\) equals \(x\).

### Properties of a PMF

**Property 1: Probabilities are nonnegative.**

$$
p_X(x) \geq 0
$$

**Property 2: The probabilities of all possible values sum to one.**

$$
\sum_x p_X(x) = 1
$$

### Example: Tossing a Coin Twice

Suppose a fair coin is tossed twice.

The sample space is:

$$
S = \{HH, HT, TH, TT\}
$$

Let \(X\) represent the number of heads.

| Outcome | Number of heads |
|---|---:|
| HH | 2 |
| HT | 1 |
| TH | 1 |
| TT | 0 |

The possible values are:

$$
X \in \{0,1,2\}
$$

The probability distribution is:

| Value \(x\) | Probability \(P(X=x)\) |
|---|---:|
| 0 | 0.25 |
| 1 | 0.50 |
| 2 | 0.25 |

Therefore:

$$
p_X(0) = 0.25
$$

$$
p_X(1) = 0.50
$$

$$
p_X(2) = 0.25
$$

The probabilities sum to one:

$$
0.25 + 0.50 + 0.25 = 1
$$

**Interpretation:** The probability of getting exactly one head in two fair coin tosses is 50%.

### When Is a PMF Used?

A PMF is used for discrete random variables, including:

- Number of defective products.
- Number of customers arriving in an hour.
- Number of purchases made by a customer.
- Number of emails received in a day.
- A binary outcome represented by 0 or 1.

## 3. What Is a PDF?

A **Probability Density Function (PDF)** describes the probability density of a continuous random variable.

It is commonly written as:

$$
f_X(x)
$$

Unlike a PMF, a PDF does not directly give the probability of an exact value. Instead, we calculate probabilities over intervals by integrating the density.

For a continuous random variable with PDF \(f_X(x)\):

$$
P(a \leq X \leq b) = \int_a^b f_X(x)\,dx
$$

Here, \(a\) and \(b\) are the endpoints of the interval.

### Properties of a PDF

**Property 1: The density is nonnegative.**

$$
f_X(x) \geq 0
$$

**Property 2: The total integral of the density equals one.**

$$
\int_{-\infty}^{\infty} f_X(x)\,dx = 1
$$

**Property 3: An individual point has probability zero.**

For a continuous random variable with a PDF:

$$
P(X=a) = 0
$$

This does not mean that the value \(a\) is impossible. It means that a single point has zero probability under a continuous distribution.

### Example: Uniform Distribution

Suppose \(X\) follows a continuous uniform distribution between 0 and 10.

Its PDF is:

$$
f_X(x) =
\begin{cases}
\frac{1}{10}, & 0 \leq x \leq 10 \\
0, & \text{otherwise}
\end{cases}
$$

The density is constant between 0 and 10.

The total area under the density is:

$$
\int_0^{10} \frac{1}{10}\,dx = 1
$$

Now calculate the probability that \(X\) lies between 2 and 5:

$$
P(2 \leq X \leq 5) = \int_2^5 \frac{1}{10}\,dx
$$

$$
P(2 \leq X \leq 5) = \frac{5-2}{10}
$$

$$
P(2 \leq X \leq 5) = 0.3
$$

The probability is 30%.

However, the probability of exactly 3 is:

$$
P(X=3) = 0
$$

### Important Difference Between Density and Probability

A PDF value is a density, not a probability.

A PDF can have a value greater than one, provided it is nonnegative and its integral over the entire domain equals one.

The probability of an interval depends on the area under the density curve, not simply the height of the curve at one point.

### When Is a PDF Used?

PDFs are commonly used to model continuous measurements, such as:

- Height and weight.
- Temperature.
- Travel time.
- Measurement errors.
- Certain financial quantities.

Common continuous distributions include the Normal, Uniform, and Exponential distributions.

## 4. What Is a CDF?

A **Cumulative Distribution Function (CDF)** gives the probability that a random variable is less than or equal to a specified value.

It is defined as:

$$
F_X(x) = P(X \leq x)
$$

A CDF can describe any random variable, including discrete, continuous, and mixed random variables.

### Properties of a CDF

**Property 1: The CDF lies between zero and one.**

$$
0 \leq F_X(x) \leq 1
$$

**Property 2: The CDF is nondecreasing.**

If \(a \leq b\), then:

$$
F_X(a) \leq F_X(b)
$$

This is because every outcome satisfying \(X \leq a\) also satisfies \(X \leq b\).

**Property 3: The limits of the CDF are zero and one.**

$$
\lim_{x \to -\infty} F_X(x) = 0
$$

$$
\lim_{x \to \infty} F_X(x) = 1
$$

**Property 4: A CDF is right-continuous.**

The CDF's value at a point agrees with its limit as the input approaches that point from the right.

### Example: CDF of the Number of Heads

Consider a fair coin tossed twice, and let \(X\) be the number of heads.

Its PMF is:

| Value \(x\) | Probability \(P(X=x)\) |
|---|---:|
| 0 | 0.25 |
| 1 | 0.50 |
| 2 | 0.25 |

At \(x=0\):

$$
F_X(0) = P(X \leq 0)
$$

$$
F_X(0) = P(X=0) = 0.25
$$

At \(x=1\):

$$
F_X(1) = P(X \leq 1)
$$

$$
F_X(1) = P(X=0) + P(X=1)
$$

$$
F_X(1) = 0.25 + 0.50 = 0.75
$$

At \(x=2\):

$$
F_X(2) = P(X \leq 2) = 1
$$

The CDF is therefore:

$$
F_X(x) =
\begin{cases}
0, & x < 0 \\
0.25, & 0 \leq x < 1 \\
0.75, & 1 \leq x < 2 \\
1, & x \geq 2
\end{cases}
$$

The CDF increases in steps because \(X\) is discrete.

### CDF of a Continuous Random Variable

For a continuous random variable with PDF \(f_X(x)\), the CDF is obtained by integrating the PDF from negative infinity to \(x\):

$$
F_X(x) = \int_{-\infty}^{x} f_X(t)\,dt
$$

For the uniform distribution between 0 and 10:

$$
F_X(x) =
\begin{cases}
0, & x < 0 \\
\frac{x}{10}, & 0 \leq x \leq 10 \\
1, & x > 10
\end{cases}
$$

For example:

$$
F_X(4) = P(X \leq 4) = \frac{4}{10} = 0.4
$$

This means that the probability of \(X\) being at most 4 is 40%.

## 5. PMF vs PDF vs CDF

| Feature | PMF | PDF | CDF |
|---|---|---|---|
| Full form | Probability Mass Function | Probability Density Function | Cumulative Distribution Function |
| Main purpose | Probability of an exact discrete value | Density of a continuous distribution | Probability up to a specified value |
| Applies to | Discrete random variables | Continuous random variables with a density | Any random variable |
| Notation | \(p_X(x)\) | \(f_X(x)\) | \(F_X(x)\) |
| Definition | \(P(X=x)\) | Density whose integral gives interval probability | \(P(X\leq x)\) |
| Probability calculation | Sum probabilities | Integrate density over an interval | Evaluate the CDF or take a CDF difference |
| Total probability | Sum equals one | Integral equals one | Approaches one as \(x\) approaches infinity |
| Exact point probability | Can be positive | Zero for a continuous distribution with a PDF | A jump can represent point probability |
| Typical shape | Values at discrete points | Density curve | Nondecreasing cumulative curve |

### Key Formulas

PMF:

$$
p_X(x) = P(X=x)
$$

PDF interval probability:

$$
P(a \leq X \leq b) = \int_a^b f_X(x)\,dx
$$

CDF:

$$
F_X(x) = P(X \leq x)
$$

For any random variable, the following formula gives the probability of the interval that excludes \(a\) and includes \(b\):

$$
P(a < X \leq b) = F_X(b) - F_X(a)
$$

This formula works for discrete, continuous, and mixed distributions.

For a continuous random variable with a PDF, individual points have zero probability. Therefore, including or excluding the endpoints does not change an interval's probability.

## 6. Relationship Between PMF, PDF, and CDF

PMF, PDF, and CDF are related ways of describing probability distributions.

### 6.1 For a Discrete Random Variable

The PMF gives the probability of each possible value.

The CDF accumulates the PMF probabilities up to the specified value:

$$
F_X(x) = \sum_{t \leq x} p_X(t)
$$

For example:

$$
F_X(1) = P(X=0) + P(X=1)
$$

The PMF describes the probability at each possible value, while the CDF accumulates those probabilities.

### 6.2 For a Continuous Random Variable

The PDF describes probability density.

The CDF is obtained by integrating the PDF:

$$
F_X(x) = \int_{-\infty}^{x} f_X(t)\,dt
$$

Where the CDF is differentiable, its derivative gives the PDF:

$$
f_X(x) = \frac{d}{dx}F_X(x)
$$

This relationship applies where the derivative exists and the distribution has a density.

### 6.3 Recovering Interval Probabilities

For any random variable:

$$
P(a < X \leq b) = F_X(b) - F_X(a)
$$

For a continuous random variable with a PDF, the same interval probability can be calculated using an integral:

$$
P(a \leq X \leq b) = \int_a^b f_X(x)\,dx
$$

For a discrete random variable, the CDF difference includes the probabilities of the values in the interval \((a,b]\).

## 7. Intuitive Analogy

Imagine tracking the time customers take to complete an online purchase.

### PMF: How Likely Is an Exact Count?

Suppose we record the number of items in a customer's basket.

The PMF can give the probability that a basket contains exactly three items:

$$
P(X=3)
$$

Because the number of items is discrete, the probability of an exact count can be positive.

### PDF: Where Are Continuous Values Concentrated?

Suppose we record how long each customer takes to complete a purchase.

The PDF describes where completion times are more or less densely concentrated.

A higher density near a particular time indicates greater concentration around that region. The density at a point is not the probability of that exact time.

### CDF: How Much Probability Has Accumulated?

The CDF gives the probability that a customer's completion time is no more than a specified duration.

For example:

$$
F_X(5) = P(X \leq 5)
$$

This represents the probability that the completion time is at most five time units, assuming the units have been defined.

## 8. Applications in Machine Learning

PMFs, PDFs, and CDFs are useful in probabilistic modeling, prediction, and uncertainty estimation.

### 8.1 Classification

In classification, the target variable is often discrete.

For a binary classification problem:

$$
Y \in \{0,1\}
$$

A model might estimate:

$$
P(Y=1 \mid X=x)
$$

This represents the probability that the target belongs to class 1 given the observed features.

A Bernoulli distribution can model a binary target. For a multiclass problem, a categorical distribution is commonly used.

### 8.2 Regression

Regression often predicts continuous values such as price, temperature, or delivery time.

A probabilistic regression model may estimate a conditional density:

$$
f_{Y \mid X}(y \mid x)
$$

This describes the conditional distribution of target \(Y\) given the input features \(X=x\).

Such a model can estimate interval probabilities and prediction uncertainty.

Some regression tasks predict counts instead, so the appropriate distribution depends on the target and modeling assumptions.

### 8.3 Likelihood and Model Training

Probability distributions are used to construct likelihood functions during model training.

Examples include:

- Bernoulli likelihood for binary outcomes.
- Categorical likelihood for multiclass outcomes.
- Poisson likelihood for counts under suitable assumptions.
- Normal likelihood for continuous targets under suitable assumptions.

The distribution should be chosen based on the target variable and the assumptions of the model.

### 8.4 Prediction Uncertainty

A CDF can answer questions about prediction uncertainty.

For example, if a model predicts a distribution for delivery time, its CDF can estimate the probability that a delivery takes no more than a specified duration.

Quantiles obtained from a CDF can also help construct prediction intervals and service-level estimates.

### 8.5 Generative Models

Generative models attempt to represent or learn probability distributions over data.

- PMFs can describe discrete outcomes, such as categories or tokens.
- PDFs can describe continuous quantities when a density exists.
- CDFs can be used to analyze cumulative probabilities and compare distributions.

## 9. Common Mistakes

### Mistake 1: Thinking a PDF Value Is an Exact Probability

A PDF value is a density.

For a continuous random variable with a PDF:

$$
P(X=a) = 0
$$

Interval probabilities require integration.

### Mistake 2: Thinking a CDF Is Only for Continuous Variables

A CDF is defined for any random variable:

$$
F_X(x) = P(X \leq x)
$$

It applies to discrete, continuous, and mixed distributions.

### Mistake 3: Confusing PMF and CDF

A PMF gives the probability of a particular discrete value.

A CDF gives the cumulative probability up to a specified value.

### Mistake 4: Assuming a PDF Must Be Less Than or Equal to One

A PDF can be greater than one. It must be nonnegative and integrate to one over its full domain.

### Mistake 5: Forgetting That a CDF Is Nondecreasing

A CDF cannot decrease as \(x\) increases because the event \(X \leq x\) expands or stays the same.

### Mistake 6: Assuming Every Random Variable Has a PDF

Some distributions are discrete, and some are mixed. A PDF alone does not describe every possible probability distribution.

### Mistake 7: Using the Wrong Interval Formula

For any random variable:

$$
P(a < X \leq b) = F_X(b) - F_X(a)
$$

For a discrete distribution, including or excluding an endpoint can change the probability.

For a continuous random variable with a PDF, endpoint inclusion does not change the probability because each individual point has probability zero.

## 10. Common Interview Questions and Answers

### Q1. What is a PMF?

**Answer:** A probability mass function gives the probability that a discrete random variable equals a specific value.

$$
p_X(x) = P(X=x)
$$

### Q2. What is a PDF?

**Answer:** A probability density function describes the density of a continuous random variable. Probabilities over intervals are calculated by integrating the PDF.

$$
P(a \leq X \leq b) = \int_a^b f_X(x)\,dx
$$

### Q3. What is a CDF?

**Answer:** A cumulative distribution function gives the probability that a random variable is less than or equal to a specified value.

$$
F_X(x) = P(X \leq x)
$$

### Q4. Can a PDF be greater than one?

**Answer:** Yes. A PDF represents density rather than point probability. It must be nonnegative and integrate to one over its domain.

### Q5. Can a CDF be used for a discrete random variable?

**Answer:** Yes. A CDF is defined for every random variable. For a discrete variable, it accumulates probabilities up to the specified value and typically has jumps.

### Q6. How do you calculate an interval probability using a CDF?

**Answer:** For any random variable:

$$
P(a < X \leq b) = F_X(b) - F_X(a)
$$

### Q7. What is the relationship between a PDF and a CDF?

**Answer:** For a continuous random variable with a PDF, the CDF is the integral of the PDF from negative infinity to \(x\). Where the CDF is differentiable, its derivative equals the PDF.

### Q8. Why is the probability of an exact point zero for a continuous random variable with a PDF?

**Answer:** Probability is calculated by integrating the density over a set. A single point has zero width, so its probability is zero. An interval can still have positive probability.

### Q9. What is the difference between a PMF and a PDF?

**Answer:** A PMF directly assigns probabilities to discrete values. A PDF describes density, and the probability of an interval is calculated by integrating that density.

### Q10. How are PMF, PDF, and CDF used in machine learning?

**Answer:** They help model discrete and continuous targets, calculate likelihoods, estimate class probabilities, quantify uncertainty, and evaluate probabilities of outcomes or intervals.

## 11. Key Takeaways

- PMF gives the probability of an exact value for a discrete random variable.
- PDF describes the density of a continuous random variable when a density exists.
- CDF gives the probability that a random variable is less than or equal to a specified value.
- PMF probabilities sum to one.
- A PDF integrates to one.
- The probability of an exact point is zero for a continuous random variable with a PDF.
- A PDF can be greater than one because it represents density, not point probability.
- CDFs can describe discrete, continuous, and mixed distributions.
- CDF differences provide interval probabilities.
- These concepts are important for probability calculations and probabilistic machine-learning models.

## 12. Practice Problems

### Problem 1: PMF Calculation

A fair coin is tossed twice. Let \(X\) be the number of heads.

Calculate:

1. \(P(X=0)\)
2. \(P(X=1)\)
3. \(P(X=2)\)

#### Solution

The sample space is:

$$
S = \{HH,HT,TH,TT\}
$$

There is one outcome with zero heads:

$$
P(X=0) = \frac{1}{4} = 0.25
$$

There are two outcomes with one head:

$$
P(X=1) = \frac{2}{4} = 0.50
$$

There is one outcome with two heads:

$$
P(X=2) = \frac{1}{4} = 0.25
$$

The probabilities sum to one:

$$
0.25 + 0.50 + 0.25 = 1
$$

### Problem 2: PDF Calculation

Suppose \(X\) is uniformly distributed between 0 and 10.

Calculate:

$$
P(3 \leq X \leq 7)
$$

#### Solution

The PDF is:

$$
f_X(x) = \frac{1}{10}
\quad \text{for } 0 \leq x \leq 10
$$

Therefore:

$$
P(3 \leq X \leq 7) = \int_3^7 \frac{1}{10}\,dx
$$

$$
P(3 \leq X \leq 7) = \frac{7-3}{10}
$$

$$
P(3 \leq X \leq 7) = 0.4
$$

The probability is 40%.

### Problem 3: CDF Calculation

Suppose \(X\) is uniformly distributed between 0 and 10.

Calculate:

$$
F_X(6) = P(X \leq 6)
$$

#### Solution

For this uniform distribution:

$$
F_X(x) = \frac{x}{10}
\quad \text{for } 0 \leq x \leq 10
$$

Therefore:

$$
F_X(6) = \frac{6}{10} = 0.6
$$

The probability that \(X\) is at most 6 is 60%.

### Problem 4: Use the CDF to Calculate an Interval Probability

Suppose a random variable has the following CDF values:

$$
F_X(2) = 0.30
$$

$$
F_X(5) = 0.80
$$

Calculate:

$$
P(2 < X \leq 5)
$$

#### Solution

Use the CDF difference:

$$
P(2 < X \leq 5) = F_X(5) - F_X(2)
$$

$$
P(2 < X \leq 5) = 0.80 - 0.30
$$

$$
P(2 < X \leq 5) = 0.50
$$

The probability is 50%.

### Problem 5: Interview Challenge

A continuous random variable has a PDF. An interviewer asks whether its PDF value at \(x=2\) can be 1.5.

Is this possible?

#### Solution

Yes. A PDF can have a value greater than one, provided it remains nonnegative and its integral over the full domain equals one.

The value \(f_X(2)=1.5\) is a density, not the probability that \(X=2\).

For a continuous random variable with a PDF:

$$
P(X=2) = 0
$$

---

**Final reminder:** PMF gives discrete point probabilities, PDF describes continuous probability density, and CDF gives cumulative probability for any random variable.
