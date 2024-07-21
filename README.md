# Mobile Games A/B Testing

## Project Overview

Cookie Cats is a hugely popular mobile puzzle game developed by Tactile Entertainment. It is a classic "connect three" style puzzle game where players must connect tiles of the same color to clear the board and win levels. Throughout the game, players encounter gates that force them to wait a certain amount of time before progressing, or they can make an in-app purchase to continue immediately. This project analyzes the results of an A/B test where the first gate in Cookie Cats was moved from level 30 to level 40. The primary focus is on understanding the impact of this change on player retention.

## Contents

- [1. Data Collection](#1-data-collection)
- [2. Data Cleaning and EDA](#2-data-cleaning-and-eda)
- [3. Pre-processing and Modeling](#3-pre-processing-and-modeling)
- [4. Evaluation and Conceptual Understanding](#4-evaluation-and-conceptual-understanding)
- [5. Conclusion and Recommendations](#5-conclusion-and-recommendations)

## 1. Data Collection

The dataset contains information on player retention from a split test where the first gate in Cookie Cats was moved from level 30 to level 40. A total of 90,189 players installed the game while the A/B test was running. The dataset includes the following features:

| Feature          | Type    | Description                                                                              |
|------------------|---------|------------------------------------------------------------------------------------------|
| **userid**       | _id_    | A unique identifier for each player.                                                     |
| **version**      | _string_| Indicates the group (control: gate_30 or test: gate_40) to which the player was assigned. |
| **sum_gamerounds** | _integer_ | Total number of game rounds played by the player within the first 14 days post-installation. |
| **retention_1**  | _boolean_| Whether the player returned to play 1 day after installation.                           |
| **retention_7**  | _boolean_| Whether the player returned to play 7 days after installation.                          |

## 2. Data Cleaning and EDA

Exploratory Data Analysis (EDA) and data cleaning steps included:

- Handling missing values and ensuring data consistency.
- Visualizing retention rates and player engagement metrics.
- Investigating distributions and identifying outliers in the dataset.

## 3. Pre-processing and Modeling

- Pre-processing steps involved encoding categorical variables, normalizing numerical features, and splitting the data into training and testing sets.
- Statistical tests (chi-squared test) and Bayesian analysis were performed to compare retention rates between the control and test groups.

## 4. Evaluation and Conceptual Understanding

### 1-day Retention
- **Observation:** A slight decrease in 1-day retention from 44.8% (level 30) to 44.2% (level 40).
- **Statistical Analysis:** No significant difference in 1-day retention rates at the 5% significance level (chi-squared test). Bayesian analysis shows a 96.7% probability that retention is higher at level 30.

### 7-day Retention
- **Observation:** A decrease in 7-day retention from 19.0% (level 30) to 18.2% (level 40).
- **Statistical Analysis:** Significant difference at the 1% significance level (chi-squared test). Bayesian analysis confirms a 100% probability that retention is higher at level 30.

## 5. Conclusion and Recommendations

### Summary of Findings
- Strong evidence supports that the 7-day retention rate is higher when the gate is at level 30.
- Although the 1-day retention rate showed no statistically significant difference, Bayesian analysis suggests a preference for level 30.

### Recommendations
1. **Maintain the Gate at Level 30:** Retaining the gate at level 30 is recommended to optimize player retention.
2. **Collect Player Feedback:** Address early player disengagement by gathering feedback through in-app surveys.

---

## How to Run the Project

1. **Clone the repository:**
    ```sh
    git clone https://github.com/yourusername/mobile-games-ab-testing.git
    cd mobile-games-ab-testing
    ```

2. **Install the required packages:**
    ```sh
    pip install -r requirements.txt
    ```

3. **Run the Jupyter Notebook:**
    ```sh
    jupyter notebook
    ```

4. **Open and run the `AB Testing - Cookie Cats.ipynb` notebook to see the analysis and results.**

---
