---
layout: post
---
<head>
    <style>
        h1 {
            text-align: center;
        }

        .small-text {
            font-size: 60%; /* Adjust the percentage as needed */
        }
    </style>
</head>

<body>
    <h1>
        Beyond Blockbusters <br>
        <span class="small-text"> Unveiling Actors Career Evolution After A Big Hit </span>
    </h1>
</body>

<p><img src="imgs/trueman.jpeg" style="width: 100%; margin: 0 auto;"/></p>

## Introduction
Ever wondered what happens after the blockbuster applause fades ?

Is it a straight road to more box office triumphs, or does the plot take unexpected turns ? Do actors try on new roles and genres, or do they stick to what brought them fame ?

Get ready for the big reveal, we're digging deep into the lasting effects of blockbuster stardom. 

Join us on a journey through Hollywood's reel-life drama as we tackle burning questions about actors post-blockbuster. Through this investigation, we’ll make the focus on blockbuster actors compared to less well-known actors, to uncover the patterns of the most noteworthy aspect of their professional journey.

We’ll take a look at the most successful blockbusters and evaluate the success of their main actors/actresses in following movies. We'll also investigate how the new character type affects the reception by the audience: is an actor/actress less convincing in new role with a persona very far from his/her successful character? Some successful actors/actresses can incarnate a large palette of different roles, whereas some others are stuck to their successful character and have troubles getting out of it.

Get your front-row seat to the blockbuster aftermath, where we untangle the threads of success, genre exploration, and career longevity in the ever-enthralling world of Hollywood.

## Dataset
The CMU Movie Dataset contains information about more than 40 000 movies, including plot summaries from Wikipedia and metadata from Freebase.

With such a large database, it is complex to describe the careers of an English celebrity in the 40's and that of an actor in Japan in the 2000's.. Cultural and economical differences also make it difficult to find a common metric for success.

We focused our analysis on movies from the U.S. released after (and including) 1950. We also limited ourselves to actors that played at least in two movies. 

## Blockbusters
### Success of a movie
How would you define the success of a movie? The success of a movie is hard to define, but it can be related to the box office that it made.

However this doesn’t take into account the public impressions.. Did the audience enjoy it ?

To bridge this gap, we’ll use the IMDb dataset, known for its user ratings, as a barometer of a movie's popularity.

The success of a movie will be defined here as the product of the movie revenue with its average IMDb rating.

<p><img src="imgs/movies_success_per_year.png" style="width: 80%; margin: 0 auto;" /></p>

### The blockbuster metric
It is common to use the term “blockbuster” or “big hit” to describe movies scoring a huge success. They are in fact movies that stand out compared to the others.

To define these type of movies, we’ll consider that it has to be an outlier with respect to our previously defined success metric.

An outlier presents the following characteristic : 

outlier’s success metric > Q3 + 1.5(IQR)

where Q1, Q3 and IQR are respectively the first, third quantiles and the interquantile range

Now that we defined what makes a movie a big hit, let’s check there distribution over the years 

<p><img src="imgs/blockbuster_movies.png" style="width: 80%; margin: 0 auto;" /></p>

Exactly as expected, isn't it? Blockbuster movies are clearly more successful than the other average movies.

## Blockbuster actors: famous or low-key ?
Let’s look at the major differences between blockbuster actors and moderate actors and see if we can uncover some secrets

<p><img src="imgs/gender.png" style="width: 80%; margin: 0 auto;" /></p>

Aside from the fact that there are more men than women altogether, the difference is even bigger in blockbusters actors. It appears that men take center stage in the world of blockbusters

What about the peak of success of an actor ? The peak of an actor's carrier could be defined by the year were the actor played in the most number of most successful movies. We define this peak of success by the year where the product of the number of movies played in with their respective success metric is the highest.

Of course you’re gonna think “but what about the actors that.. don’t have a career peak and stay low-key?” Well we’ll take the career peak from blockbuster actors as reference time points, so that we can compare them

Let’s look if there’s a difference between the age of the career peak between blockbuster actors compared to ohter actors

<p><img src="imgs/peak_age.png" style="width: 80%; margin: 0 auto;" /></p>

Looks like actors in big hits usually hit their peak at an older age than those who don't star in big hits. 

<p><img src="imgs/peak_age.png" style="width: 80%; margin: 0 auto;" /></p>

### It's a match !

Let’s compare the characteristics of blockbuster actors to those of less-well known ones. The actors will be divided into two groups: those who starred in blockbusters and those who didn’t. Each actor from one group will be paired to an actor from the another group using a matching. These actors will be matched on their gender and their age at career peak. 

<p><img src="imgs/matching.jpeg" style="width: 60%; margin: 0 auto;" /></p>


### Career longevity
How about the career longevity of an actor ? Do you have more chances to have a long career if you’ve played in a big hit movie ?Let’s look at the career lifespans of actors that played in blockbusters versus the others. 

<p><img src="imgs/longevity_distribution.png" style="width: 80%; margin: 0 auto;" /></p>

Charting the journey of actors from their screen debut to their latest act, a striking pattern emerges. Actors involved in blockbuster hits tend to have longer careers, averaging a glamorous 22.12 years. In contrast, their counterparts averaged a more modest 15.73 years. This emphasizes the transformative power of a blockbuster role in an actor's career.

<img src="imgs/sean_connery.jpeg" style="width: 30%; margin: 0 auto;" />

### Movie counts
In the next exciting chapter of our data-driven story, we shifted the focus to the number of movies each actor has starred in. Our investigation uncovered a notable distinction: actors in big hits (the Treatment Group) tend to have a higher average number of movie appearances (16 on average) compared to actors who haven't starred in big hits (7 on average). The results of Welch's t-test, yielding a p-value of 0.0, emphasize a significant difference in movie counts between the two actor groups. This reinforces our earlier findings: actors in big hits not only experience a momentary surge in fame but are likely to have more extensive filmographies compared to their colleagues without big-hit experiences.

<p><img src="imgs/movie_counts.png" style="width: 80%; margin: 0 auto;" /></p>

The median line in the blue box, which represents our Treatment Group (actors in big hits), is noticeably higher than its counterpart. The range of movie counts, especially on the higher side, is broader in the Treatment Group, indicating a more varied and often prolific career span among these actors. Another interesting point is the group's outliers—actors with exceptionally high movie counts—reinforcing the idea that a role in a big hit can lead to a more diverse and prolific acting career.

## Career analysis

Let's examine the average success for movies arranged chronologically.

<p><img src="imgs/movie_counts.png" style="width: 80%; margin: 0 auto;" /></p>

The median success values follow a similar pattern before the big hit, but here's the twist: after the blockbuster moment, the treatment group's median skyrockets, and instead of falling back to its original low, it stabilizes at a slightly higher level for the next movies.

P-values for Wilcoxon tests also confirm that the movie success value of actors after they played in their first big hit is higher than the rest of the actors.

Finally, let's look at the character role evolution in our actors careers

<p><img src="imgs/movie_counts.png" style="width: 80%; margin: 0 auto;" /></p>

## Conclusion
