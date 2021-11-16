
<!-- https://stackoverflow.com/questions/40289457/stan-using-target-syntax -->
Thus, the essence of computation in Stan is dealing with the logarithm of the posterior probability density and its gradient; there is no direct random sampling of parameters from distributions.

The syntax

`target += u;`

adds u to the target log density.

The target density is the density from which the sampler samples and it needs to be equal to the joint density of all the parameters given the data up to a constant (which is usually achieved via Bayes's rule by coding as the joint density of parameters and modeled data up to a constant). You access it as lp__ in the posterior, but be careful, as it also contains the Jacobians arising from the constraints and drops constants in sampling statements---you do not want to use it for model comparison.

From a sampling perspective, writing

`target += normal_lpdf(y | mu, sigma);`

has the same effect as

`y ~ normal(mu, sigma);`

Following logarithm calculation rules, this multiplication is equal to add the log probability density of a given data `y` to the current log-probability. `(log(a*b) = log(a) + log(b)`, hence the equality of multiplication and sum).

The _lpdf signals it's the log probability density function for the normal, which is implicit in the sampling notation. The sampling notation is just shorthand for the target += syntax, and in addition, drops constant terms in the log density.

It's explained in the statements section of the language reference (the second part of the manual) and used in multiple examples through the programmer's guide (the first part of the manual).
