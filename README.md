# Time-Series-Analysis
## What is time series analysis?

Time series analysis is a specific way of analyzing a sequence of data points collected over an interval of time. 
In time series analysis, analysts record data points at consistent intervals over a set period of time rather than just 
recording the data points intermittently or randomly. However, this type of analysis is not merely the act of collecting data over time. 
What sets time series data apart from other data is that the analysis can show how variables change over time. 
In other words, time is a crucial variable because it shows how the data adjusts over the course of the data points as well as the final results. 
It provides an additional source of information and a set order of dependencies between the data. 
Time series analysis typically requires a large number of data points to ensure consistency and reliability. 
An extensive data set ensures you have a representative sample size and that analysis can cut through noisy data. 
It also ensures that any trends or patterns discovered are not outliers and can account for seasonal variance. 
Additionally, time series data can be used for forecasting—predicting future data based on historical data.

## Why organizations use time series data analysis

Time series analysis helps organizations understand the underlying causes of trends or systemic patterns over time. 
Using data visualizations, business users can see seasonal trends and dig deeper into why these trends occur.

## Where it is implimented


    Weather data
    Rainfall measurements
    Temperature readings
    Heart rate monitoring (EKG)
    Brain monitoring (EEG)
    Quarterly sales
    Stock prices
    Automated stock trading
    Industry forecasts
    Interest rates

## Classification and considerations

While time series data is data collected over time, there are different types of data that describe how and when that time data was recorded. 
For example:

    * Time series data is data that is recorded over consistent intervals of time.
    * Cross-sectional data consists of several variables recorded at the same time.
    *  Pooled data is a combination of both time series data and cross-sectional data.

Further, time series data can be classified into two main categories:

    * Stock time series data means measuring attributes at a certain point in time, like a static snapshot of the information as it was.
    * Flow time series data means measuring the activity of the attributes over a certain period, 
      which is generally part of the total whole and makes up a portion of the results.

In time series data, variations can occur sporadically throughout the data:

    * Functional analysis can pick out the patterns and relationships within the data to identify notable events.
    * Trend analysis means determining consistent movement in a certain direction. There are two types of trends: deterministic, 
      where we can find the underlying cause, and stochastic, which is random and unexplainable.
    * Seasonal variation describes events that occur at specific and regular intervals during the course of a year. 
      Serial dependence occurs when data points close together in time tend to be related.

Time series analysis and forecasting models must define the types of data relevant to answering the business question. 
Once analysts have chosen the relevant data they want to analyze, they choose what types of analysis and techniques are the best fit.

 
## Types of time series analysis

Even within time series analysis, there are different types and models of analysis that will achieve different results.

    Classification: Identifies and assigns categories to the data.
    Curve fitting: Plots the data along a curve to study the relationships of variables within the data.
    Descriptive analysis: Identifies patterns in time series data, like trends, cycles, or seasonal variation.
    Explanative analysis: Attempts to understand the data and the relationships within it, as well as cause and effect.
    Exploratory analysis: Highlights the main characteristics of the time series data, usually in a visual format.
    Forecasting: Predicts future data. This type is based on historical trends. It uses the historical data as a model for future data, 
    predicting scenarios that could happen along future plot points.
    Intervention analysis: Studies how an event can change the data.
    Segmentation: Splits the data into segments to show the underlying properties of the source information.

 
## Primary techniques and tools for time series analysis

Just as there are many types and models, there are also a variety of methods to study data. Here are the three most common.

    1. Box-Jenkins ARIMA models: These univariate models are used to better understand a single time-dependent variable, 
      such as temperature over time, and to predict future data points of variables. 
      These models work on the assumption that the data is stationary. 
      Analysts have to account for and remove as many differences and seasonality in past data points as they can. 
      Thankfully, the ARIMA model includes terms to account for moving averages, seasonal difference operators, 
       and autoregressive terms within the model.
    
    2. Box-Jenkins Multivariate Models: Multivariate models are used to analyze more than one time-dependent variable, 
       such as temperature and humidity, over time.
       
    3. Holt-Winters Method: The Holt-Winters method is an exponential smoothing technique. 
       It is designed to predict outcomes, provided that the data points include seasonality.
    
    
  ## Autocorrelation

Informally, autocorrelation is the similarity between observations as a function of the time lag between them.
Example of an autocorrelation plot

Above is an example of an autocorrelation plot. Looking closely, you realize that the first value and the 24th value have a high autocorrelation. Similarly, the 12th and 36th observations are highly correlated. This means that we will find a very similar value at every 24 unit of time.

Notice how the plot looks like sinusoidal function. This is a hint for seasonality, and you can find its value by finding the period in the plot above, which would give 24h.
    
![Autocorrelation](https://user-images.githubusercontent.com/86042628/134364499-0626daf5-c0e4-4d72-8251-40cc9705bbf0.png)

    
  ## Seasonality

Seasonality refers to periodic fluctuations. For example, electricity consumption is high during the day and low during night, or online sales increase during Christmas before slowing down again.

Example of seasonality
As you can see above, there is a clear daily seasonality. 
Every day, you see a peak towards the evening, and the lowest points are the beginning and the end of each day.
Remember that seasonality can also be **derived from an autocorrelation plot** if it has a **sinusoidal shape.** Simply look at the period, and it gives the length of the season. 
![Seasonality](https://user-images.githubusercontent.com/86042628/134364917-9851d39e-6dfe-4b3d-ae5e-42347cd5eb42.png)
    
## Stationarity

Stationarity is an important characteristic of time series. A time series is said to be stationary if its statistical properties do not change over time. 
In other words, it has constant mean and variance, and covariance is independent of time.
Example of a stationary process
![Stationary](https://user-images.githubusercontent.com/86042628/134365078-5b180c89-26be-4019-8d53-fa17bbaade4f.png)

Looking again at the same plot, we see that the process above is stationary. The mean and variance do not vary over time.

Often, **stock prices are not a stationary process**, since we might see a growing trend, or **its volatility might increase over time** (meaning that variance is changing).

Ideally, we want to have a stationary time series for modelling. Of course, not all of them are stationary, but we can make different transformations to make them stationary.    

## How to test if a process is stationary

You may have noticed in the title of the plot above Dickey-Fuller. This is the statistical test that we run to determine if a time series is stationary or not.
Without going into the technicalities of the Dickey-Fuller test, it test the null hypothesis that a unit root is present.
If it is, then p > 0, and the process is **not stationary.**
Otherwise, p = 0, the null hypothesis is rejected, and the process is considered to be **stationary.**
As an example, the process below is not stationary. Notice how the mean is not constant through time.
  ![Process is stationary](https://user-images.githubusercontent.com/86042628/134366147-2f0852a8-c59c-4e6f-82b4-b70c3cc504b8.png)


# Modelling time series

There are many ways to model a time series in order to make predictions. Here, I will present:

   1. Moving Average
   2. Exponential Smoothing  > Double exponential smoothing > Triple Exponential smoothing
   3. ARIMA
    
    Source: https://www.tableau.com/learn/articles/time-series-analysis , https://towardsdatascience.com/the-complete-guide-to-time-series-analysis-and-forecasting-70d476bfe775
