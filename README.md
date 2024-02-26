# Module_10_challenge

**Background**

You’ll assume the role of an advisor in one of the top five financial advisory firms in the world. Competitors are fierce, so you want to propose a novel approach to assembling investment portfolios that are based on cryptocurrencies. Instead of basing your proposal on only returns and volatility, you want to include other factors that might impact the crypto market—leading to better performance for your portfolio.

When you present the idea, your manager loves it! So, you’re asked to create a prototype for submitting your crypto portfolio proposal to the company board of directors.

You’ll combine your financial Python programming skills with the new unsupervised learning skills that you acquired in this module.

You’ll create a Jupyter notebook that clusters cryptocurrencies by their performance in different time periods. You’ll then plot the results so that you can visually show the performance to the board.

The provided CSV file contains the price change data of cryptocurrencies in different periods.

**Project**

The project begins by importing the csv file  and creating a data frame using seven metrics of the 41 securities. The next section includes data preparation and scaling. Then, I find the best k-value. I create a loop to compute inertia and use that inertia with its corresponding k-value to create a data frame. This data frame is plotted on a line chart called an Elbow Curve to easily see which will be the best k-value.I find that a k-value of four is optimal. Then I create a model with four clusters. I fit and predict the cluster of each security and append the cluster assignment to the original data frame. I take this new data frame and plot the seven-day and 24-hour percentage change of each security by cluster on a scatter plot. I find that based off these two metrics, bitcoin-cash is a consistent performer, while theta-coin and ethlend are the losers of the pack. Most securities clustered around the 0 mark based on 24-hour percentage change but showed variability based on seven-day percentage change. I do see that celsius-degree-token performs very similarly to digibyte. The former is the only security in cluster one. This leads me to believe that three clusters are better, but I do stick to what the Elbow Curve designates.

The next section requires optimization of clusters through Principal Component Analysis (PCA). I choose three to be the amount of principal components and transform the data. I find that the three components explain 89.5% of the original performance with components one and two accouting for over 70% of it. I create a data frame of the new PCA data and recreate the previous model to find the optimal k-value of the new PCA data. Again, I find that the optimal k-value is four. I recreate the previous models to create and assign clusters. I plot the the first two of three principal components by cluster on a scatter plot. I find the results to be much more concentrated around the 0 mark, but also found two surprising results. First, while ethland was the consistent loser in the first scatter plot, it performed extremely well based off of principal component one. Second, recall that celsius-degree-token was needlessly in a cluster of its own in the first scatter plot. Well, this time it is still in a cluster of its own, but with returns that far exceed any other security. 

Ultiamtely, using the PCA method is useful to narrow down the components while maintaining high result accuracy. Yet, I don't believe the PCA is absolutely necessary. I think it is very intteresting to see the model place celsius-degree-token in a cluster of its own in both methods. Being in a cluster of its own seems unnecessary in the original method, while in the second method it is obvious why it got assigned its own cluster. I guess the numbers don't lie. 


**Code Source**

The code was sourced from the classwork assignments. 


**Technologies**

This assignment requires the use of pandas, hvplot, pathlib, and sklearn. KMeans, PCA, and StandardScaler is imported from sklearn. This assignment was developed using Python as the coding language on Visual Studio Code. 