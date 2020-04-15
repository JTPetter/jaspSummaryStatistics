Summary Statistics Bayesian One sample T-Test
==================

This function allows you to compute Bayes factor corresponding to a one sample t-test using the classical *t* statistic. The null hypothesis states that the population mean equals a specific constant, i.e., the test value. This Bayesian assessment can be executed in the absence of the raw data.

### Input
---

#### Assignment Box
- *t*: t-Statistic
- *Group size*

#### Alt. Hypothesis
- *&ne; Test value*: Two-sided alternative hypothesis that the population mean is not equal to the test value
- *&gt; Test value*: One-sided alternative hypothesis that the population mean is larger than the test value
- *&lt; Test value*: One sided alternative hypothesis that the population mean is smaller than the test value

#### Bayes Factor
- *BF10*: Bayes factor to quantify evidence for the alternative hypothesis relative to the null hypothesis
- *BF01*: Bayes factor to quantify evidence for the null hypothesis relative to the alternative hypothesis
- *Log(BF10)*: Natural logarithm of BF10

#### Plots
- *Prior and posterior*: Displays the prior (dashed line) and posterior (solid line) density of the effect size under the alternative hypothesis; the gray circles represent the height of the prior and the posterior density at effect size delta = 0. The horizontal solid line represents the width of the 95% credible interval of the posterior.
  - Additional info: Adds the Bayes factor computed with the user-defined prior; adds a probability wheel depicting the odds of the data under the null vs. alternative hypothesis; adds the median and the 95% credible interval of the posterior density of the effect size
- *Bayes factor robustness check*: Displays the Bayes factor as a function of the width of the Cauchy prior on effect size. The scale of the Cauchy prior is varied between 0 and 1.5 (between 0 and 2 if user prior width is greater than 1.5), creating progressively more uninformative priors.

### Prior
- **Standardized effect size**
  - Default
    - *Cauchy*: Scale of the Cauchy prior density on effect size under the alternative hypothesis; the default is 0.707
  - Informed
    - *Cauchy*: Scale and location
    - *Normal*: Mean and Standard deviation
    - *Student's t*: Scale, Location and Degrees of freedom (df)

[comment]: # (- **Raw effect size (Dienes)**)
[comment]: # ( - *Half-Normal*: Standard deviation)
[comment]: # (  - *Normal*: Mean and Standard deviation)
[comment]: # (  - *Uniform*: Lower and Upper bounds)


### Output
---
- **Bayes factor**
  - BF+0: Bayes factor that quantifies evidence for the one-sided alternative hypothesis that the population mean is larger than the test value.
  - BF-0: Bayes factor that quantifies evidence for the one-sided alternative hypothesis that the population mean is smaller than the test value.
  - BF0+: Bayes factor that quantifies evidence for the null hypothesis relative to the one-sided alternative hypothesis that the population mean is larger than the test value.
  - BF0-: Bayes factor that quantifies evidence for the null hypothesis relative to the one-sided alternative hypothesis that that the population mean is smaller than the test value.
- **error %**: The error of the Gaussian quadrature integration routine used for the computation of the Bayes factor.
- **p**: p-value corresponding to t-statistic.

### References
---
- Gronau, Q. F., Ly, A., & Wagenmakers, E.-J. (in press). Informed Bayesian t-tests. *The American Statistician*. <a href="https://arxiv.org/abs/1704.02479">https://arxiv.org/abs/1704.02479</a>
- Jeffreys, H. (1961). *Theory of probability (3rd ed.)*. Oxford, UK: Oxford University Press.
- Rouder, J. N., Speckman, P. L., Sun, D., Morey, R. D., & Iverson, G. (2009). Bayesian t-tests for accepting and rejecting the null hypothesis. *Psychonomic Bulletin & Review, 16*, 225-237.
- Morey, R. D. & Rouder, J. N. (2011). Bayes Factor Approaches for Testing Interval Null Hypotheses. *Psychological Methods, 16*, 406-419

### R Packages
---
- BayesFactor
- ggplot2
- logspline
- stats