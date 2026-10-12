# Q8. What Is the Law of Total Probability?

## 1. Introduction

The **Law of Total Probability** is a fundamental rule in probability that helps us calculate the probability of an event by breaking it into several mutually exclusive and exhaustive cases.

It is especially useful when an event can occur through multiple possible scenarios, and we know the probability of the event under each scenario.

For example, suppose two factories manufacture products. Each factory has a different defect rate. If a product is selected randomly, we can calculate the overall probability that it is defective by considering the contribution from each factory.

The law combines:

- The probability of each possible scenario.
- The conditional probability of the event within that scenario.

## 2. Formal Definition

Suppose \(B_1, B_2, \ldots, B_n\) form a partition of the sample space \(S\).

This means:

1. The events are mutually exclusive:

$$
B_i \cap B_j = \varnothing
\quad \text{for } i \ne j
$$

2. The events are collectively exhaustive:

$$
\bigcup_{i=1}^{n} B_i = S
$$

3. Each event has positive probability:

$$
P(B_i) > 0
$$

For any event \(A\), the Law of Total Probability states that:

$$
\boxed{
P(A) = \sum_{i=1}^{n} P(A \mid B_i)P(B_i)
}
$$

In expanded form:

$$
\begin{aligned}
P(A) ={}&
P(A \mid B_1)P(B_1) \\
&+ P(A \mid B_2)P(B_2) \\
&+ \cdots \\
&+ P(A \mid B_n)P(B_n)
\end{aligned}
$$

### Meaning of the terms

- \(A\): The event whose probability we want to calculate.
- \(B_i\): One of the possible scenarios or categories.
- \(P(B_i)\): The probability that scenario \(B_i\) occurs.
- \(P(A \mid B_i)\): The probability of event \(A\), given that scenario \(B_i\) occurs.

In simple terms, calculate the probability of the target event within each scenario, weight it by the probability of that scenario, and add the results.

## 3. Example: Defective Products from Two Factories

Suppose a company manufactures products at two factories.

The following information is available:

| Information | Factory A | Factory B |
|---|---:|---:|
| Proportion of total production | 60% | 40% |
| Defect rate | 2% | 5% |

A product is selected randomly from the company's total production. What is the probability that the selected product is defective?

### Step 1: Define the events

Let:

- \(A\): The product comes from Factory A.
- \(B\): The product comes from Factory B.
- \(D\): The product is defective.

The probabilities are:

$$
P(A) = 0.60
$$

$$
P(B) = 0.40
$$

The conditional defect probabilities are:

$$
P(D \mid A) = 0.02
$$

$$
P(D \mid B) = 0.05
$$

Since every product comes from either Factory A or Factory B, the events \(A\) and \(B\) form a partition of the sample space.

### Step 2: Apply the Law of Total Probability

The product can be defective and come from Factory A, or it can be defective and come from Factory B.

Therefore:

$$
P(D) = P(D \mid A)P(A) + P(D \mid B)P(B)
$$

Substitute the values:

$$
P(D) = (0.02)(0.60) + (0.05)(0.40)
$$

Calculate each contribution:

$$
P(D \mid A)P(A) = 0.012
$$

$$
P(D \mid B)P(B) = 0.020
$$

Add the contributions:

$$
P(D) = 0.012 + 0.020
$$

Therefore:

$$
\boxed{P(D) = 0.032 = 3.2\%}
$$

### Interpretation

A randomly selected product has a **3.2% probability of being defective**.

Notice that we do not simply average the two defect rates. Each factory's defect rate is weighted by its proportion of total production.

Factory B has a higher defect rate, but Factory A produces more products. Both factors affect the overall defect probability.

## 4. Why Do We Multiply and Then Add?

The formula follows from the multiplication rule and the addition rule for mutually exclusive events.

### Step 1: Calculate each scenario's contribution

The probability that a product comes from Factory A and is defective is:

$$
P(D \cap A) = P(D \mid A)P(A)
$$

Similarly, the probability that a product comes from Factory B and is defective is:

$$
P(D \cap B) = P(D \mid B)P(B)
$$

We multiply because we want the joint probability of two events occurring together.

### Step 2: Add the mutually exclusive possibilities

A single product cannot come from both factories at the same time. Thus, the events \(D \cap A\) and \(D \cap B\) are mutually exclusive.

Therefore:

$$
P(D) = P(D \cap A) + P(D \cap B)
$$

Substituting the multiplication-rule expressions gives:

$$
P(D) = P(D \mid A)P(A) + P(D \mid B)P(B)
$$

This is the Law of Total Probability for two scenarios.

For \(n\) possible scenarios, the same reasoning gives:

$$
\boxed{
P(A) = \sum_{i=1}^{n} P(A \mid B_i)P(B_i)
}
$$

## 5. Intuitive Understanding

Imagine that a company produces 1,000 products:

- Factory A produces 600 products.
- Factory B produces 400 products.

Based on their respective defect rates:

- Factory A produces an expected \(600 \times 0.02 = 12\) defective products.
- Factory B produces an expected \(400 \times 0.05 = 20\) defective products.

The expected total number of defective products is:

