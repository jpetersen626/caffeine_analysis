# Hackathon Project 🚀


## Problem Statement

Can we predict the type of drink based on the attribute of the drink? Since the data is imbalanced, I will be scoring based on the balanced accuracy score.

## The Data

The data originally came from Kaggle: https://www.kaggle.com/datasets/heitornunes/caffeine-content-of-drinks

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**drink**|*object*|caffeine.csv|Drink's name.|
|**Volume (ml)**|*float64*|caffeine.csv|Volume quantity.|
|**Calories**|*int64*|caffeine.csv|Calories quantity.|
|**Caffeine (mg)**|*int64*|caffeine.csv|Caffeine quantity.|
|**type**|*object*|caffeine.csv|Drink's type. (Coffe, Energy Drinks, Energy Shots, Soft Drinks, Tea, Water)|

## Summary of Analysis

This project was one that was done in one hackathon - it was completed in one day in about 7 or so hours. We were to find a dataset and build a predictive model with it.

During the EDA process, I was looking for any meaningful relationship with the various attributes of the drink and the type. Nothing very distinct stood out until I looked at the vectorized words in the 'drink' column. Funnily enough, the most common words in each type class were words that were the exact name of the beverage (e.g. 'Coffee' for the Coffee type class). When starting the modeling, I originally wanted to see if Caffeine content could predict the type of drink. However, that was a bad performing model using Logistic Regression. I tried multiple other types of Logistic Regression models with various other parameters and transformers, including using imblearn's module for imbalanced data. The best predictive model that was achieved during this hackathon was an imlearn model with Logistic Regression and SMOTE, as this dataset was fairly imbalanced. It also used Count Vectorizer for the 'drink' column, with stop words including the most common words in each type class, and standard scaler on the numerical features. This model increased it's correct predictions on the minority class, Water. It wound up with a balanced accuracy score on the test set of 0.86. This is an improvement over the baseline accuracy of 0.36.

## Conclusions and Future Steps

With this best model, it was really interesting to see the coefficients that came out of the model for each class and how they change from the EDA process. Some of the coefficient words that came up from the drink name were ones that weren't prevalent at all during EDA as they were so few, but working with SMOTE allowed them to be increased and thus properly scored alongside the other prevalent words. I also thought it was interesting how caffeine content was the strongest predictor of Energy Shots, and by a long shot too. It was 114 times more likely to predict Energy Shots, 25 times more likely to predict Energy Drinks, and 65 times more likely to predict Coffee. It wasn't in the top 5 for Soft Drinks, Tea, or Water.

For future steps, I'd like to explore other model types as well to see if that score can improve. For this hackathon I only focused on Logistic Regression with many different types of parameters and features.
