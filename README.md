# INSTAGRAM REACH ANALYSIS AND PREDICTION TOOL ON TECHNOLOGY USING MACHINE LEARNING AND DEEP LEARNING TECHNIQUES


PROJECT OVERVIEW

The Instagram Engagement Analysis and Prediction Tool is an advanced Python - based project designed to collect, analyze and predict Instagram engagement metrics using state - of - the - art techniques. This project automates the collection of Instagram data via Selenium, explores insights using Exploratory Data Analysis (EDA) and leverages both Machine Learning (ML) and Deep Learning (DL) models for predicting likes on posts based on hashtags and other features.

With a comprehensive dataset of 200 Instagram posts, this project provides a robust platform for social media managers, influencers and analysts to understand trends, optimize content strategies and predict user engagement.


KEY OBJECTIVES

1. Profile Analysis: 
Retrieve essential data from any public Instagram profile, including follower count, following count and the total number of posts.

# 2. Post Data Collection: 
Automatically collect data from the latest 200 posts, including:
   * Post URL
   * Number of Likes
   * Number of Comments (if visible on the main page)
   * Hashtags used in the caption
   * Date and Timestamp of each post

# 3. Data Export: 
Store the scraped data in a structured JSON format, enabling easy further analysis and insights extraction.


# REQUIREMENTS

To run this project, you need the following dependencies installed:
* Python 3.x
* Selenium - For browser automation
* WebDriver Manager - To automate the download of Chrome WebDriver for Selenium
* Google Chrome - Latest version, to match with WebDriver


# KEY FEATURES

# 1. Data Collection
Automated Web Scraping:
Utilizes Selenium WebDriver to log into Instagram and scrape profile details, posts, likes, comments and hashtags.

Robust Navigation:
Handles dynamic Instagram DOM elements using XPath and CSS Selectors.

Data Storage:
Saves data in structured formats such as JSON and CSV for further analysis.

Collected Metrics:
Profile - level: Follower count, following count, number of posts.
Post - level: Post URL, likes, comments, hashtags, timestamp and location.

Profile Summary Extraction: 
Gathers high-level metrics for the specified profile, such as the total number of followers, following and posts.

Post  - by - Post Data Extraction: 
Analyzes each of the latest 10 posts, capturing:
   * Post URL: Direct link to each post.
   * Engagement Metrics: Counts of likes and shares (if available).
   * Comments and Hashtags: Fetches all comments and hashtags within each post.

JSON Data Export: 
Saves the data to beebomco_data.json for persistent storage, facilitating data review and analysis.

Error Handling and Robust Navigation: 
Handles common Selenium errors like ElementNotVisibleException and TimeoutException to ensure smooth, uninterrupted scraping.


# 2. Exploratory Data Analysis (EDA)

Visualizing Engagement:
Distribution of likes and comments across posts.
Temporal patterns in engagement (daily, monthly trends).

Hashtag Analysis:
Identifies top hashtags and their contribution to post engagement.

Location Insights:
Analyzes location-wise average likes to understand audience preferences.


# 3. Machine Learning

Implements various regression algorithms to predict likes based on features:
Linear Regression.
Ridge and Lasso Regression.
Random Forest Regressor.
XGBoost Regressor.
Evaluation Metrics:
Mean Squared Error (MSE).
Mean Absolute Error (MAE).
R - Squared Score.
Results indicate the predictive performance of different models for engagement metrics.


# 4. Deep Learning

# Bidirectional LSTM for Hashtag-Based Predictions:
Tokenizes hashtags and creates embeddings for training.
Leverages sequential information in hashtags for predicting likes.

# Model Architecture:
Embedding Layer: Converts hashtags into dense vector representations.
Bi - LSTM Layer: Captures contextual and sequential dependencies.
Fully Connected Layers: Outputs predicted likes as a regression problem.
Training and Optimization:
Early stopping to prevent overfitting.
Dynamic learning rate scheduling.

# 5. Visualizations

Bar Plot: Top 10 videos by views.
Box Plot: Likes distribution based on hashtags.
Line Chart: Monthly engagement trends.
Pie Chart: Top hashtags by frequency.

			
# 6. Dynamic Hashtag Prediction

Accepts user - defined hashtags to predict likes using the trained deep learning model.
Enables real - time predictions for new hashtag strategies.


# PROJECT FILE DESCRIPTION

# Project Files			                  File Description
Web_Scraper.py			                  Script for scraping Instagram data using Selenium.
instagram_profile_beebomco.json	      JSON file containing the scraped Instagram data for analysis.
Tech_Instagram_Analysis.ipynb	        Jupyter Notebook for EDA, ML / DL training and visualizations.
requirements.txt		                  List of dependencies required for the project.
README.md			                        This comprehensive project documentation.


