# Q15. Explain the Poisson Distribution and When It Is Useful

## 1. Introduction

The **Poisson distribution** is a discrete probability distribution used to model the number of times an event occurs within a fixed interval of time, space, distance, or another measurable quantity, under suitable assumptions.

It is especially useful when we want to model counts of events that occur independently at a relatively stable average rate.

### Real-world examples

- Number of customer arrivals at a store in one hour.
- Number of calls received by a call center in one minute.
- Number of defects found in a length of material.
- Number of website requests received in a second.
- Number of insurance claims received in a day.
- Number of errors occurring in a computer system during a fixed period.

The Poisson distribution focuses on **how many events occur within an interval**, rather than the exact time at which each event occurs.

## 2. Definition of the Poisson Distribution

A random variable \(X\) follows a Poisson distribution with parameter \(\lambda\) if it represents a count of events and has probability mass function:

$$
P(X=k)=\frac{e^{-\lambda}\lambda^k}{k!}
$$

where:

- \(X\) is the number of events in the specified interval.
- \(k\) is a possible event count: \(0,1,2,\ldots\).
- \(\lambda\) is the expected number of events in that interval.
- \(e\) is Euler's number, approximately 2.71828.
- \(k!\) is the factorial of \(k\), with \(0!=1\).

The parameter must satisfy:

$$
\lambda>0
$$

The degenerate case \(\lambda=0\) can also be defined: the count is zero with probability 1.

The notation is:

$$
X\sim \mathrm{Poisson}(\lambda)
$$

For example, if a call center receives an average of 4 calls per minute, the number of calls received during a one-minute interval may be modeled as:

$$
X\sim \mathrm{Poisson}(4)
$$

This model gives probabilities for receiving 0 calls, 1 call, 2 calls, and so on during that interval.

## 3. Understanding the Parameter Lambda

The parameter \(\lambda\) represents the **expected count of events in the interval being modeled**.

It is not necessarily the probability of an event.

For a Poisson random variable:

$$
E[X]=\lambda
$$

Suppose a store receives an average of 6 customers every hour. If \(X\) is the number of customer arrivals in one hour, then:

$$
\lambda=6
$$

The expected number of arrivals is:

$$
E[X]=6
$$

The observed number of customers in a particular hour might be 3, 5, 6, 8, or another nonnegative integer. The expected count is a long-run average, not a guarantee that exactly 6 customers will arrive every hour.

### Important: The Interval Matters

The value of \(\lambda\) depends on the interval.

Suppose a website receives an average of 12 requests per minute and the rate is constant.

For one minute:

$$
\lambda=12
$$

For 30 seconds:

$$
\lambda=12\left(\frac{30}{60}\right)=6
$$

For five minutes:

$$
\lambda=12(5)=60
$$

When the event rate is constant, the expected count scales proportionally with the interval length.

## 4. Poisson Probability Mass Function

The probability mass function gives the probability of observing exactly \(k\) events.

$$
P(X=k)=\frac{e^{-\lambda}\lambda^k}{k!}
$$

### Example: Exactly Two Calls

Suppose a call center receives an average of 4 calls per minute. Assume the number of calls follows a Poisson distribution.

We want to calculate the probability of receiving exactly two calls in one minute.

The parameters are:

$$
\lambda=4,\qquad k=2
$$

Substituting into the PMF:

$$
P(X=2)=\frac{e^{-4}4^2}{2!}
$$

Since:

$$
4^2=16,\qquad 2!=2
$$

we obtain:

$$
P(X=2)=8e^{-4}
$$

Using \(e^{-4}\approx 0.0183156\):

$$
P(X=2)\approx 8(0.0183156)
$$

Therefore:

$$
P(X=2)\approx 0.1465
$$

The probability of receiving exactly two calls in one minute is approximately **14.65%**.

## 5. Step-by-Step Example: Zero, One, or Two Events

Suppose a website receives an average of 3 requests per second. Let \(X\) be the number of requests received in a one-second interval.

Assume:

$$
X\sim \mathrm{Poisson}(3)
$$

### 5.1 Probability of Zero Requests

Set \(k=0\):

$$
P(X=0)=\frac{e^{-3}3^0}{0!}
$$

Because \(3^0=1\) and \(0!=1\):

$$
P(X=0)=e^{-3}
$$

