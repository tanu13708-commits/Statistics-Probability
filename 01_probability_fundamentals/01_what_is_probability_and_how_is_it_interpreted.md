# Question 2. What is Probability and How Is It Interpreted?

## What is Probability?

Probability is a mathematical measure of how likely an event is to occur. Its value ranges from 0 to 1, where 0 represents an impossible event and 1 represents a certain event.

In simple terms, probability helps us quantify uncertainty.

Consider a machine learning model that predicts whether a customer will leave a subscription service. The model outputs:

```
probability_of_churn = 0.80
```

This means the model assigns an 80% probability to the customer belonging to the churn class, assuming the output is intended as a probability.

It does not mean the customer will definitely leave. It means the model estimates a high likelihood of churn based on the available information.

Probability is fundamental to machine learning because data is uncertain, outcomes are not always predictable, and models often need to reason about possible outcomes.

## 1. How is Probability interpreted?

Probability can be expressed in three common ways.

Probability = 0

Impossible event in the specified model.

Example: Getting a 7 when rolling a standard six-sided die.

Probability = 0.5

A 50% probability.

Example: Getting heads on a fair coin toss.

Probability = 1

Certain event under the specified conditions.

Example: Getting a result between 1 and 6 when rolling a standard six-sided die.

The general interpretation is:

| Probability | Percentage | Interpretation                                   |
| ----------- | ---------- | ------------------------------------------------ |
| 0           | 0%         | Impossible                                       |
| 0.25        | 25%        | Low likelihood                                   |
| 0.50        | 50%        | Equal probability for two complementary outcomes |
| 0.75        | 75%        | High likelihood                                  |
| 1           | 100%       | Certain                                          |

Terms such as low and high are contextual, not universal mathematical thresholds.

## 2. How do we calculate Probability?

For equally likely outcomes, probability is calculated using:

 P(A)={Favourable outcomes}\{Total possible outcomes}

