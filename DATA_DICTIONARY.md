# Data Dictionary for Movie Streaming Services Analysis


## Data frame 1: `[selected-genre].csv` is user selectable from a function.  This Data frame consists of 16 seperate CSV files that contain an assortment of movie titles... Some movie titles may be found in multiple genres...

Column Name     Data Type   Description 

`MOVIE NAME`     Object      Title of the movie.
`YEAR`           Int64       Year the movie was released.
`CERTIFICATE`    Category    Movie rating (e.g., PG-13, R, Not Rated).
`GENRE`          Object      Primary genres (e.g., Action, Drama, Sci-Fi).
`RATING`         Float64     IMDB rating (scale of 1-10).
`DESCRIPTION`    Object      Short summary of the movie.
`GROSS (IN $)`   Float64     Box office revenue in USD. 


## Data frame 2: `MoviesOnStreamingPlatforms.csv.csv`

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

Data frame 1 `[selected-genre].csv` uses a function to clean because the data loaded varies by selection.

Data frame 2 `MoviesOnStreamingPlatforms.csv.csv` is cleaned directly inline with the bulk code because it remains static when ran.

**Missing Data Handling:**  
Removed all rows with null values for each dataset individually.
Removed rows with null values after merging datasets to remove movies that would not be available on the streaming services.

**Dropped Unused Colounms:**  
Dropped these columns from Data Frame 1 `MOVIE ID`, `RUNTIME`, `DIRECTOR`, `DIRECTOR ID`, `STAR`, `STAR ID`, `VOTES`; and these from Data frame 2 `UNAMED: 0`,`ID`,`YEAR`,`AGE`, `TYPE`


## Notes
- These datasets were sourced from Kaggle and merged based on `MOVIE NAME`.
- Some movies might be missing from the merged dataset if they exist in only one source or if they were not available on the streaming services.
- Some movies may be classified under multiple genres
- Future improvements: Create a function that will run all of the genres independent of each other and score the streaming platforms based on those results.
- Other ideas: Take this data to find movies based on ratings to watch