# Reflection Paper: House Price Prediction

## 1. What did you implement?
I built a machine learning pipeline to predict house prices using a dataset with features like size, bedrooms, bathrooms, and location. I started by cleaning the data—removing weird characters from the price, fixing location names (like correcting "Subrb" to "Suburb"), and filling in missing values with averages or the most common values.

After cleaning, I split the data into training (80%) and testing (20%) sets. I then trained two different models:
1.  **Linear Regression:** A simple model that fits a straight line to the data.
2.  **Random Forest Regressor:** A more complex model that uses many decision trees to make predictions.

## 2. Comparison of Models
When I ran the "Sanity Check" on a test row, the Random Forest model's prediction was typically closer to the actual price than the Linear Regression model's prediction. The Linear Regression prediction was often a bit off, probably because it assumes a straight-line relationship which might be too simple for house prices that can vary wildly based on location and size.

I found that Random Forest generally gave more realistic results because it can capture non-linear patterns, like how a house price might jump significantly if it's in a specific popular location, rather than just increasing linearly with size.

## 3. Understanding Random Forest
In simple terms, a **Random Forest** is like asking a large group of people for their opinion instead of just one expert. It creates many "Decision Trees" during training. Each tree looks at a random subset of the data and makes its own prediction.

When we want to predict a price, the Random Forest asks all these individual trees for their guess, and then calculates the average of all their answers. This "averaging" helps smooth out errors that a single tree might make, providing a final prediction that is more accurate and stable. It's called a "Forest" because it's made of many "Trees".

## 4. Metrics Discussion
The **Random Forest** model had better metrics overall.
*   **R² (R-squared):** This number was higher for Random Forest, meaning it explained more of the variance in house prices.
*   **MAE (Mean Absolute Error) & RMSE (Root Mean Squared Error):** These error numbers were lower for Random Forest, which means typically its predictions are closer to the real prices in dollar terms.

This tells me that Random Forest is stronger at capturing the complex relationships in the housing data compared to Linear Regression.

## 5. Your Findings
Based on the results, I prefer the **Random Forest Regressor** for this task. While Linear Regression is faster and easier to interpret (you can see exactly how much each bedroom adds to the price), it's not flexible enough for real-world data like housing markets which have outliers and complex rules. Random Forest handles these complexities much better, providing more reliable predictions for potential buyers or sellers.
