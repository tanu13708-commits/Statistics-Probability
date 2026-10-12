# Q5. Explain the Multiplication and Addition Rules of Probability

## 1. Introduction

The **addition rule** and **multiplication rule** are two fundamental rules of probability used to calculate the likelihood of events.

They answer two different questions:

- **Addition rule:** What is the probability that event `A` or event `B` occurs?
- **Multiplication rule:** What is the probability that event `A` and event `B` both occur?

In probability, "or" generally means that at least one of the events occurs, including the possibility that both occur. "And" means that both events occur.

These rules are useful in card problems, dice experiments, medical diagnosis, machine learning, and many other real-world situations.

---

## 2. Addition Rule of Probability

The addition rule calculates the probability that event `A` occurs, event `B` occurs, or both occur.

Mathematically:

$$
P(A \cup B) = P(A) + P(B) - P(A \cap B)
$$

Where:

- `P(A ∪ B)` = probability that at least one of the events occurs.
- `P(A)` = probability of event `A`.
- `P(B)` = probability of event `B`.
- `P(A ∩ B)` = probability that both events occur.

### Why do we subtract the intersection?

When we add `P(A)` and `P(B)`, outcomes belonging to both events are counted twice. Subtracting `P(A ∩ B)` removes the extra count.

### Example 1: Rolling a Die

Suppose a fair six-sided die is rolled once.

Let:

- `A` = the outcome is even.
- `B` = the outcome is greater than 3.

The sample space is:

$$
S = \{1,2,3,4,5,6\}
$$

Event `A`:

$$
A = \{2,4,6\}
$$

Therefore:

$$
P(A) = \frac{3}{6} = \frac{1}{2}
$$

Event `B`:

$$
B = \{4,5,6\}
$$

Therefore:

$$
P(B) = \frac{3}{6} = \frac{1}{2}
$$

Their intersection is:

$$
A \cap B = \{4,6\}
$$

Therefore:

$$
P(A \cap B) = \frac{2}{6} = \frac{1}{3}
$$

Using the addition rule:

$$
P(A \cup B) = P(A) + P(B) - P(A \cap B)
$$

$$
P(A \cup B) = \frac{1}{2} + \frac{1}{2} - \frac{1}{3}
$$

$$
P(A \cup B) = \frac{2}{3}
$$

**Answer:** The probability of rolling an even number or a number greater than 3 is `2/3`.

We can verify this directly. The outcomes satisfying at least one condition are:

$$
A \cup B = \{2,4,5,6\}
$$

There are 4 favorable outcomes out of 6, giving `4/6 = 2/3`.

---

## 3. Addition Rule for Mutually Exclusive Events

Two events are **mutually exclusive** if they cannot occur at the same time.

Mathematically:

$$
A \cap B = \varnothing
$$

Therefore:

$$
P(A \cap B) = 0
$$

Substituting this into the general addition rule gives:

$$
P(A \cup B) = P(A) + P(B)
$$

### Example 2: Rolling a Die

Let:

- `A` = rolling a 1.
- `B` = rolling a 6.

These events are mutually exclusive because a single die roll cannot produce both 1 and 6.

Therefore:

$$
P(A) = \frac{1}{6}
$$

$$
P(B) = \frac{1}{6}
$$

Using the addition rule:

$$
P(A \cup B) = \frac{1}{6} + \frac{1}{6}
$$

$$
P(A \cup B) = \frac{1}{3}
$$

**Important:** Use the simplified addition rule only when the events are mutually exclusive. Otherwise, subtract their intersection to avoid double-counting.

---

## 4. Multiplication Rule of Probability

The multiplication rule calculates the probability that two events occur together.

The general formula is:

$$
P(A \cap B) = P(A)P(B \mid A)
$$

Equivalently:

$$
P(A \cap B) = P(B)P(A \mid B)
$$

Where:

- `P(A ∩ B)` = probability that both events occur.
- `P(B | A)` = probability of `B` occurring given that `A` has occurred.
- `P(A)` = probability of event `A`.

### Intuition

To find the probability that both events occur:

1. Calculate the probability that the first event occurs.
2. Multiply it by the probability that the second event occurs under the condition that the first event has occurred.

The second probability may change depending on whether the events are independent or dependent.

### Example 3: Drawing Two Cards Without Replacement

Suppose a standard deck contains 52 cards, including 4 aces.

Two cards are drawn one after another without replacement.

Find the probability that both cards are aces.

Let:

- `A` = the first card is an ace.
- `B` = the second card is an ace.

The probability that the first card is an ace is:

$$
P(A) = \frac{4}{52}
$$

After drawing an ace, only 3 aces remain among 51 cards.

Therefore:

$$
P(B \mid A) = \frac{3}{51}
$$

Using the multiplication rule:

$$
P(A \cap B) = P(A)P(B \mid A)
$$

$$
P(A \cap B) = \frac{4}{52} \times \frac{3}{51}
$$

Simplifying:

$$
P(A \cap B) = \frac{1}{221}
$$

**Answer:** The probability of drawing two aces in succession without replacement is `1/221`, approximately `0.4525%`.

Notice that the second probability is `3/51`, not `4/52`, because the first draw changes the deck.

---

## 5. Multiplication Rule for Independent Events

Two events are **independent** when the occurrence of one event does not change the probability of the other.

For independent events:

$$
P(B \mid A) = P(B)
$$

Therefore, the general multiplication rule becomes:

$$
P(A \cap B) = P(A)P(B)
$$

### Example 4: Tossing Two Coins

Suppose two fair coins are tossed.

Let:

- `A` = the first coin lands heads.
- `B` = the second coin lands heads.

