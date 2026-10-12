# Q8. What Is the Law of Total Probability?

## 1. Introduction

The **Law of Total Probability** is a fundamental rule that calculates the probability of an event by considering all possible, mutually exclusive scenarios in which that event can occur.

Instead of calculating the probability directly, we calculate the probability of the event under each scenario, weight it by the probability of that scenario, and add the results.

**Intuition:** If an outcome can happen through several different scenarios, calculate each scenario's contribution and add those contributions together.

## 2. Formal Definition

Suppose \(B_1, B_2, \ldots, B_n\) form a partition of the sample space \(\Omega\). This means:

1. **Mutually exclusive:** No two partition events can occur simultaneously.
2. **Collectively exhaustive:** Their union covers the entire sample space.
3. Each event has a well-defined probability.

Mathematically, for distinct \(i\) and \(j\),

$$
B_i \cap B_j = \varnothing
$$

and

$$
\bigcup_{i=1}^{n} B_i = \Omega
$$

For any event \(A\), the Law of Total Probability states:

$$
P(A) = \sum_{i=1}^{n} P(A \mid B_i)P(B_i)
$$

This formula assumes that the conditional probabilities are defined for the partition events with positive probability. Terms for zero-probability partition events contribute zero and can be omitted.

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
- \(P(A \mid B_i)\): probability of event \(A\), given that scenario \(B_i\) occurs.

Each term, \(P(A \mid B_i)P(B_i)\), is the joint probability \(P(A \cap B_i)\).

## 3. Worked Example: Defective Products

Suppose a company receives products from two factories:

- Factory A supplies 60% of all products.
- Factory B supplies 40% of all products.
- Factory A has a defect rate of 2%.
- Factory B has a defect rate of 5%.

A product is selected randomly. What is the probability that it is defective?

Define the events:

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

Since every product comes from exactly one of these two factories, \(A\) and \(B\) form a partition of the sample space.

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

**Interpretation:** A randomly selected product has a 3.2% probability of being defective.

Notice that we do not simply average the two defect rates. Each defect rate is weighted by the proportion of products supplied by that factory.

## 4. Why Do We Multiply and Then Add?

The formula follows from conditional probability and the addition rule for mutually exclusive events.

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

Because a product cannot come from both factories, the events \(D \cap A\) and \(D \cap B\) are mutually exclusive.

Therefore:

$$
P(D) = P(D \cap A) + P(D \cap B)
$$

Substituting the expressions from Step 1 gives:

$$
P(D) = P(D \mid A)P(A) + P(D \mid B)P(B)
$$

This is the Law of Total Probability for two partition events.

## 5. Intuitive Interpretation

Think of all products as belonging to two groups:

- 60% come from Factory A, and 2% of those are defective.
- 40% come from Factory B, and 5% of those are defective.

Their contributions to the overall defective probability are:

$$
\underbrace{0.60 \times 0.02}_{\text{Factory A: }1.2\%}
+
\underbrace{0.40 \times 0.05}_{\text{Factory B: }2.0\%}
=
3.2\%
$$

Factory B has a higher defect rate, but Factory A supplies more products. Both the defect rate and the size of each group affect the overall result.

## 6. Relationship to Conditional Probability and Bayes' Theorem

These three concepts are closely related, but they serve different purposes.

### 6.1 Conditional probability

For events \(A\) and \(B\), provided \(P(B) > 0\):

$$
P(A \mid B) = \frac{P(A \cap B)}{P(B)}
$$

Rearranging gives:

$$
P(A \cap B) = P(A \mid B)P(B)
$$

This calculates the joint probability of \(A\) and \(B\).

### 6.2 Law of Total Probability

If \(B_1, B_2, \ldots, B_n\) form a partition, then:

$$
P(A) = \sum_{i=1}^{n} P(A \mid B_i)P(B_i)
$$

This combines the contributions from every partition event to calculate the overall probability of \(A\).

### 6.3 Bayes' theorem

Bayes' theorem calculates the probability of a scenario after observing an event:

$$
P(B_j \mid A) =
\frac{P(A \mid B_j)P(B_j)}{P(A)}
$$

Substituting the Law of Total Probability for the denominator gives:

$$
P(B_j \mid A) =
\frac{P(A \mid B_j)P(B_j)}
{\sum_{i=1}^{n} P(A \mid B_i)P(B_i)}
$$

This form applies when \(P(A) > 0\).

**Example:** We already calculated that the probability of a defective product is 3.2%. We can now use Bayes' theorem to find the probability that a defective product came from Factory A:

$$
P(A \mid D) =
\frac{P(D \mid A)P(A)}{P(D)}
$$

$$
P(A \mid D) = \frac{0.02 \times 0.60}{0.032}
$$

$$
P(A \mid D) = \frac{0.012}{0.032} = 0.375
$$

Therefore:

$$
\boxed{P(A \mid D) = 37.5\%}
$$

Although Factory A supplies 60% of all products, only 37.5% of defective products are expected to come from Factory A, because its defect rate is lower.

## 7. Applications in Machine Learning

### 7.1 Naive Bayes classification

Let \(X\) represent the observed features and \(Y\) represent the class label.

For discrete classes, the marginal probability of the features is:

$$
P(X) = \sum_y P(X \mid Y=y)P(Y=y)
$$

