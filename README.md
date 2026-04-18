# Montgomery County Crime Analysis — Research Report & Visualisation

> **MSc Data Science | Kingston University | Applied Data Programming**
> Group project — team of 4 | My contributions: data wrangling & preprocessing pipeline, Q3 (hourly Pareto analysis), Q7 (COVID-19 impact analysis), geospatial visualisations

---

## Overview

A comprehensive exploratory data analysis of **306,094 crime incidents** reported in Montgomery County, Maryland (USA) between January 2018 and December 2022, sourced from the National Incident-Based Reporting System (NIBRS). The project answers 10 research questions through temporal, spatial, environmental and operational analysis, producing over 20 visualisations.

---

## Dataset

**Montgomery County Crime Statistics (NIBRS)** — 306,094 rows × 30 columns  
Variables: offence type, date/time, location (lat/lon, ZIP, district, beat, sector), police agency, victim count, response time  
Source: Montgomery County Police Department / FBI UCR Program  
Period: January 2018 – December 2022

---

## Tools & Technologies

- Python 3
- pandas, NumPy
- Matplotlib, Seaborn
- GeoPandas, Folium (geospatial mapping)
- SciPy, scikit-learn
- Jupyter Notebook

---

## Data Preprocessing Pipeline

- Dataset: 306,094 records, 30 columns → cleaned to 24 variables after preprocessing
- Removed columns with >90% missing data (Street Prefix: 95.5% missing, Street Suffix: 98.2% missing)
- Converted datetime fields from object strings to proper datetime format for time-series analysis
- Standardised column names (lowercase, underscores, stripped whitespace)
- Fixed incorrect state codes, standardised city names, repaired invalid ZIP codes
- Replaced incorrect latitude/longitude values with ZIP-code averages
- Filled missing crime names using NIBRS code mappings
- Removed duplicate entries — **0.88% noise reduction**
- Created engineered features: year, month, day_of_week, hour_of_day, duration_of_day, response_time_min

---

## Research Questions & Key Findings

| Q | Question | Key Finding |
|---|---|---|
| Q1 | Crime trends 2018–2022 | Crime peaked in 2017 (48,054) and declined to 23,380 by 2022. Theft, auto theft, and assault consistently dominated. |
| Q2 | Monthly & weekday patterns | Seasonal peaks identified; patterns shifted year-on-year; polar heatmap revealed cyclical trends |
| Q3 | Hourly crime patterns (Pareto) | 80% of daytime crime concentrated by 10 AM; 80% of nighttime crime by 11 PM. Property crimes dominate volume (83.9%); person crimes (16.1%) show steadier hourly behaviour |
| Q4 | Top crime districts | Silver Spring (44,213), Wheaton (40,182), Montgomery Village (37,664) — highest crime volumes |
| Q5 | ZIP/sector/beat distribution | Top ZIP: 20902 (17,848 incidents); crime-type composition varies significantly by ZIP |
| Q6 | Victim count vs crime type | Bubble matrix shows residential and street-vehicle environments drive highest victim exposure |
| Q7 | COVID-19 impact | Crime dropped ~18% during COVID (pre mean: 3,639 → during: 2,979 → post: 3,099). Property crimes drove most of the reduction |
| Q8 | Agency-level analysis | MCPD handled 225,197 incidents (dominant agency); all agencies showed COVID-related decline around April 2020 |
| Q9 | Environmental crime risk | Residential single-family (29,275) and street-in-vehicle (25,603) locations had highest incident counts |
| Q10 | Police response times | Silver Spring and Wheaton showed broadest response-time spreads; slowest median: 143.2 min |

---

## My Contributions

### Data Wrangling & Preprocessing
- Led the full **data quality assessment** — structure review, missing value analysis, type corrections, duplicate detection
- Implemented **location data repair**: fixing state codes, city name standardisation, ZIP-code imputation, lat/lon coordinate correction using ZIP-code averages
- Created **engineered temporal features** (year, month, hour_of_day, response_time_min) for time-series analysis
- Achieved **0.88% noise reduction** through systematic duplicate and anomaly removal

### Q3 — Hourly Crime Patterns (Pareto Analysis)
- Applied **Pareto analysis** to identify the "vital few" hours responsible for 80% of crime
- Built separate daytime (06:00–17:59) and nighttime (18:00–05:59) panels with rank-ordered bars and cumulative percentage curves
- Created **4-panel comparison dashboard** of person vs property crimes: yearly trend, hourly pattern (raw + smoothed), day-of-week distribution, and donut chart showing 83.9% property vs 16.1% person crimes

### Q7 — COVID-19 Impact Analysis
- Designed **phase-wise analysis** (Pre → During → Post COVID) with monthly rolling averages
- Built hourly heatmaps showing biggest declines during daytime and early-evening peak hours
- Created year-over-year category shift chart showing property crimes drove the 18% decline
- Phase-wise crime composition stacked bar: Pre (157,935) → During (59,960) → Post (55,207) incidents

---

## Visualisations Produced (20+ total)

Stacked bar charts · Line plots · Heatmaps · Polar/radar plots · Pareto charts · Bubble matrices · Geospatial bubble maps · Donut charts · Ridgeline plots · Pair plots · Environmental impact matrix · Phase-wise dashboards

---

MSc Data Science, Kingston University, London
