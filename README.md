# CS210 Project - Spotify Top Songs Analysis by Berk Efe Erdem #28403

Introduction and Motivation

For the Final Project of CS210, Introduction to Data Science course at Sabancı University, I decided to use my Spotify Top Songs Playlists in years 2020, 2021, 2022 and 2023; to have an insight of my listening habits. I aimed to see my statistics about different metrics, different genres and different artists in recent years, so I decided to use not only the last year's data but a 4 year worth of data consisting top 100 songs for each year.
My plan for the project is to first get the data as a CSV file, then I'll implement it in Jupyter Notebook. I will clean the data and handle the NaN values, to get better insights in every step of action. Then I will conduct different EDA and Visualization techniques, to observe how is the data in different metrics are distributed over the course of 4 years, and each year individually. I will analyze the trends, and correlations, to see how my listening habits have changed from age 20 to 23.
As a next step, I will conduct various Hypothesis Tests, including t-tests, ANOVA tests, and chi-square tests. I will form my null hypothesis for each before starting the test, and as a result, I aim to see that if my predictions about my listening habits are statistically true or not.
As the final step, I will use different Machine Learning processes like Regression and Classification Models, K - Means Clustering, Time Series Analysis, Random Forest Classifying; to observe different metrics that is not included in the CSV file, to forecast my future listening habits based on the changes, find the collaborations between genres and artists.



Data Source

The playlists that I will use in the project are located in Spotify's own database. I added Top Songs 2020, 2021, 2022 and 2023 to my Liked Playlists, and then I used a third-party program called Exportify to export all those playlists in the CSV format. With the aid of Microsoft Excel, I concatenated all playlists as a one single playlist, called 'your_top_songs_4yearsv3.csv'. Starting below, I will clean, and analyze the data as I planned step by step, with further elaborations like EDA and Visualization, Hypothesis Testing and Machine Learning Models



Data Analysis Steps:

1- Data Importing, Cleaning, and Handling Null Values
2- Exploratory Data Analysis and Visualization
3- Hypothesis Testing
4- Machine Learning Models



Findings:

1) Findings in Exploratory Data Analysis and Visualization Part
While analyzing the music dataset from 2020 to 2023, I found some interesting insights. The most popular genres during this timeframe were notably Turkish trap and hip-hop, with "turkish trap" leading the chart, closely followed by "turkish hip-hop" and "rap." Most of my listening time goes to Turkish songs, so much that my dataset can be divided as Turkish and Non-Turkish Songs. The other languages are mostly English and German, with some Greek especially in 2023.
Ezhel kept his top place among my favorite artists when considering all 4 years, despite he is not the top artist in my later datas like 2022 or 2023.
The visual representation through bar plots and pie charts that I created offered a snapshot of how genres were distributed. Additionally, a closer look at the trends over the years revealed a shift in musical preferences, underscoring the aging landscape :).
My exploration, utilizing descriptive statistics, histograms, boxplots, and scatterplots, provided a better understanding of numerical variables, uncovering distribution patterns, outliers, and trends. The personalized touch of pair plots and correlation matrices shed a light to relationships between numerical features, such as the noteworthy correlation between "popularity" and "loudness."
Altogether, my analysis and visualizations provided a rich understanding of my musical journey from 2020 to 2023.

2) Findings in Hypothesis Tests
I conducted 4 different hypothesis tests to check if my predictions about my listening habits are statistically true.
To understand the dynamics of popularity, the first hypothesis test checked the mean popularity difference between Turkish and Non-Turkish songs. The results were interesting, revealing a substantial difference in mean popularity, as denoted by the test statistic of -6.509 and a minuscule p-value of 2.53e-10. Cohen's d, standing at -0.689, emphasized this discrepancy, solidifying the rejection of the null hypothesis. Visualizing confidence intervals through an error bar plot enriches insights into the uncertainty surrounding mean popularity estimates for both genres.
The second hypothesis test checked the popularity variations among the top 10 artists. A F-statistic of 105.83, coupled with a p-value of 2.03e-33, led to the rejection of the null hypothesis, signifying significant differences in popularity among the top 10 artists. The post-hoc analysis, courtesy of Tukey's HSD, pinpointed specific pairs of artists with notably distinct popularity levels.
Zooming into numeric columns for hypothesis test three, danceability, energy, loudness, speechiness, acousticness, instrumentalness, and liveness exhibited no significant differences between 2020 and 2023. However, valence and tempo stood out with statistically significant disparities. Tempo was expected as the BPM preference of my music taste decreased significantly after 2021 era(where drill music made the top of the lists in various countries), I wasn't expecting a significant change in valence.
Finally, the fourth hypothesis test, examining the statistical changes in my top artists from 2020 to 2023, brought forth a Chi-square statistic of 129.38 with a p-value of 0.79. The conclusive finding? No significant change in top artists during this period. That was interesting too, because my top artists actually changed a lot for me. What's causing this data is some of the artists included in all 4 years, which I cannot stop listening.

