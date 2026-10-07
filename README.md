SWYNEX Final Data Analytics Project
Netflix Content Analytics — A Complete Case Study
Author: Shaik Deen MohammedInternship: Data Analytics @ SWYNEX Technologies

1. Problem Statement
Netflix hosts thousands of movies and TV shows from around the world,but the raw catalog data is messy — missing values, incorrect datatypes and misplaced entries make it impossible to analyze directly.

Business questions this project answers:

What is the overall composition of the catalog (movies vs shows)?
Which countries and genres drive Netflix's content?
How has content acquisition grown over time?
Which audience segment (ratings) does Netflix target?
Are there hidden patterns or anomalies in the catalog?
My job: clean the raw data → explore it → build an interactivedashboard → deliver business-ready insights.

2. Dataset Information
Item	Detail
Source	Netflix Movies & TV Shows (Kaggle)
Raw size	8,807 rows × 12 columns
Each row	One title (type, title, director, cast, country, date added, release year, rating, duration, genres)
Final clean size	8,797 rows × 14 columns · 0 missing values
3. Tools Used
Python (pandas, numpy) · Google Colab · matplotlib · Microsoft Power BI Desktop · GitHub

4. Project Pipeline
Raw CSV (8,807 rows, 4,307 missing values)        ↓  Data Cleaning (Python/pandas)Clean dataset (8,797 rows, 0 missing)        ↓  Exploratory Data Analysis (Python/matplotlib)7 insights + 6 charts        ↓  Interactive Dashboard (Power BI)4 KPIs + 5 charts + 3 slicers        ↓Business insights & recommendations
5. Part 1 — Data Cleaning
Problems found in the raw data:

4,307 missing values (director 2,634 · cast 825 · country 831 · date_added 10 · rating 4 · duration 3)
date_added stored as text instead of dates
3 rows had durations (e.g. "74 min") misplaced inside the rating column
What I did & why:

Checked and removed duplicates
Converted date_added from text → datetime (enables time analysis)
Moved misplaced durations from rating → duration
Filled missing director/cast/country with "Unknown" (deleting = losing 30% of data)
Filled missing ratings with "Not Rated" (standard industry label)
Removed 10 rows with no date (minimal loss)
📄 Full code: notebooks/SWYNEX_Task1.ipynb · cleaned file: data/netflix_cleaned.csv

6. Part 2 — Exploratory Data Analysis
Key statistics: 6,131 Movies · 2,666 TV Shows · average movie ≈ 100 min(shortest 3 min · longest 312 min)

#	Insight	Evidence
1	Movies dominate: 69.7% of catalog	
2	Additions grew steeply, peaked 2019 (2,016 titles), then dropped (pandemic + incomplete 2021)	
3	USA leads (2,812), India 2nd (972), UK 3rd (418)	
4	Top genres: International Movies, Dramas, Comedies	
5	TV-MA is the most common rating	
6	Typical movie = 80–120 min; outliers at 3 min and 312 min	
Anomaly found: "Pioneers: First Women Filmmakers" (1925) was addedto Netflix in 2018 — a 93-year gap. Netflix actively acquiresrestored classic content.

📄 Full code: notebooks/SWYNEX_Task2_EDA.ipynb

7. Part 3 — Interactive Dashboard (Power BI)
KPIs: Total Titles 8,797 · Movies 6,131 · TV Shows 2,666 · Avg Movie Length ~99.6 min

Interactive features: Type / Year / Rating slicers + click-to-cross-filter on every chart.

Full dashboardTV Show filter appliedCross-filtered on India

📊 Open with free Power BI Desktop: dashboard/Netflix_Dashboard.pbix

8. Key Business Insights
Movie-led strategy — 69.7% of the catalog is movies; series are the minority play
The 2015–2019 acquisition boom — content additions peaked at 2,016 titles in 2019; the post-2019 drop shows acquisition sensitivity to external shocks
Concentrated sourcing — 3 countries supply the bulk of content; regional expansion is a visible opportunity
Global-first catalog — "International Movies" is the #1 genre, confirming Netflix's localization strategy
Mature audience skew — TV-MA dominates; family/kids content is an underserved segment
Standard film lengths — the catalog favors ~100-min features; shorts are rare
Heritage content play — century-old restored films enter the catalog, serving niche audiences
9. What I Learned
Real data is always messy — cleaning is 60% of analytics work
Every cleaning decision is a trade-off (fill vs delete) that must be documented
EDA turns data into stories; anomalies are often the best stories
Dashboards make insights touchable for decision-makers
Tools are learnable: I started this internship with zero coding experience
10. Repository Structure
├── data/          → raw + cleaned CSVs├── notebooks/     → Task 1 (cleaning) & Task 2 (EDA) code├── dashboard/     → Power BI file + screenshots└── charts/        → 6 EDA charts
*Individual task repositories:
Task 1 (Cleaning): [https://github.com/SHAIK-DEEN-MOHAMMED/SWYNEX-Data-Cleaning-Preparation]
Task 2 (EDA): [https://github.com/SHAIK-DEEN-MOHAMMED/SWYNEX-Exploratory-Data-Analysis/tree/main]
Task 3 (Dashboard): [https://github.com/SHAIK-DEEN-MOHAMMED/SWYNEX-Interactive-Dashboard/tree/main/SWYNEX-task-3]
