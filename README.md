# nba-3pt-analysis

note* All data preparation and analysis can be found with annotated code in the file nba-3pt-analysis.ipynb. I will outline the most important details here.

Lets start with what we know anecdotally. 3-point shots have taken on a much bigger role in the NBA. Watching a game these days, it is rare to see anyone attempt a mid-range shot. Nearly all shots seem to come from either 3-point range, or right next to the hoop. At least thats the impression one would get watching the playoffs this year. Watching any sports talk show, you'll also hear about how the Warriors 3-pt heavy offense (which rose to prominance in their 2014 championship season) played a major role in ushering in this new era. So, does this impression hold true in the data?

All data was acquired from the official nba website (specifically, https://www.nba.com/stats/teams/boxscores/ ). 
From this page, I gathered the regular season data from the 1996-1997 season through the 2019-2020 season. To do so, I simply selected the 'All' rows option for each season, highlighted the data with a cursor, copied and then pasted the data into text files. Conveniently, the data pastes in as perfect TSV files.

Once I had a file for each season of interest, I wrote a script that imported all files into a single dataframe

![](plots/dataframe_screenshot.png)

I prepped the data by adding several useful columns, and breaking the data down into several useful dataframes. I added columns indicating whether the team was home or away and who their opponent was, and created separate dataframes for winners/losers. In addition, I created a 'matchups' dataframe that combined the two rows for each game (winner and loser) into a single row for direct comparisons, and an 'avgs' dataframe with the average values for each statistic each season.

## Beginning to analyze the data:

Lets start simple. How has the usage of 3-pointers changed over the years in our data set? Specifically, how many 2 and 3 point shots did teams attempt per game, and what percentage of shots were 2 pointers or 3 pointers? 

![](plots/1-shots-from-2-and-3.png)

We can see that right around the time of the first recent Warriors championship, teams started to take a larger percentage of their shots from 3-point range, and a smaller percentage from 2 point range. However, if we look at the number of points scored on 2 vs. 3-pointers, we see that while teams score more points on 3-pointers than in the past, they do not score any fewer on 2-pointers. 

![](plots/2-points-scored-from-2-and-3.png)

This means teams must be shooting 2-point shots more accurately than in the past.

![](plots/3-accuracy-from-2-and-3.png)

Indeed we see this effect. This is likely a result of teams taking more layups and dunks, while taking fewer midrange shots. A deeper analysis of changes in 2-point shot locations certainly warrents interest, but it is outside of the scope of this project. From here, we will focus primarily on 3-pointers. 
