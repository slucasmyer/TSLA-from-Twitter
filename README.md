# TSLA-from-Twitter
Determining whether tweet volume and sentiment can improve our ability to forecast Tesla stock price

## Project Goal:
   #### Investigate whether the incorporation of sentiment and volume of tweets can aid our ability to predict the stock price of a company 1 minute hence.
## Process:
   #### Gathered tweets from the Twitter Developer Labs 'RecentSearch' endpoint using the search query "$TSLA"
   #### Pulled minutely aggregated TSLA price series from AlphaVantage Intraday API
   #### Clean, explore, and process our data, feature engineer, determine appropriate modeling techniques
   #### Contruct our baseline against which wwe'll judge our model's performance
   #### Construct and cross-validate our models, pick the best, test it on our hold-out set

##  Repo Contents
- ### alphaVantage-price-data notebook
   pull price series from alphaVantage API
   <br>
    <p align = "center">
      <img src = "/Graphs/tsla_price_data.jpg" width = 700>
    </p>
   <br>
- ### TSLA-tweets notebook
   gather tweets from Twittter Developer Labs 'Recent Search' endpoint
   <br>
    <p align = "center">
      <img src = "/Graphs/tweet_volume.png" width = 700>
    </p>
   <br>
   <br>
    <p align = "center">
      <img src = "/Graphs/compoound_sentiment.png" width = 700>
    </p>
   <br>
- ### TSLA-EDA-feature-engineering notebook
   clean and explore our data, then combine and process to prepare for modeling
- ### TSLA-EDA-feature-engineering-test-set notebook
   clean and explore our data, then combine and process to prepare for modeling
- ### baseline-models notebook
   create a baseline prediction against which to judge the outcomes of our modeling process
- ### TSLA-modeling notebook
   a range of LSTM models with varying hyper-parameters
- ### Pickle Folder
  - Prices dataframe
  - Tweets dataframe 
  - Data processed for modeling saved as a dataframe
