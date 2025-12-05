# Student Engagement Study - STA304 Fall 2024

**Course:** STA304: Surveys, Sampling and Observational Data  
**Term:** Fall 2024  
**University:** University of Toronto

## Project Overview

This repository uses statistical methods to analyze factors influencing student engagement in extracurricular activities. The study examines relationships between students' participation in extracurriculars and various factors such as study time, work hours, financial necessity, and family supportiveness.

The analysis focuses on understanding how these independent variables affect the likelihood of student engagement (`activities_status`).

## Methodology

The study employs several statistical techniques to analyze the survey data (`survey_respond_clnd.csv`):

### 1. Sampling Design
- **Simple Random Sampling (SRS):** Power analysis and sample size calculations were performed to ensure statistical validity.
- **Sample Selection:** Random samples were drawn using set seeds (`002`, `212`) for reproducibility.

### 2. Statistical Analysis
The following tests and models were used to explore the data:

- **Two-Sample Proportion Tests:**
    - To compare activity status between students who work vs. those who don't.
    - To compare activity status between students with different study habits.
- **Linearity Assumption Checks:**
    - Scatter plots (with jitter) to check for linear relationships between activity status and predictors (Study Time, Travel Time, Work Time, Necessity Scale).
- **Logistic Regression Models:**
    - **Simple Logistic Regression:** Modeling `activities_status` against `necessity_scale` and `supportiveness`.
    - **Multiple Logistic Regression:** Combining multiple predictors to assess their joint effect on engagement.
    - **Variance Inflation Factor (VIF):** Used to check for multicollinearity among predictors.
- **Pearson's Chi-Square Test:**
    - To test independence between `favorite_activity` and `activity` type.

## Repository Structure

The repository is organized as follows:

- **`data/`**: Contains the raw and processed data.
    - `survey_respond_clnd.csv`: The cleaned survey response dataset.
    - `Codebook.pdf`: Description of the variables in the dataset.
- **`scripts/`**: Contains the code used for analysis.
    - `sta304_analysis.Rmd`: The R Markdown file containing all data loading, cleaning, and statistical analysis code.
- **`reports/`**: Contains the final outputs.
    - `STA304 Final Report.pdf`: The detailed final report of the study findings.

## Usage

This project is implemented in R. To run the analysis:

1.  Open `scripts/sta304_analysis.Rmd` in RStudio.
2.  Ensure you have the required R packages installed:
    - `readr`
    - `dplyr`
    - `broom`
    - `gt`
    - `car`
    - `ggplot2`
    - `tidyr`
    - `pander`
3.  Adjust the file path in the `read_csv` call to point to `../data/survey_respond_clnd.csv` (relative path recommended).
4.  Knit the R Markdown file to generate the analysis report.