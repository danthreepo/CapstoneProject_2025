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

Column Name       Data Type  | Description |

`MOVIE NAME`         Object      Title of the movie (used to merge datasets).
`ROTTEN TOMATOES`    Object      Rotten Tomatoes score (e.g., `98/100`).
`NETFLIX`            Boolean     `True` if available on Netflix, otherwise `False`.
`HULU`               Boolean     `True` if available on Hulu, otherwise `False`.
`PRIME VIDEO`        Boolean     `True` if available on Prime Video, otherwise `False`.
`DISNEY+`            Boolean     `True` if available on Disney+, otherwise `False`.

---

## 🔹 Data Cleaning & Transformations
- **Column Standardization:**  
  - Renamed `TITLE` → `MOVIE NAME` for consistency across datasets.
  - Converted streaming platform columns (`NETFLIX`, `HULU`, etc.) from `0/1` to `True/False` for better readability.
- **Missing Data Handling:**  
  - Removed rows with null values after merging datasets.
- **Formatting Adjustments:**  
  - Converted `ROTTEN TOMATOES` from a string (`98/100`) to a percentage (`98.0` as float) for analysis.

---

## 📍 Notes
- The datasets were sourced from Kaggle and merged based on `MOVIE NAME`.
- Some movies might be missing from the merged dataset if they exist in only one source.
- Future improvements: Handle cases where movies have multiple genres.

---
