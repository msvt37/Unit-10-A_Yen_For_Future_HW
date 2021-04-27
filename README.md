# Unit-10-A_Yen_For_Future_HW
Homework for unit 10, time series analysis and regression analysis
----------------------------------------------------------------------
#### Matthew Szoke for UPENN Fintech 2021

This homework for unit 10 focused on the use of time series analysis and regression analysis for the purpose of predicting Yen futures returns.

Much of the code was pulled from various class examples.  A data file, yen.csv, was provided which contained the historical OHLC Yen values and Yen-Dollar futures.

###### Time Series

"time_series_analysis.ipynb" focused on using the ARMA and ARIMA models for analysis.  The ARMA modeled generated the following for the model summary:

P>|z| : .422, .810, .921, 817


Above, we can see P values over .05, indicating the model is not a good fit.

The ARIMA model has similar performance, with all P values being over .05 as well.

ARIMA Model Results

P>|z| : 0.652, 0.687,0.966,0.302,0.374,0.949,0.671


Lastly, the GARCH model had better performance with the following showing all P values smaller than .05.

P>|z|: 3.708e-02, 2.974e-03


