# Logistic Regression and Tree-Based Modelling for Employee Retention

# Overview
The goal of this project was to analyze the data collected by the HR department and to build a model that predicts whether or not an employee will leave the company based on their department, number of projects, average monthly hours, and any other data points deemed helpful. The logistic regression model achieved a precision of 80%, recall of 83%, f1-score of 80% (all weighted averages), and accuracy of 83%, on the test set. After conducting feature engineering, the decision tree model achieved an AUC of 93.8%, precision of 87.0%, recall of 90.4%, f1-score of 88.7%, and accuracy of 96.2%, on the test set. The random forest modestly outperformed the decision tree model.

# Business Understanding
The HR department at Salifort Motors wants to take some initiatives to improve employee satisfaction levels at the company. They collected data from employees, but now they don’t know what to do with it. They refer to you as a data analytics professional and ask you to provide data-driven suggestions based on your understanding of the data. They have the following question: what’s likely to make the employee leave the company? Your goals in this project are to analyze the data collected by the HR department and to build a model that predicts whether or not an employee will leave the company. If you can predict employees' likely to quit, it might be possible to identify factors that contribute to their leaving. Because it is time consuming and expensive to find, interview, and hire new employees, increasing employee retention will be beneficial to the company.

# Data Understanding
The dataset provided is found on Kaggle and can be accessed here [here](https://www.kaggle.com/datasets/mfaisalqureshi/hr-analytics-and-job-prediction?select=HR_comma_sep.csv). The dataset has 14,999 rows, 10 columns, and these variables: Satisfaction level, last evaluation, number projects, average monthly hours, tenure, work accident, promotion last 5 years, department, left and salary.

# Modelling and Evaluation
Logistic regression and Tree-based modellings like the decision tree and random forest were built. The main reason was to compare the model performance between these approaches where the logistic regression model achieved a precision of 80%, recall of 83%, f1-score of 80% (all weighted averages), and accuracy of 83%, on the test set. After conducting feature engineering, the decision tree model achieved an AUC of 93.8%, precision of 87.0%, recall of 90.4%, f1-score of 88.7%, and accuracy of 96.2%, on the test set. The random forest modestly outperformed the decision tree model.

## Confusion matrix of the logistic regression
![image](https://github.com/oscarkalinga/Logistic-Regression-and-Tree-Based-Modelling-for-Employee-Retention/assets/73540285/359e1369-2c71-494c-8768-9b55047eb9b1)

The upper-left quadrant displays the number of true negatives. The upper-right quadrant displays the number of false positives. The bottom-left quadrant displays the number of false negatives. The bottom-right quadrant displays the number of true positives.
- True negatives: The number of people who did not leave that the model accurately predicted did not leave.
- False positives: The number of people who did not leave the model inaccurately predicted as leaving.
- False negatives: The number of people who left that the model inaccurately predicted did not leave
- True positives: The number of people who left the model accurately predicted as leaving
A perfect model would yield all true negatives and true positives, and no false negatives or false positives.

## Confusion matrix of the random forest
![image](https://github.com/oscarkalinga/Logistic-Regression-and-Tree-Based-Modelling-for-Employee-Retention/assets/73540285/9b45ac64-673b-414f-af1d-12c722035102)

The model predicted more false positives than false negatives, which means that some employees may be identified as at risk of quitting or getting fired when that's actually not the case. But this is still a strong model.
# Feature Importance
![image](https://github.com/oscarkalinga/Logistic-Regression-and-Tree-Based-Modelling-for-Employee-Retention/assets/73540285/8554bf65-2297-41ec-86d4-9b244bc41235)

The barplot above shows that in this decision tree model, last_evaluation, number_project, tenure, and overworked have the highest importance, in that order. These variables are most helpful in predicting the outcome variable, left.
![image](https://github.com/oscarkalinga/Logistic-Regression-and-Tree-Based-Modelling-for-Employee-Retention/assets/73540285/eb71b6e3-d437-4cc2-9c2a-2d712d214ead)

The plot above shows that in this random forest model, last_evaluation, number_project, tenure, and overworked have the highest importance, in that order. These variables are most helpful in predicting the outcome variable, left, and they are the same as the ones used by the decision tree model.

# Conclusion
The models and the feature importances extracted from the models confirm that employees at the company are overworked. `last_evaluation`, `tenure`, `number_project`, `overworked`, `salary_low`, and `work_accident` have the highest importance. These variables are most helpful in predicting the outcome variable, `left`.


# Recommendations
- To retain employees, the following are the recommendations to the stakeholders:
- Cap the number of projects that employees can work on.
- Consider promoting employees who have been with the company for at least four years, or conduct a further investigation about why four-year tenured employees are so dissatisfied.
- Either reward employees for working longer hours, or don't require them to do so.
- If employees aren't familiar with the company's overtime pay policies, inform them about this. If the expectations around workload and time off aren't explicit, make them clear.
- Hold company-wide and within-team discussions to understand and address the company work culture, across the board and in specific contexts.
- High evaluation scores should not be reserved for employees who work 200+ hours per month. Consider a proportionate scale for rewarding employees who contribute more/put in more effort.

# Next Steps
It may be justified to still have some concerns about data leakage. It could be prudent to consider how predictions change when last_evaluation is removed from the data. It's possible that evaluations aren't performed very frequently, in which case it would be useful to be able to predict employee retention without this feature. It's also possible that the evaluation score determines whether an employee leaves or stays, in which case it could be useful to pivot and try to predict performance score. The same could be said for satisfaction scores.

