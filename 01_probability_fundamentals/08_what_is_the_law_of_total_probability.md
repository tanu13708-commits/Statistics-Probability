# Q8. What Is the Law of Total Probability?

## 1. Introduction

The **Law of Total Probability** is a rule for calculating the probability of an event by dividing the sample space into mutually exclusive and collectively exhaustive cases.

Instead of calculating the probability of an event directly, we calculate its probability under each case, multiply it by the probability of that case, and add the contributions.

**Intuition:** Calculate how much each possible scenario contributes to the overall probability, then add those contributions together.

## 2. Formal Definition

Suppose \(B_1, B_2, \ldots, B_n\) form a partition of the sample space \(\Omega\). This means:

1. **Mutually exclusive:** No two distinct partition events can occur simultaneously.
2. **Collectively exhaustive:** The partition events cover the entire sample space.

Mathematically, for \(i \ne j\),

$$
B_i \cap B_j = \varnothing
$$

and

$$
\bigcup_{i=1}^{n} B_i = \Omega
$$

For any event \(A\), the Law of Total Probability is:

$$
P(A) = \sum_{i=1}^{n} P(A \mid B_i)P(B_i)
$$

Here:

- \(P(A)\) is the overall probability of event \(A\).
- \(P(B_i)\) is the probability of scenario \(B_i\).
- \(P(A \mid B_i)\) is the probability of \(A\), given that \(B_i\) occurs.

The conditional probability \(P(A \mid B_i)\) is defined when \(P(B_i)>0\). Zero-probability partition events can be omitted from the sum.

By the multiplication rule,

$$
P(A \cap B_i) = P(A \mid B_i)P(B_i)
$$

Therefore, the Law of Total Probability can also be written as:

$$
P(A) = \sum_{i=1}^{n} P(A \cap B_i)
$$

This works because the events \(A \cap B_i\) are mutually exclusive and together cover event \(A\).

## 3. Worked Example: Defective Products

Suppose a company receives products from two factories:

- Factory A supplies 60% of the products.
- Factory B supplies 40% of the products.
- 2% of Factory A's products are defective.
- 5% of Factory B's products are defective.

A product is selected randomly. What is the probability that it is defective?

Define the events:

- \(A\): The product came from Factory A.
- \(B\): The product came from Factory B.
- \(D\): The product is defective.

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

Assume every product comes from exactly one of these two factories. Thus, \(A\) and \(B\) form a partition of the sample space.

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

Therefore,

$$
\boxed{P(D) = 3.2\%}
$$

**Interpretation:** A randomly selected product has a 3.2% probability of being defective.

We do not simply average the two defect rates. Each rate is weighted by the proportion of products supplied by its factory.

## 4. Why Do We Multiply and Then Add?

The formula follows from the multiplication rule and the addition rule for mutually exclusive events.

### Step 1: Calculate each scenario's contribution

The probability that a product came from Factory A and is defective is:

$$
P(D \cap A) = P(D \mid A)P(A)
$$

Similarly, for Factory B:

$$
P(D \cap B) = P(D \mid B)P(B)
$$

### Step 2: Add the contributions

The events \(D \cap A\) and \(D \cap B\) are mutually exclusive because a product cannot come from both factories under our assumption.

Therefore,

$$
P(D) = P(D \cap A) + P(D \cap B)
$$

Substituting the multiplication-rule expressions gives:

$$
P(D) = P(D \mid A)P(A) + P(D \mid B)P(B)
$$

This is the Law of Total Probability for two partition events.

## 5. Intuitive Interpretation

The overall defect probability combines two weighted contributions:

$$
\underbrace{0.60 \times 0.02}_{\text{Factory A: }1.2\%}
+
\underbrace{0.40 \times 0.05}_{\text{Factory B: }2.0\%}
=
3.2\%
$$

Factory B has a higher defect rate, but it supplies fewer products. The overall probability depends on both the defect rate and the probability that a randomly selected product comes from each factory.

## 6. Relationship to Conditional Probability and Bayes' Theorem

These concepts are connected, but they answer different questions.

### 6.1 Conditional Probability

For events \(A\) and \(B\), when \(P(B)>0\),

