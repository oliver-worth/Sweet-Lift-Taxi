# Sweet Lift Taxi Demand Prediction

## Project Overview
In this project, I developed a predictive model to forecast the number of taxi orders for Sweet Lift Taxi Company during the next hour. The objective was to ensure that the model's Root Mean Squared Error (RMSE) on the test set did not exceed 48. Achieving this goal would allow the company to efficiently allocate resources and attract more drivers during peak hours.

# Project Motivation
As the demand for ride-hailing services continues to grow, accurately predicting taxi demand is crucial for both operational efficiency and customer satisfaction. By leveraging historical data, this project aimed to build a robust model that would help Sweet Lift Taxi Company forecast taxi orders and better prepare for fluctuating demand.

## Data Description
The dataset used in this project consists of historical taxi order data, with the number of orders aggregated by hour. The data is stored in /datasets/taxi.csv, and the primary target variable is num_orders, representing the number of taxi orders per hour.

- Features:
- Date and Time: Timestamps indicating the hour of the order.
- num_orders: The number of taxi orders recorded in each hour.
## Methodology
1. Data Preprocessing and Feature Engineering
- Resampling: The data was resampled to hourly intervals to aggregate the number of orders per hour.
- Feature Creation: Time-based features such as year, month, day of the week, and hour were created. These features were then encoded using one-hot encoding to prepare them for the machine learning models.
2. Model Training and Evaluation
- Baseline Models:
- Simple Models: Initial benchmarks were established using the median and previous values. These models provided baseline RMSE scores to compare against more sophisticated models.

Time Series Models:
- Autoregressive (AR) Model: Trained with an order of 24 based on the Partial Autocorrelation Function (PACF) plot. The AR model achieved an RMSE of approximately 64.26 on the test set.
- Moving Average (MA) Model: Trained with an order of 25 based on the Autocorrelation Function (ACF) plot. The MA model achieved an RMSE of approximately 73.50 on the test set.

Gradient Boosting Model:
- Gradient Boosting: A Gradient Boosting model was trained and hyperparameter-tuned using GridSearchCV. This model significantly outperformed the time series models, achieving a test RMSE of 35.70, well below the project goal of 48.
  
3. Model Performance
- Gradient Boosting: The best performing model with an RMSE of 35.70 on the test set.
- AR Model: RMSE of 64.26 on the test set.
- MA Model: RMSE of 73.50 on the test set.
## Conclusion
The Gradient Boosting model emerged as the superior model for predicting the number of taxi orders in the next hour. It effectively captured the complex patterns in the data, outperforming traditional time series models.

Key Takeaways:
- Accuracy: The Gradient Boosting model achieved a test RMSE of 35.70, which is well within the acceptable limit of 48.
- Time Series Models: Despite their relevance to time series data, the AR and MA models did not perform as well as expected, suggesting the need for more complex models to capture the intricacies of the data.
- Feature Engineering: Effective feature engineering and the use of gradient boosting were critical in achieving the project's objectives.
## Future Work
Future improvements could involve:

- Further refining the Gradient Boosting model with additional hyperparameter tuning.
- Exploring additional external data sources to enhance predictive accuracy.
- Integrating more sophisticated time series models and experimenting with hybrid approaches.
## Technical Skills Demonstrated
- Time Series Analysis: Identified trends, seasonality, and patterns in time series data.
- Feature Engineering: Created and encoded time-based features.
- Modeling: Trained and evaluated multiple models, including Gradient Boosting, Autoregressive (AR), and Moving Average (MA) models.
- Hyperparameter Tuning: Used GridSearchCV to fine-tune model parameters.
