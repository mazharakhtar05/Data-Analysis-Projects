# Analyzing the TMDB Movies Dataset
### Project 1 | Udacity Data Analyst Nanodegree
**Author:** MAZHAR AKHTAR ANSARI

| Contents |
| -------- |
| [Dataset Overview](#Dataset-Overview) |
| [Features Dictionary](#Features-Dictionary) |
| [Analysis Questions](#Analysis-Questions) |
| [Data Collection & Wrangling](#Data-Collection-&-Wrangling) |
| [Data Preprocessing](#Data-Preprocessing) |
| [Exploratory Data Analysis (EDA)](#Exploratory-Data-Analysis-(EDA)) |
| [Tools & Libraries](#Tools-&-Libraries) |

## Dataset Overview
This dataset features details on approximately 10,000 movies gathered from [TMDB](https://www.themoviedb.org/). It spans releases from 1960 through 2015 and includes key metrics like box office revenue and audience ratings. The raw data was originally sourced from [Kaggle](https://www.kaggle.com/tmdb/tmdb-movie-metadata).

## Features Dictionary
- `id`, `imdb_id`: Unique identifiers for the movie on TMDB and IMDB respectively.
- `popularity`: A calculated score representing how popular the film is.
- `budget`: The movie's total production cost in USD.
- `revenue`: The worldwide box office earnings in USD.
- `original_title`: The movie's original release title.
- `cast`: Principal actors, delimited by a pipe "|".
- `homepage`: The official promotional website for the film (if applicable).
- `director`: The filmmaker(s) involved (separated by "|" for co-directors)...
- `tagline`: The film's promotional slogan or catchphrase.
- `keywords`: Distinctive tags and themes associated with the movie.
- `overview`: A brief synopsis of the movie's storyline.
- `runtime`: The total duration of the film in minutes.
- `genres`: Movie categories, delimited by "|".
- `production_companies`: The studio(s) that backed and produced the film.
- `release_date`: The official premiere date.
- `vote_count`: The total number of audience ratings submitted.
- `vote_average`: The mean score given by viewers.
- `release_year`: The year the movie came out (ranging from 1960 to 2015).
- `budget_adj`: The production budget adjusted for inflation (in 2010 USD).
- `revenue_adj`: Box office returns adjusted for inflation (in 2010 USD).

## Analysis Questions
- Is there a clear link between a movie's popularity score and its financial earnings?
- Which movie genres are the most common within this dataset?
- Does a higher production budget translate to higher box office revenue?

## Data Collection & Wrangling
The data is stored in the `tmdb-movies.csv` file within this repository. This specific file is a curated version of Kaggle's [TMDB 5000 Movie Dataset](https://www.kaggle.com/tmdb/tmdb-movie-metadata), supplied specifically for the Udacity Data Analyst Nanodegree Program.

## Data Preprocessing
**Key Steps & Observations:**
1. The initial dataset contained 10,866 entries across 21 columns.
2. A single duplicate row was identified and subsequently removed.
3. Several columns were dropped entirely, as they weren't necessary for our specific analysis goals.
4. Missing values (NaNs) in essential columns were handled appropriately.
5. The `cast`, `director`, and `genres` fields contained multiple values grouped by a '|' delimiter, which required formatting to extract primary values.
6. The `release_date` column was converted to the correct data type.
7. A new `profit` column was engineered using the calculation: $profit = revenue - budget$.
8. The `vote_average` feature was transformed into a categorical variable to group rating brackets together.
9. The `profit` column was also binned into categories to simplify exploratory visuals.

## Exploratory Data Analysis (EDA)
Following the cleaning phase, the refined dataset held 10,840 records and 10 columns. At this stage, the data was free of nulls and duplicates, with properly formatted data types and newly appended categorical bins. We then conducted visual and statistical analyses to answer our primary questions.

### Q1: Is there a clear link between a movie's popularity score and its financial earnings?
> The data strongly suggests that films with higher popularity scores yield significantly greater box office revenues compared to less popular ones.

### Q2: Which movie genres are the most common within this dataset?
> - `Drama`, `Comedy`, and `Action` represent the top three most frequently produced genres out of the 10,839 analyzed films.
> - `Drama` is particularly dominant, accounting for roughly 22.6% of all movies in the dataset.

### Q3: Does a higher production budget translate to higher box office revenue?
> Yes, there is a distinct positive correlation between `budget` and `revenue`, showing that higher investments generally align with higher returns, aside from a few minor outliers.

## Tools & Libraries
- JupyterLab
- Python 3
- Pandas
- NumPy
- Matplotlib & Seaborn
