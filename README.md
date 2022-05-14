# Store Sales - Time Series Forecasting

____

##### Project Tasks:
Investigate sales at Favorita stores in Ecuador during 2013-2017. Predict the behavior of the time series of sales of
goods in Favorita stores in Ecuador


### Data
Data for this project were taken from **kaggle**:  
https://www.kaggle.com/c/store-sales-time-series-forecasting/data

`.csv` files:
- **oil.csv** - Daily oil price. Includes values during both the train and test data timeframes. (Ecuador is an oil-dependent country and it's economical health is highly vulnerable to shocks in oil prices.)
- **train.csv** - The training data, comprising time series of features store_nbr, family, and onpromotion as well as the target sales.
- **test.csv** - The test data, having the same features as the training data. You will predict the target sales for the dates in this file.
- **sample_submission.csv** - A sample submission file in the correct format.
- **holidays_events.csv** - Holidays and Events, with metadata
- **stores.csv** - Store metadata, including city, state, type, and cluster.
- **transactions.csv** - transaction data, store numbers, and dates

To predict the behavior of the time series was to create a `df` dataset with columns:
- `date`
- `sales`

### Preprocessing
Dataset was divided into `train.df` and `test.df`. In `train.df` are sales data for the previous 62 days, and in `test.df`
for 63 days. The model will learn from sales data for the previous 62 days, and will issue values for the 63rd day.

Before learning the model, the data was scaled using `MinMaxScaler()`:
```
from sklearn.preprocessing import MinMaxScaler
```
## Model
The `LSTM` model from the `tensorflow.keras.layers` was selected to predict the behavior of the time series.  


<img src = "https://github.com/Vvold/Store-Sales-Time-Series-Forecasting/blob/master/img%20time%20series/2022-02-23%20212822.png" alt = "time series">

Result model:  

<img src = "https://github.com/Vvold/Store-Sales-Time-Series-Forecasting/blob/master/img%20time%20series/2022-02-23%20212852.png" alt = "pred">  

<img src = "https://github.com/Vvold/Store-Sales-Time-Series-Forecasting/blob/master/img%20time%20series/2022-02-23%20212910.png" alt = "pred">

The time series forecasting model in general correctly predicted the behavior of the series, the model takes into
account the seasonality of sales and the trend of increasing sales. But there are some inaccuracies: the model does
not show a sharp decline in sales on January 1 each year, this is due to the work of the model itself, a clearer 
adjustment of which will give a more accurate result, and the model slightly lowers sales per week
## Contacts

---
### Vitkovskiy Volodymyr
- email: VitkovskyiVB@gmail.com
- telegram: @wvld_11
- github: [Vvold](https://github.com/Vvold)
