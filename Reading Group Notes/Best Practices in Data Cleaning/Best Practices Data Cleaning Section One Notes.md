Video: [PadComp Reading Group Session Two - Best Practices in Data Cleaning Section One](https://www.youtube.com/watch?v=vySoxSswk8s)
## Good things to know

### ANOVA - Analysis of Variance
Is there meaningful differences between the averages of three or more groups. If there are three groups and there is some benefit from a higher or lower average, then we can say the groups differ. We look at 
- a) variance in a group, or how spread out values are inside a group, and 
- b) the variance between groups, or how different groups are from each other.

#### Anova Table

| Source             | Sum of Squares (SS) | Degrees of Freedom (df) | Mean Square (MS)         | F-Ratio               |
| ------------------ | ------------------- | ----------------------- | ------------------------ | --------------------- |
| Between (B) Groups | $SSB$               | $df_B = k - 1$          | $MSB = \frac{SSB}{df_B}$ | $F = \frac{MSB}{MSW}$ |
| Within (W) Groups  | $SSW$               | $df_W = N - k$          | $MSW = \frac{SSW}{df_W}$ |                       |
| Total (T)          | $SST$               | $df_T = N - 1$          |                          |                       |

### Null Hypothesis Testing
$H_0$ is the null hypothesis, which simply means  'no effect' or 'no difference'. Refer above to ANOVA. if the variance between groups is no different, then that is the null hypothesis being true. We then collect some data and test it, decide on how strict you will be about deciding is if something is unusual, which is the chance you are okay with if you reject the null hypothesis and are incorrect in rejecting it, this is $\alpha$ . Finally we do some test, and if the probability of getting the result if the null hypothesis was true. 

If it is smaller than chance we decided above we are okay with $\alpha$, then we reject the null hypothesis, $H_0$. 

If the probability of getting a result if the null hypothesis is greater than $\alpha$, or our comfort level, then we can say there's not enough evidence to say the effect is real. Maybe the null hypothesis is true, maybe we can't tell from what we have either way.

### Surveys
Method of collecting data by asking questions to a group of people (a sample) to gather information about a larger population. We hope that what we get from a smaller group is representative of a larger group.

## Section One Notes
### Chapter Two
Statistical power is how we can correctly reject a null hypothesis. Based on a few things:
- Effect size, like my drug reduces some symptom by 60% (big) or 5% (small), big is easier to spot.
- Alpha size, described above in good to know before, but threshold for deciding if result is significant
- Sample size relative to a strategy

A two types
- A prior, or before/pre sampling think about forward looking, power. How many samples we should get before we start
- A posteriori, or looking backwards or after sampling, power. Power after data collected and analyzed, might seem pointless, but tells us probability of correctly rejecting a false null hypothesis. Low power much less informative.

Seems like few researchers to a prior sample size estimation! Might get too small a sample size to tell anything or might waste resources ($) getting many many which might be overkill to detect something.

We can make type I and type II errors
- Type I is when we say there is an effect when there isn't
- Type II is when there is an effect but we conclude there isn't

Power gives us insight into probability of replication, significance tests do not.

High power means we correctly reject null hypothesis on average 80% of the time but 20% we fail, type II error, so failure to reject a null hypothesis when there is a real effect. So we fail to see an effect when it is present 1 out of 5 times. 

Low power in a field can lead to conflicting results in a field due to methods as opposed to substantive reasons.

#### As an engineer in start-up
When iterating on feedback from users, you want to include as much feedback as you can within a cost effective manner, not having a large enough sample means you might not have a significant effect if you develop a feature, or ask for user feedback.

#### As a VC analyst/associate 
Imagine you are trying to understand what founders characteristics or qualities are similar amongst those that succeed or have some returns to your fund. 

### Chapter Three
Representativeness, does what I'm sampling make sense, relative to what I want to generalize up to?

Basic processes are similar, maybe sometimes generalizability does not suffer a long as we do not range from sample demographics.

Sampling plan is important, its your due diligence, the basics that may have downstream effects in your research. When we sample, we want to gather a small amount of data on some quality or effect, such that we can infer something about a larger population. So we take a small amount information from 'something', find out something from it, and try to extrapolate that to a larger amount of that same 'something'. So we want to match a sample to a population, but it'll never be perfect but with some work (mechanisms, theories and understanding of the problem domain) it can be good/better.

In a sample, there can be subsamples, or sub groups that get aggregated together, may want to disaggregate the subgroups. Omission is where you fail to examine/isolate a particular subgroup  which may have a different pattern than other groups, which may have real meaning.

Identifying who might be your target population is tough, but very important, want to be highly specific, and may lead to sloppy samples which includes many irrelevant subgroups that have different patterns which may effect what you are trying to measure.

'No real incentive for some students to spend a good deal of their time taking a test that has little bearing on their grade or life' - that's me. Misalignment of incentives between people in the sample and the researcher.
#### Norms and Externalities
Societal norms or externalities can effect the results of surveys, kinda obvious but I think this gets lost by a lot of people. How you phrase a question can effect the response, or how someone thinks in their head about what the answer may look like. 

'Informed consent has led to low levels of recruitment through increasing the anxiety of patients who are already in a very anxious state', might make things worse by asking for informed consent and freak out people! 
#### Ranges
Restrict the range of a variable in some way, that resembles what would be in the population. 

- **Ceiling Effect**: Mismatch of an instrument too sensitive with a sample relatively extreme on the trait being assessed, we get very high values. Our sensor is not tuned or and may be reading values incorrectly, or its pointed in the wrong direction to pick up some extreme value. Think about how sometimes when you are talking on a phone you hear a lot of ambient noise that is distracting but some systems are able to use some band pass filters to remove the noise.
- **Floor Effect**: Caused by instrument that cannot pick up samples that are low level. Think about a microphone that someone is talking into that doesn't pick up their voice if they are talking, I think this is noise gating.


#### EGA
Extreme group analysis is where researchers choose individuals that represent extremes of a distribution. Without good reasons, looks like researcher is cherry picking data to create a fake effect size. 

Imagine getting some feedback where you can sort by rating, with 10 being a good rating and 0 being a bad, and you choose only to look at the ratings with 10, you are doing extreme group analysis. You should have a good reasons to do so, and doing EGA 


### Chapter Four

Publicly available datasets have had work done on them! And have complex sampling methods you might have to apply. Expectations that best practices are done in using the samples.

With some complex sampling methodologies, oversampling may occur in certain groups. Many good reasons to use variety of methods which may result in oversampling, but unfortunately small groups may be completely missed. Researchers then will weight to get representativeness up. 

In complex sampling, sample in its original form can be way different than the population, and a sample that is not independent of other samples can lead to misestimation of significance levels in inferential statistical tests.

There's some other code in this chapter that I don't care about.

