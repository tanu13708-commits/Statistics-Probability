# Q2. What Are Sample Space, Events, and Outcomes?

## 1. What Is an Outcome?

An **outcome** is a single possible result of a random experiment.

For example, when rolling a standard six-sided die, the possible outcomes are 1, 2, 3, 4, 5, and 6.

- Rolling a 2 is one outcome.
- Rolling a 5 is another outcome.
- Rolling a 7 is impossible for a standard six-sided die.

## 2. What Is a Sample Space?

A **sample space** is the set of all possible outcomes of a random experiment. It is represented by `S` or `Ω`.

For a standard six-sided die:

$$
S = \{1,2,3,4,5,6\}
$$

For a coin toss:

$$
S = \{H,T\}
$$

For two coin tosses:

$$
S = \{HH,HT,TH,TT\}
$$

If both coins are fair and independent, each outcome has probability:

$$
P(\text{each outcome}) = \frac{1}{4}
$$

## 3. What Is an Event?

An **event** is a set of one or more outcomes from the sample space.

Suppose we roll a die and define event `A` as getting an even number.

The sample space is:

$$
S = \{1,2,3,4,5,6\}
$$

The event is:

$$
A = \{2,4,6\}
$$

An event is a subset of the sample space:

$$
A \subseteq S
$$

If the outcome is 4, event `A` occurs. If the outcome is 3, event `A` does not occur.

## 4. Types of Events

### A. Simple Event

An event containing exactly one outcome.

Example: Rolling a 3.

$$
A = \{3\}
$$

For a fair die:

$$
P(A) = \frac{1}{6}
$$

### B. Compound Event

An event containing multiple outcomes.

Example: Rolling an odd number.

$$
B = \{1,3,5\}
$$

Therefore:

$$
P(B) = \frac{3}{6} = \frac{1}{2}
$$

### C. Certain Event

An event that always occurs under the defined experiment.

$$
P(S) = 1
$$

### D. Impossible Event

An event that cannot occur under the defined experiment.

$$
P(\varnothing) = 0
$$

### E. Complementary Event

The complement of event `A`, written as `Aᶜ`, contains all outcomes that do not belong to `A`.

If:

$$
A = \{2,4,6\}
$$

Then:

$$
A^c = \{1,3,5\}
$$

The complement rule is:

$$
P(A^c) = 1 - P(A)
$$

If the probability of rolling an even number is `1/2`, the probability of rolling an odd number is also `1/2`.

## 5. Application in Machine Learning

Suppose a model classifies customer support tickets into three categories:

$$
S = \{\text{Billing},\text{Technical},\text{Account}\}
$$

Assume the model predicts:

| Class | Probability |
|---|---:|
| Billing | 0.50 |
| Technical | 0.30 |
| Account | 0.20 |

Let event `A` represent a ticket belonging to either Billing or Account.

$$
A = \{\text{Billing},\text{Account}\}
$$

Since these classes are mutually exclusive:

$$
P(A) = 0.50 + 0.20 = 0.70
$$

The model assigns a combined probability of 70% to the ticket belonging to Billing or Account.

## 6. Interview Questions

**Q1. Can an event contain multiple outcomes?**

Yes. A compound event can contain multiple outcomes from the sample space.

**Q2. Is every outcome an event?**

An individual outcome can be represented as a singleton event. For example, the outcome 3 corresponds to the event `{3}`.

**Q3. Can an event equal the sample space?**

Yes. The event `A = S` is certain because every possible outcome belongs to it.

**Q4. What is the difference between an impossible event and a rare event?**

An impossible event has probability zero under the specified model. A rare event has a very low probability but can still occur.

**Q5. What is the sample space when two dice are rolled?**

When recording each die separately, there are 36 ordered outcomes.

$$
S = \{(i,j): i,j \in \{1,2,3,4,5,6\}\}
$$

For two fair, independent dice, each ordered pair has probability:

$$
P((i,j)) = \frac{1}{36}
$$

## Key Takeaways

- An outcome is one possible result.
- A sample space contains all possible outcomes.
- An event is a subset of the sample space.
- Probability formulas describe the likelihood of events.
- These concepts are foundational for conditional probability, independence, and Bayes' theorem.
