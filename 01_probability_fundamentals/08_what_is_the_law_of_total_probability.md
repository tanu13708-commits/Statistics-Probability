# Q8. What Is the Law of Total Probability?

## 1. Introduction

The **Law of Total Probability** is a fundamental rule in probability that allows us to calculate the probability of an event by dividing the sample space into multiple mutually exclusive and collectively exhaustive cases.

Instead of calculating the probability of an event directly, we calculate its probability under each possible case and then combine the results.

It is particularly useful when an event can occur through several different scenarios.

**Intuition:** If there are multiple ways for something to happen, calculate the probability of each way and add their contributions, accounting for how likely each scenario is.

## 2. Formal Definition

Suppose \(B_1, B_2, \ldots, B_n\) form a partition of the sample space. This means:

- They are mutually exclusive: no two events can occur simultaneously.
- They are collectively exhaustive: at least one of these events must occur.
- Each event has a well-defined probability.

For any event \(A\), the Law of Total Probability states:

$$
P(A) = \sum_{i=1}^{n} P(A \mid B_i)P(B_i)
$$

Expanded form:

$$
\begin{aligned}
P(A) ={}& P(A \mid B_1)P(B_1) \\
&+ P(A \mid B_2)P(B_2) \\
&+ \cdots \\
&+ P(A \mid B_n)P(B_n)
\end{aligned}
$$

Here:

- \(P(A)\): overall probability of event \(A\).
- \(P(B_i)\): probability of scenario \(B_i\).
- \(P(A \mid B_i)\): probability of event \(A\) occurring under scenario \(B_i\).

Each term represents the contribution of one scenario to the overall probability.

## 3. Understanding Through an Intuitive Example

Imagine a company receives products from two factories.

- Factory A supplies 60% of all products.
- Factory B supplies 40% of all products.
- Factory A has a defect rate of 2%.
- Factory B has a defect rate of 5%.

Suppose we randomly select one product. What is the probability that it is defective?

Define:

- \(A\): the product came from Factory A.
- \(B\): the product came from Factory B.
- \(D\): the product is defective.

Given:

$$
P(A) = 0.60
$$

$$
P(B) = 0.40
$$

$$
P(D \mid A) = 0.02
$$

$$
P(D \mid B) = 0.05
$$

Since the product must come from either Factory A or Factory B, these factories form a partition of the sample space.

Applying the Law of Total Probability:

$$
P(D) = P(D \mid A)P(A) + P(D \mid B)P(B)
$$

Substitute the values:

$$
P(D) = (0.02)(0.60) + (0.05)(0.40)
$$

$$
P(D) = 0.012 + 0.020
$$

$$
P(D) = 0.032
$$

Therefore:

$$
\boxed{P(D) = 0.032 = 3.2\%}
$$

**Interpretation:** The probability that a randomly selected product is defective is 3.2%.

Notice that we did not simply average the two defect rates. We weighted each defect rate by the proportion of products supplied by its factory.

## 4. Why Do We Multiply and Then Add?

The formula follows directly from two probability principles.

### Step 1: Calculate each scenario's contribution

The probability that a product comes from Factory A and is defective is:

$$
P(D \cap A) = P(D \mid A)P(A)
$$

Similarly, for Factory B:

$$
P(D \cap B) = P(D \mid B)P(B)
$$

### Step 2: Add the contributions

Because a product cannot come from both factories at once, the events \(D \cap A\) and \(D \cap B\) are mutually exclusive.

Therefore:

$$
P(D) = P(D \cap A) + P(D \cap B)
$$

Combining these expressions gives:

$$
P(D) = P(D \mid A)P(A) + P(D \mid B)P(B)
$$

This is the Law of Total Probability.

## 5. Visualizing the Concept

Think of all products as belonging to two groups:

- 60% come from Factory A, and 2% of those are defective.
- 40% come from Factory B, and 5% of those are defective.

The overall defective probability combines the weighted contributions:

$$
\underbrace{0.60 \times 0.02}_{\text{Factory A: }1.2\%}
+
\underbrace{0.40 \times 0.05}_{\text{Factory B: }2.0\%}
=
3.2\%
$$

Factory B has the higher defect rate, but Factory A supplies more products. Both the defect rate and the size of each group affect the overall result.

## 6. Relationship to Conditional Probability and Bayes' Theorem

The Law of Total Probability is closely related to conditional probability and Bayes' theorem.

### Conditional probability

The conditional probability formula is:

$$
P(A \mid B) = \frac{P(A \cap B)}{P(B)}
$$

Rearranging:

$$
P(A \cap B) = P(A \mid B)P(B)
$$

This lets us calculate the joint probability of an event and a scenario.

### Law of Total Probability

If \(B_1, B_2, \ldots, B_n\) partition the sample space, then:

$$
P(A) = \sum_{i=1}^{n} P(A \mid B_i)P(B_i)
$$

This combines the joint probabilities across all possible scenarios.

### Bayes' theorem

