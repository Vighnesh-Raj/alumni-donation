# Alumni Donation Case Study

## Introduction
The Alumni Donation Case Study explores factors influencing alumni donation rates at universities and develops a predictive linear regression model to understand these factors. The primary objective is to identify the most significant predictors of alumni giving rates, ensuring that the model adheres to statistical assumptions and delivers actionable insights for improving alumni engagement strategies.

## Dataset Description
The dataset consists of 49 universities and includes the following features:

- **School**: Name of the university.
- **Percent of Classes Under 20**: Percentage of classes with fewer than 20 students.
- **Student-Faculty Ratio**: The ratio of students to faculty members.
- **Alumni Giving Rate**: Percentage of alumni who donate to the university (response variable).
- **Private**: A binary indicator (1 for private institutions, 0 for public institutions).

### Key Observations:
- **Alumni Giving Rate**: Ranges from 7% to 67% with a mean of 29.27%.
- **Student-Faculty Ratio**: Ranges from 3 to 23, indicating varying class size experiences.
- **Percent of Classes Under 20**: Ranges from 29% to 77%.
- **Private Institutions**: Approximately 69% of universities are private.

## Methods
### 1. Exploratory Data Analysis (EDA):
- **Distribution Analysis**: Histograms revealed that the alumni giving rate is right-skewed, suggesting the need for transformation.
- **Correlation Analysis**: Scatter plots identified a strong negative correlation between the student-faculty ratio and alumni giving rate. Other predictors showed weaker associations.
- **Box Plots**: Highlighted higher donation rates among private institutions.

### 2. Data Transformation:
To address skewness and heteroscedasticity, the alumni giving rate was log-transformed:
- Transformed response variable: `log(alumni giving rate)`.

### 3. Model Selection:
- **Stepwise Selection with BIC**: A forward stepwise approach was employed to identify the best model. This method minimizes the Bayesian Information Criterion (BIC) by iteratively adding or removing predictors and interaction terms.

### 4. Diagnostic Checks:
- **Linearity**: Verified using scatterplots of residuals against fitted values.
- **Homoscedasticity**: Checked to ensure consistent variance of residuals.
- **Normality**: Residuals were normally distributed.

## Results
### Final Model:
The best-fit linear regression model is:
`log(alumni giving rate) = 3.533 + 0.41(private) - 0.052(student-faculty ratio)`


### Coefficients:
- **Private (0.41)**: Private institutions have, on average, 1.50 times higher alumni giving rates than public institutions (e^0.41).
- **Student-Faculty Ratio (-0.052)**: A one-unit increase in the student-faculty ratio reduces the alumni giving rate by approximately 5.2%.

### Model Performance:
- **R-squared**: 0.6383 (63.8% of the variance in the log-transformed alumni giving rate is explained).
- **Adjusted R-squared**: 0.6222.
- **Residual Standard Error**: 0.328.
- **Mean Squared Error (Test Set)**: 0.13, indicating good predictive accuracy.

### Diagnostic Results:
- Residuals showed no significant patterns or correlations.
- Adding other predictors (e.g., percent of classes under 20) or interaction terms did not significantly improve the model.

## Conclusions
- **Key Findings**:
  - Private institutions generally have stronger alumni donation rates.
  - Lower student-faculty ratios positively impact alumni giving rates, likely due to stronger student-teacher connections.
- **Non-significant Variables**:
  - The percentage of classes under 20 showed no significant impact on alumni giving rates.

## Applications
This study offers a framework that can be applied to:
1. **Educational Institutions**: Optimizing alumni engagement strategies by focusing on student-faculty interactions.
2. **Non-Profit Organizations**: Understanding donation behaviors based on organizational characteristics.
3. **Corporate Retention Models**: Analyzing employee retention rates using analogous predictors (e.g., manager-employee ratios).

