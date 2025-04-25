# Task_2-EDA
The Exploratory Data Analysis was carried out to better understand the distribution, relationships, and potential issues within the dataset. This step included summary statistics, univariate and bivariate visualizations using tools such as Pandas, Matplotlib, and Seaborn.
1. Summary Statistics
We began by generating summary statistics for both numerical and categorical variables to get a high-level overview of the dataset.

Numerical Summary:

ApplicantIncome and LoanAmount have high standard deviations, indicating a wide income and loan range among applicants.
Median values are significantly lower than the means, especially for ApplicantIncome and LoanAmount, confirming right-skewed distributions.
Credit_History mostly consists of 1s, suggesting that most applicants have a good credit background.

Categorical Summary:

Most applicants are male, married, and graduates.
The most common property area is Semiurban, and around 68% of loans were approved.
Loan_ID is unique for each record and serves only as an identifier.

2. Histograms and Boxplots for Numeric Features
To understand the distribution and presence of outliers:

Histograms:

ApplicantIncome, CoapplicantIncome, and LoanAmount histograms show positive skewness with long right tails, indicating that while most applicants have moderate values, a few high-income or high-loan cases stretch the distribution.
Loan_Amount_Term shows a strong peak at 360 months, confirming a standard 30-year term.

Boxplots:

Outliers are present in ApplicantIncome and LoanAmount, seen clearly in the boxplot whiskers.
When grouped by categories like Education or Self_Employed, boxplots revealed some differences in average values but also overlapping ranges, suggesting potential but not strong predictive separation.

3.  Correlation Matrix and Pairplot
To explore interrelationships between variables:

A correlation matrix heatmap was created using Seaborn. Key findings:
ApplicantIncome and LoanAmount showed a moderate positive correlation.
CoapplicantIncome had a weaker correlation with LoanAmount, indicating it may play a secondary role in determining loan size.
A pairplot highlighted spread and density relationships. Since the data is skewed, correlations appeared non-linear in some cases, and the distributions revealed heteroscedasticity in a few variable pairs.

4. Patterns, Trends, and Anomalies Identified
Distribution Patterns
ApplicantIncome and CoapplicantIncome exhibit a right-skewed distribution. A majority of applicants have moderate incomes, but there are a few with exceptionally high income values, stretching the tail to the right.
LoanAmount also shows right skewness, with most loans clustered between ₹100K–₹200K and a few large loans (up to ₹650K) acting as outliers.
The Loan_Amount_Term has a sharp peak at 360 months, indicating that the 30-year loan term is the standard choice among applicants.

Feature Relationships & Trends
Graduates tend to request slightly higher loan amounts than non-graduates.
Self-employed individuals show a higher average applicant income, but this doesn’t necessarily translate to higher loan approval.
Loan approval rates are highest in Semiurban areas, while Rural areas have relatively lower approval percentages.
The average loan amount increases with the number of dependents, suggesting that applicants with more dependents might seek higher financial support.

Anomalies & Outliers
A few extremely high incomes (e.g., ₹81,000) and large loan amounts (₹600K+) can potentially influence model performance and may be considered for log transformation or capping during preprocessing.
Some entries have zero coapplicant income, which, although valid, may represent individual applicants and should be interpreted accordingly.
There are missing values in columns like LoanAmount, Loan_Amount_Term, and Credit_History, which need to be handled before modeling.

5. Basic Feature-Level Inferences
Education, Employment Type, and Property Area show visible differences in terms of income, loan amount, and approval rate, indicating they may have predictive value in determining loan approval.
Credit History (not visualized here but observed in summary stats) has a strong influence on approval status, as expected.
Applicant and Coapplicant Income, though skewed, are crucial variables and should be carefully transformed or scaled for downstream modeling.
Income-related features are important, but due to skewness and outliers, may need transformation (e.g., log scaling).
Education, Self-Employment, and Property Area show promising patterns that can help predict Loan_Status.
Credit History is likely a strong predictive feature, with the majority of approved applicants having a credit history value of 1.
Features such as Dependents may show subtle patterns but could gain value when combined with other features.
