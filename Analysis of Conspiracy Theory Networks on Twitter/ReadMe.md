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

### Collection of data

The process we implemented to track conspiracy theories is as follows:<br>
1. Find the hashtags most commonly used with a conspiracy theory.<br>
2. Typically contradictors use the same hashtag with words like conspiracy suffixed to it. We used these hashtags to compare the facts versus the conspiracy theories.<br>
3. We scraped tweets using Tweepy using these hashtags.<br>
4. We then constructed a directed graph such that: any retweet (RT), mention or reply would result in an arrow from the person retweeting to the person retweeted, mentioned or replied to.<br>

### Analysis

For all the networks constructed, we followed this procedure:<br>
1. Calculated centrality measures such as in-degree, out-degree and betweenness using networkx in Python<br>
2. Used these centrality measures to identify top influencers in the networks.<br>
3. Visualized the networks using NodeXL.<br>
4. Removed the top influencers from the networks. If the network still looked dense, we concluded that the network was self-sustaining. If the network became sparse, we concluded that the network was influencer-driven.<br>

## Results




