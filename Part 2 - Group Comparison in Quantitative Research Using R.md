# Part 2 - Group Comparison in Quantitative Research Using R

**Responsible Teacher**
- **M.A. Hannes Tegelbeckers**

**Tutors**
- A E M Sabbir Rifat
- Masub Makhdoom
- Mahwish Kanwal

---

# Objectives of the Lecture

- Explore and analyze the following techniques:

  - **ANOVA (Analysis of Variance)**
  - **Non-Parametric Tests**:
    - Chi-Squared Test
    - Mann-Whitney U
    - Kruskal-Wallis
    - Fisher’s Exact Test
- Criteria for selecting the appropriate method
- Understand and evaluate assumptions for each statistical method.
- Gain practical skills in performing these analyses using **R programming**.

---
# Group Comparison

Group comparison in quantitative research refers to the statistical methods used to compare differences between groups in terms of their central tendencies (e.g., means, medians), variability or other statistical properties. It helps researchers determine whether the observed differences between groups are statistically significant or likely due to random chance.



# Overview of Group Comparison Methods

<div style="text-align: center;">
  <img src="https://github.com/AEMSabbirRifat/QuRM-Sabbir-/raw/e90eec1f9b8a39b135be76f5e965a4de4f2ab9e2/media/Group%20Comparison%20in%20Quantitative%20Research%20Using%20R%20(Part%202)/Picture1.jpg" alt="Group Comparison Image" width="50%">
</div>

# Parametric Tests

 __Data Set Criteria__

- Data should come from a **normal distribution** (bell-shaped curve).
- Groups should have **similar variances** (spread of data is similar).
- The data should be measured on an **interval or ratio scale** (e.g., height, weight, income).


# Analysis of Variance (ANOVA)

__ANOVA__ (Analysis of Variance) is a statistical method used to compare the means of three or more groups to determine if there are significant differences among them. Instead of performing multiple T-tests (which increases the risk of errors), ANOVA provides a single statistical test to assess whether at least one group mean is different from the others.


# When to Use ANOVA

- **Continuous dependent variable**
- **Categorical grouping variable**
- **Multiple groups (3 or more)**

# Types of Analysis of Variance (ANOVA)

<div style="text-align: center;">
  <img src="https://github.com/AEMSabbirRifat/QuRM-Sabbir-/raw/a97504babab47c887b4cb66c8c6cb36a06620703/media/Group%20Comparison%20in%20Quantitative%20Research%20Using%20R%20(Part%202)/Picture2.jpg" alt="Group Comparison Image" width="40%">
</div>



# Types of Analysis of Variance (ANOVA) (contn.)

__One-way ANOVA__

- **Hypothesis (Ha):** At least one month's mean ozone level is different from the others.  
- **Null Hypothesis (H0):** The mean ozone levels are the same across all months.  

<span style="color:black; font-weight:bold;">For statistical analysis, please follow the instructions given through R.</span>


# Types of Analysis of Variance (ANOVA) (contn.)

__Two-way ANOVA__

- **Hypothesis (Ha):** There is an interaction effect between the factors (dose and supp) on tooth length.
- **Null Hypothesis (H0):** There is no interaction effect between the factors (dose and supp) on tooth length.

<span style="color:black; font-weight:bold;">For statistical analysis, please follow the instructions given through R.</span>


# Types of Analysis of Variance (ANOVA) (contn.)

__Repeated Measures ANOVA__

- **Alternative Hypothesis (Ha):** There is a significant difference in the mean extra hours of sleep between the drug and placebo groups (i.e., the drug has an effect).
- **Null Hypothesis (H0):** There is no difference in the mean extra hours of sleep between the drug and placebo groups (i.e., the drug does not have an effect).

<span style="color:black; font-weight:bold;">For statistical analysis, please follow the instructions given through R.</span>

# Post-Hoc Tests for ANOVA

A post-hoc test is used after ANOVA to perform pairwise comparisons between the group means and determine where the differences lie. 
One commonly used post-hoc test is **Tukey’s Honest Significant Difference (HSD) test**.

__When to Use Tukey’s HSD__

- There are three or more groups.
- You need to compare every pair of groups to determine which specific groups differ from each other.


# Introduction to MANOVA

- **Extension of ANOVA** for multiple dependent variables.
- Compares means across groups on a combination of dependent variables.

__When to Use MANOVA__

- a. Multiple related dependent variables.
- b. One or more independent variables (factors).

# Non-Parametric Tests

__Non-parametric tests__ are statistical methods that do not assume a specific distribution for the data. They are particularly useful for analyzing ordinal data or when sample sizes are small, as they rely on ranks rather than raw data values.


# **Non-Parametric Tests (Data set criteria)**

- Data can be **ordinal** (ranked) or **nominal** (categorical).  
- Some tests can be applied to **interval** or **ratio** data that do not meet parametric assumptions.  
- **Small sample sizes** where parametric tests might lack power or reliability.  
- **No assumption** of normality in the data distribution.  
- Non-parametric tests are **robust to outliers** and skewed distributions.  
- **Independence of observations** is still a key requirement for most tests.  
- **Does not rely** on equal variances between groups assumption.  
- Use when **assumptions of parametric tests are violated**.  


# **Chi-Squared Test**

- Used for **categorical variables**  
- Compares **observed frequencies** with **expected frequencies**  
- It does not require assumptions of **normality** or **homogeneity of variance**  
- Data is arranged in a **table (2x2 or larger)**  
- Shows the **frequency counts** for combinations of categories.  


# **Chi-Squared Test (contn.)**

- **Null Hypothesis (H₀):** There is no association between car efficiency (efficiency) and the number of cylinders (cyl_cat).  
- **Alternative Hypothesis (H₁):** There is an association between car efficiency (efficiency) and the number of cylinders (cyl_cat).  

<span style="color:Black; font-weight:bold;">For statistical analysis, please follow the instructions given through R.</span>

# **Types of Chi-Squared Tests**  

- **Goodness of Fit Test**  
- **Test of Independence**  


# **Mann-Whitney U Test / Wilcoxon Rank-Sum Test**  

- An **alternative** to the Independent Samples t-test  
- It **compares differences** between two independent groups on a **continuous or ordinal** dependent variable.  
- It tests whether the **distribution** of the two groups is the same or if one group tends to have **higher values** than the other.  


# **Kruskal-Wallis Test**  

- **Compare 3+ independent groups**  
- It is an **extension** of the Mann-Whitney U Test to more than two groups  
- The test evaluates whether the **distributions** of the groups are the same  
- Checks if one or more groups have **systematically higher or lower values** than the others.  


# **Fisher’s Exact Test**  

- **Alternative** to Chi-squared for **small sample sizes**  
- Determines if there is a **significant association** between two categorical variables in a **contingency table**  
- Calculates the **exact probability** of observing the data under the **null hypothesis**  
- **Ideal** for small datasets  


# Practical Exercise  

🟡__ **Use AI platforms** for this step-by-step procedure, check feedback, rationalize and improve accordingly.__ 🟡