The probability of heads on either fair coin is:

$$
P(A) = \frac{1}{2}
$$

$$
P(B) = \frac{1}{2}
$$

The coin tosses are independent, so:

$$
P(A \cap B) = P(A)P(B)
$$

$$
P(A \cap B) = \frac{1}{2} \times \frac{1}{2}
$$

$$
P(A \cap B) = \frac{1}{4}
$$

**Answer:** The probability that both coins land heads is `1/4`, or 25%.

### Important distinction

The multiplication rule applies to both dependent and independent events.

- For **dependent events**, use the conditional probability form:

$$
P(A \cap B) = P(A)P(B \mid A)
$$

- For **independent events**, simplify it to:

$$
P(A \cap B) = P(A)P(B)
$$

Do not multiply the two individual probabilities directly unless independence is established or otherwise justified.

---

## 6. Addition Rule vs. Multiplication Rule

| Feature | Addition Rule | Multiplication Rule |
|---|---|---|
| Main question | Does `A` or `B` occur? | Do `A` and `B` both occur? |
| Set operation | Union: `A ∪ B` | Intersection: `A ∩ B` |
| General formula | `P(A) + P(B) - P(A ∩ B)` | `P(A)P(B | A)` |
| Special case | Mutually exclusive events | Independent events |
| Simplified formula | `P(A) + P(B)` for mutually exclusive events | `P(A)P(B)` for independent events |

**Memory trick:**

- **OR → Addition**, with an overlap correction when necessary.
- **AND → Multiplication**, using conditional probability when necessary.

These are useful memory aids, but always check the event conditions before applying a simplified formula.

---

## 7. Real-World Example: Machine Learning

Probability rules are used extensively in machine learning, especially in probabilistic models.

### A. Addition Rule in Classification

Suppose a system classifies a message as belonging to one of two categories:

- `A` = the message is classified as spam.
- `B` = the message is classified as phishing.

If a message can belong to both categories, then the probability that it is spam or phishing is:

$$
P(A \cup B) = P(A) + P(B) - P(A \cap B)
$$

The intersection must be subtracted because a message that is both spam and phishing would otherwise be counted twice.

If the categories are guaranteed to be mutually exclusive, the formula simplifies to:

$$
P(A \cup B) = P(A) + P(B)
$$

### B. Multiplication Rule in Naive Bayes

Naive Bayes uses conditional probabilities to estimate the probability of a class given observed features.

Suppose an email contains two features:

- `X_1` = the email contains the word "free".
- `X_2` = the email contains the word "prize".
- `Y` = the email is spam.

The chain rule of probability gives:

$$
P(X_1, X_2 \mid Y)
=
P(X_1 \mid Y)P(X_2 \mid X_1, Y)
$$

Naive Bayes makes a simplifying conditional independence assumption:

$$
P(X_2 \mid X_1, Y) = P(X_2 \mid Y)
$$

Under that assumption:

$$
P(X_1, X_2 \mid Y)
=
P(X_1 \mid Y)P(X_2 \mid Y)
$$

This allows the model to calculate a joint feature likelihood by multiplying individual conditional probabilities.

**Important:** Naive Bayes assumes that features are conditionally independent given the class. Real-world features do not always satisfy this assumption exactly, but the model can still work well in practice.

---

## 8. Common Interview Questions

### Q1. State the addition rule of probability.

For any two events `A` and `B`:

$$
P(A \cup B) = P(A) + P(B) - P(A \cap B)
$$

### Q2. When can we use the simplified addition rule?

When events are mutually exclusive, meaning they cannot occur together:

$$
P(A \cup B) = P(A) + P(B)
$$

### Q3. State the multiplication rule of probability.

The general multiplication rule is:

$$
P(A \cap B) = P(A)P(B \mid A)
$$

### Q4. When can we use the simplified multiplication rule?

When the events are independent:

$$
P(A \cap B) = P(A)P(B)
$$

### Q5. Are mutually exclusive events always independent?

No. If two events are mutually exclusive and both have positive probability, they cannot be independent.

Mutual exclusivity means they cannot occur together, while independence means one event does not change the probability of the other.

### Q6. What is the difference between dependent and independent events?

For independent events:

$$
P(B \mid A) = P(B)
$$

For dependent events, the occurrence of `A` changes the probability of `B`, so the conditional probability differs from the unconditional probability.

### Q7. Why do we subtract the intersection in the addition rule?

Because outcomes in the intersection are counted once in `P(A)` and again in `P(B)`. Subtracting `P(A ∩ B)` removes this double-counting.

### Q8. Why does drawing cards without replacement involve dependent events?

Because the first draw changes the number and composition of the cards remaining in the deck. Consequently, the probability of the second draw depends on the first draw.

---

## 9. Key Takeaways

- The addition rule calculates the probability that at least one of two events occurs.
- The general addition formula is:

$$
P(A \cup B) = P(A) + P(B) - P(A \cap B)
$$

- For mutually exclusive events:

$$
P(A \cup B) = P(A) + P(B)
$$

- The multiplication rule calculates the probability that two events occur together.
- The general multiplication formula is:

$$
P(A \cap B) = P(A)P(B \mid A)
$$

- For independent events:

$$
P(A \cap B) = P(A)P(B)
$$

- Drawing without replacement generally creates dependence between successive draws.
- These rules form the foundation of conditional probability, Bayes' theorem, Naive Bayes, and many other probabilistic machine learning techniques.

**One-line interview answer:** The addition rule calculates the probability of `A` or `B` occurring, correcting for overlap, while the multiplication rule calculates the probability of both events occurring using conditional probability; their simplified forms apply to mutually exclusive and independent events, respectively.
