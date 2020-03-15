# Predict Customer Churn with Logistic Regression

### Introduction
When implementing new features within an application, it is extremely important to analyze the effects of this feature in order to definitively know whether or not the implementation impacted user behavior. This analysis can help companies evaluate these features and properly reallocate resources if the feature is not effective. KyngaCell, a leader in the mobile gaming industry, is interested in assessing the effectiveness of their new online community feature in regard to increased revenue, retention, and customer lifetime value.

### Data Description
Data was obtained on various behaviors of 199 users before and after the introduction of the online community. These behaviors include whether the user joined the community (41% joined), the spend of users one month before (avg = $78) and one month after (avg = $121) the introduction of the community, and the number of months a user had been playing the game before the community was introduced (avg = 4). Data was also included on whether each user churned within the first 90 days following the introduction of the online community (59% churned) and how much each user spent in their last 90 days using the app (avg = $80).

### Evaluating Revenue: Model and Results
The data provided consist of users’ spending one month before and one month after the launch of the online community feature. Additionally, there is information about whether or not that customer joined the online community. With this data, we can build a
differences-in-differences (diff-in-diff) model where we assess the spending differences of two groups (those who joined the online community and those who did not) and compare those spending differences at two different points in time (one month before and one month after the feature launch). Comparing the group differences at these two points in time will allow us to assess the exact effect of joining the online community on user spending.

![pic1](/figure1.png)

Based on the diff-in-diff model created, there is strong evidence that joining the online community feature can increase user revenue. Comparing the group spending differences before and after the launch of the online community, we found out that there is a significant increase of 29 dollars in revenue due to the new feature. Hence we can draw the conclusion that the launch of the online community helped increase sales by a factor of $29; however it is important to note that the small sample size poses a limitation to this conclusion, simply because there is not enough data to reach a definitive conclusion.

### Evaluating Retention: Model and Results
The data provided contain customers’ spending and churn status in the three months following the online community launch, as well as the monthly age of the customer at the time of the online community launch. With this information we can create a logistic regression model that predicts the probability of a customer churning or not based on their spending, whether or not they joined the online community, and their monthly age. We chose a logistic regression because it provides a quantified value for the strength of the association while adjusting for other variables (removes confounding effects). The exponential of coefficients correspond to the odds ratios for the given factor, which enables us to achieve a result with strong interpretation power.

Based on our logistic regression model, the online community will not raise the user retention rate. We found that whether the user joined the online community or not is the only factor that has a statistically significant impact on the probability of churn. The coefficient estimate of this variable “join” being 0.21, means that if a customer joined the online community, their probability of churning increased by 0.21. To assess the model accuracy, we looked at the classification error, which is the proportion of observations that have been misclassified. From this error, we found the accuracy of the model is 0.6281; we can then prove that the prediction is quite accurate and validate our initial conclusion. Intuitively, joining the online community should decrease the churn rate, but our analysis says otherwise. Three months, however, could be too short to see the return on retention, so the data may not be valid for the assumption. Also, it is possible that other unobserved factors may also be interfering with the result.

### Evaluating Customer Lifetime Value: Model and Results
When determining whether joining the online community had any affect on Customer Lifetime Value (CLV), we used predicted churn rates and calculated profit margin from average spending of users in their last 90 days using the app. The regression showed that joining the online community had an effect on CLV, however it was not positive. The results showed that joining the online community was correlated with a $26 decrease in CLV. This finding goes hand-in-hand with the finding that joining the community was related to decreased retention.

Predicting CLV is incredibly difficult, and relies on an accurate prediction of churn along with other factors. While the direction of the relationship between joining the community and CLV may be accurate (negative), more user data would make the analysis of the size of the effect more accurate. There also may be other factors affecting CLV for which this model does not account for.

### Conclusion

Adding the online community for app users had mixed results on customer behaviors.

Joining the community led to a $29 increase in spending by users which would not have happened had the community not been introduced. However, those who joined the community were more likely to churn within a 90-day period and overall had a lower Customer Lifetime Value. The company must now decide whether short-term income gains or long-term increases in retention and CLV are of more importance. This also shows that it is important to always back up beliefs with data, otherwise important insights may be missed.

