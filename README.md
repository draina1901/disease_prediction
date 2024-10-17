# Disease_Prediction

Use the provided dataset `training_data.csv` to build a binary classifier (i.e., logistic regression or an SGDClassifier) that predicts the `has_disease` column. Place your work in a notebook named `submission.ipynb` in this directory. Make sure to:

- Carefully handle the missing data by choosing suitable imputation methods for both categorical and numeric columns. 
- Check for outliers
- Standardize numeric features
- Encode categorical features appropriately before training.
- Make sure to build imputation models / scaling on the training set only.

Your aim is to maximize your f1 scores!  To do this, you might try:

- Removing columns that you don't think are necessary
- Attempting different imputation methods
- Creating new features (note - we haven't done this yet, but you can inspect the data to create "meta-features" that combine existing features)
- Try a different classifier (anything in SciKit learn is fair game)

Be careful not to overfit, as this might lead to a classifier that performs poorly on the test data! When you are done, train your model on the full training data, and then obtain predictions for the `test_data.csv`. Save your predictions to a file called `answers.csv`, which should contain a single column `has_disease` for predictions. For the test data, impute any missing data using the transformers that have been trained on your training data before testing (no data leakage!).

Note that this assignment is like a Kaggle competition, meaning that you don't know the answers in the `test_data.csv`.  We have the answers, and will determine your F1 scores on the test data.

# Rubric

Points will given for each of the following sections present in your notebook.  Each section must be named with a heading.  Code must be documented where necessary, and markdown should be present to explain summary findings at the end of each section. Points will be awarded based on the thoroughness and quality of code in each section.

1. **Exploratory Data Analysis** (2 points) - Did you: 
    - Explore your data  
    - Examine distributions  
    - Look for correlations 
    - Identify nulls

2. **Preprocessing** (3 points) - As necessary, did you correctly:
    - Handle outliers 
    - Encode features
    - Standardize features
    - Handle nulls (whether by imputation or some other method)

4. **Modeling & Evaluation** (3 points) - Did you:
    - Use a cross-validation procedure?
    - Avoid data leakage?
    - Correctly evaluate F1-Score?

5. **Test data** (2 points) - Did you:
    - Train you model appropriately?
    - Impute data correctly?
    - Achieve at least 75% f1 on the test data?
    - Save your answers to an `answers.csv` file?

**Extra Credit** For every 5% over 80% in your `answers.csv` against the actual answers, you will get an additional 1 point on your final grade for the class.
