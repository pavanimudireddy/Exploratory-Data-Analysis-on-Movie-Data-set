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
│ └── movies_metadata.csv # Original raw dataset CSV file
│
├── notebooks/
│ └── movie_analysis.ipynb # Jupyter notebook with data cleaning, transformation, and visualization
│
├── screenshots/ # Folder containing all screenshots for documentation
│ ├── distribution_vote_averages.png
│ ├── budget_vs_profit_scatterplot.png
│ ├── average_roi_by_genre.png
│ └── avg_budget_revenue_over_time.png
│
├── finalcleanedata.csv # Cleaned and processed dataset saved as CSV
│
└── README.md # Project overview, instructions, and insights

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

---

## How to Use

1. Clone the repository  
   ```bash
   git clone https://github.com/yourusername/moviemetadata-analysis.git
