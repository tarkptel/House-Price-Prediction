<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
  
</head>
<body>
    <h1>House Price Prediction - Feature Engineering Focus</h1>
    <h2>Overview</h2>
    <p>
        This project focuses on predicting house prices using advanced feature engineering techniques.
        The dataset contains various attributes of houses, and the goal is to build a machine learning
        model that accurately predicts house prices based on these features. The notebook outlines a
        structured approach to data preprocessing, feature engineering, and model development.
    </p>
    <h2>Project Highlights</h2>
    <ul>
        <li>Comprehensive data preprocessing to handle missing values and outliers.</li>
        <li>Application of domain-specific knowledge for feature engineering.</li>
        <li>Exploration of feature transformation techniques to improve model performance.</li>
        <li>Implementation of machine learning models to predict house prices.</li>
        <li>Visualization and evaluation of results to derive actionable insights.</li>
    </ul>
    <h2>Dataset Description</h2>
    <p>
        The dataset used in this project includes the following types of features:
    </p>
    <ul>
        <li><strong>Numerical Features</strong>: Lot area, living area, number of bedrooms, etc.</li>
        <li><strong>Categorical Features</strong>: Neighborhood, building type, etc.</li>
        <li><strong>Target Variable</strong>: House price.</li>
    </ul>
    <h2>Key Steps</h2>
    <h3>1. Data Preprocessing</h3>
    <ul>
        <li><strong>Handling Missing Values</strong>: Imputation strategies based on feature types (e.g., mean, median, mode).</li>
        <li><strong>Outlier Detection and Removal</strong>: Identified and treated outliers to ensure data quality.</li>
        <li><strong>Feature Scaling</strong>: Standardization or normalization of numerical features.</li>
    </ul>
    <h3>2. Feature Engineering</h3>
    <p>Selected only numerical columns with types <code>float64</code> and <code>int64</code>. Combined existing columns to create new features and reduce dimensionality:</p>
    <ul>
        <li><code>totalsqrft</code> = <code>1stFlrSF</code> + <code>2ndFlrSF</code></li>
        <li><code>TotalBathrooms</code> = <code>FullBath</code> + (<code>HalfBath</code> * 0.5)</li>
        <li><code>TotalBasementBaths</code> = <code>BsmtFullBath</code> + (<code>BsmtHalfBath</code> * 0.5)</li>
        <li><code>HouseAge</code> = <code>YrSold</code> - <code>YearBuilt</code></li>
        <li><code>YearsSinceRemod</code> = <code>YrSold</code> - <code>YearRemodAdd</code></li>
    </ul>
    <p>Created binary columns:</p>
    <ul>
        <li><code>wooddeck</code> = Indicator for whether a property has a wood deck (Y/N).</li>
        <li><code>BsmtFns</code> = Indicator for whether <code>BsmtFinSF1</code> is finished or not.</li>
    </ul>
    <p>Dropped certain columns to reduce noise and dimensionality:</p>
    <ul>
        <li>Columns dropped due to high number of zeros: <code>PoolArea</code>, <code>3SsnPorch</code>, <code>ScreenPorch</code>, <code>EnclosedPorch</code>, <code>GarageYrBlt</code>, <code>BsmtFinSF2</code>, <code>MiscVal</code>, <code>LowQualFinSF</code>.</li>
        <li>Columns dropped due to high correlation: <code>GrLivArea</code>, <code>GarageCars</code>, <code>OverallQual</code>.</li>
    </ul>
    <h4>Using Recursive Feature Elimination (RFE)</h4>
    <p>
        Recursive Feature Elimination (RFE) was used to identify and select the most important features for the model.
        This technique involves iteratively fitting a model and removing the least important feature at each iteration until the desired number of features is reached.
    </p>
    <p>Benefits of using RFE in this project:</p>
    <ul>
        <li>Helped reduce dimensionality by eliminating irrelevant or redundant features.</li>
        <li>Improved model performance by focusing on the most predictive features.</li>
        <li>Provided insights into feature importance, aiding in the interpretation of the model.</li>
    </ul>
    <p>
        RFE contributed significantly to identifying the optimal subset of features, leading to a simpler and more efficient model with better generalization on unseen data.
    </p>
    <h3>3. Model Development</h3>
    <ul>
        <li>Split the data into training and testing sets.</li>
        <li>Trained multiple machine learning models, including:</li>
        <ul>
            <li>Linear Regression</li>
            <li>SGDRegressorr</li>
            <li>Random Forest Regressor</li>
            <li>Gradient Boosting Regressor</li>
            <li>XG Boost Regressor</li>
        </ul>
        <li>Tuned hyperparameters using RandomizedSearchCV.</li>
    </ul>
    <h3>4. Model Evaluation</h3>
    <ul>
        <li>Evaluated models using metrics such as RMSE, MAE, and R^2.</li>
        <li>Visualized feature importance to understand key predictors of house prices.</li>
    </ul>
    <h2>Reason for Choosing Gradient Boosting</h2>
    <p>
        Among the models tested, Gradient Boosting Regressor provided the highest R^2 score on the test set. 
        The R^2 score for Gradient Boosting was <strong>0.89</strong>, indicating strong predictive performance. 
        Its ability to handle complex non-linear relationships and minimize overfitting made it the best choice for this task.
    </p>
    <h2>Results</h2>
    <p>
        The model achieved high accuracy in predicting house prices, with significant improvement observed after applying feature engineering techniques.
        Feature engineering played a critical role in boosting model performance.
    </p>
    <h2>Future Work</h2>
    <ul>
        <li>Explore advanced feature selection methods.</li>
        <li>Experiment with deep learning models for price prediction.</li>
        <li>Deploy the model using a web framework (e.g., Flask or FastAPI).</li>
    </ul>
    <h2>Contributing</h2>
    <p>
        Contributions are welcome! Please fork the repository and submit a pull request with a detailed explanation of your changes.
    </p>
    <h2>License</h2>
    <p>
        This project is licensed under the MIT License - see the <a href="LICENSE">LICENSE</a> file for details.
    </p>
    <h2>Author</h2>
    <p><strong>Author:</strong> Tark Patel</p>
    <p><strong>LinkedIn:</strong> <a href="https://www.linkedin.com/in/tark-patel">@tark-patel</a></p>
</body>
</html>
