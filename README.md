# Traffic-XGB

A Jupyter Notebook used to conduct exploratory data analysis and time series forecasting on traffic volume for westbound I-94, a major interstate highway in the US that connects Minneapolis and St Paul, Minnesota. Here, we developed an Extreme Gradient Boosting (XGBoost) model with Mean Absolute Percentage Error (MAPE) as the scoring method. Cross validation splits were generated with TimeSeriesSplit and hyperparameter tuning was conducted with GridSearchCV.

## Data Source

The dataset used in this notebook was taken from the [UC Irvine Machine Learning Repository](https://archive.ics.uci.edu/dataset/492/metro+interstate+traffic+volume). The data was collected by the Minnesota Department of Transportation (MnDOT) from 2012 to 2018 at a station roughly midway between the two cities. The descriptions of included variables are as follows.

- `holiday`               - (Categorical)   : US National holidays plus regional holiday, Minnesota State Fair
- `temp`                  - (Numeric)       : Average temp in kelvin
- `rain_1h`               - (Numeric)       : Amount in mm of rain that occurred in the hour
- `snow_1h`               - (Numeric)       : Amount in mm of snow that occurred in the hour
- `clouds_all`            - (Numeric)       : Percentage of cloud cover
- `weather_main`          - (Categorical)   : Short textual description of the current weather
- `weather_description`   - (Categorical)   : Longer textual description of the current weather
- `date_time`             - (DateTime)      : Hour of the data collected in local CST time
- `traffic_volume`        - (Numeric)       : Hourly I-94 ATR 301 reported westbound traffic volume

## Additional Resources

This project was made possible with the help of the following openly-available learning resources.

- [Rob Mulla's Two-Part Series on XGBoost](https://www.youtube.com/@robmulla) available on his YouTube Channel. This focuses more on the applications of the model in practice.
- [Josh Starmer's Four-Part Series on the XGBoost Algorithm](https://www.youtube.com/@statquest) available on his YouTube Channel. This focuses more on the theoretical aspect of general machine learning and also the mathematical elements of XGBoost.
- [Previous Example of Using XGBoost with this Dataset](https://www.kaggle.com/code/dannyperez014/project-06-interstate-i-94-traffic-forecasting). This example leans more toward feature engineering and exploratory data analysis of given variables. However it lacks the use of cross validation.
- [Dataset Kaggle Link](https://www.kaggle.com/datasets/anshtanwar/metro-interstate-traffic-volume/data). This is the original link with which I first found the dataset.

## Remarks

This project was probably my first time training and using a openly available and powerful model like XGBoost. I learned concepts such as model training, train-test splitting for time series data, L1 and L2 regularization, data visualization with correlation matrixes, boxplots, time series lineplots, and so on. Here, note that TimeSeriesSplit must be used in order to avoid a data leak, where we would train with future data whilst testing on past data during cross validation. This is a mistake that most people fall into when following online tutorials.

Another issue was the gap of missing observations, particularly around the year 2015. Although overall this was project was a good exercise to get familiar with one of the famous and publicly available models out there, I certainly do wish that the data was in better quality. Finally, there wasn't a proper train-test split for this data. Generally people tend to use 80-20 splits, which is something I didn't do in this project. It may also be beneficial to look at more traditional time series forecasting models like ARMA, and actually learn to deal with stationarity, trends, and other aspects of time series data.
