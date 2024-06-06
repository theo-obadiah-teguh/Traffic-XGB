# Traffic-XGB

A Jupyter Notebook used to conduct Exploratory Data Analysis and Time Series Forecasting on traffic volume for westbound I-94, a major interstate highway in the US that connects Minneapolis and St Paul, Minnesota. Utilized an Extreme Gradient Boosting (XGBoost) model with Mean Absolute Percentage Error (MAPE) as the scoring method. Cross validation splits were generated with TimeSeriesSplit and hyperparameter tuning was conducted with GridSearchCV.

## Data Source

The dataset used in this notebook was taken from the [UC Irvine Machine Learning Repository](https://archive.ics.uci.edu/dataset/492/metro+interstate+traffic+volume). The data was collected by the Minnesota Department of Transportation (MnDOT) from 2012 to 2018 at a station roughly midway between the two cities. The descriptions of included variables are as follows.

- holiday                Categorical    US National holidays plus regional holiday, Minnesota State Fair
- temp                   Numeric        Average temp in kelvin
- rain_1h                Numeric        Amount in mm of rain that occurred in the hour
- snow_1h                Numeric        Amount in mm of snow that occurred in the hour
- clouds_all             Numeric        Percentage of cloud cover
- weather_main           Categorical    Short textual description of the current weather
- weather_description    Categorical    Longer textual description of the current weather
- date_time              DateTime       Hour of the data collected in local CST time
- traffic_volume         Numeric        Hourly I-94 ATR 301 reported westbound traffic volume
