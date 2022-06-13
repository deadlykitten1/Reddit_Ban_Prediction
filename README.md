# Flatiron School Capstone Project

# Political Alignment Prediction of Sub-Reddits

This project was inspired by my frustration with political discourse in the United States and our government's complete inability to combat the rising and continual threat of neo-nazis and the alt-right. 

Many young white men in this country find themselves trapped in a social media spiral where they are consistently fed them content that pushes them further and further to the right, until they are so brainwashed and hateful that they purchase an assault rifle and murder innocent people from marginalized groups. Even if the United States government passed well regulated militia laws, the issue would still persist, and we would still have events like the Capital Inssurection.

This project intends to create a solution to the issue at the root cause: social media echo chambers and the alt-right pipeline. This project will provide a solution to social media companies that can facilitate the interruption of the alt-right pipeline and hopefully reduce violent hatecrimes in the US. Social media companies can use my model to interupt users on their way down the pipeline.

# Data

I pulled the top 100 posts of all time and the top 100 posts of this year from 190 different subreddits. You can see the official list in the data wrangling notebook. I chose some of the most popular subreddits along with subs that are on the left and on the right. I plan on adding to this list more subreddits, including subreddits that have been banned like r/TheDonald and r/NoNewNormal.

For now, the model relies solely upon my domain knowledge of which subreddit is as risk of a ban. I hand labeled each subreddit based on its political alignment. I also used an agglomerative clustering algorithm to create an additional feature for the predictive modeling that groups subreddit's together based on topic.

# Models

I tried a few different models, but the ones showcased in the modeling notebook are a Decision Tree model (my dummy model), a Random Forest with 500 estimators, and Warm Bagging Model. I tasked each model with predicting the alignment of a post's subreddit based upon a single post. My best model with the Random Forest, which had an accuracy of 73%. Given that my hand labels are not entirely accurate, I believe this to be adequate. The model gives a benchmark idea of a subreddit's politics, and then a human would need to follow up and confirm. This reduces the load of human checking significantly.

# Conclusion

The model in its current state is unable to predict with high accuracy a subreddit's political alignment, but there are a number of improvements that can be made. Firstly, banned subreddits should be added to the model so that it knows what consitutes a ban. Right now I have one quarentined subreddit, but I assume banned subs are much much worse. Secondly, my preprocessing uses a count vectorizer. There are more sophisticated vectorization methods that I can try to garner more information from the text. Lastly, more data is needed. 190 subreddits is simply not enough data. I will be implemented these changes in the coming weeks so stay tuned!