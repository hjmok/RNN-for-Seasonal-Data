# RNN-for-Seasonal-Data

For this project, an RNN model using LSTM is created to predict seasonal data for Alcohol Sales and Gas/Electricity Production. 


## Dataset and Library
PyTorch was used as the main module for this model.
The two datasets both contain 325 points of monthly data, with the two columns showing the date and consumption (either Alcohol or Electricity usage) for that month. The datasets be found from the Federal Reserve of Economic Data:

Alcohol Sales - https://fred.stlouisfed.org/series/S4248SM144NCEN

Gas/Electricity Production - https://fred.stlouisfed.org/series/IPG2211A2N

## RNN Model
For the model input, the sequence size selected was 12. This is due to the data being seasonal by each month, therefore the trends following a yearly pattern (i.e. Alcohol sales are expected to increase in summer or holiday time). In addition, the RNN will predict 1 month into the future for every 12 months before it.

The model starts with 1 input leading into an LSTM layer. This LSTM outputs 125 neurons to a fully connected layer. The fully connected layer outputs the final predicted value 1 month into the future. The loss metric used is Mean Squared Error, since this is a continuous value problem. The Adam optimizer was used for this model. 

## Results
Both models were trained for 200 epochs. The predicted values are within the same scale as the labels when compared for the last 12 months. More importantly, the general trend is followed, showing the model understands when seasons of low and high consumption are expected. Furthermore, the trend pattern is continued when predicting for later dates that are beyond the datasets.

Please visit the following link for the resulting images: https://hjmok.github.io/josephmok_portfolio/#/SeasonalRNN
