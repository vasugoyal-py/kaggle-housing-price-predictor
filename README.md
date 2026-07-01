# kaggle-housing-price-predictor
A Random Forest machine learning model to predict housing prices, utilizing hyperparameter tuning for model optimization.

1. Import Libraries

The project begins by importing the required libraries.

Pandas for loading and manipulating data.
Scikit-learn for machine learning.
RandomForestRegressor for training the prediction model.
train_test_split to create training and validation datasets.
mean_absolute_error (MAE) to evaluate model accuracy.
2. Load the Dataset

The training dataset is loaded into a Pandas DataFrame.

The dataset contains various features describing each house, such as:

Lot Area
Year Built
Living Area
Number of Bedrooms
Number of Bathrooms
Overall Quality
Overall Condition

The target variable is:

SalePrice — the selling price of the house.

3. Feature Selection

The project selects numerical features that have a strong relationship with house prices.

These features are used as the input variables (X) while SalePrice is used as the output (y).

4. Train-Validation Split

The dataset is divided into two parts:

Training Data – used to train the model.
Validation Data – used to measure how well the model performs on unseen data.

This helps prevent overfitting and provides a realistic estimate of model performance.

5. Train a Random Forest Model

A Random Forest Regressor is trained using the training dataset.

Random Forest combines predictions from many decision trees to produce more accurate and stable predictions than a single decision tree.

The final model uses:

450 decision trees (n_estimators=450)
410 maximum leaf nodes (max_leaf_nodes=410)
Random state = 1 for reproducibility
6. Hyperparameter Tuning

Before selecting the final model, different hyperparameter values were tested.

Experiments included:

Varying the number of trees (n_estimators)
Varying the maximum number of leaf nodes (max_leaf_nodes)

The model performance was evaluated using Mean Absolute Error (MAE).

The notebook also contains code (currently commented out) that plots MAE against these hyperparameters to visualize how model performance changes.

7. Train on the Full Dataset

After finding the best hyperparameters, the model is retrained using the entire training dataset to maximize the amount of information available for learning.

8. Make Predictions

The trained model is applied to the test dataset to predict house prices.

Each prediction represents the estimated selling price of a house that the model has never seen before.

9. Generate Submission File

The predictions are stored in a CSV file containing:

Column	Description
Id	House identifier
SalePrice	Predicted selling price
