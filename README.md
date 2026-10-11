Cognifyz Task 4: Location-Based Restaurant Analysis

Open In Colab

Program: Cognifyz Technologies, Data Science / Machine Learning Internship Author: Pradeep Srinivas B

Overview

This project explores the geographical distribution of restaurants and how location relates to cuisine concentration, ratings, and price range. It uses a restaurant dataset with 9,551 records and 21 columns.

Objectives
Audit location data and identify missing, invalid, or placeholder coordinates.
Visualize the global distribution of restaurants.
Examine restaurant concentration in Delhi-NCR.
Compare restaurant counts and ratings across cities.
Identify common cuisines in New Delhi, Gurgaon, and Noida.
Compare locality-level ratings using minimum sample-size filters.
Analyze the relationship between price range and restaurant ratings.
Key Findings
Concentration: The dataset has 9,551 restaurants across 141 cities. New Delhi, Gurgaon, and Noida hold 80.3% of them (New Delhi alone: 5,473).
Cuisines: North Indian, Chinese, and Fast Food are the top three cuisines in all three major cities.
Best-rated locality in Delhi-NCR: Sector 29, Gurgaon (average 3.89 across 38 rated restaurants), closely followed by Cyber Hub (3.86, 41 restaurants). Their confidence intervals overlap, so the ranking is not decisive.
Price vs rating: Among rated restaurants, the average rating rises from 3.24 (price range 1) to 3.89 (price range 4), with a moderate correlation (Pearson r = 0.40). These are associations, not causal effects.
Data quality: 497 restaurants have placeholder (0, 0) coordinates (excluded from maps, leaving 9,054 usable locations), and 2,148 are unrated (rating 0, excluded from rating analysis). Counting unrated restaurants as real scores would exaggerate the price effect (2.00 to 3.82).
Preview

Show Image

Key Methods
Data inspection and validation with Pandas and NumPy.
Global geographical visualization with Plotly.
Delhi-NCR restaurant-density visualization with Matplotlib.
City, cuisine, and locality summaries with Pandas.
Locality rating comparison with approximate 95% confidence intervals.
Rating distributions and price-range comparisons with Seaborn.
Pearson and Spearman correlations for price range versus ratings.
Data Cleaning Decisions
Issue	Count	Treatment
Placeholder (0, 0) coordinates	497	Excluded from all maps
Unrated restaurants (rating = 0)	2,148	Excluded from all rating-based comparisons
Missing or out-of-range coordinates	0	None needed
Duplicate rows	0	None needed
Repository Structure
.
├── Task_4_Cognifyz_Location_Based_Analysis.ipynb   # Main analysis notebook
├── images/                                          # Screenshots used in this README
├── requirements.txt                                 # Python libraries
└── README.md
Dataset

The dataset is not included in this repository because redistribution permission has not been confirmed. Before running the notebook, upload the restaurant CSV to the notebook environment. The notebook searches /content first and then the current working directory for a .csv file.

Use only a dataset you are authorized to access and share. If the notebook finds multiple CSV files, make sure the intended restaurant dataset is the one selected.

How to Run in Google Colab
Open the notebook in Google Colab using the badge at the top of this page.
Upload the restaurant CSV using the Files panel.
Choose Runtime → Restart session and run all.
Review the outputs and verify that the summary figures match the fresh run.
Libraries

See requirements.txt.

Limitations
The dataset is heavily concentrated in Delhi-NCR and does not represent all cities equally.
Some localities and cities have small samples (the top-rated cities have only about 20 rated restaurants each), so their average ratings are less stable.
About 22% of restaurants are unrated and are excluded from rating comparisons.
The analysis identifies associations, not causal relationships.
Map and visualization rendering can depend on the notebook environment and network availability. The interactive Plotly map may not display in GitHub's notebook viewer, so use Colab or the preview image above.
Future Work
Build an interactive city and locality filter dashboard.
Add interactive Delhi-NCR density maps (for example with folium).
Model ratings while controlling for cuisine and price range, for example with regression.
Explore vote-weighted locality comparisons.

Created as an internship analysis project for learning and portfolio demonstration.
