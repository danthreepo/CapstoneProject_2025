Project Plan:

Data Analysis of Streaming Services with Genre “Sci-Fi Movies” to Return Maximum Value

Overview
    Analyze Sci-Fi movies by combining two datasets retrieved from Kaggle, one containing a large movie dataset and a second streaming availability dataset. The goal is to clean, merge, and analyze the data to uncover trends related to ratings, revenue, and streaming availability.

Technical Insight

I plan on pulling these datasets from Kaggle using the Kagglehub module.
    Primary Dataset: From Kaggle movie dataset (filtered for Sci-Fi).
    Secondary Dataset: From Kaggle Streaming availability dataset (Netflix, Hulu, Prime, Disney+).

Data Cleaning & Preparation
    ---Remove unused columns.
    ---Filter the movie dataset to include only Sci-Fi movies.
    ---Merge it with the streaming dataset using movie titles.
    ---Drop rows with any missing data.
    ---Create a new feature: "Combined Rating" (average of IMDb and Rotten Tomatoes scores).

Exploratory Data Analysis & Visualizations
    ---I will analyze the data frame for any statistical value.
    ---Using either Matplotlib or Seaborn, I will create the following visualization:
    ---Top Rated Sci-Fi Movies (Based on Combined Rating).
    ---Streaming Service with the Most Sci-Fi Movies (Bar Chart).
    ---Comparison of Ratings vs. Box Office Revenue (Scatter Plot).
    I will make several types of visualizations and ultimately choose which one looks the most appealing.

Additional Project Steps
    I will create and include the following in order to complete the requirements of this project.
    ---Utilize a virtual environment and provide the instructions for the user to create their own environment in a README.MD file.
    ---Create a data dictionary for use.

Additional Mentor Feedback
    So far based on feedback and other examples in class I have scaled back my ambitions and I am focusing on completing the minimum requirements and then adding more after I have completed.
