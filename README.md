# Airline Passenger Prediction
Predict the number of international airline passengers in units of 1,000, given a year and a month. The data ranges from January 1949 to December 1960 or 12 years, with 144 observations, one for each month.  
Credit: Deep Learning with Python by Jason Brownlee  
data source: https://raw.githubusercontent.com/jbrownlee/Datasets/master/airline-passengers.csv

## EDA
Plot the 144 observations and it has a prominent cycle in it.  
![passenger](https://github.com/sindhri/airplane_passenger_prediction/blob/master/doc/img1.png) 

## Data preparation
Split the time series sampple in 67% for training and 33% for validation  

## Models
### 1. MLP
![MLP_input](https://github.com/sindhri/airplane_passenger_prediction/blob/master/doc/img3.png) 

1. Create a function, which takes argument X and 1 at time t and output Y at time t+1 based on the dataset  
2. Use the function to create training and prediction from the dataset  
Train Score: 530.44 MSE (23.03 RMSE)  
Test Score: 2350.94 MSE (48.49 RMSE)  
The model has anaverage error of 23 passengers (in thousands) on the training dataset and 48 passengers (inthousands) on the test dataset.  
Not very great on the test score, even though the prediction plot looks pretty  
![MLP](https://github.com/sindhri/airplane_passenger_prediction/blob/master/doc/img2.png) 

### 2.  MLP with increased window
![MLP_window_input](https://github.com/sindhri/airplane_passenger_prediction/blob/master/doc/img4.png) 

Given the current time (t) wewant to predict the value at the next time in the sequence (t+1), we can use the current time(t) as well as the two prior times (t-1 and t-2).  Increasd thelookback argument from 1 to 3.  
Train Score: 453.45 MSE (21.29 RMSE)  
Test Score: 2029.01 MSE (45.04 RMSE)  
The model has an average error of 21 passengers (in thousands) on the training dataset and 45 passengers (inthousands) on the test dataset.
Improved.
![MLP_window](https://github.com/sindhri/airplane_passenger_prediction/blob/master/doc/img5.png) 

# Conclusion: MLP with a larger lookback window makes a better prediction
With the final error of 21 passengers (in thousands) on the training dataset and 45 passengers (in thousands) on the test dataset. 
