Video" [Recording](https://youtu.be/uQKGlA0Zby0)
### Chapter Five - Screening Your Data for Potential Problems
Consider the standard normal distribution, with a symmetrical distribution with very useful mathematical properties. With these known properties we can make inferences about where an individual lies some where in the distribution. 
95.44% of the population falls within +/- 2 standard deviations of the mean
99.74% of the population falls within +/- 3 standard deviations of the mean

We can use the normal distribution for null hypothesis testing, if the probability p was less than 0.05 then we can reject the null hypothesis and look at the alternative, nothing new. Thus far our parametric statistics like ANOVA assumed the variables are normally distributed, but variables may violate normality, and if you use the tools that require assumed normality, well you've probably biased your analysis. 

Most procedures that assume normal distribution are fairly non-robust to modest violations of the this assumption.

Lets look at ways to describe distributions: skew and kurtosis

Skew is the symmetry, to be negatively skewed means you have values to the 'left' or negative direction in the number line away from the 'peaks' of your distribution. Positively skewed means the tail of the distribution is point to the positive numbers or to the 'right' of the number line.

Kurtosis is the shape of the distribution, meaning the height relative to width. In a leptokurtotic distribution we have a tall n skinny distribution. In a platykurtotic distribution we have a flatter and wider distribution.

We previously looked at ceiling and floor effects regarding instrumentation. These effects create non-normal distributions that are not easily grappled with, and you need to deal with instrumentation very early on.

#### Testing for normality
First, visualize your data, it's usually pretty easy to see if things are messed up.

Then we can do things like K-S and S-W tests which look at if a variable confirms to a distribution or if it differs significantly, like a null hypothesis test. If the null hypothesis is that the variable is normally distributed then a significant result leads to rejection of normality, then we probably have a non-normal distribution and we have some work to do!

Power can infer something about normality, in that using S-W/K-S testing can be tough in large sample situations, as there can be some sensitivity to minor deviations. Power and sample size effects these tests, might be difficult to get a non-significant test now matter how normally distributed data is because power to detect minute deviations from normality is great.

### Chapter Six - Dealing with Missing or Incomplete Data
Most statistical techniques assume nearly or completely complete data, and all researchers should examine their data for missingness. If any data or any variable from any participant is not present the researcher is dealing with missing or incomplete data. 

There are situations where you can change the denominator of data, meaning we can cut out the samples with not at random missingness effectively but slicing out some subset of samples. But we lose some of our sample size. 

Illegit missing data common in all research, missing data can also be caused by having done data cleaning, but few authors deal with issue of missing data. Most report, of those that do report something, that they used list wise deletion or mean substitution, which are not great.

MCAR - Missing Completely at Random - Ignorable since its random, and has no effect, unrelated to any variable.
MAR - Missing at Random  - Maybe ignorable
MNAR - Missing Not at Random - Can bias result

#### Listwise Deletion
Deleting any cases/rows with missing data is list wise deletion, which is a default in many statistical software packages (in pandas its not). It's possible that having used listwise deletion would lead researchers to draw an opposite conclusion. Another problem with listwise deletion is loss of statistical power. 

#### Mean Substitution
Group or overall mean is substituted into the missing value. Flaw is that if 20% of a sample is missing, even MCAR/MAR, substituting the identical score for a large portion of the sample artificially reduces variance which can lead to something like leptokurtosis. However, mean substitution for missing scale items when internal consistency is strong and scale is unidimensional appears to be defensible practice. 

Scale items are an individual question or statement in a survey that respondents are going to respond to. A scale is collection of items that are supposed to measure the same thing, like the same underlying concept or dimension, i.e. unidimensionality of questions all belong to the measurement of stress but not questions that measure stress and happiness.

### Imputation
We can use machine learning models to imput the missing values back into our sample! We can take non-missing data and have the information surrounding the missing values in a row be replaced. Sometimes as the model worse and worse at modelling the value its designed to replace, can simply resemble mean substitution but still better. With strongly correlated variables and low rates of missing data, an be a strong option for replacement.

#### Multiple Imputation
Fairly advanced, markov chains monte carlo simulations, which create permuted versions of the same data set. Models the missingness and gives researcher some different options of what missing data may look like. Appear to have delivered better results than a single, weak imputation.

#### Missingness as something of interest
A dummy variable can be used, representing a row with missing data, then you can do some analysis on the missing data to see if anything interesting arises. Might give insight into some phenomenon, or something to interpret results with.

Act of estimating values and retaining rows or data often leads to more replicable findings as they are sometimes more closer to the actual population than you would have had if you discarded the missing data.

