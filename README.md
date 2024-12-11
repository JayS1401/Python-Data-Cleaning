Movies Data Cleaning Project
Description
This project focuses on cleaning a dataset of movies, which includes various attributes such as movie titles, release years, genres, ratings, and more. The cleaned dataset is prepared for further analysis or visualization.
Table of Contents
Installation
Usage
Data Description
Data Cleaning Steps
License
Installation
To run this project, you need to have Python installed along with the following libraries:
bash
pip install numpy pandas matplotlib seaborn
Usage
Clone the repository:
bash
git clone https://github.com/JayS1401/movies-data-cleaning.git
cd movies-data-cleaning
Place your CSV file in the project directory.
Run the script:
bash
python your_script.py
Data Description
The dataset consists of 9999 rows and 9 columns with the following attributes:
MOVIES: Title of the movie.
YEAR: Year of release.
GENRE: Genre(s) of the movie.
RATING: IMDb rating.
ONE-LINE: Brief description of the movie.
STARS: Main actors/actresses.
VOTES: Number of votes received.
RunTime: Duration of the movie in minutes.
Gross: Total gross revenue.
Data Cleaning Steps
The following steps were taken to clean the dataset:
Loaded the dataset using pandas.
Extracted release years from strings and converted them to integers.
Handled missing values by filling them with appropriate defaults (e.g., filling missing years with '2020').
Cleaned genre and one-line description fields by removing unnecessary whitespace and newline characters.
Saved the cleaned dataset back into a CSV file for further analysis.
Example code snippet for data cleaning:
python
import pandas as pd

# Load the dataset
df = pd.read_csv("path_to_your_file.csv")

# Clean 'YEAR' column
df['YEAR'] = df['YEAR'].str.extract(r'(\d{4})').fillna('2020').astype(int)

# Clean 'GENRE' column
df['GENRE'] = df['GENRE'].str.strip().str.replace(r'\n', '', regex=True)

# Save cleaned data
df.to_csv("cleaned_movies.csv", index=False)
