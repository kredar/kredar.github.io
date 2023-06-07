---
title: "Exploring the Capabilities of Large Language Models"
excerpt: "Using Large Language Models for Android app review analysis, covering sentiment analysis, emotion detection, summarization, and more."
categories:
  - Gen-AI
  - AI
tags:
  - NLP
  - LLM
  - AI
header:
  overlay_image: /assets/images/openai_img.jpg
  overlay_filter: 0.7 # same as adding an opacity of 0.7 to a black background
  # caption: "Photo by: [**Mariia Shalabaieva**](https://unsplash.com/it/@maria_shalabaieva?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [**Unsplash**](https://unsplash.com/photos/nYSdjVD2ayo?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)"
  teaser: /assets/images/openai_img.jpg
show_date: true
author_profile: true
classes: wide
#layout: splash
published: true
toc: true
toc_sticky: true
#toc_label: "Table of Contexts"
#toc_icon: "python"  
---

# Introduction

A couple of weeks ago, I completed a short course on prompt engineering - **"ChatGPT Prompt Engineering For Developers"** by [DeepLearning.AI](https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/). The best part is, it's available for free, but only for a limited time! 

The course provided me with valuable insights into prompt engineering techniques, which further fueled my enthusiasm for exploring the vast capabilities of Language Models. Eager to put my newfound knowledge to the test, I decided to write a script to analyze Android app reviews using the power of an LLM. 

Gone are the days of spending countless hours and extensive data to build specific ML models for sentiment analysis, emotion detection, topic extraction, and summarization. Thanks to Large Language Models, this can now be achieved with clever prompts and several API calls. It's absolutely mind-boggling 🤯!

Utilizing the techniques I learned in the course and playing with prompts,  I was able to get the sentiment, emotions, topics, summary and auto-generated response in just two API calls. Although it's possible to achieve everything in one API call, it can get too lengthy, longer than allowed number of tokens in one API call, I decided to split them into 2 API calls. 

# Prompts

The first prompt, a straightforward zero-shot learning task, requests GPT to generate the following:

1. One-Sentence Summary: A succinct summary of each review.
2. App Review Sentiment: Determination of whether reviews are positive, negative, or neutral.
3. Emotion Detection: Interpretation of the emotions conveyed in the reviews.
4. Anger and Frustration: These emotions are singled out for separate analysis.
5. Topic Extraction: Identification of the main topics discussed in the reviews.

I've requested GPT to deliver the response in JSON format for seamless integration into my dataframe. Despite the prompt's simplicity, achieving optimal results required considerable experimentation and tuning. For instance, the GPT-3.5 turbo model results were inconsist and occasionally failed to return the requested JSON format. Adding `Make sure the output is in a valid JSON format` at the end of the prompt resolved this issue. However, for production-level applications, more rigorous testing and exception handling would be necessary.

```python
"""Your task is to perform the following actions on the mobile app review delimited by triple backticks: 
1 - Summarize with 1 sentence.
2 - Determine the sentiment of the review 
3 - Identify a list of emotions in the review. Include no more than \
five items on the list. Format your answer as a list of \
lower-case words separated by commas.
4 - Identify if the writer of the app review is expressing anger.
5 - Identify if the writer of the app review is expressing frustration.
6 - Determine five topics that are being discussed in the review. \
Make each item one or two words long. Format your response as a list of items separated by commas.

Output a json object only that contains the following keys: \ 
summary, sentiment, emotions, anger as a boolean, frustration as boolean, topics.\
  Make sure the output is in a valid JSON format

Review: ```{review}```"""
```

The second prompt aims to generate responses to app reviews. To achieve more consistent results, I've employed a few-shot learning approach. In the `responses_training_prompt`, I've incorporated five actual responses from the past to guide the learning process. These five instances of app reviews and corresponding responses proved sufficient in yielding consistent and high-quality responses.

