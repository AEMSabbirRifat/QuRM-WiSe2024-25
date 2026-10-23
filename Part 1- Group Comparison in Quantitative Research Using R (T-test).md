# Part 1- Group Comparison in Quantitative Research Using R (T-test)

<span style="font-size: 22px;">__Teaching Team__</span>
 

> **Responsible Teacher:** M.A. Hannes Tegelbeckers  
> **Tutors:** A E M Sabbir Rifat, Masub Makhdoom, Mahwish Kanwal

# Objectives of the Lecture

- Understand different group comparison techniques  
- Learn when to apply each method  
- Apply methods using R  
- Interpret results meaningfully  

# Group Comparison

## Group Comparison Concept
Group comparison in quantitative research refers to the statistical methods used to compare differences between groups in terms of their central tendencies (e.g., means, medians), variability or other statistical properties. It helps researchers determine whether the observed differences between groups are statistically significant or likely due to random chance.

## Key Measures of Variability

- Range  
- Variance  
- Standard Deviation  
- Interquartile Range (IQR)  

## Assumptions in Group Comparisons

- **Normality**  
  - *Checking tools:* Histograms, Q-Q plots, Density plots, Shapiro-Wilk test, Kolmogorov-Smirnov test  

- **Homogeneity of Variance**  
  - *Checking tools:* Boxplots to compare variances, Levene's Test, Bartlett's Test  

- **Independence of Observations**  
  - *Checking tools:* Random sampling, No overlap between groups  

- **Sample Size Considerations**  
  - *Checking tools:* Power analysis, Sample size guidelines  

### 1. Normality test

### 2. Homogeneity of variance text


## Key Elements in Test Output (Interpreting Results)

- **Test Statistic**  
  - A numerical value that summarizes the difference between groups.  

- **Degrees of Freedom**  
  - The number of independent pieces of information in the data used for estimating parameters.  

- **p-value**  
  - The probability of obtaining test results at least as extreme as the observed results, assuming the null hypothesis is true.  

- **Significance Level (usually α = 0.05)**  
  - The threshold for determining statistical significance; if p-value < α, reject the null hypothesis.  

- **Rejecting or Failing to Reject the Null Hypothesis**  
  - If p-value < α, reject H₀ (null hypothesis); otherwise, fail to reject H₀.  

- **Effect Size**  
  - A measure of the magnitude of the difference between groups, independent of sample size.  


# Overview of Group Comparison Methods

## Types of Comparison Methods

<div style="text-align: center;">
  <img src="https://raw.githubusercontent.com/OVGU-VET-TechEd/Quantitative_Methods_with_R/e2f8eecfb1e53a5bb58868917964b972efde2001/Media_week7/Picture1.jpg" alt="Group Comparison Image" width="50%">
</div>


# Parametric Test

## Parametric Tests´ Data Set Criteria

- **Normal Distribution**  
  - Data should come from a normal distribution (bell-shaped curve).

- **Homogeneity of Variance**  
  - Groups should have similar variances (spread of data is similar).

- **Interval or Ratio Scale**  
  - Data should be measured on an interval or ratio scale (e.g., height, weight, income).


# T-tests

T-tests are used to **compare means between groups** to determine if differences are **statistically significant**.


 __When to Use:__

 - The **dependent variable** is **continuous**  
  - *(e.g., height, test scores)*  

- The **independent variable** is **categorical with up to two levels**  
  - *(Binary Grouping Variable, e.g., male vs. female)*


## Types of T-tests

<div style="text-align: center;">
  <img src="https://raw.githubusercontent.com/OVGU-VET-TechEd/Quantitative_Methods_with_R/e2f8eecfb1e53a5bb58868917964b972efde2001/Media_week7/Picture2.jpg" alt="Group Comparison Image" width="50%">
</div>




## Types of T-tests (contn.)

| Type                                  | Purpose                                              | Example |
|---------------------------------------|------------------------------------------------------|-----------------------------------------------------------|
| **One-Sample T-test**                 | Compare the mean of one group to a known value.      | Test if average working hours differ from 40 hours.       |
| **Independent T-test (Two-Sample T-test)** | Compare means of two independent groups.        | Test if male and female students have different math scores. |
| **Paired T-test**                      | Compare means of two related groups (same individuals). | Test if an exercise program improves weightlifting performance before and after participation. |


## One-Sample T-test in R

**Question:** Do cars in the built-in `mtcars` dataset average a fuel economy different from 20 miles per gallon?

- **H₀:** The mean `mpg` equals 20.
- **H₁:** The mean `mpg` differs from 20 (significance level 5%).

```r
data(mtcars)

# Assumption: the variable is roughly normally distributed
shapiro.test(mtcars$mpg)        # p > .05 -> no evidence against normality

# One-sample t-test against the known value 20
t.test(mtcars$mpg, mu = 20)
```

**Read the output:** look at `t`, `df`, the `p-value` and the 95% confidence interval. If the interval contains 20 and p > .05, we cannot reject H₀.

## Two-Sample T-test (Independent T-test) in R

**Question:** Do cars with manual transmission (`am = 1`) have a different mean `mpg` than automatic cars (`am = 0`)?

- **H₀:** Mean `mpg` is equal in both groups.
- **H₁:** Mean `mpg` differs between the groups (significance level 5%).

```r
data(mtcars)
mtcars$am <- factor(mtcars$am, labels = c("automatic", "manual"))

# Assumption 1: normality within each group
by(mtcars$mpg, mtcars$am, shapiro.test)

# Assumption 2: homogeneity of variance
var.test(mpg ~ am, data = mtcars)

# Welch t-test (R's default, robust when variances differ)
t.test(mpg ~ am, data = mtcars)

# Student t-test, only if variances are equal
t.test(mpg ~ am, data = mtcars, var.equal = TRUE)

boxplot(mpg ~ am, data = mtcars, ylab = "Miles per gallon")
```

## Paired T-test (Dependent T-test) in R

**Question:** The built-in `sleep` dataset measures extra hours of sleep for the **same 10 patients** under two drugs. Do the drugs differ in effect?

- **H₀:** The mean difference between drug 1 and drug 2 is 0.
- **H₁:** The mean difference is not 0 (significance level 5%).

```r
data(sleep)
drug1 <- sleep$extra[sleep$group == 1]
drug2 <- sleep$extra[sleep$group == 2]

# Assumption: the differences are roughly normally distributed
shapiro.test(drug1 - drug2)

# Paired t-test (each patient is compared with themselves)
t.test(drug1, drug2, paired = TRUE)
```

**Tip:** Use a paired test whenever the same people are measured twice (before/after, two conditions). Treating paired data as independent wastes statistical power.


# Practical Exercise

**Formulate and test a hypothesis using either an Independent T-test or Dependent T-test.**

- Based on your dataset, create a hypothesis suitable for either an **Independent or Dependent T-test**.  
- If necessary, modify the dataset to ensure it fits the hypothesis.  
  - Justify these changes logically in your hand-in document.  
- Perform the **T-test in R**, following the procedure discussed in class.  
- **Interpret the output and check the p-value.**  
- If the result is **significant**, explain why.  
- If **not significant**, explain why.  

<span style="background-color: yellow; font-weight: bold;">Use AI platforms for this step-by-step procedure, check feedback, rationalize and improve accordingly</span>

