# DA/BA Job Market Intelligence
### Decoding skill demand, salary premiums, and hiring hotspots from 1.3M LinkedIn job postings

[Live Dashboard →](https://public.tableau.com/app/profile/ragul.velmurugan/viz/DA-BA-Job-Market-Intelligence/Dashboard1)

---

## Key findings

- **Excel dominates** — appears in 60.3% of all DA/BA postings, more than any other tool
- **SQL commands the highest salary** — roles mentioning SQL average **$113,347/year**, the top-paying skill in the dataset
- **dbt is the fastest-rising niche skill** — highest avg salary at **$140K+** despite low volume, signaling premium demand
- **Texas leads hiring volume** — 80 DA/BA postings, ahead of CA (75) and VA (49)
- **968 DA/BA roles analyzed** across 34 US states from 123,849 total LinkedIn postings

---

## What this project does

Most job seekers apply blindly without knowing which skills actually drive salary or where demand is highest. This project analyzes 1.3M real LinkedIn job postings (2023–2024) to extract actionable intelligence for Data Analyst and Business Analyst candidates — mapping skill demand, salary premiums, and geographic hiring patterns into a single dashboard.

**Business questions answered:**
1. Which skills appear most in DA/BA job descriptions?
2. Which skills carry the highest salary premium?
3. Which US states have the most DA/BA openings?
4. How does average salary vary by state and work type?

---

## Dashboard

<img width="1194" height="793" alt="dashboard_preview png" src="https://github.com/user-attachments/assets/624e8c63-ba46-4486-aaa1-dfd0beead91d" />

Four views in one dashboard:
- **Skill Frequency** — horizontal bar chart, color-encoded by avg salary
- **Skill vs Salary** — bubble scatter, bubble size = frequency, position = salary
- **Salary by State** — bar chart sorted by avg salary, color gradient
- **Jobs by State** — US choropleth map, shading intensity = job count

---

## Tech stack

| Layer | Tools |
|---|---|
| Data source | LinkedIn Job Postings 2023–2024 (Kaggle, arshkon) |
| Data cleaning | Python · pandas |
| Skill extraction | Keyword-based NLP (custom SKILLS taxonomy) |
| SQL analysis | PostgreSQL-compatible queries |
| Visualization | Tableau |
| Environment | Jupyter Lab · Python 3.10 |

---

## Project structure

```
linkedin-job-market-intelligence/
├── data/
│   ├── raw/                    # Original Kaggle CSV (not committed — too large)
│   └── processed/
│       ├── da_ba_clean.csv     # 968 filtered DA/BA postings
│       ├── skill_stats.csv     # Skill frequency + avg salary table
│       └── state_summary.csv  # State-level job count + salary aggregates
├── notebooks/
│   └── 01_analysis.ipynb      # Full analysis pipeline
├── sql/
│   └── analysis_queries.sql   # Reference SQL queries
├── visuals/
│   ├── dashboard_preview.png  # Full dashboard screenshot
│   ├── skill_frequency.png
│   ├── skill_salary_scatter.png
│   ├── salary_by_skill.png
│   ├── top_states.png
│   └── remote_salary.png
└── README.md
```

---

## How to run locally

```bash
# 1. Clone the repo
git clone https://github.com/RXGUL/LinkedIn-job-market-intelligence.git
cd linkedin-job-market-intelligence

# 2. Install dependencies
pip install pandas matplotlib seaborn jupyter openpyxl

# 3. Download the dataset
# Go to: https://www.kaggle.com/datasets/arshkon/linkedin-job-postings
# Place postings.csv in data/raw/

# 4. Run the notebook
jupyter lab notebooks/01_analysis.ipynb
```

---

## Dataset

**LinkedIn Job Postings (2023–2024)** by arshkon on Kaggle  
123,849 total postings · 31 columns · filtered to 968 DA/BA roles  
[kaggle.com/datasets/arshkon/linkedin-job-postings](https://www.kaggle.com/datasets/arshkon/linkedin-job-postings)

---

## Skills taxonomy

13 skills tracked across all job descriptions:

`SQL` · `Python` · `Excel` · `Tableau` · `dbt` · `Snowflake` · `AWS` · `R` · `Looker` · `Azure` · `Spark` · `Statistics`

---

*Built by Ragul Velmurugan · MS Business Analytics & AI · UT Dallas · 2024*
