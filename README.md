# IMDB Web Scraping Pipeline

A comprehensive Python-based data pipeline that scrapes movie information from IMDB across multiple genres and stores the data in a PostgreSQL database.

## Project Overview

This project automates the collection of movie data from IMDB's website, extracting detailed information about the first 10,000 movies from 14 different genres. The pipeline is built using Python, BeautifulSoup for web scraping, pandas for data manipulation, and SQLAlchemy for database operations.

## Features

- **Multi-Genre Scraping**: Extracts data from 14 movie genres including Action, Comedy, Drama, Horror, Sci-Fi, and more
- **Comprehensive Data Collection**: Captures 12+ data points per movie including ratings, duration, cast, gross revenue, and metadata
- **Data Cleaning & Processing**: Automated data cleaning pipeline that handles missing values, data type conversions, and formatting
- **Database Integration**: Exports cleaned data to PostgreSQL database for analysis and reporting
- **Modular Architecture**: Organized notebook structure for easy maintenance and updates

## Data Points Collected

For each movie, the pipeline extracts:
- **Title**: Movie name
- **Release Year**: Year of release
- **Maturity Rating**: Content rating (G, PG, R, etc.)
- **Duration**: Runtime in minutes  
- **Genre**: Movie genres
- **User Rating**: IMDB user rating (1-10 scale)
- **Meta Score**: Metacritic score
- **Gross Revenue**: Box office earnings
- **Vote Count**: Number of user ratings
- **Description**: Plot summary
- **Director**: Film director
- **Stars**: Main cast members
- **Thumbnail**: Movie poster URL

## Project Structure

```
├── main.ipynb              # Entry point - runs the entire pipeline
├── pipeline.ipynb          # Orchestrates genre-specific notebooks  
├── database.ipynb          # Exports data to PostgreSQL
├── README.md              # Project documentation
└── genres/                # Individual genre scraping notebooks
    ├── action.ipynb
    ├── comedy.ipynb
    ├── drama.ipynb
    ├── horror.ipynb
    ├── sci-fi.ipynb
    ├── thriller.ipynb
    ├── romance.ipynb
    ├── crime.ipynb
    ├── fantasy.ipynb
    ├── mystery.ipynb
    ├── adventure.ipynb
    ├── animation.ipynb
    ├── action-comedy.ipynb
    └── romantic-comedy.ipynb
```

## Workflow

1. **Genre-Specific Scraping**: Each notebook in `/genres` scrapes 10,000 movies from a specific IMDB genre page
2. **Data Aggregation**: `pipeline.ipynb` runs all genre notebooks and combines their dataframes
3. **Data Cleaning**: Automated cleaning processes handle data type conversions, missing values, and formatting
4. **Database Export**: `database.ipynb` exports the master dataframe to PostgreSQL
5. **Pipeline Execution**: `main.ipynb` serves as the entry point to run the entire pipeline

## Technologies Used

- **Python**: Core programming language
- **BeautifulSoup**: HTML parsing and web scraping
- **Pandas**: Data manipulation and analysis
- **NumPy**: Numerical computing
- **SQLAlchemy**: Database ORM and connectivity
- **PostgreSQL**: Database for data storage
- **Requests**: HTTP library for web requests
- **Jupyter Notebooks**: Development environment

## Database Integration

The pipeline includes PostgreSQL integration with the following configuration:
- **Server**: localhost
- **Database**: capstone  
- **Table**: imdb
- **Credentials**: postgres/postgres
- **Port**: 5432

## Getting Started

1. Ensure all required Python packages are installed
2. Set up PostgreSQL database with the specified credentials
3. Run `main.ipynb` to execute the entire pipeline
4. Data will be automatically scraped, cleaned, and stored in the database

## Data Volume

The pipeline processes approximately **140,000 movie records** (10,000 per genre × 14 genres), providing a comprehensive dataset for movie analysis and machine learning applications.