```python
prompt = f"""
You are part of a Customer Advocacy team that is responsible to respond to all customer app reviews. \
Here are some examples of reviews and responses:\
{responses_training_prompt}
Your tasks is to write a response to the mobile app review delimited by triple backticks.\
Make sure to be polite and use formal language but not too formal.\
Output a json object only that contains the following key: response. 
```name:{name} review:{review}```
Make sure output is a valid json format.
"""
```

I recommend experimenting with prompts and parameters in the OpenAI [Playground](https://platform.openai.com/playground?mode=chat) prior to implementing your Python code.

# Python Code

Let's delve into the Python code. We'll first extract Google Play app reviews using the Google Play Store scraper library, then call the OpenAI API using two prompts discussed earlier to analyze Android app reviews and auto-generate responses.

Before we proceed, ensure you've [created an OpenAI account](https://auth0.openai.com/u/signup/identifier?state=hKFo2SBsNDg0R2pEUW1Ta2U4T1hxTmt2cjJsTGNZNTdDZk5USKFur3VuaXZlcnNhbC1sb2dpbqN0aWTZIGFqVkVrR01qR3QteWlWcFphczVMSVFqZjJUMXhkaUZjo2NpZNkgRFJpdnNubTJNdTQyVDNLT3BxZHR3QjNOWXZpSFl6d0Q) and [added an API key](https://platform.openai.com/docs/quickstart/add-your-api-key) to execute the code below.

Let's start by importing the necessary libraries. 

```python
import pandas as pd
import json
import os
import openai
openai.api_key = os.getenv("OPENAI_API_KEY")     
```

Next, we'll retrieve Google App reviews. I'm [using]() the `google_play_scraper` library to fetch all reviews, but for our analysis, we'll limit ourselves to 100 reviews. You'll need the app package name, which can be found in the Google Play Store URL. For additional information, refer to the [Google-Play-Scraper documentation](https://pypi.org/project/google-play-scraper/).

```python
# First lets use the scraper to get all Google App reviews
from google_play_scraper import app,Sort, reviews_all
all_reviews = reviews_all(
    'com.wealthsimple.trade',
    sleep_milliseconds=0, # defaults to 0
    lang='en', # defaults to 'en'
    country='ca', # defaults to 'us'
    sort=Sort.NEWEST, # defaults to Sort.MOST_RELEVANT
)
df_reviews = pd.DataFrame(np.array(all_reviews),columns=['review'])
df_reviews = df_reviews.join(pd.DataFrame(df_reviews.pop('review').tolist()))
df_reviews['at'] = df_reviews['at'].astype(str)
df_reviews.head()
# let's take last 100 app reviews with rating below 4 stars
last_100_reviews_df=df_reviews[df_reviews['score']<4][0:100]
```

Then we are going to add new columns to our data frame:

```python
# I want to detect the following using openai api
last_100_reviews_df['summary']=''
last_100_reviews_df['sentiment']=''
last_100_reviews_df['emotions']=''
last_100_reviews_df['anger']=''
last_100_reviews_df['frustration']=''
last_100_reviews_df['topics']=''
last_100_reviews_df['review_response']=''
```

We'll establish a helper function to invoke the OpenAI API. I've opted for the `gpt-3.5-turbo` model, given its speed and effectiveness I thought it should be good for app review analysis. To enhance consistency and minimize randomness, I've set the `temperature` parameter to **0**.

```python
def get_completion(prompt, model="gpt-3.5-turbo"):
    messages = [{"role": "user", "content": prompt}]
    response = openai.ChatCompletion.create(
        model=model,
        messages=messages,
        temperature=0, # this is the degree of randomness of the model's output
    )
    return response.choices[0].message["content"]	
```

Next, we'll invoke the OpenAI API using the first prompt. Given the rate limits imposed by the OpenAI API, it's necessary to incorporate pauses between calls.

```python
import time

for index, row in last_100_reviews_df.iterrows():
    review=row['content']
    prompt = f"""
Your task is to perform the following actions on the mobile app review delimited by triple backticks: 
1 - Summarize with 1 sentence.
2 - Determine the sentiment of the review 
3 - Identify a list of emotions in the review. Include no more than \
five items on the list. Format your answer as a list of \
lower-case words separated by commas.
4 - Identify if the writer of the app review is expressing anger.
5 - Identify if the writer of the app review is expressing frustration.
6 - Determine five topics that are being discussed in the review. \
Make each item one or two words long. Format your response as a list of items separated by commas.

Output a json object only that contains the following keys: \ 
summary, sentiment, emotions, anger as a boolean, frustration as boolean, topics.\
  Make sure the output is in a valid JSON format

Review: ```{review}```
"""
    
    response = get_completion(prompt)
    print(response)
    response_json = json.loads(response)
   
    time.sleep(2)
    last_100_reviews_df.at[index, 'summary']=response_json['summary']
    last_100_reviews_df.at[index, 'sentiment']=response_json['sentiment']
    last_100_reviews_df.at[index, 'emotions']=response_json['emotions']
    last_100_reviews_df.at[index, 'anger']=response_json['anger']
    last_100_reviews_df.at[index, 'frustration']=response_json['frustration']
    last_100_reviews_df.at[index, 'topics']=response_json['topics']
```

For the second part, we first need to get pairs of historical reviews and responses to construct the few-shot learning prompt:

```python
# Create a training data based on reviews and responses. We took 5 examples 
responses_training_prompt=''
for index, row in df_reviews[df_reviews['repliedAt'].astype(str)!='NaT'][0:5].iterrows():
    prompt=f"""name:{row['userName']} review:{row['content']} response:{row['replyContent']}"""
    responses_training_prompt+=" "+prompt

```

And here is the second call:

```python
last_100_reviews_df['review_response']=''
for index, row in last_100_reviews_df.iterrows():
    review=row['content']
    name=row['userName']
    prompt = f"""
You are part of a Customer Advocacy team that is responsible to respond to all customer app reviews. \
Here are some examples of reviews and responses:\
{responses_training_prompt}
Your task is to write a response to the mobile app review delimited by triple backticks.\
Make sure to be polite and use formal language but not too formal.\
Output a json object only that contains the following key: response. 
```name:{name} review:{review}```
Make sure the output is a valid JSON format.
"""
    response = get_completion(prompt)
    print(response)
    response_json = json.loads(response)
    last_100_reviews_df.at[index, 'review_response']=response_json['response']
```

And there you have it! In roughly a hundred lines of code, we've managed to determine sentiment, identify emotions, extract topics, summarize reviews, and generate plausible responses.

# Findings and Conclusion

Key takeaways from my exploration with LLMs: they're akin to magic wands for NLP tasks, but they're not without their quirks.

1. Crafting the right prompt is crucial. It's no wonder Prompt Engineering is emerging as a profession. Despite completing the [Deeplearning.AI course](https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/), I had to experiment extensively with the phrasing to get desired outcomes. Resources like [PromptingGuide](https://www.promptingguide.ai/) proved beneficial. It's about trial and error with various prompt styles and language nuances.
2. The performance was commendable. If I were manually summarizing or extracting sentiment, the results would likely be comparable.
3. The GPT-3.5 Turbo model I used was somewhat slow. It's adequate for offline analysis but may lag for real-time applications. I intend to explore cheaper and faster GPT-3 models, specifically Ada.
4. Topic extraction was a mixed bag. While it worked decently for app reviews, it was hard to identify patterns in issues. The inconsistency in topic names and extraction of obvious or irrelevant topics were notable drawbacks. I plan to refine this process using varied prompts and post-processing techniques. More updates to follow.
5. I've considered comparing the cost of using OpenAI models for all these tasks against specialized ML models for specific tasks, but that's a discussion for another day.

LLMs excel in many generic NLP tasks. My next objective is to fine-tune a model and put it to the test. Stay tuned!