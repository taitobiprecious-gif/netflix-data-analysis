# Netflix Data Analysis Using Python

A four-task data analysis project on the Netflix titles dataset, completed as part of the **Auspify Technologies Data Analysis Using Python Internship Program**. The project covers data cleaning, content type analysis, country-wise analysis, and release-year trend analysis.

**Author:** Precious Atanda
**Program:** Auspify Technologies, Data Analysis Using Python Internship

\---

## Project Overview

The dataset contains 8,790 Netflix titles (Movies and TV Shows) with 10 columns: title, type, director, country, date added, release year, rating, duration and genres. The internship requires any 4 of 6 tasks. I completed **Tasks 1 to 4**.

|Task|Title|Level|
|-|-|-|
|1|Netflix Data Cleaning \& Preparation|Easy|
|2|Content Type Analysis Dashboard|Easy|
|3|Country-Wise Netflix Content Analysis|Medium|
|4|Trend Analysis by Release Year|Medium|

## Tools Used

* Python 3
* pandas (data cleaning and aggregation)
* matplotlib and seaborn (visualization)
* Jupyter Lab

## Repository Structure

```
Netflix\\\_Data\\\_Analysis/
├── Dataset.csv                  # original data
├── netflix\\\_cleaned.csv          # output of Task 1, input to Tasks 2-4
├── task1\\\_cleaning/
│   └── task1\\\_cleaning.ipynb
├── task2\\\_content\\\_type/
│   ├── task2\\\_content\\\_type.ipynb
│   └── (chart images)
├── task3\\\_country/
│   ├── task3\\\_country\\\_analysis.ipynb
│   └── (chart images)
├── task4\\\_trends/
│   ├── task4\\\_trends.ipynb
│   └── (chart images)
└── README.md
```

## Task Summaries

### Task 1: Data Cleaning \& Preparation

* Imported the dataset and inspected its structure, types and missing values.
* Found missing values hidden as the text placeholder `'Not Given'` (2,588 in `director`, 287 in `country`). These are invisible to `isnull()`, so I counted them directly.
* Replaced the placeholders with `'Unknown'` instead of dropping the rows. About 90.6% of TV Shows have no director, so dropping them would have removed most of the TV content and distorted every later analysis.
* Removed 4 duplicate records. They had different `show\\\_id` values but identical title, type, release year, country and date added, so only a check on those columns finds them.
* Fixed formatting inconsistencies: stray whitespace, a line break inside a title, and `date\\\_added` converted to a datetime type.
* Standardized `rating` (merged `NR` and `UR` into `Not Rated`) and `duration\\\_unit` (`Seasons` into `Season`).
* Split `duration` into a numeric value and a unit, and created `year\\\_added` and `month\\\_added`.
* Exported the result to `netflix\\\_cleaned.csv` (8,786 rows, 14 columns).

### Task 2: Content Type Analysis

* Movies make up 69.7% (6,123) of the catalogue and TV Shows 30.3% (2,663).
* Built a bar chart and pie chart of the split, a line chart of titles added per year, and a rating mix by type.
* Titles added per year rose sharply from 2016. Movies peaked in 2019 and TV Shows in 2019 to 2020.
* TV-MA and TV-14 are the two most common ratings, so the catalogue skews toward teen and adult audiences.
* The typical movie runs 98 minutes, and about two thirds of TV Shows have a single season.

### Task 3: Country-Wise Content Analysis

* Excluded the 287 titles with an unknown country (about 3%) and ranked the rest.
* The United States leads with 3,240 titles, followed by India (1,056) and the United Kingdom (638).
* The top 3 countries supply 58.1% of known-country content, and the top 10 supply 78.0%.
* The Movie vs TV Show mix differs sharply by country. Pakistan (83.1%), South Korea (77.1%) and Japan (66.4%) are TV-heavy, while India is the most movie-heavy at 7.7% TV.

### Task 4: Trend Analysis by Release Year

* 84.8% of titles were released since 2010.
* Release volume peaked in 2018 with 1,144 titles. The biggest jump was in 2016 (+346 titles).
* Growth slowed after 2016 (62.3% in 2016, 14.3% in 2017) and declined after the 2018 peak.
* The 2021 figure is incomplete because the data ends in September 2021.
* Movies peaked in 2018 and TV Shows in 2020, suggesting a gradual shift toward series.

## Key Decisions and Limitations

* **Missing values were relabelled, not deleted.** Missing directors are concentrated in TV Shows, so dropping them would have biased the analysis toward Movies.
* **Country analysis counts one country per title.** Co-productions are credited to a single country, and titles with no country are excluded.
* **Release year is not the same as the year added to Netflix.** The two are analysed separately (Task 2 uses year added, Task 4 uses release year).
* **The data is a snapshot.** It covers titles in the catalogue up to September 2021, and the final year is incomplete.
* **The data counts titles, not viewing.** It cannot show audience demand, only what is in the catalogue.

## How to Run

1. Clone this repository.
2. Install the requirements: `pip install pandas matplotlib seaborn jupyterlab`
3. Open Jupyter Lab and run `task1\\\_cleaning.ipynb` first. It creates `netflix\\\_cleaned.csv`.
4. Run the notebooks for Tasks 2, 3 and 4 in any order. Each loads `netflix\\\_cleaned.csv`.

## Contact

Precious Atanda | https://www.linkedin.com/in/precious-atanda-623bb9346 | taitobiprecious@gmail.com

\#Auspify #AuspifyTechnologies #AuspifyInternship #AuspifyProjects

