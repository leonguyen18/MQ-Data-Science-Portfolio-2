# COMP6200 Data Science - Portfolio 2: Analysis of an E-commerce Dataset Part 2

This project is part of the COMP6200 Data Science unit. It involves further analysis of a cleaned E-commerce dataset where each user can post a rating and review for the products they purchased. Other users can evaluate the initial rating and review by expressing their trust or distrust. 

The goal is to train linear regression models to predict users' ratings towards items, exploring the impacts of feature selections and different sizes of training/testing data on model performance.

![Dataset Description](../portfolio-part-1-leonguyen18/Fig1%20The%20Combined%20E%20commerce%20Dataset.png)

## Dataset

The dataset includes comprehensive information for each user, such as their profile, ID, gender, city of birth, product ratings (on a scale of 1-5), reviews, and the prices of the products they purchased. Moreover, for each product rating, we have information about the product name, ID, price, and category, the rating score, the timestamp of the rating and review, and the average helpfulness of the rating given by others (on a scale of 1-5).

The dataset, originating from several data sources, has been cleaned and merged into a single CSV file named `cleaned_ecommerce_dataset.csv`.

## Tools and Libraries Used
- **Jupyter Notebook**
- **Python**
  - `pandas`
  - `numpy`
  - `scikit-learn`
  - `seaborn`
  - `matplotlib`

## Project Tasks

### 1. Import Cleaned E-commerce Dataset
- Load the dataset from `cleaned_ecommerce_dataset.csv` using pandas.
- Check the total length of the dataset.

### 2. Explore the Dataset
- Use `head()` and `info()` methods to get an overview of the data.
- Calculate correlations between helpfulness, gender, category, review, and rating using the `corr()` method.
- Analyze the correlations to determine the most and least correlated features with respect to rating.

### 3. Split Training and Testing Data
- Randomly split the dataset into training and testing sets with different sizes:
  - Case 1: Training data containing 10% of the entire data.
  - Case 2: Training data containing 90% of the entire data.
- Check the shape of training and testing sets for both cases.

### 4. Train Linear Regression Models with Feature Selection
- Select the two most correlated and two least correlated features with respect to rating.
- Train four linear regression models:
  - Model-a: Case 1 with two most correlated features.
  - Model-b: Case 1 with two least correlated features.
  - Model-c: Case 2 with two most correlated features.
  - Model-d: Case 2 with two least correlated features.

### 5. Evaluate Models
- Evaluate the performance of the four models using MSE and RMSE.
- Show the results for each model.

### 6. Visualize, Compare, and Analyze Results
- Visualize the results.
- Analyze the impacts of data size and feature selection on model performance.
- Discuss whether models trained with more correlated features and larger training data perform better.

### 7. Data Science Ethics
- Study the provided examples on data ethics.
- Analyze an infographic of the 2008 Summer Olympic Medals, detailing potential ethical concerns.

## Findings

### Correlation Analysis
- **Least correlated features** with 'rating':
  - Helpfulness: -0.007523
  - Gender (encoded): -0.034337
- **Most correlated features** with 'rating':
  - Category (encoded): -0.163158
  - Review (encoded): -0.036118

### Model Performance
- **Impacts of data size**:
  - Models trained with 90% of the data generally perform better.
  - Model 2c (90% training data, most correlated features) had the best performance (MSE: 1.61, RMSE: 1.27).
- **Impacts of feature selection**:
  - Models trained with the most correlated features consistently outperform those with the least correlated features.
  - Model 1b (10% training data, least correlated features) had the worst performance (MSE: 1.84, RMSE: 1.36).

### Data Science Ethics
- The infographic on the 2008 Summer Olympic Medals raises concerns such as potential misinterpretation due to sorting criteria, presentation bias, and unbalanced representation.


## Contributing

As this is an individual assignment, I am the main contributor. However, if you find any errors or areas of improvement, feel free to create an issue or submit a pull request.

## License

This project is part of a university assignment and the dataset was provided by the lecturer. Please use this for reference or educational purposes only.