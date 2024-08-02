# BGG-boardgame-analysis
Exploratory Analysis of the Boardgamegeek.com (aka BGG) Top-5000 Board games.
Board game names, ratings, weights, and several other features were scraped using the BGG API. The resulting data was cleaned, and some exploratory data analysis was performed. I was particularly curious to see how the number of games published, their weight, and the most popular categories have changed over time. Additionally, I aimed to identify key ingredients for a successful board game today using an appropriate regression model. Here are some interesting findings:

**1. About 99% of the board games in the BGG Top 5000 were published after 1970, with a dramatic increase starting in the late 90s/early 2000s.**

![Image 1](plots/bgg1.png)

**2. There was significant fluctuation in the average board game weight from 1980 to 2020, but the overall trend was for games to get lighter. Since 2020, there's been a shift towards heavier board games.**

![Image 2](plots/bgg2.png)

**3. A correlation matrix shows a positive correlation between game weight and its average rating/Bayes average rating (the latter accounts for the number of users who rated the game, penalizing games with fewer ratings).**

![Image 3](plots/bgg3.png)

**4. Card games are the largest category in the BGG Top 5000, followed by 'Fantasy', 'Economic', and 'Wargame'.**
![Image 4](plots/bgg4.png)

**5. Different war-themed categories seem to have high average ratings but very low Bayes average ratings because fewer users rate them.**
![Image 5](plots/bgg5.png)

**6. Additionally, wargames tend to be the heaviest.**
![Image 6](plots/bgg6.png)

**7. Some of the game mechanics associated with highly rated board games are: 'Legacy Game', 'Automatic Resource Growth', and 'Delayed Purchase'.**
![Image 7](plots/bgg7.png)

**8. Finally, looking at the most common board game categories from pre-1980 to the 2020s reveals the decline in popularity of wargames and the rise of fantasy and, more recently, dice games.**
![Image 8](plots/bgg8.png)

I also ran linear regression (using ElasticNet regularization) and random forest regressor models to determine which features most significantly affect a game's Bayes average rating. Both models confirmed that weight positively impacts the rating, as observed in the correlation matrix. Additionally, certain mechanics, such as 'End Game Bonuses', 'Variable Set-up', 'Tech Trees', and 'Hand Management', were found to have a positive effect. In contrast, board game categories had a less pronounced impact on the rating compared to mechanics.