# INSTALLATION
# 1. Clone the Repository:

git clone https://github.com/yourusername/instagram-engagement-tool.git

cd instagram-engagement-tool


# 2. Install Dependencies

Install required libraries via pip:

pip install -r requirements.txt


# 3. Set Up WebDriver

Ensure the Google Chrome browser is installed and WebDriverManager is configured.


# USAGE

# Step 1: Data Collection using Instagram Scraping with Selenium

# 1. Setting Up Login Credentials
For Instagram authentication, update the Web Scraper.py file with your Instagram username and password:
username = "your_username"
password = "your_password"
Note: Use caution with storing sensitive information and avoid sharing it publicly.

# 2. Running the Script
Execute the main script to start the scraping process:
python Web Scraper.py
This script will:
1. Automatically log into Instagram using your provided credentials.
2. Navigate to the target Instagram profile (e.g., beebomco).
3. Scroll to the most recent posts and retrieve details from the latest 200 posts.

# 3. Output
The data is saved in beebomco_data.json, with each post containing:
* Post ID: Unique identifier for the post.
* Post URL: Direct URL to the Instagram post.
* Likes Count: Number of likes.
* Comments Count: Number of comments.
* Post Caption: Text description of the post.
* Hashtags: List of hashtags used.
* Timestamp: Date and time of the post.
* Comments: Detailed list of comments with usernames.

# Example Output (JSON Structure)
Below is a sample format for the output JSON file:
{
    "profile": {
        "username": “beebomco",
        "num_followers": 1000000,
        "num_following": 500,
        "num_posts": 200
    },
    "posts": {
        "post_1": {
            "post_id": "123456789",
            "post_url": "https://www.instagram.com/p/xyz/",
            "likes": 10000,
            "comments": [
                {
                    "username": "commenter1",
                    "comment": "Great post!"
                },
                {
                    "username": "commenter2",
                    "comment": "Very informative."
                }
            ],
            "caption": "Exploring the latest in tech. #technology #gadgets",
            "hashtags": ["#technology", "#gadgets"],
            "timestamp": "2023-04-15T12:34:56"
        },
        ...
    }
}

# Step 2: Data Analysis

Open the Jupyter Notebook (Tech_Instagram_Analysis.ipynb) to perform:
Visualization of likes, comments and hashtags.
Analysis of engagement patterns across time and locations.


# Step 3: Model Training
# Machine Learning:

Train models to predict likes based on post features.

from sklearn.linear_model import Ridge

model = Ridge().fit(X_train, y_train)


# Deep Learning:

Train Bi - LSTM for hashtag-based predictions.

from keras.models import Sequential

model.fit(X_train, y_train, epochs = 50, validation_split = 0.1)


# Step 4: Predictions

Dynamic Hashtag Input:

predict_likes("#technology")  # Predict likes for the hashtag


# RESULTS AND VISUALIZATIONS
  
# 1. Key Insights
# Temporal Trends:
Engagement is highest on weekends and during specific times of the day.

# Hashtag Analysis:
Certain hashtags consistently outperform others in driving likes.

# Location Analysis:
Posts tagged with "Beebom" locations had the highest average likes.


# 2. Visual Outputs

Bar Plot: Top 10 videos by views.
Pie Chart: Most frequently used hashtags.
Line Plot: Monthly engagement trends.
Scatter Plot: Actual vs. Predicted Likes.

		
# 3. Model Performance

# Machine Learning Models:
      Model			      MAE		         R²
Ridge Regression	76464914.23	  6786.53	0.37
Random Forest		  88460152.91	  6909.44	0.27

# Deep Learning:
Metric		      Value
Test Loss (MSE)	623569.32
Test MAE	      550.29


# KNOWN LIMITATIONS

# Web Scraping Challenges:
Instagram's DOM structure changes frequently, requiring script updates.
Automated scraping may trigger Instagram's rate - limiting mechanisms.

# Limited Feature Set:
Additional features like user demographics and caption sentiment could improve predictions.


# FUTURE ENHANCEMENTS
# Web App Deployment:
Convert the tool into an interactive web application for broader usability.

# Expanded Analysis:
Incorporate more features like post format (image, video) and caption analysis.

# Advanced Visualizations:
Interactive dashboards for real - time engagement monitoring.


# DEPLOYMENT

You can deploy this project on any platform that supports Python and Selenium. For best results:
1. Ensure the latest version of Chrome and WebDriver are installed.
2. Configure credentials securely in the environment.
Tip: For frequent scraping, consider rotating IPs or adding delays to prevent rate - limiting by Instagram.


# CONTRIBUTIONS

We welcome contributions to improve this project. Open issues or submit pull requests on GitHub.


# LICENSE

This project is licensed under the MIT License. See the LICENSE file for details.
