# Player Rest and Playoff Performance Analysis

## Table of Contents
- [Overview](#overview)
- [Prerequisites](#prerequisites)
  - [Required Libraries](#required-libraries)
- [How It Works](#how-it-works)
  - [1. Data Retrieval](#1-data-retrieval)
  - [2. Data Processing](#2-data-processing)
  - [3. Statistical Analysis (T-Test)](#3-statistical-analysis-t-test)
  - [4. Results Interpretation](#4-results-interpretation)
  - [5. Visualizing the Data](#5-visualizing-the-data)
- [Instructions for Use](#instructions-for-use)
  - [1. Setting Up the Script](#1-setting-up-the-script)
  - [2. Running the Script](#2-running-the-script)
  - [3. Analyzing Results](#3-analyzing-results)
- [Conclusion](#conclusion)

---

## Overview

In this project, we explore whether players who rest more during the regular NBA season perform better in the playoffs. We retrieve player data from the official NBA API, comparing regular season minutes played and playoff performance (points scored). Using statistical tests, we assess if there is a significant difference in playoff performance between players who had less regular season playing time (i.e., rested players) and those who played more minutes.

---

## Prerequisites

### Required Libraries

To run this analysis, you will need the following Python libraries:

- **nba_api**: To fetch NBA data for players and games.
- **pandas**: For data manipulation and analysis.
- **numpy**: For numerical operations.
- **scipy**: For conducting statistical analysis, particularly the t-test.
- **matplotlib** and **seaborn**: For data visualization.

To install the required libraries, run this command:

```bash
pip install nba_api scipy statsmodels matplotlib seaborn
```

## How It Works

This project is designed to analyze the relationship between player rest during the regular season and their performance in the playoffs. Here's a breakdown of the process:

### 1. Data Retrieval
- **Player Data**: Using the `nba_api`, we fetch player performance data for both regular season games and playoff games. For each player, we get information on the total minutes played during the regular season and the average points scored during the playoffs.
- **Players**: The script retrieves data for specific players (e.g., LeBron James, Jimmy Butler, etc.) based on their names.

### 2. Data Processing
- **Regular Season Minutes**: The script calculates the total number of minutes each player played during the regular season.
- **Playoff Performance**: The average points scored per game in the playoffs for each player are calculated.
- **Rest Group Classification**: Players are categorized into two groups:
  - **Rested**: Players who played less than 2000 minutes in the regular season.
  - **Not Rested**: Players who played 2000 minutes or more.

### 3. Statistical Analysis (T-Test)
A **t-test** is used to compare the playoff performance (average points scored) between the "Rested" and "Not Rested" player groups. The goal is to determine if the players who had more rest during the regular season performed significantly better in the playoffs.

- **T-statistic**: Indicates the magnitude of the difference between the two groups.
- **P-value**: Helps us determine whether the difference is statistically significant. A p-value less than 0.05 generally indicates a significant difference.

### 4. Results Interpretation
Once the t-test is performed, the script displays the t-statistic and p-value. It also makes an interpretation based on the p-value, telling us whether there is a statistically significant difference in playoff performance between the rested and non-rested players.

### 5. Visualizing the Data
To make the results easier to understand, the script generates a **boxplot** that compares the average playoff points between the "Rested" and "Not Rested" groups.

---

## Instructions for Use

### 1. Setting Up the Script
To run the script:
- First, define the list of player names for whom you want to analyze the data (e.g., LeBron James, Jimmy Butler, etc.).
- Specify the season you want to analyze (e.g., 2020).

### 2. Running the Script
The script will:
- Retrieve the player data for both the regular season and the playoffs.
- Categorize players into "Rested" or "Not Rested" based on their regular season minutes.
- Perform a t-test to compare the playoff performance of the two groups.
- Display the results of the t-test and generate a boxplot to visualize the comparison.

### 3. Analyzing Results
After running the script, you'll receive the t-statistic and p-value, as well as a graphical representation of the data. For example, if the p-value is less than 0.05, the script will inform you that there is a statistically significant difference in playoff performance between the rested and non-rested players.

---

## Conclusion

This analysis provides insight into the impact of player rest on playoff performance. By comparing the performance of "rested" vs. "not rested" players, we use statistical analysis to determine if there is any meaningful difference. In the case of the example players, the results suggest that, at least for the 2020 season, there was no statistically significant difference in playoff performance based on rest.

While these results may not show a clear correlation for all players, the analysis offers a starting point for further exploration of how rest, injuries, and other factors might influence playoff success in the NBA.
