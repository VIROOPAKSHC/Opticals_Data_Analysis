## This repository holds the code and data as part of analysis done on an Opticals shop. Details are hidden. 

#### The main aim of this analysis is to give some insights into the trend in the data of the Optical shop. The data provided by the shop as part of the project is given for January 2023.
<br><br>
This project is done as a part of course work of the course <a href="https://study.iitm.ac.in/ds/course_pages/BSMS2001.html">Business Data Management</a> course  from <a href="https://study.iitm.ac.in/ds/index.html">IIT Madras Online BSc Degree</a>.
<br><br>
The repository is structured as:<br>
  master<br>
    |<br>
    |--- BDM Project.ipynb <br>
    |--- OPTICALS.csv <br>
    |--- OPTICALS.xlsx <br>
    |--- OPTICALS_Clearned.csv <br>
<br>
The IPYNB file consists of all the code for the analysis <br>
The OPTICALS.xlsx file contains the raw data directly obtained from the shop owner. The CSV file is extracted from the xlsx file and cleaned to get the cleaned CSV file finally.<br>
<h3>Project Details</h3>
<h4>Problem Statement</h4>
<p>The difficulties an optical store faces in effectively predicting customer demand for its products and setting fair prices are the focus of this project. We will create a demand forecasting and pricing prediction model that considers many aspects that affect demand, such as seasonality and trends, using past sales data and external market data. Utilizing machine learning methods, the model will be evaluated and improved. The optical business will be able to predict demand better and set pricing that reflects market conditions by using this model, leading to improved inventory management and more prospects for sales. The data is gathered using the procedures specified, and the analysis tools described shall be used following the plotting and prediction methodologies described. This data is utilised to train the model, which will be used to estimate demand and predict sales in the future. According to the textiles indicated in this proposal, the project delivery timetable is spread out over the upcoming few months.</p>
<h4>Solving Approach</h4><p>
  <p>•	Details about the methods used with Justification:
  -- Time series analysis: Based on previous observations, time series data estimate future values. A time series analysis will be performed to find patterns and trends in the previous sales data that can be utilised to forecast future demand.
  -- Regression analysis will be utilised to find correlations between various factors, such as sales volume and price, and will assist in guiding the development of the price prediction model.
  -- Machine learning techniques: Random Forest and Gradient Boosting are two effective machine learning techniques that can be used to produce predictions based on historical data. The demand forecasting and price prediction models will be created and improved using these algorithms.</p>
<p>•	Details about Data Collection methods with Justification:
  -- Historical sales information: The demand forecasting and pricing prediction models will be built using historical sales information from the optical store. This data will provide details on past product sales, pricing, and volumetric sales to forecast future demand.
  -- External market data such as weather information and economic indicators will be gathered to support the demand forecasting model. These data points can be used to determine the connections between outside variables and product demand at the optical store.</p>
<p>•	Details about the analysis tools with Justification:  
  -- Visualization tools: Tools for visualising data will be used to identify patterns and trends in the data, which will help create models for predicting demand and prices.
  -- Machine Learning Libraries: Scikit-learn and TensorFlow are two well-known machine learning libraries offering various tools and methods for creating and evaluating predictive models. The price prediction and demand forecasting models will be implemented using these libraries.
  -- Evaluation Metrics: Mean absolute error and root mean squared error are two metrics frequently used to gauge how well predictive models work. The accuracy of the demand forecasting and price prediction models will be evaluated using these measures, which will also aid in their optimization.</p>
</p>

<h4>Metadata</h4> 
<p>is the data about the data collected from the optical shop.
Metadata of the daily sales data of shop “Opticals” is -
<ul>
<li>Date: The date on which the sales were recorded</li>
<li>Brand: The brand name of the frame or lens, or solution sold.</li>
<li>Type: The type of frame, lens, or solution sold. If nothing is specified, Regular.</li>
<li>Shape: The shape of the frame or lens sold. If nothing is specified, Regular</li>
<li>Quantity: The quantity of the product sold.</li>
<li>Price: The selling price of the product sold.</li>
<li>Total: The total money earned from selling the product.</li></ul>
The metadata of the Brands data is -
<ul>
<li>Brand Name: The name of the brand of frame or glass or lens or solution</li>
<li>Quantity: Number of pieces bought</li>
<li>Total Price: Total price at which the quantity of brand was brought</li>
<li>Average Price: Total Price divided by Quantity</li></p>
</ul>

