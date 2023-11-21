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
    
- Part 2

    Run a second logistic regression model setting the penlayt parameter to 'l2'
    Fit the model on the test data
    Create a confusion matrix and provide the different fit measures
    
- Compare the two models in terms of how well they fit

#### Random Forest
- Train a random forest  using the default parameters.
- Fit the model on the test data.
- Create a confusion matrix and provide different fit measures.
- Compare the performance of the best logistic with random forest.

#### Visualize the best Model

- Use shap to plot feature importance for your best model and describe.

#### Test with data from other agency
- Using code from earlier make the same recodes to the Dept. of Commerce dataframe.
- Fit the data using your best model.
- Create a confusion matrix and provide different fit measures.
- Compare the performance of the model with the test data from the first agency with the performance using the data from the second agency.

## Summary 
who does this predict poorly for
how does it predict differently for different sub-populations
identify those it identifies correctly or incorrectly to check for bias




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