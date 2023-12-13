# Machine_Learning_Study
An application of machine learning models to evaluate primary schools in Singapore

As the Ministry of Education shifts to a less competitive education system, a system using Achievement Levels (ALs) has been introduced. 
We can use machine learning regression to predict AL scores for schools, using the school’s characteristics.

2 datasets were obtained from data.gov.sg and the Ministry Of Education website -
* School Directory and Information
    Contains information about schools, such as subjects offered, CCAs, bus connections, general location
*Indicative PSLE Score Range of 2020
    Contains information about the likely PSLE score ranges for current schools

## Data Processing
* Removing Unused Data
    Secondary schools entries were identified and other entries were filtered out.
* Dropping Unused Features
    Features such as address, names of principals were removed.
* Quantifying Descriptive Data
    Descriptive data such as names of CCAs and subjects offered were converted into numerical terms.
* One-Hot Encoding
    Features such as general location (NSEW) was one-hot encoded
* Combining Datasets
    The spreadsheet with indicative PSLE scores (y-values) was combined into the main dataset.

## Methods
Different machine learning algorithms were used to find the best model. They include -
1. Linear Regression
2. Ensemble Learning (with and without Grid Search)
3. Decision Tree Regression
4. K-Nearest Neighbours

Of the models being used, the ensemble learning model using hyperparameters tuned with GridSearch outperformed the rest by a large margin.

|Algorithm Used|Linear Regression|Ensemble Learning|Ensemble Learning (with GridSearch)| Decision Tree|K-Nearest Neighbours|
|--|--|--|--|--|--|
|Training Set Error|1.79|0.79|0.73|NA|2.45|
|Test Set Error    |2.48|2.15|1.83|2.15|2.79|
*Mean absolute error was used*

## Insights
When each feature was ranked by importance, it was discovered that -
Gender of students mattered little to PSLE scores.

![image](https://github.com/pirong/Machine_Learning_Study/assets/23309150/ce1425b7-5acd-499e-96c1-07f492266126)

School autonomy (in designing curriculums), number of sports and arts CCAs, and MOE speciality programs significantly affect scores. 
This may be because they are a proxy indicator of school funding.

![image](https://github.com/pirong/Machine_Learning_Study/assets/23309150/8cbea7d2-402a-4e16-a06e-b73b49464ae9)

## Conclusion
Many features contribute to a good or desirable school. We can generate a machine learning regression model using features that indicate a school’s performance.
To enhance our model, we must
1. Process and clean data
2. Compare between models
3. Tune model hyperparameters