Bayes' theorem uses the overall probability calculated by the Law of Total Probability to reverse a conditional probability:

$$
P(B_j \mid A)
=
\frac{P(A \mid B_j)P(B_j)}{P(A)}
$$

Substituting the total probability expression for \(P(A)\):

$$
P(B_j \mid A)
=
\frac{P(A \mid B_j)P(B_j)}
{\sum_{i=1}^{n} P(A \mid B_i)P(B_i)}
$$

In the factory example, the Law of Total Probability calculates the probability of a defective product. Bayes' theorem can then calculate the probability that a defective product came from Factory A.

## 7. Applications in Machine Learning

The Law of Total Probability appears in several important machine learning concepts.

### 7.1 Naive Bayes classification

Suppose \(X\) represents observed features and \(Y\) represents a class label.

The overall probability of observing the features is:

$$
P(X) = \sum_y P(X \mid Y=y)P(Y=y)
$$

This sums the probability of observing \(X\) across all possible classes.

Bayes' theorem then gives:

$$
P(Y=y \mid X)
=
\frac{P(X \mid Y=y)P(Y=y)}{P(X)}
$$

The denominator normalizes the class scores into posterior probabilities when the model is properly specified.

### 7.2 Probabilistic classification

Many classifiers estimate the probability of different outcomes. Total probability helps express a marginal probability by summing over hidden or unobserved categories.

For example, the probability of a customer making a purchase can be expressed by summing purchase probabilities across customer segments:

$$
P(\text{Purchase})
=
\sum_s P(\text{Purchase} \mid S=s)P(S=s)
$$

Here, \(S\) represents a customer segment.

### 7.3 Hidden-variable models

In probabilistic models, an observed variable may depend on an unobserved variable \(Z\). To obtain the marginal probability of the observation, we sum over the possible values of \(Z\):

$$
P(X) = \sum_z P(X \mid Z=z)P(Z=z)
$$

For continuous latent variables, the corresponding operation is integration:

$$
P(X) = \int P(X \mid Z=z)p_Z(z)\,dz
$$

This idea is important in latent-variable models, mixture models, and probabilistic inference.

## 8. Common Mistakes

### Mistake 1: Taking an unweighted average

Incorrect:

$$
P(D) = \frac{P(D \mid A)+P(D \mid B)}{2}
$$

This is only valid in the two-scenario example if the scenarios are equally likely.

Correct:

$$
P(D) = P(D \mid A)P(A)+P(D \mid B)P(B)
$$

### Mistake 2: Using scenarios that do not cover all possibilities

The scenarios must collectively cover the entire sample space. Otherwise, some possible outcomes may be omitted.

### Mistake 3: Using overlapping scenarios

The standard partition formula requires the scenarios to be mutually exclusive. If they overlap, simply adding their contributions can double-count outcomes.

### Mistake 4: Confusing \(P(A \mid B)\) with \(P(B \mid A)\)

In general:

$$
P(A \mid B) \ne P(B \mid A)
$$

The probability of a defective product given its factory is not the same as the probability of a factory given that the product is defective.

## 9. Interview Questions and Answers

### Q1. What is the Law of Total Probability?

It calculates the probability of an event by summing its conditional probabilities across a partition of the sample space, weighted by the probabilities of the partition events.

$$
P(A) = \sum_{i=1}^{n} P(A \mid B_i)P(B_i)
$$

### Q2. What conditions must the events \(B_i\) satisfy?

They must be mutually exclusive and collectively exhaustive, so every possible outcome belongs to exactly one partition event.

### Q3. How is it different from Bayes' theorem?

The Law of Total Probability calculates a marginal probability from conditional probabilities. Bayes' theorem uses that marginal probability to calculate a posterior probability.

### Q4. Why is this law important in Naive Bayes?

It allows us to calculate the marginal probability of observed features by summing over possible classes:

$$
P(X) = \sum_y P(X \mid Y=y)P(Y=y)
$$

This probability appears in the denominator of Bayes' theorem.

### Q5. Can the Law of Total Probability be used with continuous variables?

Yes. When conditioning on a continuous variable \(Z\), summation is replaced by integration:

$$
P(A) = \int P(A \mid Z=z)p_Z(z)\,dz
$$

### Q6. Is the Law of Total Probability the same as the addition rule?

No. The addition rule calculates the probability of a union of events. The Law of Total Probability partitions the sample space and combines the contributions to an event from each partition.

## 10. Key Takeaways

- The Law of Total Probability calculates an overall probability by combining multiple possible scenarios.
- Each conditional probability is weighted by the probability of its corresponding scenario.
- The scenarios must form a partition: they must be mutually exclusive and collectively exhaustive.
- The formula is:

$$
P(A) = \sum_{i=1}^{n} P(A \mid B_i)P(B_i)
$$

- It is closely connected to conditional probability and Bayes' theorem.
- It is useful in Naive Bayes, probabilistic classification, mixture models, and latent-variable models.
- **Interview tip:** Explain why probabilities are weighted before adding them, rather than just memorizing the formula.
