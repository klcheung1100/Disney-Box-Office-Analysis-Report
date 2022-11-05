# Disney-Box-Office-Analysis-Report

<br> In this project, I explore a dataset of Disney movies and analyze what contributes to the success of Disney movies.

<br> Dataset: The Disney data compiled by Kelly Garrett (https://data.world/kgarrett/disney-character-success-00-16). The data contains 579 Disney movies with six features: movie title, release date, genre, MPAA rating, total gross, and inflation-adjusted gross.

<br> 1. I check which are the 10 Disney movies that have earned the most at the box office. I do this by sorting movies by their inflation-adjusted gross (I will call it adjusted gross from this point onward).
<br> The top Disney movie that have earned the most at the box office is the musical, <Snow White and the Seven Dwarfs> released in 21/12/1937. There are 4 Adventure movies and 3 musical ranked top 10 in the history. The most recent one is <Star Wars Ep. VII: The Force Awakens>, which release in 2015, ranked the 7th in the history.

<br>From the top 10 movies above, it seems that some genres are more popular than others. So, I check which genres are growing stronger in popularity. To do this, I group movies by genre and then by year to see the adjusted gross of each genre in each year. I also make a plot out of these means of groups to better see how box office revenues have changed over time.
<img alt="My Image" src="plot.png" />

<br>The line plot supports our belief that some genres are growing faster in popularity than others. For Disney movies, Action and Adventure genres are growing the fastest. Next, I build a linear regression model to understand the relationship between genre and box office gross.

<br>From the regression model, I check the effect of each genre by looking at its coefficient given in units of box office gross dollars. I focus on the impact of action and adventure genres here. (Note that the intercept and the first coefficient values represent the effect of action and adventure genres respectively). I expect that movies like the Lion King or Star Wars would perform better for box office.

<br>Next, I compute 95% confidence intervals for the intercept and coefficients. The 95% confidence intervals for the intercept a and coefficient bi means that the intervals have a probability of 95% to contain the true value a and coefficient bi respectively. If there is a significant relationship between a given genre and the adjusted gross, the confidence interval of its coefficient should exclude 0. I calculate the confidence intervals using the pairs bootstrap method.

<br>After the initialization, I perform pair bootstrap estimates for the regression parameters. I draw a sample from a set of (genre, adjusted gross) data where the genre is the original genre variable. I will perform one-hot encoding after that.

<br> Finally, I compute 95% confidence intervals for the intercept and coefficient and examine if they exclude 0. If one of them (or both) does, then it is unlikely that the value is 0 and we can conclude that there is a significant relationship between that genre and the adjusted gross.

<br> The confidence intervals from the bootstrap method for the intercept and coefficient do not contain the value zero, as we have already seen that lower and upper bounds of both confidence intervals are positive. These tell us that it is likely that the adjusted gross is significantly correlated with the action and adventure genres.

<br> From the results of the bootstrap analysis and the trend plot we have done earlier, we could say that Disney movies with plots that fit into the <b>action and adventure genre</b>, according to our data, tend to do better in terms of adjusted gross than other genres. So we could expect more Marvel, Star Wars, and live-action movies in the upcoming years!
