![alt text](https://media-exp1.licdn.com/dms/image/C4D0BAQGLbtKq3h4rnA/company-logo_200_200/0/1550065127463?e=2159024400&v=beta&t=L-UwZzZr5SPPC-Rr9PTSpD7UgAVJ5gjb5gFiaNwaWNE) 
<h1 align="center">**Tweets Classification**</h1>

<div align="center">
  <strong>Data Mining Project</strong>
</div>
<div align="center">
  <strong>Sahar letaief 3DNI1</strong>
</div>

<br />

## Table of Contents
- [Introduction](#Introduction)
- [Get Twitter API Key](#GetTwitterAPIKey)<br>
	-[Steps](#Steps)<br>	
	-[Key fields](#Keyfields)<br>
- [Tweets Collection and Preprocessing](#TweetsCollectionandPreprocessing)<br>
	-[Tweets Collection](#TweetsCollection)<br>
	-[Tweets Preprocessing](#TweetsPreprocessing)<br>
- [Natural LanguageProcessing](#NaturalLanguageProcessing)<br>
- [Tweets Classification](#TweetsClassification)<br>



## Introduction


## Get Twitter API Key
Twitter allows third-party developers partial access to its services.<br> ![alt text](https://cdn0.iconfinder.com/data/icons/twitter-ui-flat/48/Twitter_UI-02-512.png)<br>Apps created by programmers can be integrated with Twitter by means of APIs.<br>
Twitter API is an interface through which a website or an app can interact with Twitter. It allows access to the main features of the platform.<br>
Basically, there are three levels of data access which correspond to the levels of your project’s growth: Standard, Premium and Enterprise.<br> 
	### Steps
1. Create a free Twitter user account
Head over to  [Twitter](https://twitter.com) and register for a free account.
2. Apply for a Developer Account 
Create a project and add a new app in the Twitter Developer portal. 
During this process, Twitter will generate an API Key and API Secret Key for your application.
Create new application [new Application](https://dev.twitter.com/apps/new)
3. Click on “Connect to API” and begin filling out all the required API Key fields and parameters.
	### Key fields
In order for an app to read and write Direct Messages on behalf of a user, the user must grant permission to the app to do so.<br> When a user grants permission, user tokens generated for that user are provided in API requests.<br>	
	  * consumerKey<br>
	  * consumerSecret<br>
	  * accessTokenKey<br>
	  * accessTokenSecret<br>
## Tweets Collection and Preprocessing
   ### Tweets Collection
<p>Import the Twitter library and enter the credentials as follows:</p>
<pre style="padding-top: 0;" tabindex="0"><code style="padding-top: 0;">
import twitter
api = twitter.Api(consumer_key='your_consumer_key',
  consumer_secret='your_consumer_secret',
    access_token_key='your_access_token_key',
    access_token_secret='your_access_token_secret')
</code></pre>
<p>Creating an OAuthHandler instance. Into this we pass our consumer key and secret :</p>
<pre style="padding-top: 0;" tabindex="0"><code style="padding-top: 0;">
auth = tweepy.OAuthHandler(consumer_key, consumer_secret)
auth.set_access_token(access_token, access_token_secret)
api = tweepy.API(auth,wait_on_rate_limit=True,wait_on_rate_limit_notify=True)
</code></pre>
<p>Search Method:</p>
	API.search :Returns a collection of relevant Tweets matching a specified query.
   ### Tweets Preprocessing
Since we are dealing with tweets, we need to do specific tweet text cleaning along with normal text pre-processing. 
<p>Use of tweet-preprocessor:</p>	
Preprocessor is a preprocessing library for tweet data written in Python.<br>When building Machine Learning systems based on tweet data, a preprocessing is required. 
This library makes it easy to clean, parse or tokenize the tweets.

<pre style="padding-top: 0;" tabindex="0"><code style="padding-top: 0;">
!pip install tweet-preprocessor
import preprocessor as p
</code></pre>
Basic cleaning: delete URL's,Mentions,Hashtags,Emojis,Smileys
<pre style="padding-top: 0;" tabindex="0"><code style="padding-top: 0;">
 p.clean()
</code></pre> 
<p>Use of Gensim:</p>
Gensim is an NLP Python framework a Python library for topic modelling, document indexing and similarity retrieval with large corpora. <br>
Target audience is the natural language processing (NLP), we use ir here to remove_stopwords.
<pre style="padding-top: 0;" tabindex="0"><code style="padding-top: 0;">
 pip install --upgrade gensim
from gensim.parsing.preprocessing import remove_stopwords
</code></pre>

## NLP(Natural Language Processing)
![alt text](https://canopylab.com/wp-content/uploads/2019/11/shutterstock_1455391502-2.jpg)
In natural language processing (NLP), the goal is to make computers understand the unstructured text and retrieve meaningful pieces
of information from it. <br>Natural language Processing (NLP) 
is a subfield of artificial intelligence, in which its depth involves the interactions between computers and humans. <br>
<p>Tokenization : </p> is the process of tokenizing or splitting a string, text into a list of tokens.
<p>Stemming :</p> Stemming is a kind of normalization for words,where a set of words in a sentence are converted into a sequence to shorten its lookup. <br>
The words which have the same meaning but have some variation according to the context or sentence are normalized.
<p>Lemmatization :</p> The algorithmic process of finding the lemma of a word depending on their meaning.<br>
It helps in returning the base or dictionary form of a word, which is known as the lemma using PorterStemmer().<br>
	### Lemmatization better than Stemming
Stemming algorithm works by cutting the suffix from the word. In a broader sense cuts either the beginning or end of the word.<br>
On the contrary, Lemmatization is a more powerful operation, and it takes into consideration morphological analysis of the words.
<p>WordCloud:</p> Word Cloud is a data visualization technique used for representing text data in which the size of each word indicates its frequency or importance.<br>
Significant textual data points can be highlighted using a word cloud.
