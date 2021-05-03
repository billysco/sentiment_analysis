# Sentiment Analyzer

The recent incident of Wall Street/ bet has once again proved that public sentiments play a significant role in driving the market.  One of the biggest example companies like AMC and Gamestop, who were almost on the verge of bankruptcy were turned into multi-millionaire overnight just because few investors crazily pumped money into these stocks. This is how we conceived the idea for our startup. Our start-up provide the integrated platform, which combine the real time public sentiment from websites like Reddit and stock prices from like Alpaca and then feeding that data to ML machine learning mode to quantify public sentiments in order to know which are profitable stocks. The second part of this project is to connect it to trading platform to auto-trigger trades based upon user's settings. This provide users better insight to the stocks and deeper analysis of public sentiments.

![](snapshots/intro.PNG)

## Approach
The project takes raw comments from the site Reddit, stock prices from Alpaca and second part is to connect it to trading platform like Robinhood to auto trade. Since the data was so huge from Reddit, so we took only those comments which has a score greater then 200, which condensed our data to more better quality.

## Technologies

This project leverages python 3.7 with the following packages:

* [Pandas](https://pandas.pydata.org/) - For data cleaning, preparation and manipulation

* [Jupyter Notebook](https://jupyter.org/) - An open-source web application that allows you to create and share documents that contain live code, equations, visualizations and narrative text.

* [Visual Studio Code](https://code.visualstudio.com/) - A code editor redefined and optimized for building and debugging modern web and cloud applications

* [Pyviz](https://pyviz.org/) - Python visualization package that provides a single platform for accessing multiple visualization libraries. Two of these libraries are Plotly Express and hvPlot, which were used in this project

* [Flask](https://flask.palletsprojects.com/en/1.1.x/) - A Python library which allows you to build a web application


---

## Installation Guide

Download Anaconda for your operating system and the latest Python version, run the installer, and follow the steps.

Before running the application first install the following dependencies.

```python
  pip install fire
  pip install questionary
  pip install pytest
  pip install pandas
  pip install numpy
  pip install flask
  pip install hvplot
```

To install PyViz and its dependencies in your Conda dev environment, complete the following steps:

1. From your terminal, log in to your Conda dev environment.

2. Install the PyViz packages by using the conda install command as follows:
    
	conda install -c plotly plotly=4.13.
    
    conda install -c pyviz hvplot
-----------------------------------------------------------------------------------------------------------------------------------------------------

## Usage

The reddit comments are pulled through API. The stock prices are pulled from Alpaca. We used multiple machine learning model on this data. The two main ML models we used was - (1) Valdmir - this is the model which is used for text sentiment analysis that is sensitive to both polarity (positive/ negative) and intensity strength of emotion. It is in the NLTP package and can directly be applied to the unlabelled data. This library relies on the dictionary that maps lexical features to emotion intensities known as sentiment score. (2) Text blot - In this library sentiments are defined based on the frequency of each word in an input sentence that allows getting a more precise output as a result. The result we got was in the form polarity on the scale of -1 to 1 and subjectivity on the scale of 0 to 1.

Following snapshot shows the final dataframe after pulling data from both data sources and results got from two different ML model.

![](snapshots/dataframe_headline.PNG)
![](snapshots/dataframe_content.PNG)

--------------------------------------------------------------------------------------------------------------------------------------------

The correlation metrics of ML results were interesting. Following were the findings (1) The result accuracy increased significantly with the increase in the score of comments. In-fact, the weigtage of positive comments increased with more scores of public comments. (2) If there was a sudden percentage change in the stock 'close' price then weigtage of negative comments was more (3) The ML results from two different libraries have a strong  positive correlation.

![](snapshots/correlation.PNG)

--------------------------------------------------------------------------------------------------------------------------------------------

Following is the snapshot of the graph plotted between the results of two ML model.

![](snapshots/cross_results.PNG)

--------------------------------------------------------------------------------------------------------------------------------------------

Following graph shows the variation in the polarity across stocks.

![](snapshots/snapshots.PNG)

![](snapshots/polarity_variation.PNG)

--------------------------------------------------------------------------------------------------------------------------------------------

This is the heat map which tell better the score higher the positive sentiments % we got.

![](snapshots/score.PNG)

--------------------------------------------------------------------------------------------------------------------------------------------

This is the trend of positive, negative and neutral sentiments trend across stocks.

![](snapshots/sentiment_trend.PNG)

--------------------------------------------------------------------------------------------------------------------------------------------

Due to the imbalanced dataset, we found more siginificant % percentage of neutral sentiments aross different industry sectors. Following snapshots would show the percentage of sentiments, we found across sectors. 

1.Example - the capital good sector % was 23%.

![](snapshots/capital_goods.PNG)

--------------------------------------------------------------------------------------------------------------------------------------------

2.The consumer service sector postive sentiment % is 23.2%

![](snapshots/customer_services.PNG)

--------------------------------------------------------------------------------------------------------------------------------------------

3.The energy sector postive sentiment % is 14.1%

![](snapshots/energy.PNG)

--------------------------------------------------------------------------------------------------------------------------------------------

4.The finance sector postive sentiment % is 22.6%

![](snapshots/finance.PNG)

--------------------------------------------------------------------------------------------------------------------------------------------

5.The finance sector postive sentiment % is 10.1%

![](snapshots/health_care.PNG)

--------------------------------------------------------------------------------------------------------------------------------------------

6.The finance sector postive sentiment % is 10.1%

![](snapshots/public_utilities.PNG)

--------------------------------------------------------------------------------------------------------------------------------------------

7.The finance sector postive sentiment % is 10.1%

![](snapshots/public_utilities.PNG)

--------------------------------------------------------------------------------------------------------------------------------------------

## Product Interface 

This is the snapshot of the professional interactive dashboard built for the users to know the sentiments for the particular stock before investing.
This shows the list of top trend in the market as per the recent data.

![](snapshots/public_sentiments.PNG)

--------------------------------------------------------------------------------------------------------------------------------------------

1. This is the snapshot of another user interface to knOw the sentiments for the particular stock before investing. 

![](snapshots/for_which_stock.PNG)

--------------------------------------------------------------------------------------------------------------------------------------------

2. This snapshot shows the list of stocks which lie in the particular the range of sentiments.

![](snapshots/range_of_Sentiments.PNG)

--------------------------------------------------------------------------------------------------------------------------------------------



## Contributors

Brought to you by Aruna, Billy, Aye