Therefore:

$$
P(X=0)\approx 0.0498
$$

The probability of zero requests is approximately 4.98%.

### 5.2 Probability of Exactly One Request

Set \(k=1\):

$$
P(X=1)=\frac{e^{-3}3^1}{1!}
$$

Therefore:

$$
P(X=1)=3e^{-3}
$$

$$
P(X=1)\approx 0.1494
$$

The probability of exactly one request is approximately 14.94%.

### 5.3 Probability of Exactly Two Requests

Set \(k=2\):

$$
P(X=2)=\frac{e^{-3}3^2}{2!}
$$

$$
P(X=2)=\frac{9e^{-3}}{2}
$$

$$
P(X=2)\approx 0.2240
$$

The probability of exactly two requests is approximately 22.40%.

These calculations show how the Poisson PMF assigns probabilities to individual event counts.

## 6. Mean, Variance, and Standard Deviation

One of the most important properties of the Poisson distribution is that its mean and variance are both equal to \(\lambda\).

For:

$$
X\sim \mathrm{Poisson}(\lambda)
$$

the expected value is:

$$
E[X]=\lambda
$$

The variance is:

$$
\mathrm{Var}(X)=\lambda
$$

The standard deviation is:

$$
\mathrm{SD}(X)=\sqrt{\lambda}
$$

### Example

Suppose the number of support tickets received in an hour follows a Poisson distribution with an average of 9 tickets per hour.

Then:

$$
\lambda=9
$$

The expected count is:

$$
E[X]=9
$$

The variance is:

$$
\mathrm{Var}(X)=9
$$

The standard deviation is:

$$
\mathrm{SD}(X)=\sqrt{9}=3
$$

Therefore, the expected number of tickets is 9 per hour, and the standard deviation of the count is 3 tickets.

### Why Is This Property Important?

In many probability distributions, the mean and variance are different parameters. In the Poisson distribution, both are determined by the same parameter.

This gives a useful theoretical relationship:

$$
\mathrm{Var}(X)=E[X]
$$

If real-world count data have a variance substantially larger than the mean, a standard Poisson model may not adequately describe the data. Other models, such as the negative binomial distribution, may be more appropriate.

## 7. Probability of At Least One Event

A common question is: what is the probability that at least one event occurs?

For a Poisson random variable:

$$
X\sim \mathrm{Poisson}(\lambda)
$$

we want:

$$
P(X\geq 1)
$$

Using the complement rule:

$$
P(X\geq 1)=1-P(X=0)
$$

From the Poisson PMF:

$$
P(X=0)=\frac{e^{-\lambda}\lambda^0}{0!}
$$

Since \(\lambda^0=1\) and \(0!=1\):

$$
P(X=0)=e^{-\lambda}
$$

Therefore:

$$
P(X\geq 1)=1-e^{-\lambda}
$$

### Example

A server receives an average of 2 requests per second. Assume a Poisson model.

The probability of receiving at least one request in a one-second interval is:

$$
P(X\geq 1)=1-e^{-2}
$$

Since:

$$
e^{-2}\approx 0.1353
$$

we obtain:

$$
P(X\geq 1)\approx 1-0.1353
$$

$$
P(X\geq 1)\approx 0.8647
$$

The probability of at least one request is approximately 86.47%.

## 8. Probability of More Than a Certain Number of Events

The Poisson distribution can also calculate probabilities such as:

- More than 5 calls in one minute.
- At least 10 defects in a batch.
- Fewer than 3 arrivals in a given interval.

For example, the probability of more than 2 events is:

$$
P(X>2)=1-P(X\leq 2)
$$

Therefore:

$$
P(X>2)=1-[P(X=0)+P(X=1)+P(X=2)]
$$

Each probability can be calculated using the Poisson PMF.

More generally:

$$
P(X>m)=1-\sum_{k=0}^{m}P(X=k)
$$

Substituting the PMF:

$$
P(X>m)=1-\sum_{k=0}^{m}\frac{e^{-\lambda}\lambda^k}{k!}
$$

This complement approach is often easier than adding every probability above the threshold.

## 9. Assumptions Behind the Poisson Model

The Poisson distribution is useful when its assumptions reasonably match the process being modeled.

### 9.1 Events Are Counted in a Defined Interval

