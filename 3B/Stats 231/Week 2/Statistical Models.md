
Why are statistical models useful?

We know theoretical properties of probability distribution that can be applied to real-world problem, if we think those probability distribution are appropriate models for our data

By proposing a statistical model (probability distribution) for our data, we can use our knowledge of that distribution's theoretical properties to answer questions about our study.

To determine how well the model fits the data we need a value for $\theta$ from the data

**We denote this value $\hat{\theta}$**

![[Pasted image 20230919150828.png]]

# Estimating an unknown parameter

Let $Y \approx Bin(25, \theta)$ model the number of heads observed from tossing a coin 25 times.

We can't say $P(head) = \theta = 0.5$, as we don't know

We decide on how reasonable (plausible) a value of $\theta$ is by looking at how probable it makes the observed data.

Values of $\theta$ which make the observed data probable are considered to be more reasonable than values of $\theta$ which make the observed data improbable.

Values of $\theta$ for which the likelihood function $L(\theta)$ is large are more consistent with the observed data

The value of $\theta$ that maximizes $L(\theta)$ for given data $y$ is called the **maximum likelihood esitmate** (m.l. estimate)

If we toss a coin 25 times and observe 10 heads. then

- If $\theta = 0.4$ we have observed an event that occurs with probability $0.161$
- If $\theta = 0.8$ we have observed an even that occurs with probability $0.000015$

It is still **possible** that $\theta = 0.8$. We just showed that it's more probable if $\theta = 0.4$ 

# Relative Likelihood

In the coin toss example, we can calculate

$$
P(Y = 10; \theta = 0.4) = 0.161
$$
$$
P(Y = 10; \theta = 0.25) = 0.042
$$
We say that the data is approx. 4 times more likely if $\theta = 0.4$ than if $\theta = 0.25$

# Log Likelihood

Often it is easier to maximize the log likelihood function rather than the likelihood function


# Example

two polls were conducted in
2010 and 2011, each surveying 2000 Canadian adults asking whether they agreed with the statement “University and college teachers earn too much.” The results are summarized as:

• 2010: n1 = 1500, y1 = 390 agreed with the statement.
• 2011: n2 = 2000, y2 = 540 agreed with the statement.


...


*Unless otherwise stated, it is sufficient to solve the derivative to 0 to get the maximum, due to the nature of the probability models we work with.*



# Likelihood for continuous random variables


...



# Invariance property of maximum likelihood estimates

**invariance property**:

If $\hat{\theta}$ is the likelihood estimate of $\theta$, then $g(\hat{\theta})$ is the maximum likelihood estimate of $g(\theta)$
