# Pre- vs Post-COVID Job Market Shifts in Data Scientist Roles

### Authors
Johnny Nguyen and Melanie Duong  
DATA 400 – Data Analytics Capstone
Dickinson College

---

## Project Overview

The COVID-19 pandemic significantly disrupted labor markets worldwide, particularly within technology-driven roles. This project examines how **Data Scientist job postings in the United States** changed before and after COVID, using job descriptions as a lens to understand shifting employer expectations.

By comparing **pre-COVID (2018–2019)** and **post-COVID (2022–2025)** job postings, this project analyzes changes in:
- Required skills and tools
- Language used in job descriptions
- Role specialization and structure
- Emergence of AI and generative AI terminology

The goal is to understand whether COVID led to fundamental changes in data roles or accelerated existing trends.

---

## Research Questions

- How did Data Scientist job descriptions change after COVID?
- Which technical skills remained stable across time?
- Which new skills or technologies gained prominence post-COVID?
- How did the structure and specialization of job postings evolve?

---

## Data Sources

This project uses two datasets:

1. **Jobspikr Data Scientist Job Postings (2018–2019)**  
   - U.S.-based Data Scientist job postings  
   - Used to represent the pre-COVID labor market

2. **Google Search Job Postings (2022–2025)**  
   - Aggregated job postings collected via Google Search  
   - Used to represent the post-COVID labor market

Both datasets are provided as CSV files and must be placed in the same directory as the Jupyter Notebook.

---

## Data Description

The primary dataset used for analysis, `job_postings_clean.csv`, is **generated programmatically by the Jupyter Notebook** during the data cleaning and preprocessing stage. This cleaned dataset combines and standardizes job postings from both source datasets into a single analysis-ready table.

Each row represents a **single Data Scientist job posting**. The cleaned dataset includes postings from two time periods:
- **Pre-COVID (2018–2019)** job postings from Jobspikr
- **Post-COVID (2022–2025)** job postings collected via Google Search

Key variables in the cleaned dataset include:
- `date`: Job posting date
- `year`: Year extracted from posting date
- `period`: Indicator for pre-COVID or post-COVID period
- `title`: Job title
- `description`: Full job description text
- `company`: Employer name
- `location_raw`: Original free-text job location
- `state_norm`: Standardized U.S. state abbreviation (best-effort)
- `region`: U.S. Census-style region (Northeast, Midwest, South, West, or Remote)
- `is_remote`: Indicator for remote job postings
- `role_group`: Categorized role type based on job title
- Keyword indicators and counts (e.g., `ai_word`, `genai_any`, `python_any`)

During preprocessing, job postings without valid dates were removed, text fields were cleaned, and postings were filtered to **Data Scientist roles only** for comparability. To reduce geographic bias, a matched sample was created based on region and remote status, resulting in equal-sized pre- and post-COVID samples used in the main analysis.


---

## Methodology

### Data Cleaning and Standardization
- Standardized column names across datasets
- Parsed posting dates, job titles, locations, and descriptions
- Removed postings without valid dates
- Focused on **Data Scientist roles only** for comparability

### Matching for Comparability
To ensure a fair comparison between periods:
- Job postings were matched by **U.S. region** (Northeast, Midwest, South, West)
- Remote postings were treated as a separate category
- Final matched sample includes an equal number of pre- and post-COVID postings

### Analysis Techniques
- Exploratory Data Analysis (EDA)
- Keyword frequency analysis
- Word clouds for qualitative comparison
- TF-IDF + KMeans clustering (k = 3)
- Simple linear regression controlling for region and remote status
- Trend analysis within post-COVID postings (2022–2025)

---

## Exploratory Analysis

Exploratory analysis focused on:
- Posting frequency patterns over time
- Geographic distribution of job postings
- Common keywords in job descriptions

Visualizations such as time-series plots, bar charts, and word clouds were used to identify initial patterns and guide further analysis.


---

## Key Findings

- **Core data skills** such as Python and SQL remained consistently important across both periods
- **AI-related language increased significantly** after COVID
- **Generative AI terminology** appears almost exclusively in post-COVID job descriptions
- Job descriptions became **more specialized and diverse** after COVID
- Clustering results suggest a broader range of Data Scientist role types in the post-COVID period

---

## Files in This Repository

- `Pre_Post_COVID_Job_Market_Project.pdf`  
  Final project report/presentation summarizing the analysis, findings, and interpretations.

- `README.md`  
  Project overview, methodology, and key findings.

## Note on Data and Notebook

The original datasets and full Jupyter Notebook are not included in this repository because the dataset files are too large for GitHub upload. The PDF contains the final summarized results of the analysis.

---

## Installation & Setup

This project was developed using Python and Jupyter Notebook.

Required packages include:
- pandas
- numpy
- matplotlib
- scikit-learn
- wordcloud

All dependencies can be installed by running the first cell of the Jupyter Notebook.

---

## Limitations

- Data sources differ in collection methodology
- Geographic information is extracted from free-text location fields
- The project compares pre- and post-COVID periods but does not include postings from 2020–2021
- Results are descriptive and exploratory rather than causal

---

## Conclusion

This project shows that while foundational data skills remained stable across the COVID divide, the post-COVID labor market reflects increased specialization and a growing emphasis on AI and generative AI technologies. Job postings provide valuable insight into how external shocks reshape technical roles and employer expectations over time.

---

## References & Resources

- Jobspikr Job Postings Dataset  
- Google Search Job Postings  
- Scikit-learn Documentation  
- Matplotlib Documentation  

---

## Acknowledgments

Thanks to Professor Eren Bilen for guidance throughout the course and to the DATA 400 class for feedback during the progress presentation.

---

## Contact

For questions about this project, please contact:  
Johnny Nguyen (nguyenjo@dickinson.edu) or Melanie Duong (duongng@dickinson.edu)
Dickinson College