The interval may be time, distance, area, volume, or another measurable quantity.

Examples include calls per minute, defects per meter, or requests per second.

### 9.2 The Average Rate Is Stable

The model assumes that the expected event count per unit of exposure is constant within the interval being modeled.

If customer arrivals rise sharply during lunch hours, one constant rate may not adequately describe the whole day. Separate time periods or a model with a changing rate may be more suitable.

### 9.3 Events Occur Independently

In a standard Poisson process, events in non-overlapping intervals are independent.

In practical applications, this assumption can fail if events trigger other events or occur in clusters.

For example, one system failure may cause many related error messages.

### 9.4 Events Are Not Simultaneously Clumped in Infinitesimally Small Intervals

For a standard Poisson process with a finite rate, the probability of two or more events occurring in a sufficiently small interval is negligible compared with the probability of one event.

This assumption is part of the standard Poisson-process model.

### Important Note

Real-world count data do not automatically follow a Poisson distribution merely because they represent event counts. The distribution should be chosen based on the data-generating process, assumptions, and model fit.

## 10. What Is a Poisson Process?

A **Poisson process** is a stochastic process that describes events occurring over time or another continuous exposure scale under particular assumptions.

For a homogeneous Poisson process with rate \(r\) events per unit of time, the number of events in an interval of length \(t\) follows:

$$
N(t)\sim \mathrm{Poisson}(rt)
$$

The expected count is:

$$
E[N(t)]=rt
$$

The variance is:

$$
\mathrm{Var}(N(t))=rt
$$

Here:

- \(r\) is the event rate per unit of time.
- \(t\) is the interval length.
- \(N(t)\) is the number of events in that interval.

The rate \(r\) and the Poisson parameter \(\lambda\) are related by:

$$
\lambda=rt
$$

### Example

A help desk receives an average of 6 calls per hour.

The rate is:

$$
r=6
$$

For a 30-minute interval:

$$
t=0.5
$$

The expected number of calls is:

$$
\lambda=rt
$$

$$
\lambda=6(0.5)=3
$$

Thus, under a homogeneous Poisson-process model, the number of calls in 30 minutes follows:

$$
N(0.5)\sim \mathrm{Poisson}(3)
$$

### Rate Versus Expected Count

Do not confuse the rate with the expected count.

- **Rate:** Events per unit of exposure, such as 6 calls per hour.
- **Expected count:** Expected number of events in a specific interval, such as 3 calls in 30 minutes.

The expected count is the rate multiplied by the interval length when the rate is constant.

## 11. Relationship Between the Poisson and Binomial Distributions

The Poisson distribution is closely related to the binomial distribution.

The binomial PMF is:

$$
P(X=k)=\binom{n}{k}p^k(1-p)^{n-k}
$$

where \(n\) is the fixed number of trials and \(p\) is the probability of success in each trial.

The Poisson distribution can approximate a binomial distribution when:

- \(n\) is large.
- \(p\) is small.
- The product \(np\) remains moderate.

Define:

$$
\lambda=np
$$

Then:

$$
\mathrm{Binomial}(n,p)\approx \mathrm{Poisson}(\lambda)
$$

This is an approximation, not an exact identity for general values of \(n\) and \(p\).

### Example: Rare Defects

Suppose a factory produces 1,000 items, and each item independently has a defect probability of 0.002.

The number of defective items can be modeled exactly as a binomial random variable if the assumptions hold:

$$
X\sim \mathrm{Binomial}(1000,0.002)
$$

The mean is:

$$
\lambda=np
$$

$$
\lambda=1000(0.002)=2
$$

Because the number of trials is large and the defect probability is small, a Poisson approximation may be useful:

$$
X\approx \mathrm{Poisson}(2)
$$

The probability of exactly two defective items can then be approximated by:

$$
P(X=2)\approx \frac{e^{-2}2^2}{2!}
$$

$$
P(X=2)\approx 0.2707
$$

The Poisson approximation gives a probability of approximately 27.07%.

For comparison, the exact binomial probability is:

$$
P(X=2)=\binom{1000}{2}(0.002)^2(0.998)^{998}
$$

The approximation is useful because it replaces a binomial calculation with a simpler expression when the conditions are appropriate.

## 12. Poisson Distribution vs. Binomial Distribution

