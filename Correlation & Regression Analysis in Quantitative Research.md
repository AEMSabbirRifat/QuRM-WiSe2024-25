<!--
author:  Sabbir
email:   a.rifat@ovgu.de
version:  0.1.0
language: en
comment:  A presentation on Correlation & Regression Analysis in Quantitative Research Using R
license: CC-BY-4.0

link:     https://cdn.jsdelivr.net/chartist.js/latest/chartist.min.css
script:   https://cdn.jsdelivr.net/chartist.js/latest/chartist.min.js
-->

# Correlation & Regression Analysis in Quantitative Research

**Responsible Teacher:** M.A. Hannes Tegelbeckers  
**Tutors:** A E M Sabbir Rifat, Masub Makhdoom, Mahwish Kanwal

## Objectives of the Lecture

- Understand the concept of correlation and its applications.
- Learn how to compute and interpret correlation coefficients.
- Explore the basics of regression analysis and its assumptions.
- Understand how to build and interpret regression models.
- Discuss the limitations and practical considerations of these methods.

## Correlation

Correlation analysis is a statistical method used to assess the strength and direction of the relationship between two variables. It indicates how closely the variables with a linear relationship are associated.(RJ Janse,2021)

<div class="ct-chart ct-golden-section">
<!-- Add an r-plot here showing correlation examples -->
</div>

### Key Points:

- Ranges from -1 to +1
- Positive values indicate a positive relationship
- Negative values indicate a negative relationship
- Values closer to ±1 indicate stronger relationships
- Value of 0 indicates no linear relationship

## When to Use Correlation Statistical Analysis

Correlation analysis is appropriate in the following scenarios:

- To assess the strength and direction of a relationship between two quantitative variables.
- Before conducting regression analysis to identify potential predictors.
- In exploratory data analysis to uncover patterns.

## Conditions for Correlation Statistical Analysis

For valid correlation analysis, these conditions should be met:

1. **Quantitative Variables**: Both variables must be numeric.
2. **Linearity**: The relationship between variables should be approximately linear.
3. **Normality**: Data should follow a normal distribution (for Pearson correlation).
4. **No Outliers**: Outliers can distort the correlation coefficient.
5. **Independent Observations**: Data points should not be influenced by each other.

<div class="ct-chart ct-golden-section">
<!-- Add an r-plot here showing these conditions -->
</div>

## Types of Correlation

