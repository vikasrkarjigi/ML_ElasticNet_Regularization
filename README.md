# ElasticNet Regularization for Housing Price Prediction
This project explores the application of ElasticNet regularization for predicting  housing prices using the **Ames Housing** dataset. The notebook demonstrates preprocessing, custom model implementation, and performance evaluation using different regression techniques, with a focus on how ElasticNet combines Lasso(L1) and Ridge(L2) regularization for better predictive performance.

## Project Overview
### Dataset
The **Ames Housing** dataset includes detailed information on house features and sale prices. This dataset is a more advanced dataset.
  - **Target Variable**: SalePrice (the sale price of the house).
  - **Features**: A mix of categorical and numeric features, describing various aspects of the house (eg. square footage, neighborhood, number of bathrooms and many more).

### Objective
The goal is to predict house prices using regularized regression techniques. ElasticNet regularization is used to avoid overfitting and enhance the model's ability to generalize on unseen data.

### Extra Feature - Efficient Alpha and L1 Ratio Search
The implementation includes a grid search feature to find the best alpha (regulatisation strength) and L1 ratio (balance between Lasso and Ridge) values for ElasticNet using a user-defined range of alphas and L1 ratios. This helps in selecting the optimal model based on R2 scores.

### Steps in the Notebook
1. **Data Preprocessing**:
  - Dopping irrelevant columns and handling missing data using median/mode imputation.
  - One-hot encoding categorical variables to convert them into a numeric format.
  - Splitting the data into training and testing sets.
  - Standardizing numerical features to improve model performance.
2. **Model Implementation**:
  - Base Regression: This is the base class for all regression models.
  - Linear Regression without regularization: A basic linear regression model is implemented from scratch.
  - Regularized Regression: Implements both Lasso and Ridge by tuning the l1_ratio and alpha parameters. 
  -  ElasticNet Regularization: Combines the strengths of both Lasso(L1) and Ridge(L2) regression to handle feature selection and multicollinearity.
  -  find_best_elastic_net: This function performs grid search on a range of alphas and L1 Ratios to find the best ElasticNet model.
3. **Model Training and Evaluation**:
  - After splitting the data into training and test sets, each model is trained, and predictions are made for both the training and test sets.
  - The performance of each model is evaluated using the R² score, which measures how well the model explains the variance in the data.
  - The code prints R² scores for all models:
    - Simple Linear Regression
    - Lasso (L1 Regularization)
    - Ridge (L2 Regularization)
    - ElasticNet (Best performing model from grid search)
4. **Visualisation**:
  - The R2 scores for the training and testing sets are visualized in a bar plot for comparison.

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

### Questions Answered in this README.
1. Why ElasticNet?
  - Lasso(L1): It is good for feature selection by shrinking some coefficients to zero, but may perform poorly when there are highly correlated features.
  - Ridge (L2): Effective at dealing with multicollinearity but does not perform feature selection.
  - ElasticNet: Combines the benefits of both, providing robust regularization and feature selection.

2. What is the function of the model you have created and in what situations should it be utilized?
  - The model is designed to address situations with multicollinearity or overfitting, using linear regression with or without regularization. It can be employed when we need to manage model complexity and avoid excessive coefficients, particularly in datasets with many dimensions.
  - ElasticNet is especially handy when you need to strike a balance between L1 (for selecting features) and L2 (for shrinkage) regularization.

3. What method did you use to evaluate if your model is functioning reasonably well?
  - The Ames Housing dataset was utilized to test the models, and the R² score was utilized to assess the adequacy of the fit for both the training and test sets.
  - Moreover, the grid search process for the ElasticNet model helped ensure the selection of the optimal hyperparameters for the dataset provided.

4. Which parameters have you made available to users of your implementation to adjust and optimize performance?
  - Alpha: Regulates the overall level of regularization.
  - Balance between L1 (Lasso) and L2 (Ridge) penalties is controlled by the L1 Ratio for ElasticNet.

5. Does your implementation struggle with certain inputs? If given additional time, would you be able to find solutions to these issues or are they essential to the model?
  - The implementation might face difficulties with datasets that exhibit significant multicollinearity or complex missing data patterns.
  - Although median imputation is used for handling missing values, employing more sophisticated imputation methods could enhance performance.
  - Moreover, the code employs a set number of iterations for enhancing performance, but it may not always lead to convergence. Better results could be achieved with a more flexible stopping criterion.

## Results
The code in this notebook demonstrates how ElasticNet improves the model's performance by reducing overfitting and achieving a better trade-off between bias and variance. The performance is compared using the R score on both the training and testing datasets.

## Team Members
1. Ayyappa Boovadira Kushalappa **(A20555146)**
2. Binaal Bopanna Machanda Beliappa **(A20599896)**
3. Vikas Ravikumar Karjigi **(A20581687)**
4. Yashas Basavaraju **(A20586428)**