| Feature | Binomial distribution | Poisson distribution |
|---|---|---|
| What it models | Number of successes in a fixed number of trials | Number of events in a defined interval |
| Parameters | \(n,p\) | \(\lambda\) |
| Possible values | \(0,1,\ldots,n\) | \(0,1,2,\ldots\) |
| Mean | \(np\) | \(\lambda\) |
| Variance | \(np(1-p)\) | \(\lambda\) |
| Typical use | Conversions among a fixed number of users | Calls received in a time interval |
| Key assumptions | Fixed trials, independence, same success probability | Suitable count process with a defined rate and appropriate independence assumptions |

The binomial distribution counts successes among a fixed number of trials. The Poisson distribution models event counts over an interval and can also approximate binomial counts under suitable conditions.

## 13. When Is the Poisson Distribution Useful?

### 13.1 Call Centers

A call center may model the number of incoming calls per minute to estimate staffing needs.

If the average arrival rate is stable, the Poisson distribution can help estimate the probability of unusually busy intervals.

### 13.2 Website Traffic

A web server may use a Poisson model for the number of incoming requests per second.

This can help with capacity planning, although real traffic may show bursts and dependencies that violate the basic assumptions.

### 13.3 Manufacturing Quality Control

The Poisson distribution can model the number of defects per unit of material or production interval when defects occur independently at a stable rate.

For example, it may be used to model defects per meter of cable or flaws per sheet of material.

### 13.4 Insurance Claims

The number of claims received by an insurer over a fixed period may be modeled using a Poisson distribution when the assumptions are appropriate.

The expected number of claims can help with planning and risk analysis.

### 13.5 Healthcare and Public Health

Poisson models may be used to study event counts, such as the number of arrivals at a clinic or the number of reported cases within a specified interval.

The suitability of the model depends on the rate stability, independence, and other characteristics of the data.

### 13.6 Reliability Engineering

The number of component failures over a period may be modeled using a Poisson distribution under suitable assumptions.

This can support maintenance planning and reliability analysis.

### 13.7 Machine Learning and Count Prediction

The Poisson distribution is used in statistical models when the target variable is a nonnegative count.

Examples include:

- Number of purchases by a customer.
- Number of support tickets submitted by a user.
- Number of accidents at a location.
- Number of events occurring during a fixed period.

A Poisson regression model relates the expected count to input features.

## 14. Poisson Regression in Machine Learning

**Poisson regression** is a generalized linear model commonly used when the target variable is a nonnegative integer count.

Suppose \(Y_i\) is a count associated with observation \(i\). A Poisson regression model assumes:

$$
Y_i\sim \mathrm{Poisson}(\lambda_i)
$$

The expected count depends on input features.

A common model uses the logarithm link:

$$
\log(\lambda_i)=\beta_0+\beta_1x_{i1}+\cdots+\beta_px_{ip}
$$

Equivalently:

$$
\lambda_i=\exp\left(\beta_0+\sum_{j=1}^{p}\beta_jx_{ij}\right)
$$

where:

- \(\lambda_i\) is the expected count for observation \(i\).
- \(x_{ij}\) is feature \(j\) for observation \(i\).
- \(\beta_0\) is the intercept.
- \(\beta_j\) is the coefficient for feature \(j\).

The exponential function ensures that the predicted mean count is positive.

### Example: Predicting Support Tickets

Suppose a company wants to predict the number of support tickets submitted by a customer in one month.

Potential features include:

- Number of products owned.
- Customer tenure.
- Number of recent transactions.
- Customer plan type.

A Poisson regression model estimates the expected ticket count from these features.

For example, if the predicted mean for a customer is 2.5, the model assigns probabilities to possible counts such as 0, 1, 2, 3, and higher values.

The predicted mean does not imply that a customer must submit exactly 2.5 tickets. Individual counts remain nonnegative integers.

### When Poisson Regression May Not Fit Well

A standard Poisson regression model assumes that the conditional variance equals the conditional mean:

$$
\mathrm{Var}(Y_i\mid X_i)=E[Y_i\mid X_i]=\lambda_i
$$

If the data exhibit substantial overdispersion, meaning that the variance is greater than the mean after accounting for the model, a negative binomial model may be more appropriate.

If there are more zeros than the standard model can reasonably explain, zero-inflated or hurdle models may also be considered.

