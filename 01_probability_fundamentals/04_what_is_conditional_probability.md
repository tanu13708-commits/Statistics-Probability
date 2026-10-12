# Q4. What Is Conditional Probability?

## 1. Definition

**Conditional probability** is the probability that an event occurs given that another event has already occurred.

In simple words, it answers:

> How does the probability of an event change when we know some additional information?

For example:
- What is the probability that a student passes an exam, given that they attended all classes?
- What is the probability that an email is spam, given that it contains the word "winner"?
- What is the probability that a customer buys a product, given that they clicked an advertisement?

Conditional probability is important because real-world decisions often depend on information that is already available.

## 2. Mathematical Formula

The conditional probability of event `A` given event `B` is written as:

$$
P(A \mid B) = \frac{P(A \cap B)}{P(B)}
$$

Where:

- `P(A | B)` = probability that event `A` occurs given that `B` has occurred.
- `P(A ∩ B)` = probability that both `A` and `B` occur.
- `P(B)` = probability that event `B` occurs.

**Important condition:** `P(B)` must be greater than zero because we cannot condition on an event that has zero probability using this formula.

The key idea is that once `B` is known to have occurred, we focus only on the outcomes where `B` is true.

## 3. Intuition Behind the Formula

Suppose a school has 100 students:

- 60 students are boys.
- 30 students wear glasses.
- 20 students are boys who wear glasses.

Let:

- `A` = the selected student is a boy.
- `B` = the selected student wears glasses.

We want to calculate the probability that a student is a boy, **given that the student wears glasses**.

Without additional information, the probability of selecting a boy is:

$$
P(A) = \frac{60}{100} = 0.60
$$

However, we now know that the selected student wears glasses. Therefore, we consider only the 30 students who wear glasses.

Among those 30 students, 20 are boys.

So:

$$
P(A \mid B) = \frac{20}{30} = \frac{2}{3}
$$

Therefore:

$$
P(A \mid B) \approx 0.667
$$

The probability is approximately 66.7%.

**Key intuition:** The original population had 100 students, but after learning that the student wears glasses, our relevant population shrinks to 30 students.

This is why the denominator is `P(B)`, not the total population.

## 4. Step-by-Step Example Using a Deck of Cards

Consider a standard deck of 52 playing cards.

Let:

- `A` = the selected card is a king.
- `B` = the selected card is a face card.

There are:
- 4 kings.
- 12 face cards (4 jacks, 4 queens, and 4 kings).
- 4 cards that are both kings and face cards.

We want to find `P(A | B)`: the probability that the selected card is a king, given that it is a face card.

Using the formula:

$$
P(A \mid B) = \frac{P(A \cap B)}{P(B)}
$$

Substitute the probabilities:

$$
P(A \mid B) = \frac{4/52}{12/52}
$$

Simplifying:

$$
P(A \mid B) = \frac{4}{12} = \frac{1}{3}
$$

Therefore, the conditional probability is:

$$
P(A \mid B) = \frac{1}{3}
$$

Notice that the answer is not `4/52`. Once we know the card is a face card, only 12 possible cards remain relevant.

## 5. Conditional Probability vs. Joint Probability

These two concepts are related but different.

| Concept | Meaning | Example |
|---|---|---|
| Joint probability | Probability that both events occur | Probability that a student is a boy and wears glasses |
| Conditional probability | Probability of one event given another event | Probability that a student is a boy given that the student wears glasses |

Joint probability is represented by:

$$
P(A \cap B)
$$

Conditional probability is represented by:

$$
P(A \mid B) = \frac{P(A \cap B)}{P(B)}
$$

**Remember:** Joint probability considers both events together. Conditional probability uses the occurrence of one event as additional information.

## 6. Conditional Probability vs. Independent Events

Conditional probability also helps us understand independence.

Two events `A` and `B` are independent when knowing that `B` occurred does not change the probability of `A`.

Mathematically:

$$
P(A \mid B) = P(A)
$$

provided `P(B) > 0`.

For example, consider two fair coin tosses:

- `A` = the first toss is heads.
- `B` = the second toss is heads.

The first toss does not affect the second toss, so:

$$
P(A \mid B) = P(A) = \frac{1}{2}
$$

For independent events, we can also write:

$$
P(A \cap B) = P(A)P(B)
$$

However, if knowing that `B` occurred changes the probability of `A`, the events are dependent.

For example, drawing two cards from a deck **without replacement** creates dependence: after the first card is drawn, the composition of the deck changes.

## 7. Real-World Example: Medical Testing

Suppose a disease affects 1% of a population.

A medical test is positive for:
- 99% of people who have the disease.
- 5% of people who do not have the disease.

Let:

- `D` = the person has the disease.
- `+` = the test result is positive.

We want to calculate:

$$
P(D \mid +)
$$

This means the probability that a person has the disease given that the test is positive.

Using Bayes' theorem:

$$
P(D \mid +) =
\frac{P(+ \mid D)P(D)}{P(+)}
$$

The probability of a positive result is:

$$
P(+) = P(+ \mid D)P(D)
+ P(+ \mid \neg D)P(\neg D)
$$

