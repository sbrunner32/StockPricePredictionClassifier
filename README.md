# StockPricePredictionClassifier
This contains applications which gather stock price information for provided companies over a provided period of time and creates moving averages for this information over a provided time window which are then used to create a CSV file for that particular stock and provided time periods. After the moving averages are generated, another application takes the CSV files created and separates them into a training and testing set. Then, the unnecessary data values are removed so only the traits pertaining to the prediction remain. Finally, a variety of different data science models are applied to the training and testing data to predict for each moving average, if the stock's price will go up or down after the selected prediction period. 
## Important terms and variables for operation ##
* start - The initial date of collected stock market data.
* end - The last date of collected stock market data.
* window_period - The number of days used for the moving averages to be generated with.
* waiting_period - The number of days after each window_period that we are evaluating the stock price for.
* rsi_moving_average_period - The number of days used to calculate RSI values. This is separate from window_period as RSI is a common financial indicator which primarily uses two weeks as its observation period.
* rsi_under_value - This is an abritrary value for which I determine a stock to be undervalued if its RSI is under this value (30). This simply means the stock has had a decrease in price about 70% of the time over the RSI window.
* rsi_over_value - This is an abritrary value for which I determine a stock to be overvalued if its RSI is over this value (70). This simply means the stock has had an increase in price about 70% of the time over the RSI window.
* prev_data_period - The period of time required to collect closing costs from before the initial window so RSI values can be calulated for the first 14 days. 
* future_data_period - The period of time required to generate the last window_period number of results for the truth values. 
* post_stock - Contains the stock market information for the future_data_period. Used to generate the truth values (whether a stock's price went up or down over the given window period) for the last prediction_period number of entries.