$$
12 + 20 = 32
$$

The overall defect rate is:

$$
\frac{32}{1000} = 0.032 = 3.2\%
$$

This gives the same result as the Law of Total Probability.

The key intuition is that the overall probability is a **weighted average of the conditional probabilities**, where the weights are the probabilities of the scenarios.

## 6. Relationship to Conditional Probability and Bayes' Theorem

These three concepts are closely related, but they answer different questions.

### Conditional Probability

Conditional probability calculates the probability of an event when another event is known to have occurred.

$$
P(A \mid B) = \frac{P(A \cap B)}{P(B)}
$$

For example, it can tell us the probability that a product is defective given that it came from Factory A.

### Law of Total Probability

The Law of Total Probability combines conditional probabilities across all possible scenarios to calculate an overall probability.

$$
P(A) = \sum_{i=1}^{n} P(A \mid B_i)P(B_i)
$$

For example, it calculates the overall defect rate when the factory that produced a randomly selected product is not known.

### Bayes' Theorem

Bayes' theorem reverses a conditional probability. It helps us calculate the probability of a scenario after observing an event.

$$
P(B_j \mid A) =
\frac{P(A \mid B_j)P(B_j)}{P(A)}
$$

The Law of Total Probability can be used to calculate the denominator:

$$
P(A) = \sum_{i=1}^{n} P(A \mid B_i)P(B_i)
$$

Therefore, Bayes' theorem can also be written as:

$$
\boxed{
P(B_j \mid A) =
\frac{P(A \mid B_j)P(B_j)}
{\sum_{i=1}^{n} P(A \mid B_i)P(B_i)}
}
$$

### Example: Probability That a Defective Product Came from Factory A

Using the previous example, we know:

$$
P(D) = 0.032
$$

Bayes' theorem gives:

$$
P(A \mid D) = \frac{P(D \mid A)P(A)}{P(D)}
$$

Substitute the values:

$$
P(A \mid D) = \frac{(0.02)(0.60)}{0.032}
$$

Therefore:

$$
\boxed{P(A \mid D) = 0.375 = 37.5\%}
$$

**Interpretation:** If a product is known to be defective, the probability that it came from Factory A is 37.5%.

This is different from \(P(D \mid A) = 2\%\). The first probability concerns the source of a defective product; the second concerns the defect status of a product from Factory A.

## 7. Applications in Machine Learning

The Law of Total Probability is useful in several machine-learning and data-analysis scenarios.

### 7.1 Naive Bayes Classification

Naive Bayes uses Bayes' theorem to estimate the probability of a class given observed features.

For a class \(C\) and feature vector \(X\):

$$
P(C \mid X) = \frac{P(X \mid C)P(C)}{P(X)}
$$

The denominator is the overall probability of observing the features. For a set of mutually exclusive and exhaustive classes \(C_1, C_2, \ldots, C_n\), it can be expressed as:

$$
P(X) = \sum_{i=1}^{n} P(X \mid C_i)P(C_i)
$$

For example, in spam classification, the possible classes might be `Spam` and `Not Spam`.

The total probability of observing an email is obtained by considering the probability of that email under each class, weighted by the prior probability of that class.

In many classification tasks, the denominator is the same for every candidate class. Therefore, to compare classes, a classifier can often compare the numerators:

$$
P(X \mid C)P(C)
$$

The Naive Bayes assumption is a separate concept: it assumes that features are conditionally independent given the class. The Law of Total Probability itself does not require this assumption.

### 7.2 Customer Segmentation

Suppose customers belong to different segments, such as:

- New customers.
- Returning customers.
- Premium customers.

Each segment has a different probability of purchasing a product.

The overall purchase probability can be calculated as:

$$
P(\text{Purchase}) =
\sum_{i=1}^{n}
P(\text{Purchase} \mid C_i)P(C_i)
$$

Here, \(C_i\) represents customer segment \(i\).

This calculation helps analysts estimate overall conversion rates while accounting for the distribution of customer segments.

### 7.3 Latent Variables and Mixture Models

In some machine-learning models, observations can arise from different hidden or latent groups.

Let \(Z\) represent a latent group and \(X\) an observed variable. For discrete latent groups:

$$
P(X) = \sum_z P(X \mid Z=z)P(Z=z)
$$

For a continuous observed variable, the corresponding density can be expressed as:

$$
p(x) = \sum_z p(x \mid Z=z)P(Z=z)
$$

where \(p(x)\) is a probability density, rather than the probability of observing one exact continuous value.

For example, a mixture model may describe customer spending as a combination of several customer groups, each with its own spending distribution.

The overall distribution combines the component distributions according to their mixture weights.

## 8. Common Mistakes

### Mistake 1: Taking a Simple Average Instead of a Weighted Average

Incorrect:

$$
P(D) = \frac{2\% + 5\%}{2} = 3.5\%
$$

This is incorrect because the factories do not produce equal numbers of products.

Correct:

$$
P(D) = (0.02)(0.60) + (0.05)(0.40)
$$

$$
\boxed{P(D) = 3.2\%}
$$

A simple average would be appropriate only if the two factories contributed equally to production in this example.