Substituting the values:

$$
P(+) = (0.99)(0.01) + (0.05)(0.99)
$$

$$
P(+) = 0.0099 + 0.0495 = 0.0594
$$

Therefore:

$$
P(D \mid +) = \frac{0.99 \times 0.01}{0.0594}
$$

$$
P(D \mid +) \approx 0.1667
$$

The probability is approximately **16.67%**, despite the test being positive.

Why? Because the disease is rare, and the number of false positives can be substantial relative to the number of true positives.

This example demonstrates why conditional probability is essential for interpreting medical tests and other prediction systems.

## 8. Applications in Machine Learning

Conditional probability is fundamental to many machine learning algorithms.

### A. Naive Bayes Classifier

Naive Bayes predicts a class using the probability of observing features given that class.

For example, in spam detection:

- `S` = an email is spam.
- `W` = the email contains the word "winner".

A model may estimate:

$$
P(S \mid W)
$$

This is the probability that an email is spam given that it contains the word "winner".

Using Bayes' theorem:

$$
P(S \mid W) =
\frac{P(W \mid S)P(S)}{P(W)}
$$

The model combines:
- Prior probability: `P(S)`.
- Likelihood: `P(W | S)`.
- Evidence: `P(W)`.

For multiple features, Naive Bayes makes a conditional independence assumption to simplify calculations.

### B. Classification

Classification models estimate or approximate the probability of a class given input features.

For example:

$$
P(Y = \text{spam} \mid X)
$$

Here, `X` represents the observed features of an email, and `Y` represents its class.

The model uses the features to estimate how likely the email is to belong to the spam class.

### C. Probabilistic Models

Conditional probability appears in:
- Bayesian networks.
- Hidden Markov models.
- Natural language processing.
- Recommendation systems.
- Medical diagnosis systems.
- Sequential prediction tasks.

In general, these systems use observed information to reason about uncertain outcomes.

## 9. Common Mistakes to Avoid

### Mistake 1: Confusing `P(A | B)` with `P(B | A)`

These probabilities are generally different.

For example:

- `P(disease | positive test)` = probability of disease given a positive test.
- `P(positive test | disease)` = probability of a positive test given the disease.

The second probability is the test's sensitivity in this example. It does not directly tell us the first probability.

Bayes' theorem connects them, but they cannot be casually interchanged.

### Mistake 2: Using the Wrong Denominator

For:

$$
P(A \mid B) = \frac{P(A \cap B)}{P(B)}
$$

The denominator must be `P(B)` because `B` is the known condition.

### Mistake 3: Assuming Conditional Probability Means Causation

If `P(A | B)` differs from `P(A)`, it indicates an association in probability, but it does not automatically prove that `B` causes `A`.

Other variables may influence both events.

### Mistake 4: Assuming Events Are Independent

Events should not be assumed independent without justification. For example, drawing cards without replacement changes the probabilities of subsequent draws.

## 10. Common Interview Questions

### Q1. What is conditional probability?

Conditional probability is the probability of an event occurring given that another event has already occurred.

$$
P(A \mid B) = \frac{P(A \cap B)}{P(B)}
$$

where `P(B) > 0`.

### Q2. Why do we divide by `P(B)`?

Because we restrict our attention to the outcomes where `B` has occurred. Dividing by `P(B)` normalizes the joint probability to this reduced set of outcomes.

### Q3. What is the difference between `P(A | B)` and `P(A ∩ B)`?

`P(A ∩ B)` is the probability that both events occur. `P(A | B)` is the probability of `A` when `B` is known to have occurred.

### Q4. When are two events independent?

Two events are independent if knowing that one occurred does not change the probability of the other.

$$
P(A \mid B) = P(A)
$$

provided `P(B) > 0`.

Equivalently:

$$
P(A \cap B) = P(A)P(B)
$$

### Q5. Is `P(A | B)` always equal to `P(B | A)`?

No. They represent different conditional probabilities and are generally unequal. Bayes' theorem relates them.

### Q6. How is conditional probability used in Naive Bayes?

Naive Bayes uses conditional probabilities of features given a class to estimate the probability of each class for a given input.

### Q7. Can conditional probability be greater than 1?

No. Every valid conditional probability lies between 0 and 1, inclusive.

$$
0 \leq P(A \mid B) \leq 1
$$

provided `P(B) > 0`.

## 11. Key Takeaways

- Conditional probability measures the probability of an event given that another event has occurred.
- Its formula is `P(A | B) = P(A ∩ B) / P(B)`, provided `P(B) > 0`.
- The condition changes the relevant set of outcomes.
- Joint probability and conditional probability are related but not interchangeable.
- Independence means that conditioning on another event does not change the probability.
- `P(A | B)` and `P(B | A)` are generally different.
- Bayes' theorem uses conditional probability to update beliefs when new evidence becomes available.
- Conditional probability is important in Naive Bayes, classification, Bayesian networks, and many other machine learning applications.

**One-line interview answer:** Conditional probability is the probability of an event occurring given that another event has occurred, calculated by dividing their joint probability by the probability of the known event.
