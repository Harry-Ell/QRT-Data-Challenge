# Football Match Outcome Prediction
This repository contains the code and methodology for predicting football match outcomes using a Random Forest classifier. The prediction model utilizes team and player statistics, processed through three different feature reduction approaches to improve accuracy and performance.

## Project Overview
This project aims to predict football match outcomes by leveraging a combination of team and player statistics. The dataset consists of 140 features per team and 300 features per player, with each team having around 20 players. The features are reduced through various methods to enhance model efficiency and accuracy.

## Feature Reduction Approaches
- Approach 1: Team Statistics
In this approach, only team-level statistics are included in the prediction model. This provides a baseline for comparison with more complex feature sets.

- Approach 2: Selected Player Statistics
This approach involves selecting relevant player statistics based on discussions with GPT-4's 'Football Betting' GPT. These selected statistics are then averaged across the team and combined with team-wide stats, excluding highly correlated features.

- Approach 3: Statistical Feature Selection
This approach employs more precise statistical methods to include or eliminate features. Steps include:
  - Averaging player statistics by positions (e.g., midfielder_PLAYER_TACKLES_season_sum).
  - Running a correlation test to remove features with a correlation coefficient of 0.7 or greater with other included features.
  - Applying Recursive Feature Elimination (RFE) to reduce the feature set further.

## Model Training
**Grid Search:** A grid search is conducted on a validation set to optimize hyperparameters for the Random Forest classifier.
**Training:** The model is trained on the training split of the data using the optimized hyperparameters.
Evaluation
The model's performance is evaluated based on the accuracy of the game prediction outcome. Currently, the model achieves an accuracy of 48.83%, compared to the top-performing model's accuracy of 49.32%. This is achieved by filtering the feature set via approach 2.
