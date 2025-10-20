# Exploratory-Data-Analysis-on-Movie-Data-set

This repository contains a comprehensive data cleaning, feature engineering, and exploratory data analysis (EDA) project on a movie metadata dataset.

---

## Project Overview

This project analyses a dataset of 40,000+ movies to uncover trends budget, revenue, genres, production companies, release dates, and ratings. The goal was to clean and transform the data to enable meaningful analysis and visualization on movie profitability, popularity, genres, languages, and trends over time.

---

## Data Cleaning and Feature Engineering

- Imported and explored the dataset
- Handled mixed data types in numerical columns like `budget` and `revenue`
- Parsed nested JSON-like columns (`genres`, `belongs_to_collection`, `production_companies`) using `ast.literal_eval`
- Created one-hot encoding columns for movie genres
- Extracted multiple producers from the production companies list
- Cleaned and standardized textual data such as movie titles and overviews
- Handled missing values by dropping or imputing where appropriate
- Removed duplicate records based on `id` and `imdb_id`
- Created new features such as:
  - `return_on_invest` (ROI)
  - `profit`
  - `blockbuster` flag based on revenue
  - `genre_count`
  - `homepage_present`
  - `TotalLanguages`
  - Number of producers (`Num_Producers`)
  - `release_year` extracted from `release_date`

---
## Tools Used

- Python 3.0  
- Pandas  
- NumPy  
- Matplotlib  
- Seaborn  
- Google Colab (for running and documenting analysis)

# Project Structure
movie-metadata-analysis/
│
├── data/
│   └── movies_metadata.csv
│
├── notebooks/
│   └── movie_analysis.ipynb
│
├── screenshots/
│   ├── distribution_vote_averages.png
│   ├── budget_vs_profit_scatterplot.png
│   ├── average_roi_by_genre.png
│   └── avg_budget_revenue_over_time.png
│
├── finalcleanedata.csv
│
└── README.md


## Visualization

- Distribution plots for ratings and popularity
- Scatter plots showing relationships between budget, revenue, profit, and ratings
- Barplots for genre impact, language-wise ratings, and presence of homepage on revenue
- Heatmaps for feature correlation
- Time series plots showing trends in budget, revenue, and ROI over the years
- Analysis of top popular movies

## Screenshots

## Budget vs project
<img width="691" height="547" alt="Budget vs profit" src="https://github.com/user-attachments/assets/a0d4df4f-2e58-4e0a-98e0-cb159f85b127" />

## Budget Revenue by Language
<img width="1001" height="578" alt="Budget Reavenus by language" src="https://github.com/user-attachments/assets/2285623a-69f6-4236-9af1-812b474f8e45" />

## Release Year vs Vote Average
<img width="575" height="455" alt="release year vs vote average" src="https://github.com/user-attachments/assets/fb7e62ca-7420-4211-acb6-9444e66bcfae" />

## ROI by Genre
<img width="1001" height="616" alt="ROI by Genre" src="https://github.com/user-attachments/assets/b4072284-b927-4664-88ea-9844ab9331d3" />

## Top 10 Movies
<img width="794" height="547" alt="top 10 movies" src="https://github.com/user-attachments/assets/cc3c1e45-7f4c-4ddb-b0cb-750dabf29b46" />

## Corelation
<img width="998" height="682" alt="corelation" src="https://github.com/user-attachments/assets/e3c404b2-44d3-4752-930d-e7af38f3758b" />

## Problems Faced and Solutions
### Problems Faced

- Mixed data types in columns such as `budget` and `revenue`.
- Columns like `genres` and `production_companies` contain nested JSON-like strings.
- Duplicate entries based on `id` and `imdb_id` causing data inconsistency.
- Missing or null values in key columns like `budget`, `runtime`, and `release_date`.
- Outliers in numeric columns, especially `popularity`.
- Inconsistent and complex nested data for multiple producers.
- Genre information stored as stringified lists making direct analysis difficult.
- Text columns such as `original_title` had inconsistent casing and whitespace.

### Solutions Implemented

- Used `pd.to_numeric()` with `errors='coerce'` to safely convert columns like `budget` and `revenue` to numeric types.
- Applied `ast.literal_eval()` to parse stringified JSON lists/dictionaries in columns such as `genres` and `production_companies`.
- Removed duplicate rows based on `id` and `imdb_id` to ensure unique movie entries.
- Dropped rows with missing critical data or filled missing values logically (e.g., replacing zero runtimes with the average runtime).
- Detected and clipped outliers in `popularity` using the Interquartile Range (IQR) method.
- Extracted multiple producers by looping through parsed lists and filled missing producer info with placeholder "no producer".
- Created one-hot encoded columns for each genre to facilitate analysis.
- Standardized text data by converting to lowercase and stripping leading/trailing spaces for consistency.

## 🧠 Conclusions and Insights

- 🎯 **Movies with larger budgets tend to earn higher revenue**, but this doesn't always translate to higher return on investment (ROI).
  
- 💡 **Genres such as Drama, Adventure, and Animation often show higher ROI**, suggesting quality storytelling or broader audience appeal.
  
- 🔥 **Popularity** moderately correlates with **vote averages**, but not significantly with actual **profitability**.

- 🌍 **English-language movies dominate** the dataset and typically have both higher budgets and higher revenue than non-English movies.

- 📦 **Movies that belong to a collection (e.g., sequels or franchises)** tend to perform better financially compared to standalone films.

- 🏭 **The number of production companies involved does not significantly affect a movie's profitability**, suggesting that collaboration doesn't guarantee success.

- 📈 **Average budgets and revenues have increased over the years**, indicating rising production and marketing costs in the film industry.

- 🧛 **Horror and Thriller movies** often have **lower budgets** but can yield high ROI when successful—this makes them attractive for low-cost, high-return projects.

- 🌐 Movies with **more spoken languages or a homepage** do not always perform better, but these may indicate broader distribution strategies.

- 🏆 **Top producers (like Universal, Warner Bros., etc.)** are commonly associated with high-revenue films, but not always high-ROI ones.

  ## 🔭 Future Work

- 🧠 **Machine Learning Models:** Apply regression or classification models to predict movie revenue, profitability, or popularity based on metadata.
- 📈 **Advanced Visualizations:** Use interactive dashboards with Plotly or Streamlit for better data exploration.
- 🌐 **NLP on Overview/Taglines:** Perform sentiment analysis or keyword extraction on movie overviews to find patterns in successful films.
- 🎞️ **Deep Dive on Collections:** Analyze how sequels or franchises perform compared to standalones across multiple metrics.
- 🕵️‍♂️ **Recommendation System:** Build a movie recommendation engine using content-based or collaborative filtering techniques.
- 🌍 **Geographical Trends:** Analyze production countries for regional insights on genres, budgets, and profitability.
- 📊 **Box Office vs Streaming:** Explore additional data sources to compare theatrical releases with streaming-first movies.


## 👤 Author
## 📬 Contact Me
**Pavani Mudireddy**
- 📧 Email: [yourname@gmail.com](pavanimudireddy2003@gmail.com)  
- 💼 LinkedIn: [Your LinkedIn](www.linkedin.com/in/pavani-mudireddy)  
- 🐙 GitHub: [your-username](https://github.com/pavanimudireddy)

