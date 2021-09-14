# Lead-Scoring-Case-Study

![image](https://user-images.githubusercontent.com/76435558/133173160-1ccdd7a6-539e-499a-ba3f-ed9b7c3c1879.png)

# Problem Statement
X Education sells online courses to industry professionals and markets its courses on several websites and search engines like Google. Although sales team of X Education gets a lot of leads through search engines and also from past refrerals, however its lead conversion rate is very poor which is around 30%.

### The company wants to Know.
- Company wishes to identify the most potential leads, also known as ‘Hot Leads’.

- Higher score would mean that the lead is hot and is most likely to convert whereas a lower score would mean that the lead is cold and will mostly not get converted.

- Conversion Rate = (probability of a person becoming a customer of X Education *100)%

- Lead Score = probability of a person becoming a customer of X Education *100

### Approach in nutshell
1. Importing Data
2. Inspecting the Dataframe
3. Data Preparation (Encoding Categorical Variables, Handling Null Values)
4. EDA (univariate analysis, outlier detection, checking data imbalance)
5. Dummy Variable Creation
6. Test-Train Split
7. Feature Scaling
8. Checking Correlations
9. Model Building (Feature Selection Using RFE, Improvising the model further inspecting adjusted R-squared, VIF and p-vales)
10. Build final model
11. Model evaluation with different metrics Sensitivity, Specificity
12. Finding optimal cut off value
13. Final Model

# Conclusion:
- The logistic regression model predicts the probability of the target variable having a certain value, rather than predicting the value of the target variable directly. Then a cutoff of the probability is used to obtain the predicted value of the target variable.
- Here, the logistic regression model is used to predict the probabilty of conversion of a customer.
- Optimum cut off is chosen to be 0.27 i.e. any lead with greater than 0.27 probability of converting is predicted as Hot Lead (customer will convert) and any lead with 0.27 or less probability of converting is predicted as Cold Lead (customer will not convert).
- Our final Logistic Regression Model is built with 13 features.

- Features used in final model are ['Lead Origin_Lead Add Form', 'Lead Source_Welingak Website',
  'Last Activity_SMS Sent', 'Tags_Busy', 'Tags_Closed by Horizzon',
  'Tags_Lost to EINS', 'Tags_Ringing',
  'Tags_Will revert after reading the email', 'Tags_switched off',
  'Lead Quality_Not Sure', 'Lead Quality_Worst',
  'Last Notable Activity_Modified',
  'Last Notable Activity_Olark Chat Conversation']
 
- The top three categorical/dummy variables in the final model are ‘Tags_Lost to EINS’, ‘Tags_Closed by Horizzon’, ‘Lead Quality_Worst’ with respect to the absolute value of their coefficient factors.

‘Tags_Lost to EINS’, ‘Tags_Closed by Horizzon’ are obtained by encoding original categorical variable ‘Tags’. ‘Lead Quality_Worst’ is obtained by encoding the categorical variable ‘Lead Quality’.

- Tags_Lost to EINS (Coefficient factor = 9.645545)
- Tags_Closed by Horizzon (Coefficient factor = 8.710178)
- Lead Quality_Worst (Coefficient factor =--3.964046)
- The final model has Sensitivity of 0.935, this means the model is able to predict 93% customers out of all the converted customers, (Positive conversion) correctly.
- The final model has Precision of 0.67, this means 67% of predicted hot leads are True Hot Leads.
- We have also built an reusable code block which will predict Convert value and Lead Score given training, test data and a cut-off. Different cutoffs can be used depending on the use-cases (for eg. when high sensitivity is required, when model have optimum precision score etc.)