3) Findings in Machine Learning Models
The Random Forest Classifier achieved a 78% accuracy in predicting song preferences, with notable precision (0.79) and high recall (0.97) for songs not liked. However, precision for liked songs was lower (0.67), and recall significantly lower (0.20). The F1-scores reflected a trade-off between precision and recall, with values of 0.87 for not liked songs and 0.31 for liked songs. The macro avg and weighted averages were 0.73, 0.58, and 0.59, respectively, indicating varied performance across classes.
In Linear Regression, the Mean Squared Error (MSE) was 563.92, providing a tangible measure of the model's accuracy in predicting song popularity based on selected features. The scatter plot visualization demonstrated the model's ability to capture the inherent variability in popularity, focusing on the 'Danceability' feature.
For music genre prediction, the Random Forest Classifier achieved a 32% accuracy. Precision, recall, and F1-scores varied across genres, emphasizing the model's differing effectiveness. The macro and weighted averages considered genre imbalance, revealing insights into the model's overall performance in capturing audio features for genre prediction.
The K-Means Clustering analysis applied to audio features yielded three distinct clusters, revealing patterns in songs' 'Danceability' and 'Energy'. There are 3 different clusters detected, which I expected more, but I guess that's limited because despite I listen to various genres, my main genres are generally the same. And those genres do not really vary a lot in those metrics.
The SARIMA model showcased convergence after 22 iterations, providing a reliable forecast of an upward trend in song popularity post-2020. It plotted a prediction based on past data, and it forecasted 2024-2025 values which are interesting to check.
Correlation analysis highlighted key associations, such as the positive correlation between 'Danceability' and 'Valence', and a strong positive correlation between 'Valence' and 'Popularity', shedding light on influential factors in song success.
Feature Engineering introduced new features that does not exist in dataset, like 'Duration_minutes,' 'Decade,' 'Release Month,' and 'Popularity Category'. Visualizations provided insights into song duration distribution, release decade count, monthly distribution, and popularity category distribution. The duration minutes, decade and popularity category did not surprise as they are already my expected values for my listening habits, but it was interesting to see the Release Month data. I generally like soulful and afro-based instrumentals, hence I was expecting to see more songs released in summer. The findings show me the opposite.
The Isolation Forest algorithm successfully detected outlier songs, including "idfc" (popularity: 75), "Revenge" (popularity: 88), and "Mood Swings" (popularity: 79), revealing unique patterns in selected features. I had no idea these were outliers, it looks like they despite none of these songs is released after 2020, they are still very popular.
Genre Collaboration Network Analysis identified 157 genres with 642 collaborations. Top collaborations include "turkish hip hop - turkish trap" (115 collaborations) and "hip hop - rap" (47 collaborations). This analysis is not surprising, as artists prefer to put multiple genres in the description to enrich their chances of a trend boom.
Artist Collaboration Network Analysis highlighted collaborations like "Dante, Odin" (5 collaborations) and "Odin, Batdora" (4 collaborations), offering insights into artist relationships and industry collaborations. Dante is me, and Odin & Batdora are my close friends, so highest collaboration rate is not surprising either :)



Limitations and Future Work

There may be more metrics for songs, but Spotify does not keep them. I wanted to see the Hertz and Key values to analyze how aging 4 years changes the preferences in terms of those, because each Key has a different mood in it, and each Hertz give different signals to our brain. As a future work, I may do more Machine Learning Models, as out of all subjects, they are the ones that I'm the least familiar.
