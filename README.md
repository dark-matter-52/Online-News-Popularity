# Online-News-Popularity
# About
The main objective of this project was to crawl news and information websites and then anticipate the probability of them getting popular. For this purpose, pretrained Random Forest Regression Model was used. The dataset used for this purpose was taken from the UCI repository. It contains 61 attributes (58 predictive attributes, 2 non-predictive, 1 goal field). They are as follows:-

url: URL of the article (non-predictive)
timedelta: Days between the article publication and the dataset acquisition (non-predictive)
n_tokens_title: Number of words in the title
n_tokens_content: Number of words in the content
n_unique_tokens: Rate of unique words in the content
n_non_stop_words: Rate of non-stop words in the content
n_non_stop_unique_tokens: Rate of unique non-stop words in the content
num_hrefs: Number of links
num_self_hrefs: Number of links to other articles published by Mashable
num_imgs: Number of images
num_videos: Number of videos
average_token_length: Average length of the words in the content
num_keywords: Number of keywords in the metadata
data_channel_is_lifestyle: Is data channel 'Lifestyle'?
data_channel_is_entertainment: Is data channel 'Entertainment'?
data_channel_is_bus: Is data channel 'Business'?
data_channel_is_socmed: Is data channel 'Social Media'?
data_channel_is_tech: Is data channel 'Tech'?
data_channel_is_world: Is data channel 'World'?
kw_min_min: Worst keyword (min. shares)
kw_max_min: Worst keyword (max. shares)
kw_avg_min: Worst keyword (avg. shares)
kw_min_max: Best keyword (min. shares)
kw_max_max: Best keyword (max. shares)
kw_avg_max: Best keyword (avg. shares)
kw_min_avg: Avg. keyword (min. shares)
kw_max_avg: Avg. keyword (max. shares)
kw_avg_avg: Avg. keyword (avg. shares)
self_reference_min_shares: Min. shares of referenced articles in Mashable
self_reference_max_shares: Max. shares of referenced articles in Mashable
self_reference_avg_sharess: Avg. shares of referenced articles in Mashable
weekday_is_monday: Was the article published on a Monday?
weekday_is_tuesday: Was the article published on a Tuesday?
weekday_is_wednesday: Was the article published on a Wednesday?
weekday_is_thursday: Was the article published on a Thursday?
weekday_is_friday: Was the article published on a Friday?
weekday_is_saturday: Was the article published on a Saturday?
weekday_is_sunday: Was the article published on a Sunday?
is_weekend: Was the article published on the weekend?
LDA_00: Closeness to LDA topic 0
LDA_01: Closeness to LDA topic 1
LDA_02: Closeness to LDA topic 2
LDA_03: Closeness to LDA topic 3
LDA_04: Closeness to LDA topic 4
global_subjectivity: Text subjectivity
global_sentiment_polarity: Text sentiment polarity
global_rate_positive_words: Rate of positive words in the content
global_rate_negative_words: Rate of negative words in the content
rate_positive_words: Rate of positive words among non-neutral tokens
rate_negative_words: Rate of negative words among non-neutral tokens
avg_positive_polarity: Avg. polarity of positive words
min_positive_polarity: Min. polarity of positive words
max_positive_polarity: Max. polarity of positive words
avg_negative_polarity: Avg. polarity of negative words
min_negative_polarity: Min. polarity of negative words
max_negative_polarity: Max. polarity of negative words
title_subjectivity: Title subjectivity
title_sentiment_polarity: Title polarity
abs_title_subjectivity: Absolute subjectivity level
abs_title_sentiment_polarity: Absolute polarity level
shares: Number of shares (target)
To fit our data into this model, we will have to calculate all the above mentioned attributes related to our data. Detail of those calculations is discussed in the code.

# What is Latent Dirichlet allocation(LDA)
For the calulation of attributes like "LDA_00", "LDA_01", "LDA_02", "LDA_03", "LDA_04", we will have to make a LDA model. In natural language processing, the latent Dirichlet allocation (LDA) is a generative statistical model that allows sets of observations to be explained by unobserved groups that explain why some parts of the data are similar. For example, if observations are words collected into documents, it posits that each document is a mixture of a small number of topics and that each word's presence is attributable to one of the document's topics. LDA is an example of a topic model and belongs to the machine learning toolbox and in wider sense to the artificial intelligence toolbox. The LDA algorithm is applied in order to first identify the five top relevant topics and then measures the closeness of each articles to such topics.

# What are non-neutral tokens
Non-neutral tokens are those tokens which are more likely to exhibit the following POS Tags: Nouns, Adjectives, Adverbs, Interjections. In corpus linguistics, part-of-speech tagging (POS tagging or PoS tagging or POST), also called grammatical tagging or word-category disambiguation, is the process of marking up a word in a text as corresponding to a particular part of speech, based on both its definition and its context—i.e., its relationship with adjacent and related words in a phrase, sentence, or paragraph. A simplified form of this is commonly taught to school-age children, in the identification of words as nouns, verbs, adjectives, adverbs, etc.

To know all the possible POS tags in NLTK visit following:

https://stackoverflow.com/questions/15388831/what-are-all-possible-pos-tags-of-nltk/38264311#38264311
