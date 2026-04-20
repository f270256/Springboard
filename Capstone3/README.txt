README
======

Project name
------------
YouTube Trending Video Engagement and Reach (2024–2025)

About this project
------------------
This project studies YouTube trending videos across many countries. The purpose is to understand
what kind of trending videos get stronger engagement, how fast they enter trending list, and which
metadata patterns are connected with better performance.

Important update about data pipeline
------------------------------------
This project now clearly starts from the original raw Kaggle file (https://www.kaggle.com/datasets/asaniczka/trending-youtube-videos-113-countries/data):

- trending_yt_videos_113_countries.csv

From this raw file, the project creates a balanced analytical sample for:
- 2024: 100,000 rows
- 2025: 100,000 rows

Total final sample:
- 200,000 rows

The sample was created with:
- fixed seed = 42
- stratified annual sampling
- stratification keys = year, country, month

This process creates:
- youtube_2024_2025_balanced_sample.csv

Then the project creates two analysis files:
- yt_project_outputs/analysis_row_level.csv
- yt_project_outputs/analysis_video_level.csv

Main files
----------
00_create_2024_2025_sample.ipynb
01_data_wrangling.ipynb
02_exploratory_data_analysis.ipynb
03_preprocessing.ipynb
04_modeling.ipynb
Capstone_Final_Slides.pptx
Model_Metrics.txt
Capstone3_Final_Report.pdf

Recommended notebook order
--------------------------
Please run the notebooks in this order:
1. 00_create_2024_2025_sample.ipynb
2. 01_data_wrangling_revised.ipynb
3. 02_exploratory_data_analysis.ipynb
4. 03_preprocessing.ipynb
5. 04_modeling.ipynb

What each notebook is doing
---------------------------
01_data_wrangling:
- starts from the raw Kaggle CSV
- creates the balanced 2024 and 2025 sample
- checks data quality
- fixes dates and text fields
- creates row-level and video-level working files

02_exploratory_data_analysis:
- studies distributions and trends
- checks likes-to-views ratio
- looks at time to trend, weekday effect, language effect, and cross-country reach

03_preprocessing:
- creates engineered features for modeling
- prepares training and test datasets
- saves clean model-ready files

04_modeling:
- trains baseline Logistic Regression
- trains Random Forest model
- compares results
- reviews predictions against actual outcomes

Main data files
---------------
trending_yt_videos_113_countries.csv
- original raw Kaggle file

youtube_2024_2025_balanced_sample.csv
- balanced sample created from raw file
- 100,000 rows from 2024
- 100,000 rows from 2025

analysis_row_level.csv
- one row means one trending appearance
- used for row-level EDA, feature engineering, and modeling

analysis_video_level.csv
- one row means first observed trending appearance per video_id
- used for video-level descriptive analysis

Main findings in simple words
-----------------------------
- Most videos that trend do this very fast, usually in the first week after publish.
- Friday publish looked stronger than Sunday in median engagement in this sample.
- Language strategy matters for both engagement and cross-country spread.
- Random Forest model was better than Logistic Regression for this task.

Important limitation
--------------------
The dataset contains only videos that already trended.
Because of this, the project can explain patterns inside trending sample, but it cannot say the
true chance for any YouTube upload to trend.

Reproducibility note
--------------------
A fixed seed (42) was used in sampling and modeling steps so the workflow can be repeated in the
same way.
