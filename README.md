
---

### Steps for Data Preprocessing and Model Building:

1. **Import Required Libraries**: Begin by importing all the necessary libraries and modules for data processing, visualization, and model building.

2. **Load the Data**: Load both the training and testing datasets into memory for analysis.

3. **Examine Missing Data**: Investigate the percentage of missing values (nulls) in each attribute of both the training and testing datasets.

4. **Examine Class Distribution**: Analyze the distribution of the target variable, 'Survived', to understand the class imbalance.

5. **Examine Gender and Survival**: Based on the assumption from the movie that more females survived than males, analyze the survival rate by gender to confirm this hypothesis.

6. **Examine Pclass and Survival by Gender**: Since 'Pclass' could serve as a proxy for social status, investigate its effect on survival, particularly among females who did not survive, as priority may have been based on social status within the same gender group.

7. **Visualize Relationships**: Use Seaborn for visualization to explore various relationships between features and the target variable, 'Survived'.

8. **Create and Impute Age by Salutation**:
   - Generate a new feature called 'Salutation' (e.g., Mr, Mrs, Miss).
   - Merge similar salutations (e.g., 'Dr' and 'Mr' could be grouped) to simplify the dataset.
   - Calculate the median age for each salutation group and impute missing 'Age' values based on the median age for each salutation.

9. **Construct 'GenderPlus' Feature**: Create a new attribute called 'GenderPlus' with possible values: 'female', 'boy', and 'male'. This is based on the hypothesis that boys might have had a higher chance of survival compared to adult males.

10. **Visualize Survival Rates of Boys vs. Adult Males**: Plot the survival percentages of boys and adult males to test the hypothesis that boys had a better survival rate.

11. **Construct 'Family_Size' Feature**: Create a new feature called 'Family_Size', which is the sum of 'SibSp' (siblings and spouses), 'Parch' (parents and children), plus 1 (to include the individual themselves).

12. **Construct 'FamilySurvivalRate'**: Introduce a new attribute, 'FamilySurvivalRate'. The hypothesis is that if someone from the same family survived, the likelihood of other family members surviving is higher. Compute the survival rate for family members and assign this to the respective individual.

13. **Label Encode 'GenderPlus' and 'Sex'**: Apply label encoding to the 'GenderPlus' and 'Sex' features to convert categorical values into numerical labels for modeling.

14. **Impute Missing Fare Values**: Handle the missing values in the 'Fare' feature by imputing them. Additionally, create two new features: 
    - 'Fare_Bins' to categorize fare into bins.
    - 'Fare_Code' to assign numerical codes to fare categories.

15. **Anomaly Detection**: Use PyCaret's anomaly detection module to identify any outliers or anomalies in the dataset.

16. **Feature Selection**: For the final model, use only the following attributes:
    - 'Gender'
    - 'GenderPlus'
    - 'Family_Size'
    - 'FamilySurvivalRate'
    - 'Pclass'
    
    Other features have been tested, but this set of attributes is found to perform well.

17. **Train Model Using XGBoost**: Apply the XGBClassifier with hyperparameter tuning to train the model using the selected features.

---