Here, (P(A) means the probability that event (A) occurs.

### Example: Rolling a die

Suppose you roll a fair six-sided die and want to calculate the probability of getting an even number.

Possible outcomes:

 S={1,2,3,4,5,6}

Favourable outcomes:

 A={2,4,6} 

There are three favourable outcomes and six total outcomes.

 P(A)={3}/{6}=1/2=0.5 

Therefore, the probability of rolling an even number is 0.5, or 50%.

Important limitation: This formula assumes that all outcomes are equally likely. For events with unequal probabilities, we need to use the relevant probability model or distribution.

## 3. What does Probability mean in Machine Learning?

Suppose you train a classification model to detect spam emails.

For a particular email, the model produces:

```
P(spam | email) = 0.92
P(not_spam | email) = 0.08
```

The notation P(spam|email) means the probability assigned to the spam class, given the observed email and the model's assumptions.

The model assigns:

- 92% probability to spam.
- 8% probability to not spam.

These probabilities sum to 1 because the model is considering two mutually exclusive and collectively exhaustive classes.

### What happens next?

A classification system may use a threshold to turn the probability into a predicted label.

For example:

```
probability = 0.92
threshold = 0.50

prediction = 1 if probability >= threshold else 0

print(prediction)  # 1
```

Here, `1` represents spam.

If the threshold were 0.95, the same email would be classified as not spam under this decision rule.

This illustrates a crucial distinction:

- Probability represents the model's estimated likelihood.
- Prediction is the output or decision produced using a rule, such as a classification threshold.

The appropriate threshold depends on the application. For a spam filter, false positives matter; for a medical screening system, false negatives may be particularly costly.

Also, a model output of 0.92 is not automatically a reliable 92% probability. That interpretation is most defensible when the model is appropriately calibrated and evaluated on relevant data.

## 4. What are the different interpretations of Probability?

At interview level, it is useful to understand that probability is not interpreted in only one way.

### A. Classical interpretation

Probability is calculated from equally likely outcomes.

Example: The probability of heads on a fair coin toss is 1/2.

P(heads)=1/2

### B. Frequentist interpretation

Probability is interpreted through the long-run relative frequency of an event over repeated trials under comparable conditions.

For example, if a fair coin is tossed many times, the proportion of heads is expected to approach 0.5 as the number of tosses increases.

This does not guarantee exactly 50 heads in every 100 tosses.

### C. Bayesian interpretation

Probability represents uncertainty about an event or hypothesis given available information, expressed through a probability model.

For example, a spam detector can update its estimated probability of spam as it observes evidence from the email.

Bayesian inference combines prior beliefs with observed evidence to obtain a posterior distribution.

These interpretations are related, but they emphasize different foundations for assigning probabilities.

## 5. How is Probability used in AI/ML?

[A_05. Classification & Regression - EN - Deep Learning Bible - 2. Classification - Eng.](https://images.openai.com/static-rsc-4/WWSobtAdKYhbZMwaBIqQzg0jcdBD0ctvW7hGQ1BPc4RCp26kANJUC8xAK4D7lodL_-oerSndvmnCgAsf2BDmlcTtfSQZ-WsKxtMRcPrwZwMbJuyM_wGzwPQ7ezb399wx3U1wHlNw7aNTKehWifqyuDK_rDCBJUbFZkKvxKvQbaA?purpose=inline)

Classification

Logistic regression and many classification models produce class probabilities or scores that can be used to make decisions.

[Explaining base rate neglect – Jason Collins blog](https://images.openai.com/static-rsc-4/JFIm9_MxrNu51qWX5s7EFAaJ04yroFbq7trtnti0ZsDxEtsl8KCtFRWcnhSDsmh4AOquLA3SyoiEnyBkfJGo62JxkUxzIXqYmm7BSYFHNXcryeFO0J4vuX1AUGeB-ZbrurByV-6C0FqJNgeNbFYqFvarEmmHA9dvjzFJO_UszmY?purpose=inline)

Bayesian inference

Updates the probability of a hypothesis using observed evidence.

[Gaussian processes: inference — Probabilistic Thinking, modelling and programming with applications in Epidemiology.](https://images.openai.com/static-rsc-4/Jy9_Ntpom_31Bf3914Hd2QnXY_gtOFAm1tA3YdZWb1knS3EdO3vkc48o8TV1Wz1I7-jPFr_JUzQeO4MhA9yb9BYsG0l_09OktROUMfgwi50gfhf5Q0ZjeeV1dgFb3LaSHeZBKdpHAVaWAHIy4KMUaPDaNH0FsDj9Ml-c98BV4Cs?purpose=inline)

Uncertainty estimation

Helps quantify uncertainty in predictions and reason about possible outcomes.

[Probability and Sampling — CSCI 104: Data Science and Computing for All](https://images.openai.com/static-rsc-4/E7WVLh67vo3OE2awLkJ709yFGXcJRLskr_SkClpsg8Ru0EWR7OmJbMelsH89En2zRiyt01MUzv9C_ixEdB0tiFhmYsbhEU7eJHajcYpx1jqO4zi3TmyIjixiwUt31wLq2ClqO9WrIHkbXEnLMZd1sSaAjZDI_pBoIEjrXIEd4rc?purpose=inline)

Probabilistic modelling

Distributions such as the normal, binomial and Bernoulli distributions describe different types of random variables and outcomes.

## 6. Interview questions

Q1. Can probability be greater than 1 or less than 0?

No. For any event (A),

0<=P(A)<=1

Q2. What is the difference between probability and possibility?

Possibility is a qualitative statement about whether something can happen. Probability quantifies how likely it is under a specified probability model.

Q3. If an event has a probability of 0.8, will it definitely happen?

No. It has an assigned probability of 80%, not a guarantee. The actual outcome may occur or not occur.

Q4. If a model predicts a 90% probability, is it correct 90% of the time?

Not necessarily. An individual prediction does not establish that accuracy. If a model is well calibrated, predictions assigned approximately 90% probability should correspond to an event frequency of approximately 90% across a sufficiently large group of comparable predictions.

Q5. What is the difference between probability and statistics?

Probability generally studies the likelihood of outcomes under a specified model. Statistics uses observed data to summarize information, estimate unknown quantities and test hypotheses. Statistical inference often uses probability theory as its foundation.

Q6. What is a random experiment?

A random experiment is a process whose outcome is uncertain before it occurs, even when the possible outcomes are known. Examples include tossing a coin, rolling a die or observing whether a customer churns.

## Key takeaways

- Probability quantifies the likelihood of an event and ranges from 0 to 1.
- The favourable-outcomes formula applies when outcomes are equally likely.
- Probability is central to classification, Bayesian inference and uncertainty modelling.
- A predicted probability is not a guarantee, and its reliability depends partly on model calibration.
- Probability and Statistics are closely connected but address different aspects of reasoning about data.

