# Travelog 

## Jerry Bonnell

### 4/26/20 (5 hours)

* Set up a Twitter developer account
* Reviewed the following books/tutorials on mining Twitter data: 
    - The Programming Historian's [Beginner's Guide to Twitter Data](https://programminghistorian.org/en/lessons/beginners-guide-to-twitter-data)
    - Marco Bonzanini's [Mining Twitter Data with Python](https://marcobonzanini.com/2015/03/02/mining-twitter-data-with-python-part-1/)  
    - [Mining the Social Web](https://www.amazon.com/Mining-Social-Web-Facebook-Instagram-ebook/dp/B07L46FZ8Y/ref=sr_1_1?dchild=1&keywords=o+reiley+mining+the+social+web&qid=1588566463&sr=8-1) by Matthew A. Russell and Mikhail Klassen (Chapters 1 and 9)
    - Last two resources are nice for CS folks :-)

### 5/3/20 (4 hours)

* I am exploring the [Covid-19-TweetIDs](https://github.com/echen102/COVID-19-TweetIDs) dataset by Chen & Ferrara. 
    - Hydrating the Tweets is straightforward using Twarc and the Python script they have provided. 
    - However, there is a large volume of data in this dataset and they estimated approx. 25 hours to hydrate it all and *zipped* data size of 6.9GB. Definitely need to organize the data better for our research. See the TODO's for more on this. 
    - for some quick exploration, I focused on just one ID file, which corresponds to tweets collected during an hour on a given day.  
* Based on discussion from the [4/29](https://github.com/dh-miami/narratives_covid19/blob/master/travelogs/Minutes-04-29-2020.md) meeting, a preliminary task is to assess sentiment regarding Covid-19 with respect to different locations. 
    - Implemented the semantic orientation (unsupervised approach) defined in Bonzanini's tutorial. 
     
__TODO__ Evaluate the sentiment of select words, and apply on a dataset filtered for locations appropriate for our study.   

__TODO__ Working with Twitter data locally is infeasible. Will the database being built hold Twitter data from all the external datasets? What is the status of this database? Is this a component of my work?

__TODO__ Is there a server available that we can use to play around with the data? 

__TODO__ Need to refine further what kinds of computational studies will be conducted on the data.     

### 5/13/20 (2 hours)

* Successfully logged into Susanna's server and installed Python package manager `pip3`, 
and packages like `jupyter notebook`, `pandas`, `scikit-learn`, which we might need.
* Set up jupyter notebook so that we can run a jupyter notebook from the server, and open 
the notebook up in a browser on your local computer 
  - I make use of ssh tunneling to accomplish this. Can write a tutorial later.
  - I think this set-up is perfect for research purposes, but we may want an actual url
    that a user can follow to visit the notebooks.  

### 5/27/20 (8 hours)

* Begin work on frequency analysis Python tool, which interfaces directly with the database. 
This collection of scripts can be imported into a jupyter notebook later for obtaining
the top frequency lists, users, etc. 

### 5/31/20 (8 hours)

* Finished frequency analysis Python tool (called coveet, name is WIP) 
* Wrote a jupyter notebook demonstrating a quick visualization of the NLP statistics
  using Plotly
* Wrote a README documentation to understand how to work with the tool
* Still need input regarding preprocessing of the tweet main text data

### 6/13/20 (10 hours)

* Discuss with Susanna and Jesus about working with the database endpoints
* Updated coveet tool to use the database API prepared by Jesus. For now, user functionality
  does not work anymore as the API does not currently support it. But, we have cleaner code
  and clean tweets...also no need to input any db credentials :-)
* Updated README
* Uploaded frequency analysis (words, bigram, trigram, and hashtag) results from april 24 
  to may 1 under `outputs/` directory. I present the results as a CSV where each column
  is a top word and each row is a day. We should discuss how best to present these results. 
* quick note on bigram/trigrams: I treat the whole tweet as context for a word, rather than
  its immediate neighbors. This could bring up some interesting analyses. 

### 6/21/20 (5 hours)

* Discuss with Susanna about visualizing twitter data 
* Wrote new jupyter notebook (`top_ngrams.ipynb`) in `freq_analysis/` folder
  for visualizing top n-grams/hashtags per geographic area together, over a
  range of dates, e.g. a week.

### 6/26/20 (4 hours)

* Team meeting 
* Updated jupyter notebooks and coveet script to incorporate stopwords
* Fixed SettingWithCopy error in jupyter notebook  
* Jupyter notebook `top_ngrams` can now do top hashtags 
* Improvements to jupyter notebook `freq_viz_race`
* Updated readme 

### 6/29/20 (3 hours) 

* Some coveet code housekeeping
* Updated coveet and jupyter notebooks with unique word function; interesting to 
  note that most of these "unique" words turn out to be typos, also fl-es is 
  mainly advertisements 
* Update readme    

### 7/17/20 (12 hours)

* concordance views added to jupyter notebook 
* jupyter notebook updates for workshop preparation and after based on comments
* looked into jupyter solutions in the cloud: binder, binderhub, jupyterhub, etc..
* workshop preparation 
* update `count_ngrams()` to include a mode that retrieves n-grams according to
  formal definition 
* Update readme  

### 7/27/20 (4 hours)

* Added stopword directory 
* Added stopwords for hashtag functionality to coveet 
* Added a unique words by date function based on discussions with Dieyun
* __TODO__ planning to add a lemmatizer function to coveet

### 8/8/20 (16 hours) 

* Nidia's workshop
* Edits on the LASA proposal 
* Added a fast lemmatization mode to coveet using an UDPipe implementation
  in R; first tried an implementation with stanza, was too slow and eventually
  crashed for a full of week of tweets, then tried to parallelize the 
  work but still unsatisfied with the > 8 hours to accomplish the task, 
  also received feedback from Deiyun that installation is very difficult;
  with UDPipe, a full week of tweets can be lemmatized in ~45 minutes 
  (thanks R :-)    

### 8/15/20 (16 hours)

* Marlas journal article  
* Helped troubleshoot bugs in SoFlo jupyter notebook and edit for clarity 
* Added options to coveet for a corpus-wide search; need to discuss 
  - idea is to create a CSV that contains all tweet data in corpus 
    and then run a function periodically (could be done automatically 
    by server) to update the CSV with new tweets; also keep track of 
    a unique id for tweets (not the same one Twitter uses, just for us)
  - build a secondary table that maps search words to these unique id's
* Minor adjustments in `top_ngrams.ipynb` notebook for better clarity 

## total hours: 97

