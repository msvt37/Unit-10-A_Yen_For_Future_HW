# Unit-10-A_Yen_For_Future_HW
Homework for unit 10, time series analysis and regression analysis
----------------------------------------------------------------------
#### Matthew Szoke for UPENN Fintech 2021

This homework for unit 10 focused on the use of time series analysis and regression analysis for the purpose of predicting Yen futures returns.

Much of the code was pulled from various class examples.  A data file, yen.csv, was provided which contained the historical OHLC Yen values and Yen-Dollar futures.

"time_series_analysis.ipynb" focused on using the ARMA and ARIMA models for analysis.  The ARMA modeled generated the following for the model summary:

Dep. Variable:	y	No. Observations:	7514
Model:	ARMA(2, 1)	Log Likelihood	-7894.071
Method:	css-mle	S.D. of innovations	0.692
Date:	Tue, 27 Apr 2021	AIC	15798.142
Time:	01:44:44	BIC	15832.765
Sample:	0	HQIC	15810.030
      coef	std err	    z	  P>|z|	 [0.025	0.975]
const	   0.0063	0.008	0.804	0.422	-0.009	0.022
ar.L1.y	-0.3063	1.277	-0.2400.810	-2.810	2.197
ar.L2.y	-0.0019	0.019	-0.099	0.921	-0.040	0.036
ma.L1.y	0.2947	1.277	0.231	0.817	-2.208	2.798
Roots
Real	Imaginary	Modulus	Frequency
AR.1	-3.3339	+0.0000j	3.3339	0.5000
AR.2	-157.1560	+0.0000j	157.1560	0.5000
MA.1	-3.3927	+0.0000j	3.3927	0.5000

Above, we can see P values over .05, indicating the model is not a good fit.

The ARIMA model has similar performance, with all P values being over .05 as well.

ARIMA Model Results
Dep. Variable:	D.Settle	No. Observations:	7514
Model:	ARIMA(5, 1, 1)	Log Likelihood	-41944.619
Method:	css-mle	S.D. of innovations	64.281
Date:	Tue, 27 Apr 2021	AIC	83905.238
Time:	01:45:22	BIC	83960.635
Sample:	1	HQIC	83924.259
                 coef	std err	  z	    P>|z|	 [0.025	0.975]
         const	0.3161	0.700	 0.452	  0.652	-1.056	1.688
ar.L1.D.Settle	0.2821	0.699	 0.404	  0.687	-1.088	1.653
ar.L2.D.Settle	0.0007	0.016	 0.043	  0.966	-0.030	0.032
ar.L3.D.Settle	-0.0126	0.012	-1.032	0.302	-0.037	0.011
ar.L4.D.Settle	-0.0137	0.015	-0.889	0.374	-0.044	0.016
ar.L5.D.Settle	-0.0012	0.018	-0.064	0.949	-0.036	0.034
ma.L1.D.Settle	-0.2972	0.699	-0.425	0.671	-1.667	1.07

Lastly, the GARCH model had similar performance with the following showing all P values larger than .05.
Zero Mean - GARCH Model Results
Dep. Variable:	Settle	R-squared:	0.000
Mean Model:	Zero Mean	Adj. R-squared:	0.000
Vol Model:	GARCH	Log-Likelihood:	-7461.93
Distribution:	Normal	AIC:	14931.9
Method:	Maximum Likelihood	BIC:	14959.6
No. Observations:	7514
Date:	Tue, Apr 27 2021	Df Residuals:	7514
Time:	01:46:05	Df Model:	0
Volatility Model
      coef	          std err	    t	   P>|t|	      95.0% Conf. Int.
omega	    4.2896e-03	2.057e-03	2.085	 3.708e-02	[2.571e-04,8.322e-03]
alpha[1]	0.0381	    1.282e-02	2.970	 2.974e-03	[1.295e-02,6.321e-02]
alpha[2]	0.0000	    1.703e-02	0.000	 1.000	    [-3.338e-02,3.338e-02]
beta[1]	  0.9536	    1.420e-02	67.135 0.000	    [ 0.926, 0.981]

