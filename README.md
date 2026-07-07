## 🎬 Movie Data Analytics Dashboard

An end-to-end data analytics project on a 9,800+ movie dataset (TMDB) — covering **Python data cleaning** and an interactive **Power BI dashboard**.

---

## 📌 Project Overview

This project takes a raw, real-world messy movie dataset and turns it into a clean, and visually explorable analytics product. It demonstrates the full analytics workflow: **clean → structure → analyze → visualize**.

**Dataset:** TMDB Movies dataset (~9,827 movies), sourced from Kaggle.
**Tools used:** Python (Pandas, Matplotlib, Seaborn), Power BI Desktop.

---

## 🧩 Data Quality Issues Found & Fixed

The raw dataset had several real-world data quality problems that had to be resolved before analysis:

| Issue | Problem | Fix |
|---|---|---|
| `Release_Date` | Stored as text, not a proper date | Converted to datetime; extracted Year, Month, Decade |
| `Genre` | Multi-valued (comma-separated) in a single cell | Split into a normalized genre bridge table for accurate genre-wise counting |
| `Vote_Average` / `Vote_Count` | 100 movies had 0/0 (unrated placeholders) | Flagged with an `Is_Rated` boolean so they don't skew rating averages |
| `Original_Language` | Raw ISO codes (`en`, `ja`, `hi`) | Mapped to full readable language names |
| `Title` | 314 duplicate titles (different movies, same name — e.g. remakes) | Added a guaranteed-unique `Movie_ID` for reliable table relationships |

---

## 🛠️ Tech Stack & Workflow

### 1. Python — Cleaning & EDA
- Cleaned and transformed the raw CSV using **Pandas**
- Built a normalized **genre bridge table** (long format) to correctly handle multi-genre movies
- Exploratory analysis with **Matplotlib** / **Seaborn**: rating distribution, genre trends, popularity vs rating
- 📓 Notebook: Movie_Data_Cleaning_EDA.ipynb (https://github.com/ipshitav71-wq/movie-data-analytics-dashboard/tree/main)

### 2. Power BI — Interactive Dashboard
- Data model built on the cleaned CSV outputs, with a proper one-to-many relationship (`movies` → `movie_genres`)
- Custom DAX measures for KPIs (Total Movies, Avg Rating, Rated Movies %, Total Genres)
- Dashboard includes: KPI summary cards, year-wise release trend, genre-wise distribution and rating analysis, language breakdown, and a movie poster gallery (using Image URL data category)
- 📊 File: [`powerbi/Movie_Analytics_Dashboard.pbix`](https://github.com/ipshitav71-wq/movie-data-analytics-dashboard/tree/main)

---

## 📸 Dashboard Preview

*(Add screenshot here — e.g. `![Dashboard](screenshots/dashboard_overview.png)`)*

---

## 🔑 Key Insights

- Movie output has grown sharply since the 2000s, with a steep rise in recent years
- **Drama** and **Comedy** are the most frequently produced genres, but genres like **History** and **War** tend to have higher average ratings despite lower volume
- English-language films dominate the dataset (~79%), followed by Japanese and Spanish
- About 1% of movies in the dataset have no rating data (flagged and excluded from average calculations to avoid skew)

---

## 📂 Repository Structure

```
movie-data-analytics-dashboard/
├── README.md
├── requirements.txt
├── data/
│   └── mymoviedb.csv              # raw source dataset
├── notebooks/
│   └── Movie_Data_Cleaning_EDA.ipynb
├── powerbi/
│   └── Movie_Analytics_Dashboard.pbix
└── screenshots/
    └── dashboard_overview.png
```

---

## ⚙️ How to Run

**Python:**
```bash
pip install -r requirements.txt
jupyter notebook notebooks/Movie_Data_Cleaning_EDA.ipynb
```

**Power BI:**
Open `powerbi/Movie_Analytics_Dashboard.pbix` in Power BI Desktop.

---

## 📝 Note

Dataset sourced from Kaggle (TMDB Movies dataset). All cleaning, analysis, and dashboard design done independently for portfolio purposes.

---

**Author:** Ipshita Verma
