# NITD-college-Project
Summer project 2020 under Prof. Subrata Nandi, Dept. of Computer Science, NIT Durgapur

### Target
Time Series forecasting using LSTM.

### About the Data
A time series Pollution dataset is given with information about Temperature, Humidity, CO2, NO2 and Dust level. There are 2 dust columns - Dust (PM2.5) and Dust (PM10).

### Data Preprocessing steps
1. Fixing a datatime index column.
2. Filled the missing values with mean of that column.
3. Removing duplicates.
4. Resampled the data to per hour to make calculation and observation easier.

### Multi-Step forecasting
Here, I have made the dataset univariate by dropping other columns and keeping only the dust column. I have used the value of dust at time (t-1) to forecast the value of dust at time (t). We can forecast multiple steps ahead as per user requirement by changing the value of 'num' variable in the code. Th model can be tuned by changing the n_batch, n_epoch, n_neuron parameters. Code for this is present in [dust_multistep_forecast](https://github.com/SamratDe/NITD-college-Project/blob/master/dust_multistep_forecast.ipynb). In the code I am forecasting for 24hrs.

### Multivariate forecasting
Here, the data is multivariate i.e dust (or the output) is dependent on more than one variable (or input parameters). I have used the values of all columns (or features) at time (t-1) to forecast the value of dust at time (t). Code for this is present in [dust_multivariate_forecast](https://github.com/SamratDe/NITD-college-Project/blob/master/dust_multivariate_forecast.ipynb). This code forecasts only one time step ahead (i.e 1hr in my case).