<h4>Detailed Analysis </h4>
<p>Individual products had some trend over the month during different weeks; this has been
aggregated to plot and visualize the trends. Next, we need to perform demand forecasting.
Demand forecasting is a crucial tool in contemporary businesses to predict future demand for a good or service. The supply chain, inventory control, and production planning are significantly impacted by how accurately demand forecasts are made. Two popular
time-series forecasting techniques that can assist companies in predicting demand for a
good or service are ARIMA and Exponential Smoothing. We will describe the ARIMA and
Exponential Smoothing methods in this report and how they were applied to predict
demand for a given month’s worth of data. The information used in this report pertains to
each brand, product category, and product shape for January.<br>
Given that we have the data for only a single month of January 2023, it is impossible to calculate
the overall each-day demand for the next month. The data of 30 days is insufficient for any
models like Exponential smoothing to generate a whole of next month. Rather, it can produce
an average estimate of demand for the month. Models like ARIMA, Exponential smoothing
and Linear Regression are generally used to predict demand given the data for at least 3
months to get accurate predictions from the model. Given our single-month data, it
has been directly used to predict the next month’s average demand value.<br><br>
A well-liked time-series forecasting technique called ARIMA (AutoRegressive Integrated
Moving Average) depicts the linear relationships between the historical data and the
predicted values. The autoregressive, integrated, and moving average components of the
time series data are modelled using three parameters: p, d, and q. The mean and variance of
the time series data must remain stable over time for the data to be stationary,
which is a requirement of the ARIMA model. The data must be changed to make it stationary
if it is not already stationary. The time series data can be differentiated, which is done by
comparing two sequential observations to accomplish this. But, as the data is only
for a month, we have used a model of order (1,1,1) in predictions.<br><br>
Method of Exponential Smoothing: Using weighted averages, exponential smoothing is a
well-liked time-series forecasting technique that depicts the connections between historical
data and predicted values. It is an easy and reliable technique for predicting time-series data
that exhibit seasonality or a pattern. The data must be smoothed using different weights for
each observation to use the exponential smoothing technique. Recent observations
are given more weight than older ones because the weights allocated to each observation
diminish exponentially over time. Using this strategy, the model can adjust to
variations in the trend or seasonality of the time series data.
We can use historical data to teach the exponential smoothing model to predict future
demand. Utilizing ARIMA and exponential smoothing to forecast demand, We must first
preprocess the data from January to predict the typical demand for each
brand, type, and product shape for the following month. This entails cleaning the
data, removing any outliers, and, if required, transforming the data to make it stationary.
After preprocessing the data, we can forecast the demand for each product group using the
ARIMA and Exponential Smoothing Methods. <br>
As we have little data about quantities, we have calculated the average total sales for
the next month, given the sales of each day of a product, type, and shape for the current month.
We used Python's 'stats models' library to fit the ARIMA model to the preprocessed
data. We used the 'stats models' library to fit the exponential smoothing model to the
preprocessed data. We selected the appropriate smoothing level and trend based on the
results of the auto-correlation and partial auto-correlation plots. MAPE and RMSE
metrics are generally used to evaluate the model’s performance. Due to the lack of data availability, we
have not used these metrics.
The recurring code used was:
  ![image](https://github.com/VIROOPAKSHC/Opticals_Data_Analysis/assets/69083163/be0b50d1-1d99-4198-aced-245ccbff7c2a)

<br><br>
The trend for each day, week, fortnight, brand, and other trends have been captured using several graphs throughout the analysis in the ipynb file. See the file for graphs plotted using Matplotlib and Pandas. 
</p>
<h4>Interpretation of Results and Recommendation</h4> <p>
The availability of less data caused a bit of problematic occurrence in the
predictions for the future. Given that we have the trends weekly, monthly, daily and other
progressive decompositions for the current month, the model with input for the prediction of
a single month’s data only produces similar results for the upcoming month because the
data could not be deemed time series data. But, with some accuracy, we can give the
predicted total sales values to be an average prediction for the upcoming month because the
variation is observed for the given month and assuming seasonal factors do not affect the
optical shop sales, we can say that the current predictions from the ARIMA and exponential
smoothing can be told as good and valuable predictions for the coming month. The exponential smoothing predictions also seem to fall nearly around the current month’s average
total sales of a particular product, type or shape. So, it can be deemed that we can predict the future value as the average of the current value for less data. On the
other hand, ARIMA seems to show a difference from the month's average. So, the predictions
from both the models can be minimum and maximum total average sales for the coming
month. 
</p>
