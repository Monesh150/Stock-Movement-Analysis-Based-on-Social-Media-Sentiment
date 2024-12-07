# Stock Movement Prediction Based on Social Media Sentiment

This project predicts stock price movements based on sentiment extracted from social media discussions, specifically Reddit posts. The sentiment is analyzed from posts in the *IndianStockMarket* subreddit, and predictions are made using a Random Forest model based on sentiment, stock price data, and other relevant features.

## Project Overview

This project uses social media sentiment analysis to predict stock market trends. The model analyzes Reddit discussions about major Indian stocks, processes sentiment data using **TextBlob**, and uses historical stock prices from **Yahoo Finance** to predict stock price movements. The machine learning model is trained to predict stock prices based on various features, including sentiment scores and stock prices.

## Dependencies

To run this project, you'll need the following Python packages:

- `praw`: For scraping Reddit data.
- `yfinance`: For fetching historical stock prices.
- `pandas`: For data manipulation.
- `scikit-learn`: For machine learning model and evaluation.
- `textblob`: For sentiment analysis.
- `matplotlib`: For plotting visualizations.

You can install these dependencies by running the following command:

```bash
pip install praw yfinance pandas scikit-learn textblob matplotlib
```
## Setup

### Clone the repository:<br>
First, clone the repository to your local machine:
```bash
git clone https://github.com/yourusername/Stock-Movement-Sentiment-Prediction.git
```
### Obtain Reddit API Credentials:<br>
To access Reddit's API, you need to create an application on Reddit's Developer Portal.
Once you create the app, get the **Client ID, Client Secret,** and **User Agent**.
Replace the credentials in the scraper.py file with your own credentials:
```
reddit = praw.Reddit(
    client_id="YOUR_CLIENT_ID",
    client_secret="YOUR_CLIENT_SECRET",
    user_agent="YOUR_USER_AGENT"
)
```
### Download Stock Price Data: <br>
The stock price data is fetched using the **yfinance** package. Make sure you have an internet connection to download this data.


## How to Run the Code
### 1. Run the Scraper <br>
The scraper fetches posts related to Indian stocks from the Reddit IndianStockMarket subreddit. It also performs sentiment analysis on the post titles and stores the data.
Run the following command to fetch the data:
```bash
python scraper.py
```
This will fetch the latest posts related to Indian stocks and save them into a CSV file (reddit_posts_2024.csv).

### 2. Train the Model
After gathering the data, run the following command to train the prediction model:
```bash
python model.py
```
### This will:
i. Merge the sentiment data with stock price data.<br>
ii. Train a **Random Forest model** to predict stock prices based on the sentiment and stock features.<br>
iii. Evaluate the model's performance and display the results in the console.<br>


### 3. Model Evaluation
Once the model is trained, the program will display the following evaluation metrics in the console: <br>
Mean Absolute Error (MAE)<br>
Root Mean Squared Error (RMSE)<br>
R-Squared (R²)<br>


## Outputs
### [reddit_posts_2024.csv](./reddit_posts_2024.csv): 
Contains the scraped Reddit posts and their sentiment scores. <br>
### Model evaluation metrics: 
#### Mean Absolute Error (MAE): 
139.94443780573795<br>
#### Mean Squared Error (MSE): 
96152.41339109543<br>
#### Root Mean Squared Error (RMSE): 
310.0845262038972<br>
#### R-squared (R2): 
0.9940260805602048<br>
### [Predicted stock prices](./predicted_closing_prices_2024): 
The model will output the predicted stock prices for the test dataset.

