# Introduction to Inference

Let's review some basic definitions which are necessary to start with inferentil
statistics.
A **sample statistic** as a point estimate for a population parameter, for example,
the sample mean is used to estimate the population mean, and note that point
estimate and sample statistic are synonymous.

Notice that point estimates (such as the sample mean) will vary from one sample
to another, and we define this variability as **sampling variability** 
(sometimes also called sampling variation).

The the sampling variability of the mean, also called the **standard error**, as 
SE=\frac{\sigma}{\sqrt{n}} where sigma  is the population standard deviation.

Note that when the population standard deviation σ is not known (almost always),
the standard error SE can be estimated using the sample standard deviation s, so
that SE=\frac{s}{\sqrt{n}}.

It is important to distinguish standard deviation (σ or s) and standard error
(SE). In particular:
* standard deviation measures the variability in the data
* standard error measures the variability in point estimates from different samples 
    of the same size and from the same population, i.e. measures 
    the sampling variability.
Recognize that when the sample size n increases we would expect the sampling
variability to decrease.

In statistics, we generally cannot afford to work with entire populations most
of the times, so it is important to work with samples. We call **sample
distributions** a set of samples taken from a distribution, and we define as
**sampling distribution** (similar words but different concepts), the
distribution of the sample statistic computed on samples belonging to the sample
distributions set.

We call the standard deviation of the sampling distribution **standard error**.

So to make an example, if we consider as population, all the women in Italy,
then take 100 samples, the set of these samples goes under the name of **sample distributions**
while if we compute a specific statistic on these samples (e.g., mean or
standard deviation) we have the sampling distribution.

## Central Limit Interval

In this context it is important to introduce the **Central Limit Theorem**,
which states:
The distribution of sample statistics is nearly normal, centered at the
population mean, and with a standard deviation equal to the population standard
deviation divided by square root of the sample size.

x \circa N ( mean = mu, SE = s(or sigma) / sqrt(n))

Conditions valid to apply CLT are:
1. independence of sampled observations, which can be obtained by:
    * random sampling (or assignment, depending if we have an observational
        study or an experimental study)
    * if we are in a sampling without replacement setting, we must have sample size  
      `n < 10%` of the population, in order to not have dependent observations
      Notice that in realistic survey sampling situations we sample without
      replacement, since we don't want for example to sample the same person for
      a survey
2. sample size (or skew): either the population distribution is normal, or if it is
   skewed or in general non normal, the samples size needed will be larger (rule
   of thumb, n > 30)

### Example of application of the CLT

Let's say that we have a non normal distribution of songs with population mean of 3.45
minutes and population standard deviation of 1.63 minutes. We want to calculate the probability
that a randomly selected  song lasts more than 5 minutes, in this case we can
just divide the number of songs who last more than five minutes to the total
number of songs to obtain this probability.

Now, since we know the parameters of the distribution, let's say that we want to
estimate if a randomly selected sample of 100 songs collected from the
population will last for at least 6 hours. We know that 6 hours are 60*6 = 3600 minutes,
and so we want that the average duration of a song is at least greater than 3.6 minutes.

Now thanks to the CLT we can use this sample and build a normal distribution and
make inferential statistics on this distribution.

So the CLT says that:

\bar{x} \circa N(mean = mu = 3.45, SE = sigma/sqrt(n) = 1.63/sqrt(100) = 0.163)

Now that we have this distribution, we will search for values greater of 3.6, in
order to do this we calculate the Z-score which is:
Z = (3.6 - 3.45) / 0.163 = 0.92

now we can use find the area corresponding to 0.92 with tables or with R and we
can find out that:

P(X > 0.92) = 0.179

So this means that there is an approximately 18\% of chance of selecting a
playlist which will last at least 6 hours if we choose randomly 100 songs.



## Confidence Interval

A plausible range of values for the population parameter is called **confidence
interval**. In poor words, if we only report a point estimate (i.e., sample
statistic), we probably are not hitting the real population parameters, but 
on other hand if we use confidence intervals, we have good chances of hitting 
the population parameter.



So generally what we do is constructing an interval around the point estimate we
have, so let's say we have the sampling distribution mean, at this point since
we know we are dealing with a gaussian distribution, we can build a confidence
interval by taking into account 2 standard deviation which account for `95%` of
the entire data. So we will use the following notation:
CI = x \plusorminus 2*SE

We indeed generally construct confidence intervals taking into account a point
estimate plus or minus a **margin of error**.

Let's make an example:
One of the earliest examples of behaviorala asymmetry is a preference in humans
for turning the head to the right in the final weeks of gestation. A study of
124 couples found that 64.5% turned their heads to the right when kissing. The
standard error associated with this estimate is roughly 4%. 
Which of the following statements is **false**?

* A higher sample size would yield a lowe standard error (TRUE)
* The margin of error for a 95% CI for the percentage of kissers who turn their
    heads to the right is roughly 8%