### Mistake 2: Forgetting the Scenario Probabilities

Incorrect:

$$
P(A) + P(B)
$$

This only adds the probabilities of the source scenarios. It does not account for the defect rate within each scenario.

Correct:

$$
P(D) = P(D \mid A)P(A) + P(D \mid B)P(B)
$$

### Mistake 3: Confusing Conditional Probability with Joint Probability

These expressions are different:

$$
P(D \mid A)
$$

and

$$
P(D \cap A)
$$

The first is the probability of a defect given Factory A. The second is the probability that a product both came from Factory A and is defective.

They are related by:

$$
P(D \cap A) = P(D \mid A)P(A)
$$

### Mistake 4: Using Scenarios That Do Not Form a Partition

The standard form of the Law of Total Probability requires the scenarios to be mutually exclusive and collectively exhaustive.

If the scenarios overlap, adding their contributions directly can double-count outcomes.

If the scenarios do not cover the entire sample space, some possibilities are omitted.

### Mistake 5: Confusing the Law of Total Probability with Bayes' Theorem

The Law of Total Probability calculates an overall event probability from conditional probabilities.

Bayes' theorem uses conditional probabilities and an overall event probability to calculate a posterior probability.

They are related, but they answer different questions.

## 9. Common Interview Questions and Answers

### Q1. What is the Law of Total Probability?

**Answer:** It is a rule for calculating the probability of an event by dividing the sample space into mutually exclusive and exhaustive scenarios and summing the conditional probability of the event in each scenario, weighted by the probability of that scenario.

$$
P(A) = \sum_{i=1}^{n} P(A \mid B_i)P(B_i)
$$

### Q2. What conditions must the events \(B_i\) satisfy?

**Answer:** They must form a partition of the sample space:

- They must be mutually exclusive.
- Their union must cover the entire sample space.
- For the conditional probabilities \(P(A \mid B_i)\) to be defined using the standard ratio formula, each \(P(B_i)\) must be positive.

### Q3. Why do we multiply and then add?

**Answer:** We multiply to obtain the joint probability of the target event and a particular scenario. We then add these joint probabilities because the scenarios are mutually exclusive and cover all possibilities.

### Q4. Why is the Law of Total Probability useful?

**Answer:** It allows us to calculate an overall probability when we know conditional probabilities for different groups or scenarios but do not directly know the overall probability.

### Q5. How is it related to Bayes' theorem?

**Answer:** The Law of Total Probability often provides the denominator in Bayes' theorem.

$$
P(B \mid A) = \frac{P(A \mid B)P(B)}{P(A)}
$$

When the possible causes \(B_i\) form a partition, the denominator can be expanded as:

$$
P(A) = \sum_i P(A \mid B_i)P(B_i)
$$

### Q6. Is the Law of Total Probability a weighted average?

**Answer:** Yes. It is a weighted average of conditional probabilities, with the probabilities of the partition events serving as weights. These weights are nonnegative and sum to one.

### Q7. Does the Law of Total Probability require independence?

**Answer:** No. It does not require the target event and the partition events to be independent. It uses conditional probabilities and a partition of the sample space.

### Q8. Where does this law appear in machine learning?

**Answer:** It appears in Bayesian classification, probability calculations across customer segments, and latent-variable models. In Naive Bayes, it can be used to express the marginal probability of the observed features by summing across classes.

## 10. Key Takeaways

- The Law of Total Probability calculates an overall probability by considering all possible scenarios.
- The scenarios must form a mutually exclusive and exhaustive partition of the sample space.
- Each conditional probability is weighted by the probability of its corresponding scenario.
- The formula is a weighted average, not necessarily a simple average.
- It is closely related to the multiplication rule, addition rule, and Bayes' theorem.
- It does not require independence.
- It is useful in Bayesian reasoning, classification, segmentation, and latent-variable models.

The main formula to remember is:

$$
\boxed{
P(A) = \sum_{i=1}^{n} P(A \mid B_i)P(B_i)
}
$$

## 11. Practice Problem

A website receives visitors from mobile devices and desktop computers.

- 70% of visitors use mobile devices.
- 30% of visitors use desktop computers.
- 4% of mobile visitors make a purchase.
- 6% of desktop visitors make a purchase.

What is the probability that a randomly selected visitor makes a purchase?

### Solution

Let \(M\) represent a mobile visitor, \(D\) represent a desktop visitor, and \(P\) represent a purchase.

The given probabilities are:

$$
P(M) = 0.70
$$

$$
P(D) = 0.30
$$

$$
P(P \mid M) = 0.04
$$

$$
P(P \mid D) = 0.06
$$

Apply the Law of Total Probability:

$$
P(P) = P(P \mid M)P(M) + P(P \mid D)P(D)
$$

Substitute the values:

$$
P(P) = (0.04)(0.70) + (0.06)(0.30)
$$

$$
P(P) = 0.028 + 0.018
$$

Therefore:

$$
\boxed{P(P) = 0.046 = 4.6\%}
$$

**Final answer:** The probability that a randomly selected visitor makes a purchase is **4.6%**.