Model choice should be guided by diagnostics and the data-generating process.

## 15. Limitations of the Poisson Distribution

Although the Poisson distribution is powerful, it does not fit every count dataset.

### 15.1 Overdispersion

Overdispersion occurs when the variance is greater than the mean.

The Poisson distribution requires:

$$
\mathrm{Var}(X)=E[X]=\lambda
$$

If observed data show much larger variance, the standard Poisson model may underestimate uncertainty and assign unrealistic probabilities to extreme counts.

A negative binomial distribution is one common alternative.

### 15.2 Underdispersion

Underdispersion occurs when the variance is smaller than the mean.

A standard Poisson model may not adequately describe such data. Other count models may be needed.

### 15.3 Changing Rates

If the event rate changes substantially over time, a constant-rate Poisson model may be inappropriate.

For example, customer arrivals may vary by time of day or day of the week.

Possible approaches include modeling different time periods separately or using a Poisson regression model with time-related features.

### 15.4 Dependence and Clustering

Events may trigger additional events or occur in clusters.

Examples include repeated system errors caused by a single failure or social-media activity generated by a viral post.

Such dependence can violate the assumptions of a standard Poisson process.

### 15.5 Excess Zeros

Some datasets contain more zero counts than a standard Poisson model predicts.

For example, many customers may never use a particular service, while a smaller group uses it frequently.

A zero-inflated or hurdle model may be more appropriate in such cases.

## 16. Common Mistakes

### Mistake 1: Treating Lambda as a Probability

The parameter \(\lambda\) is an expected event count for the specified interval, not generally a probability.

A probability must lie between 0 and 1, while \(\lambda\) can be greater than 1.

### Mistake 2: Forgetting to Match the Interval

If the event rate is 8 per hour, the expected count in 30 minutes is 4, not 8.

Always match the rate to the interval being analyzed.

### Mistake 3: Confusing Exactly with At Least

The probability of exactly \(k\) events is:

$$
P(X=k)=\frac{e^{-\lambda}\lambda^k}{k!}
$$

The probability of at least one event is:

$$
P(X\geq 1)=1-e^{-\lambda}
$$

These are different questions and require different calculations.

### Mistake 4: Assuming Every Count Dataset Is Poisson

A count variable is not automatically Poisson distributed. Check whether the assumptions and model diagnostics support the distribution.

### Mistake 5: Forgetting That Mean Equals Variance

For a Poisson distribution:

$$
E[X]=\mathrm{Var}(X)=\lambda
$$

This equality is a defining property of the standard Poisson model.

### Mistake 6: Treating the Binomial Approximation as Exact

The approximation:

$$
\mathrm{Binomial}(n,p)\approx \mathrm{Poisson}(np)
$$

is most useful when \(n\) is large, \(p\) is small, and \(np\) remains moderate. It is not an exact equality in general.

## 17. Common Interview Questions and Answers

### Q1. What is the Poisson distribution?

**Answer:** It is a discrete probability distribution used to model the number of events occurring in a defined interval under suitable assumptions.

### Q2. What does lambda represent?

**Answer:** Lambda represents the expected number of events in the interval being modeled.

### Q3. What is the PMF of the Poisson distribution?

**Answer:**

$$
P(X=k)=\frac{e^{-\lambda}\lambda^k}{k!}
$$

### Q4. What are the mean and variance of the Poisson distribution?

**Answer:**

$$
E[X]=\lambda
$$

$$
\mathrm{Var}(X)=\lambda
$$

### Q5. What is the standard deviation?

**Answer:**

$$
\mathrm{SD}(X)=\sqrt{\lambda}
$$

### Q6. What is the probability of zero events?

**Answer:**

$$
P(X=0)=e^{-\lambda}
$$

### Q7. What is the probability of at least one event?

**Answer:**

$$
P(X\geq 1)=1-e^{-\lambda}
$$

### Q8. What is the relationship between the Poisson and binomial distributions?

**Answer:** The Poisson distribution can approximate a binomial distribution when the number of trials is large, the success probability is small, and the product \(np\) remains moderate.

### Q9. When is the Poisson distribution useful?

**Answer:** It is useful for modeling counts such as calls per minute, defects per unit, requests per second, and claims per month when the model assumptions are reasonable.

