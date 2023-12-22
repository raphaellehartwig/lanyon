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

Get ready for the big reveal, we're digging deep into the lasting effects of blockbuster stardom. Through this investigation, we’ll make the focus on blockbuster actors compared to less well-known actors, to uncover the patterns of the most noteworthy aspect of their professional journey.

Is it a straight road to more box office triumphs, or does the plot take unexpected turns ?

We’ll take a look at the most successful blockbuster movies and actors. Get your front-row seat to the blockbuster aftermath, where we untangle the threads of success, career longevity and other critical variables in the ever-enthralling world of Hollywood.

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

To define these type of movies, we’ll consider that it has to be an outlier with respect to our previously defined success metric, detected with a threshold depending on first, third quantiles and the interquantile range.

Now that we defined what makes a movie a big hit, let’s check there distribution over the years 

<p><img src="imgs/average_success.png" style="width: 80%; margin: 0 auto;" /></p>

Exactly as expected, isn't it? Blockbuster movies are clearly more successful than the other average movies.

## Characteristics of blockbuster actors
Let’s look at the major differences between blockbuster actors and moderate actors and see if we can uncover some secrets

<p><img src="imgs/gender.png" style="width: 80%; margin: 0 auto;" /></p>

Aside from the fact that there are more men than women altogether, the difference is even bigger in blockbusters actors. It appears that men take center stage in the world of blockbusters

What about the peak of success of an actor ? The peak of an actor's carrier could be defined by the year were the actor played in the most number of most successful movies. We define this peak of success by the year where the product of the number of movies played in with their respective success metric is the highest.

Of course you’re gonna think “but what about the actors that.. don’t have a career peak and stay low-key?” Well we’ll take the career peak from blockbuster actors as reference time points, so that we can compare them

Let’s look if there’s a difference between the age of the career peak between blockbuster actors compared to ohter actors

<p><img src="imgs/distribution_age_peak.png" style="width: 80%; margin: 0 auto;" /></p>

Looks like actors in big hits usually hit their peak at an older age than those who don't star in big hits. 

### It's a match !

Let’s compare the characteristics of blockbuster actors to those of less-well known ones. The actors will be divided into two groups: those who starred in blockbusters and those who didn’t. Each actor from one group will be paired to an actor from the another group using a matching. These actors will be matched on their gender and their age at career peak. 

<p><img src="imgs/matching.jpeg" style="width: 60%; margin: 0 auto;" /></p>


#### How long does an actor last ?
Do you have more chances to have a long career if you’ve played in a big hit movie ? Let’s look at the career lifespans of actors that played in blockbusters versus the others. 

<p><img src="imgs/longevity_distribution.png" style="width: 80%; margin: 0 auto;" /></p>

Charting the journey of actors from their acting debut to their latest movie, a striking pattern emerges. Actors involved in blockbuster hits tend to have longer careers, averaging 22.12 years. In contrast, their counterparts averaged a more modest 15.73 years.

The actors in big hits have their median career span outshines the rest of actors. This isn't just a small difference; it's a spotlight on a clear trend - the actors in big hits whose careers have a wider span range and show a more sustained success. While the limelight often favors the blockbuster stars, some non big hits actors  have impressively long careers without having roles in big hit movies. 

This analysis is confirmed by the p-value = 7.48 e-5 < 0.05 found when testing the null-hypothesis stating that there is no difference in the mean career longevity between the two groups. In fact, this value accentuates the importance that a blockbuster plays in the length of an actor's career.

<img src="imgs/sean_connery.jpeg" style="width: 30%; margin: 0 auto;" />

#### Do blockbuster actors play in a lot of movies?

Now let's focus on the quantity of movies each actor has starred in. Our investigation uncovers a notable distinction: actors in big hits tend to have a higher average number of movie appearances (16 on average) compared to actors who haven't starred in big hits (7 on average). The results of Welch's t-test, yielding a p-value of 0.0, emphasize a significant difference in movie counts between the two actor groups. This reinforces our earlier findings: actors in big hits not only experience a momentary surge in fame but are likely to have more extensive filmographies compared to their colleagues without big-hit experiences.

<p><img src="imgs/movie_counts.png" style="width: 80%; margin: 0 auto;" /></p>

The median line in the blue box, which represents our Treatment Group (actors in big hits), is noticeably higher than its counterpart. The range of movie counts, especially on the higher side, is broader in the Treatment Group, indicating a more varied and often prolific career span among these actors. Another interesting point is the group's outliers—actors with exceptionally high movie counts—reinforcing the idea that a role in a big hit can lead to a more diverse and prolific acting career. 

## Career analysis
### Evolution of success over career
Let's examine the average success for movies arranged chronologically where the blockbuster movie is n = 0. Of course you’re gonna think “but what about the actors that.. don’t have a career peak and stay low-key?” Well we’ll take the career peak from blockbuster actors as reference time points, so that we can compare them

<p><img src="imgs/mean_success.png" style="width: 80%; margin: 0 auto;" /></p>

The medians success values for both groups follow a similar pattern before the big hit event, but here's the twist: at the moment of the blockbuster moment (todelete), the treatment group's median skyrockets, and instead of falling back to its original low, it stabilizes at a slightly higher level for the next movies. However, the two medians are still close to one another even after the big hit event and there is a lot of variability in the two groups and their interquartile range overlaps. This prevents us from having a clear cut and being able to make a strong statement about a difference in the two groups. We can however see that among the big hit actors there is a much wider and variable distribution of the movie revenue (as seen in the previous plot with the numerous high-value outliers).

### Does a big hit influence an actor's roles over their career ?

Finally, let's look at the character role evolution in our actors careers.

<p><img src="imgs/success2.jpeg" style="width: 80%; margin: 0 auto;" /></p>

Most of the role importance values are equal to zero or very close to zero (note the y-axis log scale). This is because the movie summaries are quite short and lack precision. However, we can still see that in general the big hit actors seem to have a wider and more skewed distribution (toward high values) for the role importance. In addition, we see the distribution of the role importance for the control group is narrowing down to zero movie after movie. In conclusion, this graph tells us that for our dataset, more actors that are in the treatement group recieved important roles than actors in the control group. Hence the distribution of role importance is wider for actors that played in big hits movies but we can’t say anything about the role importance before and after the big hits movies.

## Conclusion
This in-depth exploration of post-blockbuster actor careers has revealed significant trends and distinctions. We dived into the aftermath of blockbuster applause to untangle the threads of success, genre exploration, and career longevity in the ever-captivating world of the movie industry.

By defining a film's success as the product of its revenue and average IMDb rating, we identified blockbusters as outliers compared to the average. Blockbuster actors exhibit distinct characteristics, including a male-dominated representation and a generally higher peak career age than their lesser-known counterparts.

By pairing blockbuster actors with their less-known peers based on gender and age, we found that blockbuster actors often have longer careers, highlighting a striking trend.


<p><img src="imgs/inception.jpeg" style="width: 70%; margin: 0 auto;"/></p>