---
layout: post
title: "Determining the Value of FIFA 2022 Players: An Analytical Approach"
date: 2025-12-21
categories: jekyll update
---


This memo analyzes what determines the value of FIFA 2022 players, focusing on how player wage, age, strength and loan impact value. Using a multiple linear regression model, examine whether wage, age, strength, and whether a player has been loaned or not determine player value. The report explores how these factors influence players’ value in the market. "The analysis reveals about 65% of a players’ market value can be predicted by wage, age, strength and loan status, highlighting a strong relationship between value and these variables"

H~1~: Player wage will be positively correlated with player value.\
H~2~: Player strength will be positively correlated with player value.\
H~3~: Loaned players will have a lower value compared to non-loaned players.\
H~4~: There is a non-linear relationship between age and player value (e.g., value increases up to a certain age and then declines).

Variable analysis and Data Preparation The study focused on variables: wages (regular payments to players), Age, strength, and loaned status to estimate the value (estimated market worth) of a player. The variables value and wage were filtered to exclude zero entries, as they represent missing or unreliable data. The loan variable was recoded into two, when the variable was “NONE” coded as 0, it meant the player had not been loaned before but where there was a team name where a player was loaned to or loaned from, this was coded as 1 which meant the player had been loaned before. Outliers, representing wages and value variables were retained for their importance in understanding wage-value dynamics in soccer. \### Frequency Distribution of Categorical Variable Table 1: Categorical Summary

| Loan Status       | Frequency | Percentage |
|-------------------|-----------|------------|
| Not loaned before | 15234\.   | 93.09%     |
| Loaned before.    | 1131      | 6.91%      |
| Total.            | 16365\.   | 100%       |

The dataset consists of 16,365 players, with 93.09% not having been loaned before and 6.91% having been loaned. This indicates that the majority of players in the dataset have not experienced loan transfers, which may influence their market value differently compared to those who have been loaned.

### Summary Statistics

Table 2: Summary Statistics

| variable    | Frequency | Min  | Max    | Median | Mean  | SD    | Skewness |
|-------------|-----------|------|--------|--------|-------|-------|----------|
| Value (mil) | 16365     | 0.00 | 194.00 | 1.30   | 3.42  | 8.19  | 82.85    |
| Wage        | 16365     | 500  | 350000 | 4000   | 11552 | 21467 | 5.57     |
| Age         | 16365     | 16   | 45     | 25     | 25.63 | 4.99  | 0.35     |
| Strength    | 16365     | 19   | 97     | 68     | 66.22 | 12.62 | -0.49    |

The dataset includes 16,365 soccer players, with wages ranging from 500 to 350,000. The average wage was over 11,500, with a large standard deviation of 21,000, indicating significant wage differencs. Similarly, player values ranged from 1,000 to 194 million, with an average of over 3.4 million and a standard deviation of over 8 million, showing a wide variation in player valuations. The minimum age was 16 years, and the oldest player was 45 years with an average of 26 years and a standard deviation of 5 years showing a relatively normal distribution. The strength of a player ranged from 19 being the minimum to 97 being the maximum strength. The average strength was around 66 with a standard deviation of 12. Strength shows a slight negative skew, suggesting most players have moderate to high strength ratings.

### Regression Analysis

![alt text](assests/images/image.png)\
Dependent variable: **Value**

| Variable | Coefficient  | Std. Error |
|----------|--------------|------------|
| Wage     | 0.0003\*\*\* | (0.0000)   |
| Age      | -0.234\*\*\* | (0.008)    |
| Strength | 0.025\*\*\*  | (0.003)    |
| Loaned   | -1.467\*\*\* | (0.151)    |
| Constant | 4.227\*\*\*  | (0.246)    |

-   Observations: 16,365\
-   R²: 0.651\
-   Adjusted R²: 0.651\
-   Residual Std. Error: 4.843 (df = 16360)\
-   F Statistic: 7,618.487\*\*\* (df = 4; 16360)

Note: *p\<0.1; **p\<0.05;*** p\<0.01\*

A multiple regression was run to predict value of a player from wages, age, strength, and loan status which resulted in a significant model, F(4, 16360) = 7,618.49, p \< .05, R2 = .651. Examining the individual predictors further indicated that the intercept was significant with (t = 17.17, p \< .001), wage was significant with (t = 172.17, p \< .001), age was significant with (t = -28.32, p \< .001), strength significant with (t = 7.92, p \< .001) and loan was significant with (t= -9.73, p \< .001)

Alpha = 0.05

### Regression Equation

Value = 4.227 + 0.0003(Wage) -0.234(Age) + 0.025(strength) -1.467(Loaned) + error

Power: u=4, V=16360, f2=1.862, sig.level=0.05, power =1 Multiple regression power calculation

Scatter plot showing the relationship between Value and independents variables ![scattter plot](assests/images/scatter.png)

The plot shows that wages and value are positively correlated, as wages increase, value tends to increase. However, the relationship is not perfect (as seen by the scattered points around the regression line), implying that while wage is a strong predictor of value, it is not the only factor determining a player's market value.

Interpretation of variables Power (1): The model has a 100% probability of detecting a true effect between value and the independent variables due to the large sample size and strong effect size. Value Coefficient Wage (0.0003*): For each unit increase in Wage, the Value increases by 0.0003 million. This effect is statistically significant at the 1% level (p \< 0.01), as indicated by the triple asterisks (*).

Age (-0.234*): For each additional year of Age, the Value decreases by 0.234. This is a negative relationship, meaning that older individuals tend to have lower values, holding all other variables constant. This coefficient is also highly significant at the 1% level (p \< 0.01) Strength (0.025*): For each unit increase in Strength, the Value increases by 0.025. This positive effect is also significant at the 1% level (p \< 0.01). Loaned (-1.467*): If someone is Loaned, their Value decreases by 1.467. This suggests that being loaned significantly decreases value, and this effect is also highly significant at the 1% level (p \< 0.01). Constant (4.227*): The Constant represents the baseline Value when all the predictors (Wage, Age, Strength, Loaned) are 0. In this model, the baseline value is 4.227, and this is statistically significant at the 1% level (p \< 0.01).

R² (0.651): The model explains 65.1% of the variance in values, showing strong predictive power but leaving some wage determinants unexplained. p-value: Both the intercept and value show highly significant p-values, meaning the observed relationship between player value and wages is unlikely to have occurred by chance. Takeaways: Player value significantly influences wages; higher market value leads to higher wages. Weakness: The model predictive power was high on wage all other things added fewer increase in R2 value, excluding other factors like experience and performance, which may impact value. Lessons Learned: While player value is driven by a lot of variables a more comprehensive approach considering other factors would improve value. Normality in data seemed to be challenged by looking at the qq plot. Conclusion: Players’ values are largely determined by wage, strength, age and loan. Whiles wage and strength increased value in the positive direction age and loaned decrease the value of a player.

![residual plots](assests/images/residual%20plots.png)