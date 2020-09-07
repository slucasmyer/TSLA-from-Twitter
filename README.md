# TSLA-from-Twitter
Determining whether tweet volume and sentiment can improve our ability to forecast Tesla stock price over and above a 1-minute lagged price series.
In other words, does the Efficient Market Theory hypothesis (that the best predictor of price at time period t+1 is the price at time t) hold true when incorporating information found on twitter?

## Project Goal:
   #### Investigate whether the incorporation of sentiment and volume of tweets can aid our ability to predict the stock price of a company 1 minute hence.
## Process:
   #### Gather tweets from the Twitter Developer Labs 'RecentSearch' endpoint using the search query "$TSLA"
   #### Pull minutely aggregated TSLA price series from AlphaVantage Intraday API
   #### Clean, explore, and process our data, feature engineer, determine appropriate modeling techniques
   #### Contruct our baseline against which wwe'll judge our model's performance
   #### Construct and cross-validate our models, pick the best, test it on our hold-out set

##  Repo Contents
- ### alphaVantage-price-data notebook
   pull price series from alphaVantage API
   <br>
    <p align = "center">
      <img src = "/Graphs/price_data_2.png" width = 700>
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
      <img src = "/Graphs/compound_sentiment.png" width = 700>
    </p>
   <br>
   
- ### TSLA-EDA-feature-engineering notebook
   clean and explore our data, then combine and process to prepare for modeling
   <br>
    <p align = "center">
      <img src = "/Graphs/tsla_price_data.jpg" width = 700>
    </p>
   <br>
   
- ### TSLA-EDA-feature-engineering-test-set notebook
   clean and explore our data, then combine and process to prepare for modeling
   
- ### baseline-models notebook
   Baseline prediction against which to judge the outcomes of our modeling process (1 minute lagged price series)
   - Baseline RMSE: .407
   - Baseline RMSE/STD: .056
   <br>
    <p align = "center">
      <img src = "/Graphs/tsla_baseline.png" width = 700>
    </p>
   <br>
- ### TSLA-modeling notebook
   Contians a range of LSTM models with varying hyper-parameters.
   Below is an image of the best model's predictions on our hold-out test set (3 trading days)
   - Validation RMSE: 1.008
   - Validation RMSE/STD: .394
   - Test RMSE: .684
   - Test RMSE/STD: .1
   - #### Configuration/Parameters:
   - 64-Dimenstional
   - Single-layer
   - 20 Epochs
   - Batch Sized of 64
   Results
   <br>
    <p align = "center">
      <img src = "/Graphs/tsla_lstm.png" width = 700>
    </p>
   <br>
- ### Pickle Folder
  - Prices dataframe
  - Tweets dataframe 
  - Data processed for modeling saved as a dataframe
  ## Conclusion
  While the investigation yielded surprisingly transferrable results, i.e. a trained model which performs better on unseen than seen data, the predictions were still a worse predictor of price at time t+1 than was the price at time t.
  This may be due to the fact that similar, yet more sophisticated methods are already in use by large financial institutions with access to a greater volume and variety of data, but nonetheless further investigation/optimization appears warranted.
