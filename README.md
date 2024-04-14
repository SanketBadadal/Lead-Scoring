# Lead Scoring Case Study Summary

# Problem Statement:
X Education sells online courses to industry professionals. X Education needs help in selecting the most promising leads, i.e. the leads that are most likely to convert into paying customers.
 The company needs a model wherein you a lead score is assigned to each of the leads such that the customers with higher lead score have a higher conversion chance and the customers with lower lead score have a lower conversion chance.
The CEO, in particular, has given a ballpark of the target lead conversion rate to be around 80%.

# Solution Summary:
## Step 1: Reading and Understanding Data:
Read and analyze the data.

## Step 2: Data Cleaning:
1. First step to clean the dataset we chose was to drop the variables having unique values.
2. Then, there were few columns with value ‘Select’ which means the leads did not choose any given option. We changed those values to Null values.
3. We dropped the columns having NULL values greater than 40%.
4. Next, we removed the imbalanced and redundant variables. This step also included imputing the missing values as and where required with median values in case of numerical variables and creation of new classification variables in case of categorical variables. The outliers were identified and removed. Also, in one column was having identical label in different cases (first letter small and capital respectively). We fixed this issue by converting the label with first letter in small case to upper case.
5. All sales team generated variables were removed to avoid any ambiguity in final solution.
## Step 3: Data Transformation:
Changed the binary variables into ‘0’ and ‘1’
## Step 4: Dummy Variables Creation:
1. We created dummy variables for the categorical variables.
2. Removed all the repeated and redundant variables
## Step 5: Test Train Split:
The next step was to divide the data set into test and train sections with a proportion of 70- 30% values.
## Step 6: Feature Rescaling:
1. We used the Min Max Scaling to scale the original numerical variables. Then using the stats model we created our initial model, which would give us a complete statistical view of all the parameters of our model.
2. Dropped the highly correlated dummy variables.
## Step 7: Model Building:
1. Using the Recursive Feature Elimination, we went ahead and selected the 15 top important features.
2. Using the statistics generated, we recursively tried looking at the P-values in order to select the most significant values that should be present and dropped the insignificant values.
3. Finally, we arrived at the 11 most significant variables. The VIF’s for these variables were also found to be good.
4. Based on the above assumption, we derived the Confusion Metrics and calculated the overall Accuracy of the model.
5. For our final model we checked the optimal probability cut off by finding points and checking the accuracy, sensitivity and specificity.
6. We then plot the ROC curve for the features and the curve came out be pretty decent with an area coverage of 88% which further solidified the of the model.
## Step 8: Finding the Optimal Cutoff Point
1. Then we plotted the probability graph for the ‘Accuracy’, ‘Sensitivity’, and ‘Specificity’ for different probability values. The intersecting point of the graphs was considered as the optimal probability cutoff point. The cutoff point was found out to be 0.38
2. Then, checked if 80% cases are correctly predicted based on the converted column.
## Step 9: Computing the Precision and Recall metrics
1. We checked the precision and recall with accuracy, sensitivity and specificity for our final model on train set.
2. Next, Based on the Precision and Recall trade-off, we got a cut off value of approximately 0.41.
3. We could also observe the new values of the ‘accuracy=80.1%, ‘sensitivity=79.1%’, ’specificity=80.8%’
## Step10: Making Predictions on Test Set
Then we implemented the learnings to the test model and calculated the conversion probability based on the Sensitivity and Specificity metrics and found out the accuracy value to be 81.6%, Specificity= 84.4%, Precision=73.4% Recall= 76.7%
## Step 11: Conclusion:
- The lead score calculated in the test set of data shows the conversion rate of 81% on the final predicted model which clearly meets the expectation of CEO has given a ballpark of the target lead conversion rate to be around 80%.
- Good value of sensitivity of our model will help to select the most promising leads.
- Our model is having stability an accuracy with adaptive environment skills. Means it will adjust with the company’s requirement changes made in future.
- Features which contribute more towards the probability of a lead getting converted are:
  1. Total Visits
  2. Total Time Spent on Website
  3. Page Views Per Visit
- Variables have very lower chance to get converted are:
  1. Lead Origin API
  2. Lead Origin Landing Page Submission
  3. Lead Origin Lead Import
  4. Last Activity Email Bounced
