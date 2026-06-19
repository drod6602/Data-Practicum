# Super Bowl Competitiveness Analysis

## Project Overview

This project analyzes Super Bowl competitiveness using historical box score data. The main goal is to understand how Super Bowl games have changed over time and what team-level statistics may be connected to closer or more one-sided games.

The original project idea focused only on final scores and point differential. After reviewing the scope of the project, I expanded the dataset to include team-level box score statistics because final scores alone did not provide enough data for a meaningful analysis.

This project now uses Super Bowl box score data to examine offensive production, turnovers, first downs, time of possession, and differences between teams.

## Research Question

The main research question is:

**How has Super Bowl competitiveness changed over time, and what team-level box score factors are associated with more balanced or one-sided games?**

Supporting questions include:

- Which Super Bowls had the largest difference in total yards?
- Which Super Bowls had the most combined turnovers?
- Have offensive totals changed by decade?
- Are games more one-sided when there is a large gap in total yards?
- Do turnovers help explain differences between teams?
- Has time of possession varied meaningfully across Super Bowls?

## Data Source

The data was collected from Pro Football Reference Super Bowl box score tables. Because the website blocks automated Python requests, the data was collected manually using the website’s table export tools.

Each Super Bowl box score was exported as a separate file, then placed into one ZIP folder. The Python script reads the ZIP file and combines the box score tables into structured datasets.

## Repository Files

This repository includes:

- `Data_Practicum_SB.ipynb`  
  Jupyter Notebook containing the Python code for reading, cleaning, analyzing, and visualizing the Super Bowl box score data.

- `SuperBowl Data_Merged.zip`  
  ZIP file containing the exported Super Bowl box score files.

- `README.md`  
  Overview of the project, data, methods, and purpose.

## Dataset Structure

The Python script creates two main datasets.

### Team-Level Dataset

The team-level dataset has one row per team per Super Bowl. Since each Super Bowl has two teams, this structure creates two observations for each game.

Important variables include:

- Super Bowl number
- Season
- Date
- Team
- Opponent
- First downs
- Rushing attempts
- Rushing yards
- Passing completions
- Passing attempts
- Passing yards
- Passing touchdowns
- Interceptions
- Sacks allowed
- Net passing yards
- Total yards
- Fumbles
- Fumbles lost
- Turnovers
- Penalties
- Penalty yards
- Third-down conversions
- Time of possession

### Game-Level Dataset

The game-level dataset has one row per Super Bowl. It summarizes each matchup by calculating combined totals and team differences.

Important variables include:

- Combined total yards
- Combined turnovers
- Combined first downs
- Combined penalty yards
- Total yards difference
- Turnover difference
- First down difference
- Penalty yard difference
- Time of possession difference
- Decade

## Data Cleaning Process

The notebook includes several cleaning and diagnostic steps to make sure the dataset is usable for analysis.

The cleaning process includes:

1. Reading all box score files from the ZIP folder
2. Converting Roman numerals into Super Bowl numbers
3. Cleaning and converting date values
4. Converting numeric variables from text into numeric data types
5. Regularizing team abbreviations by removing extra spaces and using uppercase values
6. Checking for missing values
7. Checking for sentinel values such as `NA`, `NULL`, `missing`, `-999`, and `9999`
8. Removing exact duplicate observations
9. Flagging possible near duplicates
10. Checking that each Super Bowl has exactly two team observations
11. Checking for out-of-range football statistics
12. Creating calculated variables such as third-down percentage and decade

Diagnostic print statements are included throughout the notebook so the cleaning process can be reviewed step by step.

## Analysis and Visualizations

The project includes summary tables and visualizations to explore Super Bowl trends.

Current charts include:

- Average team total yards by decade
- Average team turnovers by decade
- Combined total yards by Super Bowl
- Difference in total yards between Super Bowl teams
- Combined turnovers by Super Bowl
- Yardage difference compared to turnover difference
- Difference in first downs by Super Bowl
- Difference in time of possession by Super Bowl

These charts help show how Super Bowl games vary in offensive production, mistakes, and overall team balance.

## Current Progress

Completed so far:

- Selected Super Bowl competitiveness as the project topic
- Collected Super Bowl box score data
- Organized the box score files into a ZIP folder
- Built a Python script to read all files from the ZIP
- Created a team-level dataset
- Created a game-level dataset
- Added data cleaning checks required for the progress report
- Added diagnostic print statements
- Created summary tables and visualizations

## Next Steps

Future improvements may include:

- Adding final scores and point differential
- Classifying games as close games or blowouts
- Comparing point differential to total yards difference
- Comparing point differential to turnover difference
- Adding more visualizations focused on competitiveness
- Writing final conclusions based on the cleaned dataset

## Tools Used

This project uses:

- Python
- pandas
- NumPy
- matplotlib
- Jupyter Notebook
- GitHub

## Project Purpose

This project was created for Data Practicum. The purpose is to practice collecting, cleaning, organizing, analyzing, and presenting data in a reproducible way.
