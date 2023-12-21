---
layout: post
title: Beyond Blockbusters - Decoding Actors' Career Evolution after a big hit in the Film Industry 
---

### Introduction
Ever wondered what happens after the blockbuster applause fades ?
Is it a straight road to more box office triumphs, or does the plot take unexpected turns ? Do actors try on new roles and genres, or do they stick to what brought them fame ?
Get ready for the big reveal, we're digging deep into the lasting effects of blockbuster stardom. Does it pave the way for a lasting legacy, or are there unforeseen challenges on the horizon?

Join us on a journey through Hollywood's reel-life drama as we tackle burning questions about actors post-blockbuster. 
Through this investigation, we’ll make the focus on blockbuster actors compared to less well-known actors, to uncover the patterns of the most noteworthy aspect of their professional journey.
We’ll take a look at the most successful blockbusters and evaluate the success of their main actors/actresses in following movies.
We can also investigate how the new character type affects the reception by the audience: is an actor/actress less convincing in new role with a persona very far from his/her successful character?
Does an actor who was successful in a particular role encounter challenges when portraying different characters? Some successful actors/actresses can incarnate a large palette of different roles, whereas some others are stuck to their successful character and have troubles getting out of it.

Does a high-grossing film consistently lead to continued box office success for its actors in their subsequent films?
Is there a noticeable change in genre or type of characters portrayed by actors after a significant hit?
What are the long-term career impacts on actors who have starred in blockbuster hits? 
Get your front-row seat to the blockbuster aftermath, where we untangle the threads of success, genre exploration, and career longevity in the ever-enthralling world of Hollywood.

### Preprocessing
Analyze career trajectories of actors following their roles in high-grossing films using the CMU Movie Dataset

With such a large database, it is complex to find a model that both describes the career of an English celebrity in the 40's and that of an actor in Japan in the 2000's. Cultural and economic differences also make it difficult to find a common metric for success. Therefore, we would like to limit ourselves to a consistent and comprehensible subset of the data.

After selecting relevant features, handling the missing data, and looking into the amount of available information, filtered our data to have only U.S. movies which where released after and including the year 1950. Limited ourselves to actors that played at least in two movies. 

This leaves us with an analysis on 6443 movies and 10008 actors


### Blockbusters
Define success of an actor depending on
number of movies they played in (?)
corresponding box office revenue


IMDb dataset allows to add ratings to the definition of success
The number of movies that we lost by adding the IMDb ratings is: 289. This represents a loss of  4.49%

The blockbuster metric
 revenue and IMDb ratings to define a big hit (i.e. a very successful movie)
consider the product of the movie revenue with its average IMDb rating as a metric for success

<img src="imgs/avg_success_per_year.jpeg" alt="Description of the image">


### Evolution of this metric along the years
assume that for a movie to be a big hit it has to be an outliner with respect to our previously defined success metric
pick outliners of each year and label them as big hits
We define an outliner as: outlier's success metric > Q3 + 1.5*(IQR) where Q1
Q3 and IQR are respectively the first quantile, the third quantile and the interquantile range

<img src="imgs/Mean success per year.jpeg" alt="Description of the image">

### Treatment vs control groups
divide our actors dataset into the ones that have played in one of those big hits (treatement group) and the ones that did not (control)
The number of actors that played in a big hit is: 4403 (treatement group)
The number of actors that did not play in a big hit is: 5605 (control group)

### Distribution of different variables for which we have information
#### Gender
< graph on gender >

#### Repartition of the age at the peak of the actors carrier

<img src="imgs/big_hit_actor.jpeg" alt="Description of the image">