### Q10. What is a Poisson process?

**Answer:** It is a stochastic process in which events occur over time or another exposure scale according to specified assumptions, often with a constant rate and independent increments.

### Q11. What is Poisson regression?

**Answer:** It is a regression model used to predict count outcomes, often with a logarithmic link between the expected count and input features.

### Q12. What does overdispersion mean?

**Answer:** Overdispersion means that the variance exceeds the mean. It can indicate that a standard Poisson model does not capture all the variability in the data.

### Q13. Can the Poisson distribution model fractional event counts?

**Answer:** No. The Poisson distribution assigns probabilities to nonnegative integer counts: 0, 1, 2, and so on.

### Q14. Does the Poisson distribution always have a constant rate?

**Answer:** A single Poisson distribution has a fixed parameter for the interval being modeled. A homogeneous Poisson process assumes a constant rate over time. Processes with changing rates require a different or extended model.

## 18. Practice Problems

### Problem 1: Exactly Three Calls

A call center receives an average of 5 calls per minute. Assume a Poisson model. Find the probability of exactly three calls in one minute.

**Solution:**

The parameters are:

$$
\lambda=5,\qquad k=3
$$

Using the PMF:

$$
P(X=3)=\frac{e^{-5}5^3}{3!}
$$

Since:

$$
5^3=125,\qquad 3!=6
$$

we obtain:

$$
P(X=3)=\frac{125e^{-5}}{6}
$$

Therefore:

$$
P(X=3)\approx 0.1404
$$

The probability is approximately 14.04%.

### Problem 2: No Customer Arrivals

A store receives an average of 2 customers every 10 minutes. Assume a Poisson model. Find the probability of no customer arrivals in a 10-minute interval.

**Solution:**

The parameter is:

$$
\lambda=2
$$

For zero arrivals:

$$
P(X=0)=e^{-2}
$$

Therefore:

$$
P(X=0)\approx 0.1353
$$

The probability is approximately 13.53%.

### Problem 3: At Least One Error

A computer system experiences an average of 0.5 errors per hour. Assume a Poisson model. Find the probability of at least one error in an hour.

**Solution:**

The parameter is:

$$
\lambda=0.5
$$

Use the complement rule:

$$
P(X\geq 1)=1-e^{-0.5}
$$

Therefore:

$$
P(X\geq 1)\approx 0.3935
$$

The probability is approximately 39.35%.

### Problem 4: Convert an Hourly Rate to a 15-Minute Interval

A call center receives an average of 12 calls per hour. Assume a constant rate. Find the expected number of calls in 15 minutes.

**Solution:**

The hourly rate is:

$$
r=12
$$

The interval length in hours is:

$$
t=\frac{15}{60}=0.25
$$

Therefore:

$$
\lambda=rt
$$

$$
\lambda=12(0.25)=3
$$

The expected number of calls in 15 minutes is 3.

### Problem 5: Identify the Appropriate Model

Choose the most appropriate starting model under each scenario.

1. Number of heads in 10 independent coin tosses.
2. Number of calls received by a call center in one minute under a stable-rate assumption.
3. Number of defective items selected without replacement from a small batch with a known number of defective items.

**Solution:**

1. **Binomial distribution**, because there is a fixed number of independent trials with the same probability of heads.
2. **Poisson distribution**, if the event rate and independence assumptions are reasonable.
3. **Hypergeometric distribution**, because the items are sampled without replacement from a finite population.

## 19. Key Takeaways

- The Poisson distribution models nonnegative integer event counts over a defined interval.
- Its parameter \(\lambda\) is the expected count in that interval.
- The PMF is \(P(X=k)=e^{-\lambda}\lambda^k/k!\).
- The mean and variance are both \(\lambda\).
- The standard deviation is \(\sqrt{\lambda}\).
- The probability of zero events is \(e^{-\lambda}\).
- The probability of at least one event is \(1-e^{-\lambda}\).
- When the rate is constant, the expected count equals the rate multiplied by the interval length.
- The Poisson distribution can approximate the binomial distribution when the number of trials is large, the success probability is small, and \(np\) remains moderate.
- Poisson regression is useful for predicting count outcomes.
- Overdispersion, changing rates, dependence, and excess zeros can indicate that a standard Poisson model is not suitable.