### Chapter Seven - Extreme and Influential Data Points
Look for mention of influential data points in research and, allegedly, you will probably find none. Jumping from collection to analysis bad idea without looking at extreme scores or inappropriately influential scores, which may decrease results you are looking for. Extreme scores have outsized effect on analyses. Tests are assumed robust to these, but parametric tests rarely robust.

- Outliers - Things so far out of the rest of data, thought to be from another distribution
- Fringeliers - Things at the fringe of what could be reasonable from an examined normal distribution.

Remember 99.74% of population in a normal distribution fall within 3 SDs, therefore something outside of 3 SDs can be thought of as outliers.

Extreme values can increase error variance, and ruin statistical test by altering skew or kurtosis of a variable. They can also seriously bias or influence estimates that may be of interest like means or SDs. Extreme values can come from a few different causes
- Errors in data collection, recording or entry. This can be fixed by looking at original documents or contacting research participant to clarify
- Purposefully reporting incorrect data. Motivated misreporting due to negative influences or motivated misreporting due to socially desirable things.
- Sampling that creates biased that do not reflect actual nature of population. Sampling error where member of sample inadvertently drawn from different population than sample
- Extreme scores can be caused by research methods, especially if something weird happens during interview or experiment
- Incorrect assumptions about distribution of data can lead to data that allegedly looks like extreme scores
- Legit scores that look like extreme values or outliers can be legitimately sampled from the correct distribution. In a normal distribution it is more likely that the data will be drawn from the dense area of distribution as opposed to tails

Important to deal with extreme scores, either through transformation or a recoding/truncation strategy.

Extreme scores can be important insight and may have some interesting qualities or information in them.

Author makes point of doing an initial screening by looking at data points three or more standard deviations from the mean, in combination with eyeballing the data from visualization. Then the extreme scores can be examined itself, and which can give some insight.

In univariate extreme scores, a z transformation, or z score standardization, can convert all scores to z dist, then we can select cases with scores greater than -3.0 or less than 3.0 and keep going. Also good idea to check univariate distributions for extreme scores before correlation and regression.

In bivariate and multivariate extreme scores can exist in multiple directions, many reasons why extreme scores exist. 

Presence of extreme score appears to produce similar effects regardless if they are in a one cell or present in both for ANOVA.

Results are probably more generalizable and less likely to represent an error of inference if you do conscientious data cleaning dealing with extreme scores where warranted. Good policy to make sure data is as clean as possible when using more complex analyses. Even analyses designed to be robust to violations of distributional assumptions, such as nonparametric procedures, seem to benefit from solid, more normally distributed data.

###  Chapter Eight - Improving normality of variables through box-cox transformation

Data transformations commonly used tools that can serve many functions in quantitative analysis of data, including improving normality and equalizing variance. Useful to anchor minimum value in distribution at 1.0 to improve effectiveness of transformations, as some techniques not useful. A transformation like taking the square root of a negative number doesn't work, so this anchoring works to solve that, same as a logarithm of a number less or equal to 0 is undefined, and that taking a log of 0 to 1.0 produces negative values. Anchoring solves a variety of issues while not changing too many things.

Box-cox gives ability to fine-tune transformations, customizable to the particular dataset. 
While transformations are important tools, need to be thoughtful in their use as they might fundamentally alter nature of the variable, making interpretation of result hard.

Relevant statistical assumptions about data:
1. Assumption that variables are normally distributed
2. Assumption of equality of variance, or that variance remains constant over observed range of some other variable.
Significant violation of either increases chance of type I/II errors.

Box cox can optimizable $\alpha$ to get best effort normal distribution.

### Chapter Nine - Does reliability matter?
Unreliable measurement causes relationships to be underestimated, effect sizes of variables with poor reliability that can be underestimated while causing other variables in the analysis to be simultaneously overestimated.

Many researchers unconcerned with reliable measurement. Internal consistency most often assessed through cronbachs alpha. Alpha is a function of two aspects of a scale of set of indicators: number of items and the average correlation between the items. 

Unidimensionality:
- Refers to items(questions in a survey or test) measuring a single underlying trait (like happiness)
- Indicated by strong correlations among all items

The alpha is to provide an estimate of test/scale reliability, alpha is not a measure of unidimensionality, unidimensionality is an assumption of cronbachs alpha, if multidimensional then alpha underestimated, high values for alpha not necessarily indictors of unidimensionality. Alpha is a lower bound of reliability, real reliability may be higher than an alpha estimates.

In regression analyses:
- Variables with low reliability create error variance
- Subsequent variables may absorb this error variance
- Related variables may show inflated effects
- Social science studies often underestimate population effects by approximately one-third due to reliability issues

Low reliability in one, can lead to overestimation of effect of another related variable.

Many studies in social science underestimate the population effects by about one third due to low reliability.

