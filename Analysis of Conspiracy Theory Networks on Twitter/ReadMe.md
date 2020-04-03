# Analysis of Conspiracy Theory Networks on Twitter

## Introduction

The Wikipedia definition of a conspiracy theory is as follows: **A conspiracy theory is an explanation of an event or situation that invokes a conspiracy by sinister and powerful actors, often political in motivation, when other explanations are more probable.**
<br>
There is false information being spread all the time in today's age when social media has become the primary source of information for most people. But who controls the spread of this false information? Is it a few key individuals or is it more democratic? Our team set to find these answers out by studying the activity surrounding conspiracy theories on Twitter.

## Motivation - Why understand conspiracy theory networks?

It’s important to understand conspiracy theory networks for the following reasons:<br>
1. Conspiracies can potentially harm lives. For example, the antivaccincation conspiracy was started by a paper claiming that vaccines caused autism. Even though the author later retracted the paper and it was disproven by many other researchers, it led to many parents not getting their children vaccinated, which puts their own children and others at risk for disease.
2. Many conspiracy theories involve the government and decreased trust in government can be very destabilizing for society. 
3. Conspiracy theories can have a spiral effect: If people believe in one conspiracy, they tend to believe in others too. For example, those who tend to believe that climate change is a hoax, also end up believing that 9/11 was an inside job. These people can be highly susceptible to false information.

## Goal of the Project

1. Analyse networks of several conspiracy theories to indentify whether these networks are influencer-driven or self-sustaining since self-sustaining conspiracy networks can be extremely dangerous.
2. Compare networks of truths to those of untruths to observe resistance to acceptance of facts.
3. Find out how different types of conspiracy theories spread.

## Approach

We analysed four conspiracy theories:<br>
1. Flatearth: An archaic conception of Earth's shape as a plane or disk. <br>
2. Chemtrails: An erroneous belief that long-lasting condensation trails from aircrafts are "chemtrails" consisting of chemical or biological agents left in the sky, sprayed for nefarious purposes by the government. <br>
3. Deep State: A conspiracy theory which suggests that collusion exists within the US political system and constitutes a hidden government within the legitimately elected government. <br>
4. Iowa Caucus: A conspiracy theory suggesting that the U.S. election is rigged and that the Democratic Party attempted to tilt the election in favor of a single candidate. <br>

#### Collection of data

The process we implemented to track conspiracy theories is as follows:<br>
1. Find the hashtags most commonly used with a conspiracy theory.<br>
2. Typically contradictors use the same hashtag with words like conspiracy suffixed to it. We used these hashtags to compare the facts versus the conspiracy theories.<br>
3. We scraped tweets using Tweepy using these hashtags.<br>
4. We then constructed a directed graph such that: any retweet (RT), mention or reply would result in an arrow from the person retweeting to the person retweeted, mentioned or replied to.<br>

#### Analysis

For all the networks constructed, we followed this procedure:<br>
1. Calculated centrality measures such as in-degree, out-degree and betweenness using networkx in Python<br>
2. Used these centrality measures to identify top influencers in the networks.<br>
3. Visualized the networks using NodeXL.<br>
4. Removed the top influencers from the networks. If the network still looked dense, we concluded that the network was self-sustaining. If the network became sparse, we concluded that the network was influencer-driven.<br>

## Results

#### Flatearth Conspiracy Theory

<img src="https://github.com/akankshimody/Social-Media-Analytics/blob/master/Analysis%20of%20Conspiracy%20Theory%20Networks%20on%20Twitter/images/Flatearth.PNG" alt="Image3" width="500"/><br><br>

The image on the left shows the original network. The nodes highlighted in red and blue are the key influencers in the network (handles which have been retweeted alot). After removing these two nodes, we get the network on the right. We see that the network is highly dense. This means that this network is **self-sustaining**. The highlighted nodes are in fact bots which keep retweeting flatearth tweets.

#### Chemtrails Conspiracy Theory

<img src="https://github.com/akankshimody/Social-Media-Analytics/blob/master/Analysis%20of%20Conspiracy%20Theory%20Networks%20on%20Twitter/images/Chemtrails.PNG" alt="Image3" width="500"/><br><br>