This sums the probability of observing \(X\) across all possible classes.

Bayes' theorem then gives:

$$
P(Y=y \mid X) =
\frac{P(X \mid Y=y)P(Y=y)}{P(X)}
$$

Substituting the marginal probability:

$$
P(Y=y \mid X) =
\frac{P(X \mid Y=y)P(Y=y)}
{\sum_{y'} P(X \mid Y=y')P(Y=y')}
$$

Here, \(y'\) ranges over all possible class labels.

Naive Bayes additionally assumes that features are conditionally independent given the class. For features \(X_1, \ldots, X_m\), this assumption gives:

$$
P(X_1, \ldots, X_m \mid Y=y)
=
\prod_{k=1}^{m} P(X_k \mid Y=y)
$$

The Law of Total Probability calculates the denominator, while the conditional independence assumption simplifies the likelihood in the numerator.

### 7.2 Customer behavior prediction

Suppose customers belong to different segments, represented by \(S\). The probability that a randomly selected customer makes a purchase can be calculated as:

$$
P(\text{Purchase}) =
\sum_s P(\text{Purchase} \mid S=s)P(S=s)
$$

This is useful when purchase behavior differs between customer segments.

### 7.3 Hidden-variable models

Suppose an observed variable \(X\) depends on a discrete latent variable \(Z\). To calculate the marginal probability of \(X\), sum over the possible values of \(Z\):

$$
P(X=x) = \sum_z P(X=x \mid Z=z)P(Z=z)
$$

For a continuous latent variable \(Z\), the corresponding expression is:

$$
p_X(x) = \int p_{X \mid Z}(x \mid z)p_Z(z)\,dz
$$

This is the continuous-variable version of marginalization and is important in mixture models and other latent-variable models.

## 8. Common Mistakes

### Mistake 1: Taking an unweighted average

Incorrect in the general case:

$$
P(D) = \frac{P(D \mid A) + P(D \mid B)}{2}
$$

This expression is valid for the two-factory example only when the factories are equally likely to supply the selected product.

Correct:

$$
P(D) = P(D \mid A)P(A) + P(D \mid B)P(B)
$$

### Mistake 2: Using scenarios that do not cover all possibilities

The partition must cover the entire sample space. Otherwise, the calculation may omit possible ways in which the event can occur.

### Mistake 3: Using overlapping scenarios

The standard formula requires mutually exclusive partition events. If scenarios overlap, directly adding their contributions can double-count outcomes. Use a valid partition or account for the overlaps correctly.

### Mistake 4: Confusing conditional probabilities

In general:

$$
P(A \mid B) \ne P(B \mid A)
$$

The probability of a product being defective given its factory is not the same as the probability of a factory given that the product is defective.

### Mistake 5: Confusing the law with independence

The Law of Total Probability does not require \(A\) and \(B_i\) to be independent. It uses conditional probabilities precisely so that the relationship between the event and each scenario is accounted for.

## 9. Interview Questions and Answers

### Q1. What is the Law of Total Probability?

It calculates the probability of an event by summing its conditional probabilities across a partition of the sample space, weighted by the probabilities of the partition events.

$$
P(A) = \sum_{i=1}^{n} P(A \mid B_i)P(B_i)
$$

### Q2. What conditions must the events \(B_i\) satisfy?

They must be mutually exclusive and collectively exhaustive. Together, they partition the sample space.

### Q3. Why are the conditional probabilities weighted?

Because the scenarios may have different probabilities. A scenario that occurs more often generally contributes more to the overall probability, all else being equal.

### Q4. How is the Law of Total Probability different from Bayes' theorem?

The Law of Total Probability calculates an overall or marginal probability. Bayes' theorem uses that probability to calculate a conditional probability in the reverse direction.

### Q5. Does the law require independence?

No. The formula uses \(P(A \mid B_i)\), so it remains valid even when \(A\) and the partition events are dependent.

### Q6. Can the law be used with continuous random variables?

Yes. For a continuous conditioning variable \(Z\), summation is replaced by integration. For an event \(A\):

$$
P(A) = \int P(A \mid Z=z)p_Z(z)\,dz
$$

This expression assumes a suitable conditional probability model and density for \(Z\).

### Q7. How does the law appear in Naive Bayes?

It calculates the marginal probability of the observed features by summing across possible classes:

$$
P(X) = \sum_y P(X \mid Y=y)P(Y=y)
$$

This marginal probability appears in the denominator of Bayes' theorem.

### Q8. Is the Law of Total Probability the same as the addition rule?

No. The addition rule calculates the probability of a union of events. The Law of Total Probability calculates the probability of an event by splitting it across a partition and adding the resulting disjoint contributions.

## 10. Key Takeaways

- The Law of Total Probability calculates an overall probability by combining possible scenarios.
- Each conditional probability is weighted by the probability of its corresponding scenario.
- The scenarios must be mutually exclusive and collectively exhaustive.
- The general formula is:

$$
P(A) = \sum_{i=1}^{n} P(A \mid B_i)P(B_i)
$$

- The law does not require independence.
- It is closely connected to conditional probability, Bayes' theorem, and marginalization.
- In machine learning, it is used in Naive Bayes, probabilistic classification, and latent-variable models.
- **Interview tip:** Explain why each conditional probability is weighted by the probability of its scenario before the contributions are added.
