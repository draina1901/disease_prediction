# Disease Prediction Pipeline

This repository contains a machine learning pipeline for predicting the likelihood of having a disease based on patient data. The pipeline performs data preprocessing, outlier detection, feature engineering, and classification using several machine learning models.

## Project Structure

- `training_data.csv`: The dataset used to train the model.
- `test_data.csv`: The dataset on which predictions are made.
- `answers.csv`: File where the predictions on the test set are saved.

## Features

1. **Data Preprocessing**:
    - Handles missing values with `SimpleImputer` and `KNNImputer`.
    - Encodes ordinal and binary features.
    - Applies outlier detection using the IQR method.
    - Scales numerical data using `StandardScaler`.

2. **Data Visualization**:
    - Histograms to visualize distributions of numeric features.
    - Correlation heatmap to identify relationships between numeric features.
    - Box plots to identify outliers in numeric columns.

3. **Machine Learning Pipeline**:
    - Pipelines for different data types (binary, ordinal, numeric).
    - Outlier removal and missing value imputation.
    - Classification using Logistic Regression, SGD Classifier, Random Forest, and Gradient Boosting.
    - Class balancing using SMOTE.

4. **Model Selection**:
    - Cross-validation to compare models based on F1 score.
    - RandomForestClassifier is used as the final model after evaluating multiple classifiers.

5. **Predictions**:
    - The model is trained on the entire dataset after SMOTE oversampling.
    - Predictions on the test data are saved in `answers.csv`.

## Installation

To run this project locally, follow these steps:

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/disease-prediction.git
    ```

2. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

3. Place your `training_data.csv` and `test_data.csv` files in the root directory.

4. Run the script to train the model and generate predictions:
    ```bash
    python main.py
    ```

5. The predictions will be saved in `answers.csv`.

## Key Components

### Data Preprocessing Pipelines

- **Binary Features**: Missing values are filled with the most frequent value.
- **Gender**: One-hot encoded after filling missing values.
- **Ordinal Features**: Encoded and imputed using `KNNImputer`.
- **Numeric Features**: Outliers are clipped using IQR, missing values are filled using `IterativeImputer`, and data is scaled.

### Outlier Detection

A custom transformer `OutlierRemover` is used to remove outliers based on the Interquartile Range (IQR) method.

### SMOTE (Synthetic Minority Over-sampling Technique)

The class imbalance is addressed using SMOTE, which generates synthetic samples to balance the dataset.

### Classifiers

The following classifiers are compared using 5-fold cross-validation:
- Logistic Regression
- SGD Classifier
- Random Forest
- Gradient Boosting

The best performing classifier is used for the final model training.

## Results

Each model's performance is evaluated using F1 score, and the RandomForestClassifier is selected as the final model based on its cross-validation results.

## Future Improvements

- Add more advanced hyperparameter tuning methods.
- Experiment with other imputation techniques for missing data.
- Incorporate more classifiers to enhance the robustness of the model comparison.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