The image on the left shows the original network. The nodes highlighted are the key influencers in the network (handles which have been retweeted alot). After removing these nodes, we get the network on the right. We see that the network has became sparse. Although there is a small dense region, the network shows us that it is highly **influencer-driven**. Remove the influencers, and the propogation of the theory can be curbed. 

#### Deep state Conspiracy Theory

Here, we analysed the network of the conspiracy, as well as the network of those trying to dismiss the conspiracy. 

<img src="https://github.com/akankshimody/Social-Media-Analytics/blob/master/Analysis%20of%20Conspiracy%20Theory%20Networks%20on%20Twitter/images/DeepState1.png" alt="Image3" width="500"/><br><br>

The network on the left highlights the key influencers for the Deep State Conspiracy theory and the network on the right highlights the key influencers involved in dismissing this theory.<br><br>

<img src="https://github.com/akankshimody/Social-Media-Analytics/blob/master/Analysis%20of%20Conspiracy%20Theory%20Networks%20on%20Twitter/images/DeepState2.PNG" alt="Image3" width="500"/><br><br>

All the highlighted influencers' handles had profile pictures of women.<br>

For the Deep State Conspiracy theory (left image), the top influencers are:<br>
1. *Smile* which infact is Russian Bot<br>
2. *JoyP* is also a Russian Bot<br>

For the network dismissing the theory (right image), the top influencers are:<br>
1. *Barb* is @UMichLaw professor and a legal analyst  at NBCNews.<br>
2. *Mimi* is Former Federal Prosecutor SDNY and now a Professor at Pace Law School.<br><br>

<img src="https://github.com/akankshimody/Social-Media-Analytics/blob/master/Analysis%20of%20Conspiracy%20Theory%20Networks%20on%20Twitter/images/DeepState3.PNG" alt="Image3" width="500"/><br><br>

For the Deep state network (left image), even after removing the top 10 influencers, there is still a lot of activity. This is bad! The conversation is **self-sustaining.**<br>
For those dismissing the Deep state conspiracy (right image), if we remove the top 2 influencers, the network is already falling apart; people aren’t trying to disprove the conspiracy as aggressively. This network is **influencer-driven.**<br>


#### Iowa Caucus Conspiracy Theory

Here, we analysed the network of the conspiracy, as well as the network of those trying to dismiss the conspiracy. 

<img src="https://github.com/akankshimody/Social-Media-Analytics/blob/master/Analysis%20of%20Conspiracy%20Theory%20Networks%20on%20Twitter/images/Iowa1.PNG" alt="Image3" width="500"/><br><br>

The network on the left highlights the key influencers for the theory that the Iowa Caucus was rigged and the network on the right highlights the key influencers involved in dismissing this theory.<br><br>

<img src="https://github.com/akankshimody/Social-Media-Analytics/blob/master/Analysis%20of%20Conspiracy%20Theory%20Networks%20on%20Twitter/images/Iowa2.PNG" alt="Image3" width="500"/><br><br>

For the Conspiracy theory (left image), the top influencers are:<br>
1. *Dorcas* which is a bot.<br>
2. *Team trump* is not a bot, but it makes sense to see Trump’s campaign account in the network.<br><br>

For the network dismissing the theory (right image), notice that the activity is mostly dominated by Jesse Jackson’s viral tweet. Jesse Jackson is a well known civil-rights activist<br>

<img src="https://github.com/akankshimody/Social-Media-Analytics/blob/master/Analysis%20of%20Conspiracy%20Theory%20Networks%20on%20Twitter/images/Iowa3.PNG" alt="Image3" width="500"/><br><br>

For the DNCRigged network (left image), even after removing the top 4 influencers, there is still a lot of activity. Again, this is bad! The conversation is **self-sustaining.**<br>
For those dismissing the theory (right image), if we remove the top 1 influencer (Jesse Jackson’s) the network is still fairly connected, but not to the same level as the network of the conspiracy theories. This network is **influencer-driven.**<br>

## Conclusion
We can thus see that by analyzing networks, we can identify whether the networks are self-sustaining or influencer-driven and take action accordingly. 

Our presentation can be found [here](https://github.com/akankshimody/Social-Media-Analytics/blob/master/Analysis%20of%20Conspiracy%20Theory%20Networks%20on%20Twitter/Final_presentation.pdf)