![Correlation and Regression Image](https://raw.githubusercontent.com/AEMSabbirRifat/QuRM-Sabbir-/5c0824f35eba6bafaacfcb7be99a2323fc2d4eb3/media/Correlation%20%26%20Regression/Picture1.jpg) 



## Correlation Coefficient

**A correlation coefficient (r)** is a statistical measure that quantifies the linear association between variables. It can indicate positive correlation, where both variables increase together or negative correlation, where one variable increases while the other decreases.

### Interpretation Guidelines:

- **r = +1**: Perfect positive correlation
- **r = 0**: No linear correlation
- **r = -1**: Perfect negative correlation
- **0 < |r| < 0.3**: Weak correlation
- **0.3 ≤ |r| < 0.7**: Moderate correlation
- **0.7 ≤ |r| < 1**: Strong correlation

## Types of Correlation Coefficient

![Regression Output Image](https://raw.githubusercontent.com/AEMSabbirRifat/QuRM-Sabbir-/5c0824f35eba6bafaacfcb7be99a2323fc2d4eb3/media/Correlation%20%26%20Regression/Picture3.jpg) 


## Correlation vs Correlation Coefficient

| **Aspect** | **Correlation** | **Correlation Coefficient** |
|:-----------|:----------------|:----------------------------|
| **Definition** | Describes the relationship between variables. | Quantifies the strength and direction of the relationship. |
| **Nature** | Conceptual and descriptive. | Numerical and measurable. |
| **Range** | Not applicable. | Always between −1 and +1. |
| **Types** | Positive, Negative, None. | Pearson's r, Spearman's ρ, Kendall's τ. |
| **Causality** | Explains association but doesn't measure it. | Measures linear or monotonic association. |
| **Examples** | "As X increases, Y increases." | "The correlation coefficient between X and Y is +0.85." |


## Correlation Analysis Through R

**Null Hypothesis (H₀)**:
- There is **no significant correlation** between the variables Ozone and Temp (significance level 5%).

**Hypothesis (H₁)**:
- There is a **significant correlation** between the variables Ozone and Temp.

**_For statistical analysis, please follow the instructions given through R_**


# Regression Analysis

- Regression analysis is a statistical method used to analyze experimental data, representing the nature of relationships between studied features. It provides a graphical description and helps identify significant correlations, while also addressing potential issues like false predictions.

<div class="ct-chart ct-golden-section">
<!-- Add an R regression plot here -->
</div>

## Correlation vs Regression

| **Feature** | **Correlation** | **Regression** |
|:------------|:----------------|:---------------|
| **Purpose** | Measures the strength and direction of a relationship | Predicts the value of one variable based on another |
| **Output** | A single correlation coefficient (r) | An equation/line to predict outcomes (Y = β₀ + β₁X) |
| **Causality** | No causality, just a relationship | Can imply causality, but only under certain conditions (e.g., experimental design) |
| **Type of Relationship** | Linear relationship between two variables | Can be linear or non-linear (e.g., polynomial regression) |
| **Number of Variables** | Typically between two variables | Can involve one or more independent variables (multiple regression) |

## When to Use Regression Analysis

- To predict outcomes based on known data.
- To evaluate the strength of relationships between variables.
- To identify which variables significantly influence an outcome.

## Conditions for Regression Analysis

- **Quantitative Variables**: Dependent variable must be numeric.
- **Linearity**: The relationship between variables should be linear (for linear regression).
- **Independence**: Observations should be independent.
- **Homoscedasticity**: Equal variance of residuals across all levels of the independent variable.
- **Normality**: Residuals should be normally distributed.
- **Goodness-of-Fit**: R².

## Types of Regression Analysis

![Correlation Matrix Visualization](https://raw.githubusercontent.com/AEMSabbirRifat/QuRM-Sabbir-/5c0824f35eba6bafaacfcb7be99a2323fc2d4eb3/media/Correlation%20%26%20Regression/Picture2.jpg) 




## Simple Linear Regression Analysis Through R

**Null Hypothesis (H₀)**:
- There is **no significant relationship** between **Wind** and **Ozone** (significance level 5%).

**Hypothesis (H₁)**:
- There is a **significant relationship** between **Wind** and **Ozone**.

**_For statistical analysis, please follow the instructions given through R_**

```r
# Example R code for simple linear regression
data(airquality)
model <- lm(Ozone ~ Wind, data = airquality)
summary(model)
plot(airquality$Wind, airquality$Ozone)
abline(model, col = "red")
```

## Multiple Linear Regression Analysis Through R

**Null Hypothesis (H₀)**:
- There is **no significant relationship** between Wind, Solar.R & Temp (Independent variables) and Ozone (dependent variable) (significance level 5%).

**Hypothesis (H₁)**:
- There is a **significant relationship** between at least one of the independent variables (Wind, Solar.R or Temp) and Ozone (Dependent variable).

**_For statistical analysis, please follow the instructions given through R_**

```r
# Example R code for multiple linear regression
data(airquality)
model <- lm(Ozone ~ Wind + Solar.R + Temp, data = airquality)
summary(model)

# Checking assumptions
par(mfrow = c(2, 2))
plot(model)
```

## Practical Exercise

**Formulate and test a hypothesis using either an Independent T-test or Dependent T-test**

- Based on your dataset, create 3 hypotheses suitable for correlation and regression analysis.
- If necessary, modify the dataset to ensure it fits the hypothesis. Justify these changes logically in your hand-in document.
- Perform the statistical analysis via R, following the procedure discussed in class.
- Input the visualizations
- Interpret the output and check the p-value.

  - If the result is significant, explain why.
  - If not significant, explain why.


**Use AI platforms for this step-by-step procedure, check feedback, rationalize and improve accordingly**