$$
P(A \mid B) = \frac{P(A \cap B)}{P(B)}
$$

Rearranging gives the multiplication rule:

$$
P(A \cap B) = P(A \mid B)P(B)
$$

This calculates the probability that both \(A\) and \(B\) occur.

### 6.2 Law of Total Probability

If \(B_1, B_2, \ldots, B_n\) form a partition, then:

$$
P(A) = \sum_{i=1}^{n} P(A \mid B_i)P(B_i)
$$

This calculates the overall probability of \(A\) by combining its contributions across the partition.

### 6.3 Bayes' Theorem

Bayes' theorem calculates the probability of a scenario after observing an event:

$$
P(B_j \mid A) =
\frac{P(A \mid B_j)P(B_j)}{P(A)}
$$

When the \(B_i\) events form a partition and \(P(A)>0\), substituting the Law of Total Probability into the denominator gives:

$$
P(B_j \mid A) =
\frac{P(A \mid B_j)P(B_j)}
{\sum_{i=1}^{n} P(A \mid B_i)P(B_i)}
$$

**Example:** We know that the probability of a defective product is 3.2%. What is the probability that a defective product came from Factory A?

$$
P(A \mid D) =
\frac{P(D \mid A)P(A)}{P(D)}
$$

Substitute the values:

$$
P(A \mid D) = \frac{0.02 \times 0.60}{0.032}
$$

$$
P(A \mid D) = \frac{0.012}{0.032} = 0.375
$$

Therefore,

$$
\boxed{P(A \mid D) = 37.5\%}
$$

Although Factory A supplies 60% of all products, it accounts for 37.5% of defective products in probability terms because its defect rate is lower than Factory B's.

## 7. Applications in Machine Learning

### 7.1 Naive Bayes Classification

Let \(X\) represent the observed features and \(Y\) represent a discrete class label.

The marginal probability of the features is:

$$
P(X) = \sum_y P(X \mid Y=y)P(Y=y)
$$

The sum is over all possible class labels.

Bayes' theorem gives:

$$
P(Y=y \mid X) =
\frac{P(X \mid Y=y)P(Y=y)}{P(X)}
$$

Substituting the marginal probability gives:

$$
P(Y=y \mid X) =
\frac{P(X \mid Y=y)P(Y=y)}
{\sum_{y'} P(X \mid Y=y')P(Y=y')}
$$

Here, \(y'\) ranges over all possible class labels.

Naive Bayes also makes a **conditional independence assumption**: given the class, the features are assumed to be conditionally independent. For features \(X_1, \ldots, X_m\), this is written as:

$$
P(X_1, \ldots, X_m \mid Y=y)
=
\prod_{k=1}^{m} P(X_k \mid Y=y)
$$

This assumption simplifies the likelihood \(P(X \mid Y=y)\). The Law of Total Probability expresses the denominator \(P(X)\) as a sum across the possible classes.

### 7.2 Customer Behavior Prediction

Suppose customers belong to discrete segments represented by \(S\). The probability that a randomly selected customer makes a purchase is:

$$
P(\text{Purchase}) =
\sum_s P(\text{Purchase} \mid S=s)P(S=s)
$$

This is useful when purchase behavior differs across customer segments.

### 7.3 Hidden-Variable Models

Suppose an observed random variable \(X\) depends on a discrete latent variable \(Z\). Its marginal probability is obtained by summing over the possible values of \(Z\):

$$
P(X=x) = \sum_z P(X=x \mid Z=z)P(Z=z)
$$

For a continuous latent variable \(Z\), the corresponding density formula is:

$$
p_X(x) = \int p_{X \mid Z}(x \mid z)p_Z(z)\,dz
$$

This is a form of marginalization and appears in mixture models and other latent-variable models.

## 8. Common Mistakes

### Mistake 1: Taking an Unweighted Average

A simple average of conditional probabilities is not generally correct:

$$
P(D) = \frac{P(D \mid A) + P(D \mid B)}{2}
$$

This equals the correct weighted formula only in special cases, such as when the two factories are equally likely to supply the selected product.

The correct formula is:

$$
P(D) = P(D \mid A)P(A) + P(D \mid B)P(B)
$$

### Mistake 2: Failing to Cover All Possibilities

The partition events must cover the entire sample space. If a possible scenario is omitted, the calculation may fail to include all contributions to \(P(A)\).

### Mistake 3: Using Overlapping Scenarios

The standard formula requires mutually exclusive partition events. If scenarios overlap, adding their contributions directly may count some outcomes more than once. Use a valid partition or account for the overlap appropriately.

### Mistake 4: Reversing Conditional Probabilities

In general,

$$
P(A \mid B) \ne P(B \mid A)
$$

The probability that a product is defective given its factory is not the same as the probability that it came from a particular factory given that it is defective.

### Mistake 5: Assuming Independence Is Required

The Law of Total Probability does **not** require \(A\) to be independent of the partition events. The conditional probabilities \(P(A \mid B_i)\) account for how the probability of \(A\) may differ across scenarios.

## 9. Interview Questions and Answers

### Q1. What is the Law of Total Probability?

It calculates the probability of an event by summing its conditional probabilities across a partition of the sample space, weighted by the probabilities of the partition events.

$$
P(A) = \sum_{i=1}^{n} P(A \mid B_i)P(B_i)
$$

### Q2. What conditions must the events \(B_i\) satisfy?

They must be mutually exclusive and collectively exhaustive. Together, they form a partition of the sample space.

### Q3. Why are conditional probabilities weighted?

The scenarios can have different probabilities. Weighting each conditional probability by the probability of its scenario accounts for how frequently that scenario occurs.

### Q4. How is the Law of Total Probability different from Bayes' theorem?

The Law of Total Probability calculates a marginal probability from a partition. Bayes' theorem uses that marginal probability to calculate a posterior conditional probability.

### Q5. Does the law require independence?

No. It remains valid whether or not \(A\) is independent of the partition events.

### Q6. Can the law be used with a continuous random variable?

Yes. If \(Z\) is a continuous conditioning variable with density \(p_Z(z)\), then for an event \(A\):

$$
P(A) = \int P(A \mid Z=z)p_Z(z)\,dz
$$

This expression averages the conditional probability over the distribution of \(Z\), under the usual conditions for conditional probabilities and integration.

### Q7. How does the law appear in Naive Bayes?

It expresses the marginal probability of the observed features as a sum over the possible classes:

$$
P(X) = \sum_y P(X \mid Y=y)P(Y=y)
$$

This marginal probability is the denominator in Bayes' theorem. Naive Bayes separately uses conditional independence to simplify the feature likelihood.

### Q8. Is the Law of Total Probability the same as the addition rule?

No. The addition rule gives the probability of a union of events. The Law of Total Probability applies the addition rule to the disjoint pieces \(A \cap B_i\) created by a partition.

## 10. Key Takeaways

- The Law of Total Probability calculates an overall probability by combining all scenarios in a partition.
- The partition events must be mutually exclusive and collectively exhaustive.
- Each conditional probability is weighted by the probability of its corresponding scenario.
- The general formula is:

$$
P(A) = \sum_{i=1}^{n} P(A \mid B_i)P(B_i)
$$

- The law does not require independence.
- It is closely related to conditional probability, Bayes' theorem, and marginalization.
- In machine learning, it appears in Naive Bayes, probabilistic classification, and latent-variable models.
- **Interview tip:** Explain why the conditional probabilities are weighted by the probabilities of their scenarios instead of simply averaged.

## 11. Quick Practice Question

A website receives 70% of its visitors from mobile devices and 30% from desktop devices. The probability of a purchase is 4% for mobile visitors and 6% for desktop visitors.

What is the overall probability that a randomly selected visitor makes a purchase?

Using the Law of Total Probability:

$$
\begin{aligned}
P(\text{Purchase}) ={}&
P(\text{Purchase} \mid \text{Mobile})P(\text{Mobile}) \\
&+ P(\text{Purchase} \mid \text{Desktop})P(\text{Desktop})
\end{aligned}
$$

Substitute the values:

$$
P(\text{Purchase}) = (0.04)(0.70) + (0.06)(0.30)
$$

$$
P(\text{Purchase}) = 0.028 + 0.018 = 0.046
$$

**Answer:**

$$
\boxed{P(\text{Purchase}) = 4.6\%}
$$
