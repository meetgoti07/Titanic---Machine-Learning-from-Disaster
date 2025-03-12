1. Import the necessary stuff.
2. Load the data.
3. Examine null percentages in train and test data attributewise
4. Examine class distribution, in this case distribution of Survived
5. From the movie, we can guess that more females should have been survived than males. Examine that.
6. Pclass (proxy for social status) might have played some role in not survival as priority among same gender type may be based on that. So, Examine Pclass among the females who did not survive.
7. Let us try to visualize a few relations using seaborn
8. Create a new feature - Salutation, merge similar Salutations, i.e. replace similar salutations with one and find meadian age Salutationwise. Impute Age Salutationwise (e.g. handle missing value in age Salutationwise).
9. Construct a new attribute, let us name it 'GenderPlus' with possible values female, boy and male. This is because we suspect that boys might had better chance of survival than adult males.
10. Visualize the survuval percentage of boys vs adult males to test the above point.
11. Construct a new feature Family_Size as the sum of SibSp (Sibling and Spouce), Parch (Parents and Children) + 1.
12. Construct FamilySurvivalRate. The hypothesis is that if somebody from a family of a passenger under focus is survived then the chances of that passenger survived is also more.
13. LabelEncode GenderPlus and Sex
14. There is a missing value in Fare, impute it and create Fare_Bins and Fare_Code
15. Do anomaly detection using pycaret.anomaly
16. Use only Gender, GenderPlus, FamilySize, FamilySurvivalRate and Pclass attribute in the final training and testing set (We tried others but this set of attributes worked well).
17. Use XGBClassifier with hyperparameter tuning.
