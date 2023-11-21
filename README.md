# agency-turnover
Analysis of agency turnover using machine learning.
## Scenario
You are an analyst in the White House and you have been asked to help the
administration understand the factors predicting agency turnover.
You have downloaded the annual employee data from the Departments of Commerce 
and Labor to work with.
After a planning meeting with your manager you have developed a work plan. 
You have two weeks to conduct the analysis and prepare a brief 3 minute 
(max) presentation using no more than one slide.

#### Using: Python, Jupyter Notebooks, SKLearn, Pandas, Numpy, Matplotlib.pyplot, Seaborn, Shap


### Process
---

#### Import Data and visualize features
- Import the Dept. of Labor and the Dept. of Commerce data into separate dataframes.
- Select one dataframe and generate counts for each value and plot in a bar chart.

#### Recode any variables where this is necessary
- Identify rows and columns where large numbers are blank. 
- Drop rows with large amounts of missing data.
- Check variables for missing more than 10% of data.
- For variables with blank/missing or 'Do Not Know' recode to the median of the other values.
- Create dummy codes for Question 84.
- Recode demographic variables using dummies.
- Recode the outcome variable so that 0 if ‘No’ (‘A’) or 1 if anything else ‘Yes’ (‘B’, ‘C’, ‘D’) 
- Combine all back into a single dataframe.

#### Correlation Matrix
- Create a correlation matrix in the form of a heatmap (code provided). Color varies based on strength of correlation.
- Identify any variables that are correlated more than .8, then average them and create a new variable.
- Once you have dropped and variables and/or created composites, create a new correlation matrix.

#### Split your data in training and test sets. When doing this remember to set the random seed to a number that you will keep constant.

#### Logistic Regression
- Part 1
    
    Run a logistic regression on the training data, setting the penalty paraemt to 'None' in SKLearn
    Fit the model on the test data
    Create a confusion matrix and provide the different fit measures

<img width="761" alt="Screenshot 2023-11-20 at 8 59 24 PM" src="https://github.com/CJunger/agency-turnover/assets/131617662/c60945cc-6627-4b94-9c68-2e6a742de142">


- Part 2

    Run a second logistic regression model setting the penlayt parameter to 'l2'
    Fit the model on the test data
    Create a confusion matrix and provide the different fit measures

<img width="756" alt="Screenshot 2023-11-20 at 9 00 25 PM" src="https://github.com/CJunger/agency-turnover/assets/131617662/75285511-da06-416b-85a1-d4e89a7407af">

    
- Compare the two models in terms of how well they fit

#### Random Forest
- Train a random forest  using the default parameters.
- Fit the model on the test data.
- Create a confusion matrix and provide different fit measures.
- Compare the performance of the best logistic with random forest.

<img width="602" alt="Screenshot 2023-11-20 at 9 00 40 PM" src="https://github.com/CJunger/agency-turnover/assets/131617662/088464d0-6f68-468c-841f-e03ffc64e095">


#### Visualize the best Model

- Use shap to plot feature importance for your best model and describe.

<img width="460" alt="Screenshot 2023-11-20 at 10 53 55 PM" src="https://github.com/CJunger/agency-turnover/assets/131617662/3e2a9d1d-64ab-4246-8c29-d3fb0985fe9f">


#### Test with data from other agency
- Using code from earlier make the same recodes to the Dept. of Commerce dataframe.
- Fit the data using your best model.
- Create a confusion matrix and provide different fit measures.
- Compare the performance of the model with the test data from the first agency with the performance using the data from the second agency.

## Analysis & Summary

Accuracy shows how often a classification ML model is correct overall. Precision shows how often an ML model is correct when predicting the target class. Recall shows whether an ML model can find all objects of the target class. (source https://www.evidentlyai.com/classification-metrics/accuracy-precision-recall#:~:text=Accuracy%20shows%20how%20often%20a,when%20choosing%20the%20suitable%20metric.)

All of the models performed very similarly. The first logisitic regresssion model using the "None" penalty parameter performed slightly better than the other models and thus was used for the testing on the Department of Commerce data.

Performance of the model depends on what we are trying to target, in this case we are targeting wether or not employees leave their job in the next year by comparing their answers to a job survey. In this scenario those who said they would leave but ended up staying would not matter as much to our research as those who said they would leave and left or said they would stay and left. 



### Resources:
Correlation Matrix
https://vitalflux.com/correlation-heatmap-with-seaborn-pandas/

Used to filter correlated features
https://github.com/krishnaik06/Complete-Feature-Selection/blob/master/2-Feature%20Selection-%20Correlation.ipynb
https://www.codecademy.com/article/fe-filter-methods

filter feature reduction
https://towardsdatascience.com/feature-selection-with-pandas-e3690ad8504b

Shap Values
https://www.datacamp.com/tutorial/introduction-to-shap-values-machine-learning-interpretability
