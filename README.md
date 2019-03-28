# Goodreads_review_analysis

- All code + full writeup in [sentiment_revs.ipynb.](https://github.com/ScottVinay/Goodreads_review_analysis/blob/master/sentiment_revs.ipynb)
- Database operations performed primarily in Pandas - SQL version given in `queries_in_sql.ipynb`.
- Data from https://www.kaggle.com/gnanesh/goodreads-book-reviews.
- <b>Final accuracy of neural network = 59% | Final accuracy of human experts = 50%.<b>

***

## Abstract


An extensive investigation, involving visualisations, analytic Bayesian statistics, and neural network design applied to sentiment analysis of often poorly-structured text. 

We have downloaded a dataset of 300,000 rows from kaggle.com. Each row represents a review of a book uploaded to Goodreads.com. Included is information on the book, the average rating of the book, the rating awarded by the specific review, the name of the reviewer, and the text of the review. We investigate this first, by creating dense visualisations, showing how each reviewer's scores deviates from the rest of her peers. In doing so, we find anomalous reviewers, which may allow for detection of fraudulent reviews.

We next analyse the statistics of the reviews awarded by each reviewer, according to an analytic Bayesian analysis. By doing so, we gain two estimates for the *entropy* of an individual's reviews, which we argue is tantamount to measuring how discerning they are as a reviewer. We show that, contrary to expectations, prolific reviewers are likely to be less discerning that their peers with fewer reviews. This may be due to prolific reviewers wishing to write many reviews for its own sake, and seeking out many very good or many very bad books. This analysis may be used to seek out particularly competent book reviewers. We then investigate how reviewers of different nationalities and genders are rated, involving information that we scrape from Wikipedia. This allows us to check for unconscious bias in the reviewing world.

Finally, we examine how the score of a review may be predicted from the text of the review. We classify reviews according to three roughly equal categories: bad (less than 4-stars), good (4-stars) and excellent (5-stars). We perform cleaning of data, optimisation of network design, and design of a custom pipeline to perform 3-class classification with a binary classifier network. The result is a network that can identify the correct category around 59% of the time. In particular, bad reviews are only mis-identified as excellent reviews around 4% of the time. This may not sound like a huge accuracy, but note two things. Firstly, we are selecting between 3 classes. And secondly, many of the reviews are very hard to categorise, even to a human reader. A selection of 50 reviews was given to keen readers, and they were asked to classify them accordingly. Their overall accuracy was exactly 50% - a result easily beaten by our network.
