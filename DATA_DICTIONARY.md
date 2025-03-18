# Data Dictionary for Scifi Movie Streaming Services Analysis


## Data frame 1: `scifi.csv` This is a list of Scifi Movie Titles.

Column Name     Data Type   Description 

`MOVIE NAME`     Object      Title of the movie.
`YEAR`           Int64       Year the movie was released.
`CERTIFICATE`    Category    Movie rating (e.g., PG-13, R, Not Rated).
`GENRE`          Object      Primary genres (e.g., Action, Drama, Sci-Fi).
`RATING`         Float64     IMDB rating (scale of 1-10).
`DESCRIPTION`    Object      Short summary of the movie.
`GROSS (IN $)`   Float64     Box office revenue in USD. 


## Data frame 2: `MoviesOnStreamingPlatforms.csv.csv` This is a list of Movies and their availability on each streaming service.

Column Name          Data Type      Description 

`MOVIE NAME`         Object         Title of the movie (used to merge datasets).
`ROTTEN TOMATOES`    Object         Rotten Tomatoes score (e.g., `98/100`).
`NETFLIX`            Boolean        `True` if available on Netflix, otherwise `False`.
`HULU`               Boolean        `True` if available on Hulu, otherwise `False`.
`PRIME VIDEO`        Boolean        `True` if available on Prime Video, otherwise `False`.
`DISNEY+`            Boolean        `True` if available on Disney+, otherwise `False`.

---

## Data Cleaning & Transformations
**Column Standardization:**

Renamed `TITLE` → `MOVIE NAME` for consistency across datasets.
Converted streaming platform columns (`NETFLIX`, `HULU`, etc.) from `0/1` to `True/False` for better readability.



**Formatting Adjustments:**  

Cleaned and adjusted all columns to uppercase, stripped white space, and replaced underscores with spaces.

Data frame 1 `Scifi.csv` scifi movie file.

Data frame 2 `MoviesOnStreamingPlatforms.csv.csv` Streaming movie list.

**Missing Data Handling:**  
Removed all rows with null values for each dataset individually.
Removed rows with null values after merging datasets to remove movies that would not be available on the streaming services.

**Dropped Unused Colounms:**  
Dropped these columns from Data Frame 1 `MOVIE ID`, `RUNTIME`, `DIRECTOR`, `DIRECTOR ID`, `STAR`, `STAR ID`, `VOTES`; and these from Data frame 2 `UNAMED: 0`,`ID`,`YEAR`,`AGE`, `TYPE`

## Feature Engineering

I formatted the rating systems on each file to put them in the same format.  I then created a new column with the average of both rating systems.

## Visualizations

I created 4 charts.  One chart shows the highest rated movies, one that shows the lowest rated movies, one that shows the total amount of movies that are available on each streaming service, and one that shows how the quality of a movie relates to the box office return.

## Notes
- These datasets were sourced from Kaggle and merged based on `MOVIE NAME`.
- Some movies might be missing from the merged dataset if they exist in only one source or if they were not available on the streaming services.
- Some movies may be available on multiple streaming services.
- Future improvements: I would like to find a source where I can import the cost of the movies and then compare them to the box office returns and the ratings to see the relationship between them.
- Other ideas: Take this data to find to create a program that would recommend movies based on personal ratings.