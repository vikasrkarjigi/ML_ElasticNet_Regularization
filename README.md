# ElasticNet Regularization for Housing Price Prediction
This project explores the application of ElasticNet regularization for predicting  housing prices using the **Ames Housing** dataset. The notebook demonstrates preprocessing, custom model implementation, and performance evaluation using different regression techniques, with a focus on how ElasticNet combines Lasso(L1) and Ridge(L2) regularization for better predictive performance.

## Project Overview
### Dataset
The **Ames Housing** dataset includes detailed information on house features and sale prices. This dataset is a more advanced dataset.
  - **Target Variable**: SalePrice (the sale price of the house).
  - **Features**: A mix of categorical and numeric features, describing various aspects of the house (eg. square footage, neighborhood, number of bathrooms and many more).

### Objective
The goal is to predict house prices using regularized regression techniques. ElasticNet regularization is used to avoid overfitting and enhance the model's ability to generalize on unseen data.

### Steps in the Notebook
1. **Data Preprocessing**:
  - Dopping irrelevant columns and handling missing data using median/mode imputation.
  - One-hot encoding categorical variables to convert them into a numeric format.
  - Splitting the data into training and testing sets.
  - Standardizing numerical features to improve model performance.
2. **Model Implementation**:
  - Linear Regression without regularization: A basic linear regression model is implemented from scratch.
  -  ElasticNet Regularization: Combines the strengths of both Lasso(L1) and Ridge(L2) regression to handle feature selection and multicollinearity.
3. **Model Training and Evaluation**:
  - Models are trained using the preprocessed data.
  - Evaluation is done using the R2 score to assess how well the models predict house prices on the test set.

### Installation and Setup
  1. Clone the repository:
  2. Download the dataset: The Ames Housing dataset can be downloaded from this repository. Save the dataset and upload it to the google Co-lab.
  3. Run the google Co-lab.

### Dependencies
  - numpy: For numerical computations and matrix operations.
  - pandas: For data manipulation and preprocessing.
  - matplotlib: For plotting data visualizations.

### ElasticNet Overview
ElasticNet regularization is a powerful tool that helps deal with datasets where:
  - Some features are irrelevant and need to b shrunk to zero (like Lasso).
  - Some features are correlated, and multicollinearity needs to be handled (like Ridge).
  ElasticNet achieves a balance between L1 and L2 regularization by adding penalties for both types of cofficients, helping improve model performance and prevent overfitting.

### Why ElasticNet?
  - Lasso(L1): It is good for feature selection by shrinking some coefficients to zero, but may perform poorly when there are highly correlated features.
  - Ridge (L2): Effective at dealing with multicollinearity but does not perform feature selection.
  - ElasticNet: Combines the benefits of both, providing robust regularization and feature selection.

## Results
The code in this notebook demonstrates how ElasticNet improves the model's performance by reducing overfitting and achieving a better trade-off between bias and variance. The performance is compared using the R score on both the training and testing datasets.
