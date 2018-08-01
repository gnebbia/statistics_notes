# Statistics Basics
Statistics is a branch of mathematics dealing with the collection,
organization, analysis, interpretation and presentation of data.

## Data Basics
Data is generally organized in what we call "data matrix".
A data matrix is a table where each column represent a *variable* and each row
represents a data point (or observation or case).


### Types of Variable
Identifying the type of variables is one of the first steps done 
in Data Analysis in order to better understand which kind of analysis may 
be more appropriate.  

Variables can be categorized in:

* Numerical (or quantitative), so variables who take numerical variables and 
    sensible to arithmetic operations such as sum, product, averages and so on.
    Numerical variables can be categorized furtherly into:
    * Continuous: variables can assume an infinite set of values within a 
        given range
    * Discrete: these variables can assume a limited set of values,
        generally count data is an example of discrete numerical variables,
        e.g., the number of cars in a city
* Categorical (or qualitative), so variables who take on a limited number of
    distinct categories, these categories can be identified with numbers but
    arithmetic operations do not make sense on this type of data.
    Categorical variables cann be categorized furtherly into:
    * Ordinal: levels have an inherent ordering, like "XXL", "XL", "L", "M"
    or another type of categorical ordinal variable may be "strong", "weak",
    "super weak" and so on.
    * Regular Categorical: these variables may not have an ordering, 
    for example we can think about a variable who can only assume values "
    hot", "cold" or a variable containing the italian regions, so 
    "Campania", "Lazio", "Lombardia", these values do not have an inherent 
    ordering.

Once we have identified the types of variables, we may want to understand 
the relationships between variables. Two variablees that show some connection 
to one another called **associated**
or dependent.
An association can be further described as positive or negative, and 
if two variables are not associated they are said to be independent

## Types of Studies
Statisticians perform studies, these can be categorized into:

* Observational: so data is collected in a way that does not interfere with the
  system, so we just observe the data, in observational study we can only
  establish an **association** or a correlation, an observational study can be
  further categorized into:
    * retrospective study: if it uses data from the past
    * prospective study: if it uses data which is collected at the moment,
      throughout the study
* Experiment: researchers randomly assign subjects to treatments, and 
    try to establish causal connections.

We can make an example, let's say that we are analyzing people which is on a
particular mediterranean diet.
If we just collect data of people which is not following this diet and people
which is following this diet, then we are performing an observational study,
while in the other case if we are selecting a group of people and imposing on
some of them to follow the diet and on some of them to not follow the diet, this
is an experiment.

Notice that Random assignment is the most important difference between
observational studies and experiments.


In an observational study, we can only make associations (also called
correlations) we cannot talk about causality, so if in an observational study we
find out that girls who are on diet are slimmer, there could be three possible
explanations:

1. being on diet for girls make them slimmer
2. being slimmer causes girl to eat breakfast
3. there is a third variable responsible for both

Notice that extraneous variables that affect both the explanatory and the
response variable and make it seem like there is a relationship between them 
are called **cofounding variables**.

**REMEMBER**: correlation does not imply causation, the sell of ice creams is
highly correlated during the year to the number of drown people, but they are
not the cause.

Observational study allow us *mostly* only to observe correlations, while
experiments allow us to infer causations.
Anyway there are more advanced methods called "causal inference" which allow to
make causal inferences from observational studies.

## Sampling and Sources of Bias

When working with data, we cannot most of the times analyze all the
items/individuals in an entire population (a census).
We only can take a limited amount of items/individuals, this is because taking
the entire population can be impossible, or some items are hard to locate or
measure, or simply it's not efficient/doable taking all the individuals.

That's why we generally take samples, and try to understand things from samples.

Let's make an example, if we are cooking, and we want to understand if our soup
is salty enough, we do not drink all of our soup, we just take a sample, and do
a sort of exploratory data analysis, then we make inference about the entire
soup.

Anyway we must make sure that our sample is not biased, this means for example
that if all the salt is on the bottom of the pot and we just take a sip from the
top, this will not be representative of the entire soup, so we have to take a
sample which is representative of the entire population in order to make
inferences about the population. 
N.B.: In the case of the soup, it will be enough to stir and then sample again.


Let's see some sources of bias:

* Convenience sample: individuals who are easily accessible are more likely to be
  included in the sample
* Non-response: if only a (non random) fraction of the randomly sampled people
  respond to a survey such that the sample is no onger representative of the
  population
* Voluntary response: occurs when the sample consists of people who volunteer to
  respond because they have strong opinions on the issue


### Sampling Methods
Now that we have an idea of sampling, let's see different sampling techniques:

* **Simple Random Sampling (SRS)**: we randomly select cases from the population,
  such that the probability of each case being selected should be equal
* Stratified Sampling: we stratify (or divide) the population into homogenous
  "strata", then randomly sample from within each stratum, for example if we
  want to be sure that both gender are equally represented in a study, we might
  have two strata, male and female and then randomly sample from these strata
* **Cluster Sampling**: we divide the population into clusters, then randomly sample
  some clusters and then take all the cases in the selected clusters. For
  example if we want to sample in a city, we can randomly pick neighborhoods of
  the city which are clusters
* **Multistage Sampling**: this is like cluster sampling with an added step, so we
  divide the popultation into clusters, then randomly sample the clusters and
  then again randomly sample cases within clusters. For example if we want to
  sample from a city we can randomly pick neighborhoods and then randomly pick
  people from each neighborhood

