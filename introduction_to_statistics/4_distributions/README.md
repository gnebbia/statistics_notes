# Distributions

## Normal Distribution

A lot of variables in natures are normally distributed, for example height of
people.

The normal distribution is:
* Unimodal
* Symmetric
* Resembles a bell curve
* Many variales are nearly normal but non are exactly normal
* It has two parameters mean and standard deviations

68-95-99.7% rule states that in a normal distribution:
* 68% of data falls within a standard deviation from the mean
* 95% of the data falls within two standard deviations from the mean
* 99.7% of the data falls within three standard deviations from the mean

Given a mean value and a range (i.e., min and max) we can estimate a normal
distirbution by estimating the standard deviation, for example:

$mean \plusorminus (3\times standard deviation$

checking for standard deviation to satisfy that rule.

### Comparing Normal Scores

Sometimes we want to compare values which are distributed on different normal
distributions.
Let's take an example, let's say that Alice scored in an exam in Bangkok 1800
and scores in Bangokok are normally distributed with a mean of 1500 and a
standard deviation of 300.
And Bob did an exam in Tokyo where scores are different but still normally
distributed with a mean of 21 and a standard deviation of 5 and he scored 24.
How can we understand who performed better?
In order to do this we can understand how many standard deviations their scores
are with respect to their distribution, hence for Alice:
1800 - 1500 / 300 = 1

while for Bob:
24 - 21 / 5 = 0.6

Hence Alice did a better job with respect to Bob.

These values are called standardized scores or Z-scores.

### Z-scores

A **standardized (Z) score** of an observation is the number of standard
deviations it falls above or below the mean:

$Z = \frac{observation - mean}{SD}$


We use the Z for standardized, that's where it comes from, and we did not use S,
since S is used to denote standard deviations.

* By definition the Z score of the mean of a distribution is zero.
* Z-scores are used also to identify unusual observations, generally |Z| > 2 are
    considered unusual observations.
* Z-scores are definied for **any** distribution, since any distribution will
    have a mean and a standard deviation, so we can compute the Z-score of an
    observation even if it comes from a random variable not following the normal
    distribution
* When the distribution is normal, Z-scores can be used to calculate percentiles
* A percentile is the percentage of observations that fall below a given data
    point
* graphically, percentile is the area below the probability distribution curve
    to the left of the observation
* We can get percentiles of normal distribution using statistical programming 
    frameworks/libraries or as the old school did, so with tables

In R we can do:
```R
# this will give us the percentile corresponding to -1 of a normal distribution
# with mean 0 and stddev equal to 1
pnorm(-1, mean = 0, sd =1)
# which gives roughly 0.158, so it is the 15.8%
```

Example:

Alice scores 1800 on a SAT test and we know that SAT tests are normally
distributed with a mean of 1500 and a sd of 300. What is Alice's percentile
score?

in R we wouldl do:
```R
pnorm(1800, mean = 1500, sd = 300)
# results in 0.8413
# this means that pam scored better or equal to the 84.13% of the other students
```
If we had to do it with a table, we just do:
$Z = \frac{1800 - 1500}{300} = 1$
then we check on the table:
`P(Z < 1) = 0.8413`

now if we wanted P(Z>1) we just have to do:
P(Z > 1) = 1 - 0.8413 = 0.1587

Example 2:
ACT scores are distributed nearly normally with mean 21 and standard
deviation 5. Jim, who scored a 24 on his ACT. What is Jim's percentile?

now we first compute its standardized Z score which is:

Z = 24 - 21 / 5 = 0.6
then  we check in the table `P(Z < 0.6)` and we find out that
Jim his in 0.7257 percentile, so 72.57%.
So Jim scored better or equal than 72.57% of the other students.

We can also solve the inverse problem, so what is the cutoff value of the 90
percentile ? 
In R we can just do:
```R
qnorm(0.90, 1500, 300)
# this gives us the 90 percentile of a normal distribution with mean 1500 and
# stddev 300
```


Example 3: 
ACT scores are distributed nearly normally with mean 21 and standard deviation 5.
A friend of yours tells you that she scored in the bottom 10% on the ACT.  What 
is the highest possible score she could have gotten? Choose the closest answer.


We can either solve it with R using `qnorm` or byb using the table and looking
in the big matrix a value which is approximately 0.10, we find in the table a
value of 0.1003 which correspondsd to a Z score of -1.28.

At this point we have the Z score, the mean and the stddev by solving the
equation we can find the cutoff value which is:

$ (-1.28 * 5) + 21 = 14.60 $

So having scored in the bottom 10% she will have at maximum scored 14.60.


### When a Distribution is Normal?

The problem is how can we understand when a distribution is nearly normal?

What we do is a normal probability plot, where data are plotted on the y axis of
a normal probability plot and theoritical quantiles (following a normal
distirbution) are on the x axis.

* if there is a one-to-one relationship between data and theoritical quantiles,
    then the data dollow a nearly normal distribution
* since a one-to-one relationship would appear as a straight line ona scatter
    plot, the closer the points are to a perfect straight line, the more
    confident we are about the fact that data follow a normal distribution
* constructing a normal probability pllot requires calculating prcentiles and
    corresponding Z-scores for each observation which is tedious. Therefore we
    generally rely on software when making these plots

IMAGE: quantile plot interpretation


## Binomial Distribution



