<H3>ENTER YOUR NAME: S JAIGANESH</H3>
<H3>ENTER YOUR REGISTER NO: 212222240037</H3>
<H3>DATE: 28-04-2024</H3>
<H1 Align="center">Project Based Experiment<H1>

## Objective:
To perform sentiment analysis on Facebook data and filter for messages, comments, or posts with negative feedback.

## Program:
  
  ```py
import pandas as pd
import nltk
from nltk.sentiment.vader import SentimentIntensityAnalyzer

# Download VADER lexicon
nltk.downloader.download('vader_lexicon')

# Load Facebook posts from Excel file
file = "FacebookPosts.xlsx"
xl = pd.ExcelFile(file)
dfs = xl.parse(xl.sheet_names[0])
facebook_posts = list(dfs['Timeline'])

# Initialize NLTK's sentiment analyzer
sid = SentimentIntensityAnalyzer()

# Perform sentiment analysis on each post
for data in facebook_posts:
    print("Post:", data)
    # Get sentiment scores
    ss = sid.polarity_scores(data)
    # Print sentiment scores
    for k in ss:
        print(k, ":", ss[k])
    # Determine sentiment based on the compound score
    if ss['compound'] >= 0.05:
        print("Sentiment: Positive")
    elif ss['compound'] <= -0.05:
        print("Sentiment: Negative")
    else:
        print("Sentiment: Neutral")
    print()


 ```

## OUTPUT:
![image](https://github.com/Karthikeyan21001828/Project-Based-Experiment-AAI/assets/93427303/0a5fdbe4-a282-4826-b0ee-cef3b28e85fc)

![image](https://github.com/Karthikeyan21001828/Project-Based-Experiment-AAI/assets/93427303/412790bb-3d44-400a-afaa-4447a2225a4f)

![image](https://github.com/Karthikeyan21001828/Project-Based-Experiment-AAI/assets/93427303/30ad4738-81e0-47f6-b046-19fe59ff9793)



<H3>RESULT:</H3>
 A sentiment analysis project using Facebook data provides valuable learning experiences in data handling, text processing, sentiment analysis, and ethical considerations, while also honing communication, problem-solving, and project management skills.
