# MAP

Maximum A Posteriori (MAP) Estimation is a method used to estimate the parameters of a statistical model by maximizing the posterior distribution. It combines both the likelihood of the observed data and a prior distribution over the parameters to find the parameter values that are most probable given the data and the prior information.


Likelihood Function:
The likelihood function L(theta | X) measures the likelihood of observing the data X given the parameters theta.
L(theta | X) = P(X | theta)
Here, theta represents the parameters of the model, and X represents the observed data.

The prior distribution P(theta) represents our knowledge or belief about the parameters before observing the data. It is based on previous knowledge or assumptions about the parameters.

The posterior distribution P(theta | X) represents the probability of the parameters given the observed data. It is derived using Bayes' Theorem:
P(theta | X) = [P(X | theta) * P(theta)] / P(X)
Where:
P(X | theta) is the likelihood function.
P(theta) is the prior distribution.
P(X) is the marginal likelihood, which is a normalizing constant ensuring that the posterior distribution sums to 1.

MAP Estimation:
In MAP estimation, we seek to find the parameter values theta_hat that maximize the posterior distribution:
theta_hat = argmax_theta P(theta | X)

Since P(X) is a constant with respect to theta, we can ignore it when maximizing. Therefore, the MAP estimate is given by:
theta_hat = argmax_theta [L(theta | X) * P(theta)]

Taking the natural logarithm (which preserves the maximization) gives us:
theta_hat = argmax_theta [log(L(theta | X)) + log(P(theta))]
This expression shows that MAP estimation is like Maximum Likelihood Estimation (MLE), but with an additional term that incorporates prior information.



Consider estimating the mean mu of a normal distribution with known standard deviation sigma, assuming a normal prior on mu.

Likelihood Function:
For a normal distribution, the likelihood function for the data X = {x1, x2, ..., xn} is:
L(mu | X) = product [ (1 / (sigma * sqrt(2 * pi))) * exp(- (xi - mu)^2 / (2 * sigma^2)) ] for i = 1 to n

Prior Distribution:
Assume a normal prior on mu with mean mu_prior and standard deviation sigma_prior:
P(mu) = (1 / (sigma_prior * sqrt(2 * pi))) * exp(- (mu - mu_prior)^2 / (2 * sigma_prior^2))

Posterior Distribution:
The posterior distribution (ignoring constants) is:
P(mu | X) proportional to exp(- sum((xi - mu)^2) / (2 * sigma^2)) * exp(- (mu - mu_prior)^2 / (2 * sigma_prior^2))

MAP Estimate:
To find the MAP estimate mu_hat, maximize the log-posterior:
mu_hat = argmax_mu [ -1/(2 * sigma^2) * sum((xi - mu)^2) - 1/(2 * sigma_prior^2) * (mu - mu_prior)^2 ]
This combines the likelihood of the data with the prior belief about mu.