## Experimental Design

Let's learn some experimental design terminology, the four principles of
experimental design are:

* **Control**: compare treatment of interest to a control group
* **Randomize**: randomly assign subjects to treatments
* **Replicate**: collect a sufficiently large sample, or replicate the entire
  experiment
* **Block**: block for variables known or suspected to affect the outcome, so if
  there are variables which are known to affect the outcome, we should divide
  our sample into blocks depending on this variable


Let's make an example, let's say we want to make an experiment on some
particular gel for runners which shoule help runners to run faster, so in this
case we have:

* treatment group: gets the energy gel
* control group: gets no energy gel

now since we have the suspect that energy gels might affect pro and amateur
athletes differently, we block for "skill level", so we divide our sample into
pro and amateur and then we randomly assign pro and amateur athletes to tratment
and control groups, so both pro and amateur athletes are equally represented in
both groups

So here we must make a difference between **blocking** variables and
**explanatory** variables:

* Explanatory variables (or factors): are conditions we can impose on
  experimental units
* Blocking variables: are characteristics that the experimental units come with,
  that we would like to control for

Blocking is like stratifying, the only difference is that it is done during
random assignment instead of the random sampling phase.


Example to understand: A study is designed to test the effect of light level and
noise level on exam performance of students. The researcher also believes that
light and noise levels might have different effects on males and females, so
wants to make sure both genders are represented equally under different
conditions. 

In this case we would have 2 explanatory variables (light and noise), 1 blocking
variable (gender), and 1 response variable (exam performance).

The researchers are interested in the effect of light and noise on exam
performance. Since they believe these two variables might be affecting the
outcome, these are the explanatory variables and exam performance is the
response variable. Gender of the student is a nuisance variable they want to
control for, hence they block for it. Unlike light and noise, gender is not a
treatment that is being imposed on the subjects.


Let's cover some other experimental design terminology:

* Placebo: it is a fake treatment, often used as the control group for medical
  studies
* Placebo effect: showing change in the control group despite being on 
  the placebo experiment
* Blinding: experimental units which do not know whether they are in the
  treatment group or in the control group
* Double-Blind: both the experimental units and the researchers don't know the
  gorup assignment

#### Difference between random sampling and random assignment

Random sampling is done on a population to extract a random sample which is
representative of the entire population, so that we can infer generalizations.

Once we have our sample, we have to identify/determine the variables which can
affect the our experiment (the blocking variables) and divide our sample into
these categories, then we randomly assign elements to groups making sure that 
these categories are equally represented.
This assignment isdone randomly and is called "random assignment", this is done 
in order to evaluate causality of a specific study.

So random sampling happens before random assignment, and random assignment is
done to get rid of confounding variables in an experiment, confounding variables
are the blocking variables.

Stratified sampling allows for controlling for possible confounders in the
sampling stage, while blocking allows for controlling for such variables during
random assignment.

![random assignment and sampling][random_assignment_sampling]

[random_assignment_sampling]:img/random_sampling_and_random_assignment.png "Random Sampling and Assignment"

## EXERCISES:

* The General Social Survey conducted annually in the United States asks how
  many friends people have and how they would rate their happiness level (very
  happy, pretty happy, not too happy). In order to evaluate the relationship
  between these two variables a researcher calculates the average number of
  friends for people who categorize themselves as very happy, pretty happy, and
  not too happy. Which of the following correctly identifies the variables used
  in the study as explanatory and response?

  This question refers to the following learning objective(s):

  Identify the explanatory variable in a pair of variables as the variable
  suspected of affecting the other, however note that labeling variables as
  explanatory and response does not guarantee that the relationship between the
  two is actually causal, even if there is an association identified between the
  two variables.

  Having more friends might cause people to be happier or being happier might
  cause people to have more friends. So we can’t easily determine which variable
  is the explanatory and which the response based on which we might expect to
  affect which. However in this particular analysis the happiness level is the
  explanatory variable since we first divide the data into groups based on this
  variable, and then analyze summary statistics of number of friends of people
  who fall into these three categories. Therefore, number of friends is the
  response variable.

  So the **answer** is explanatory: level of happiness, and response is the number
  of friends

* In a study published in 2011 in The Proceedings of the National Academy of
  Sciences, researchers randomly assigned 120 elderly men and women who
  volunteered to be a part of this study (average age mid-60s) to one of two
  exercise groups. One group walked around a track three times a week; the other
  did a variety of less aerobic exercises, including yoga and resistance
  training with bands. After a year, brain scans showed that among the walkers,
  the hippocampus (part of the brain responsible for forming memories) had
  increased in volume by about 2% on average; in the others, it had declined by
  about 1.4%. Which of the following is false?


  The results of this study can be generalized to all elderly.
  This question refers to the following learning objective(s):

  Classify a study as observational or experimental, and determine whether the
  study’s results can be generalized to the population and whether they suggest
  correlation or causation.

      If random sampling has been employed in data collection, the results
      should be generalizable to the target population.
          * If random assignment has been employed in study design, the results
          suggest causality.

          * Results cannot be generalized to the population of all elderly since
          random sampling was not employed; the participants volunteered to be a
          part of the study. This introduces volunteer bias, as those who
          volunteer for this study may not necessarily constitute a
          representative sample from the population of all elderly. For example,
          they may be people who pay more attention to their health compared to
          average.


          
