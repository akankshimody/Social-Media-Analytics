## Identifying top social influencers 

The learning objectives for this assignment were to learn ways to<br>
(i) Detect social “influencers” using network analytics<br>
(ii) Quantify the financial value of influence<br>
(iii) Identify and leverage influencers<br><br>
**Part 1:**<br>
We use [training data](https://github.com/akankshimody/Social-Media-Analytics/blob/master/Assignment%201%20-%20Identify%20Social%20Influence/train.csv) on social influence to build a model predicting influencers, to find out the important predictors of influence, and to quantify the financial value of influence. <br>
**Part2:**<br>
We collect [tweets](https://github.com/akankshimody/Social-Media-Analytics/blob/master/Assignment%201%20-%20Identify%20Social%20Influence/tweets_flatearth.csv) on the flat earth conspiracy theory using [Tweepy](https://www.tweepy.org/) and use the predictors from Part I to identify 100 top influencers for the same.

### Problem Statement
The detailed problem statement provided by our professor can be found [here](https://github.com/akankshimody/Social-Media-Analytics/blob/master/Assignment%201%20-%20Identify%20Social%20Influence/Assignment%201%20Social%20Influence%20%26%20Twitter%20-%20Problem%20Statement.pdf)

### Analysis
Our code for the the assignment can be found [here](https://github.com/akankshimody/Social-Media-Analytics/blob/master/Assignment%201%20-%20Identify%20Social%20Influence/Python%20Notebook.ipynb)
<br><br>
Following are the steps we followed in our analysis:<br>
1.Using the training data set, we create an analytic model in Python for pairs of individuals to classify who is more influential. We tried three models: logistic regression, Random Forest and XGBoost. Among them, XGBoost has the highest accuracy rate of 78.8%.<br> 
The best 5 predictors of influence were retweets_received, listed_count, network_feature_2, mentions_sent, and following_count. Retweets indicate engagement whereas following count does not, so we expect retweets to be ranked higher. However, it was surprising that following count ranked
higher than follower count, because we thought how many people followed you would affect others’ perception of your influence more than how many people you follow.
A business can use these ranked features of what makes a person influential online as a guide to deciding who to partner with on social media.<br>
2. We then scraped ~5000 tweets on the flat earth conspiracy theory. We then created a graph such that any retweet (RT), mention or reply should result in an arrow from the person retweeting to the person retweeted, mentioned or replied to. We used NodeXL to visualize the [network.](https://github.com/akankshimody/Social-Media-Analytics/blob/master/Assignment%201%20-%20Identify%20Social%20Influence/Network%20Image.PNG)
We then calculate the degree, betweenness and closeness scores of each node in the above network using networkx.<br>
3. Using the results from Step 1, we found the top 50 influencers from the tweets.<br>

### Conclusion
Our results are detailed in our [report](https://github.com/akankshimody/Social-Media-Analytics/blob/master/Assignment%201%20-%20Identify%20Social%20Influence/Assignment%201%20Report.pdf)