* The 95% CI for the percentage of kissers who turn their heads to the right is
    roughly 64.5% \plusorminus 4%. (FALSE) this should be 8% to be right
* The 99.7% CI ofr the percentage of kissers who turn their heads to the right
    is roughly 64.5% \plusorminus 12% (TRUE). since 99.7 is three standard
    deviations from the mean, so 3*4=12

Specifically, a **confidence interval for a population mean** is computed as the
sample mean plus/minus a margin of error (critical value corresponding ot the
middle XX^ of the normal distribution times the standard error of the sampling
distribution)

\bar{x}\plusorminus z* \frac{s}{\sqrt{n}}

As for the CLT, there are conditions who need to be satisfied to use this
confidence interval, which are the same who apply for CLT:
1. independence, sampled observations must be independent
2. sample size/skew: n>=30, larger if the population distribution is very
   skewed, in statistics we call large samples, samples `>=30`

Note that we should always Interpret a confidence interval as "We are XX%
confident that the true population parameter is in this interval:, where XX% is
the desired confidence level. 


## Accuracy and Precision

We have to define what is the meaning of 'accuracy' and 'precision' of
confidence intervals. 
We define as **accuracy** in terms of whether or not the confidence interval containns
the true population parameter.
We define as **precision**, the width of a confidence interval.


First we need to define what is a **confidence level**, in order to explain what
it is, we have to suppose to take many samples and build a confidence interval
from each sample using the equation:

point estimate \plusorminus 1.96 \times SE
N.B.: Notice that 1.96 is due to the fact that we are assuming a confidence
level of 95\%.

At this point, 95\% of those intervals would contain the true population mean
(mu).

The confidence level is not something we calculate but it is something we
choose, and then we base our calculations on this choice.

Commonly used confidence levels in practice are, 90\%, 95\%, 98\% and 99\%.

Remember that changing the confidence level simply means to change the
coefficient we use in the determination of our confidence interval.

So remember these differences:
* **Confidence Interval**: it is an interval around a point estimate, and it is
    computed based on a confidence level which determines the coefficient to use
    in its formula
* **Confidence Level**: it is a percentage that we choose a priori to compute
    our confidence interval, it basically can be interpreted as the percentage
    of times our confidence interval for the sample will contain the real
    population parameter

Notice that as the confidence level increases the confidence interval gets wider.

So of course if we want to catch the real population parameter, we should use a
wider confidence level, but this will also increase the width of our interval.

Anyway sometimes keeping a high confidence level and hence a high confidence
interval, although it is **accurate**, it is very low informative or in other
words precise.

To make an example, if I say that tomorrow temperature is with a confidence
level of 99.9999% in a confidence interval which goes from -29 degrees to 43
degrees, this is very accurate, but low informative and it is definitely not
precise in many contexts.

So how can we get the best of both worlds? How can we be both precise and
accurate?

SOLUTION: **increase the sample size**, if we increase our sample size, this
will shrink our standard error and our margin of error and therefore we can
still remain at a high confidence level while not necessarily needing to
increase the width of the confidence interval as well.


### Required Sample Size for Margin of Error

Now we will see how to determine the required sample size depending on the
margin of error we want to achieve.

Consider that, if all else held constant, as sample size increases, the margin of
error decreases.

Once e have a formula for the confidence interval of a specific sample statistic
we can easily the sample size with a given confidence level.

For example we know that at the 95\% confidence level the confidence interval
for the mean is:

mean \plusorminus 2*StandardError
where standard error is sigma/sqrt(n)
so we just have to apply basic math to find the equation for n.

N.B.: Long story short about the relationship between the margin of error and the 
sample size, as a rule of thumb, if we want to cut our margin of error by half, 
we have to quadruple our sample size.

QUESTION: A given confidence interval is calculated based on a random sample of
n observations. If we want to make this interval narrower (1/3 of what it is
now), how many observations should we sample?
ANSWER: 9n, since n is under the square root sign.

### Example of Application of the CLT

A sample of 50 college students were asked how many relationships they have been in so
far. The students in the sample had an average of 3.2 relationships with a
standard deviation of 1.74. In addition, the sample distribution was only
slightly skewed to the right. Estimate the true average number of exclusive
relationships based on this sample using a 95\% confidence interval.

Well again, we apply the formulas of the CLT, since we assume that data is
independent and 50 as size is less than 10\% of the total number of students 
in a typical college.

We first calculate the Standard Error, so:
SE = s/sqrt(n) = 1.74/sqrt(50) = 0.246, so our confidence interval is:
3.2 \plusorminus 1.96 (0.246) = (2.72, 3.68).

So concluding:
* So we are 95\% confident that college students on average have been in 2.72 to
  3.68 exclusive relationships.
* And that 95\% of random samples of 50 college students will yield Confidence
  Intervals that capture the true population parameter.
