# Prompts Used in ChatGPT to Make this Analysis
In same order as Python File

## Prompt:
Take this xml data and tell me how to parse it into data I can use in python. 

## Response:
What the file looks like conceptually
Using xml.etree.ElementTree (standard)
How to clean the data as xml is all strings
Convert it to work in a Time Series

## Prompt: 
Start by making a correlation heatmap of the variables that make sense to do so 

## Response:
Only numerical variables can be put into a heatmap so only year and estimate will get compared.

## Prompt:
Run a Pearson correlation between the two columns and get a p value to see significance

## Response:
Code for to run Pearson correlation and get the p-value
Guide to typical values of p and whether to reject or accept hypothesis based on that value

## Prompt:
Start modeling the Year and Estimate variables as a time series

## Response:
Start by looking at the plot (line graph) to see trends, jumps, etc
Run an augmented Dickey-Fuller Test to test for stationarity.
(This test is critical for seeing knowing if we can use the ARIMA model for this data)
p>= 0.05 -> Not stationary, p<0.05 -> Stationary
If not stationary, take the differences and check that for stationary

## Prompt: 
The stationary p-value for the **difference**  is less than 0.05 at under 3.57e-20, so this leads up to believe we should try the ARIMA model. Set up the dataset to run through the ARIMA model. 

## Response: 
Use ACF and PACF Plots to identify ARIMA Parameters
Build ARIMA Model
Fill in the correct p, d, q values
Print the forecast

## Prompt: 
Im debating between having the p parameter be 1 or 2. So I ran both here are my results for ARIMA (1,1,1) … 
Here are the results for ARIMA(2,1,1)…

## Response:
Comparing will determine the best model for this data. 
(1,1,1) has weak negative autoregressive effect and is not statistically significant at p=0.087>0.05, but is borderline. Moving average has a very strong effect and high statistical significants at 0.001 < 0.05 (Good ACF plot value picked)
Varience (sigma^2) represents residual noise. Nothing concerning
Ljung-Box Test shows residuals appear independent and captures temporal structure well.
Jarque-Bera Test (Normality) residuals are approximtely normally distributed, acceptable assumption for ARIMA
Heteroskedaticity Test residual varience is NOT constant, evidence of volatility changes, Not fatal but interesting. 
(2,1,1) had Autoregressive 1 as not significant but Autoregressive 2 is significant as p = 0.001. Moving average is very significant at 0.001 < 0.05
Ljung-Box test shows residual independence . Jarque-Bera Test shows residuals are appoximately normal. 
Heteroskedaticity same as (1,1,1), present in model. 

AIC has lower for (2,1,1) is better, BIC has lower for (1,1,1) is better, log likelihood if higher for (2,1,1) is better. 

## Prompt:
Due to the heteroskadasticity and the fact this is a time series lets model this data using ARCH and GARCH models

## Response:
Use the ARIMA model's residuals to use the ARCH and GARCH model
Plot the residuals
Build ARCH model
Build GARCH model (likely better) 
Plot Conditional Volatility of GARCH (likely interesting)

## Prompt:
Help me interpret my results: 
Labeled and pasted below

## Response:
Residuals plot displays classic volatility clustering (what we want, confirms heteroskedasticity)

AIC GARCH is significantly lower than ARCH, Log likelihood is also a better fit for GARCH as it's larger. 

The Conditional Volitality Plot indicated 
	• Increasing uncertainty in overdose trends
	• Escalating epidemic instability
	• Structural change in public health dynamics

## Prompt:
Now use GARCH and ARIMA (2,1,1) to forecast the next 5 years)

## Response:
Convert GARCH Varience to Volitality
Combine ARIMA mean and GARCH Volitality
Make Confidence Interval
Plot Forecast
