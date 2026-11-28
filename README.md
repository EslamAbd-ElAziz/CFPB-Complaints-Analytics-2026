# CFPB Consumer Complaints Analytics

> An end-to-end data analytics project exploring U.S. consumer financial complaints using Python, PostgreSQL, and Power BI.

## Table of Contents
- [Project Overview](#project-overview)
- [Business Questions](#business-questions)
- [Dataset](#dataset)
- [Tools and Technologies](#tools-and-technologies)
- [Project Workflow](#project-workflow)
- [Data Model](#data-model)
- [Key Performance Indicators](#key-performance-indicators)
- [Dashboard Pages](#dashboard-pages)
- [Key Findings So Far](#key-findings-so-far)
- [Team and Responsibilities](#team-and-responsibilities)
- [Repository Structure](#repository-structure)
- [Project Status](#project-status)
- [Instructor](#instructor)
- [Project Resources](#project-resources)

## Project Overview

The **CFPB Consumer Complaints Analytics** project analyzes consumer complaints submitted to the **Consumer Financial Protection Bureau (CFPB)** about financial products and services, including credit reporting, banking, debt collection, and lending.

The project uses a dataset of **6,634,578 complaints covering January 1 to November 19, 2026** to transform raw complaint data into meaningful business insights. The analysis focuses on complaint patterns, company response performance, geographic distribution, and response timeliness.

The overall objective is to build a complete analytics workflow, from data collection and preparation to database modeling, SQL analysis, and an interactive Power BI dashboard.

## Business Questions

This project aims to answer the following questions:

1. Which financial products and complaint issues receive the highest number of complaints?
2. How do complaint volumes change over time, particularly month over month?
3. Which financial companies receive the most complaints?
4. How do companies respond to complaints (for example, explanation, monetary relief, or complaints still in progress)?
5. Which U.S. states have the highest complaint volumes?
6. How long does it take for complaints to be sent to companies?
7. What percentage of complaints receive a timely response?
8. Which companies and products have the highest relief rate?
9. What does the picture look like once credit reporting complaints are excluded?

## Dataset

- **Source:** [CFPB Consumer Complaint Database](https://www.consumerfinance.gov/data-research/consumer-complaints/)
- **Coverage:** January 1 – November 19, 2026
- **Volume:** 6,634,578 complaints, 3,989 companies, 11 products
- **Data type:** Consumer complaints about financial products and services

The dataset is collected from the CFPB public database and prepared for analysis through a Python-based data-cleaning process.

> **Data note:** November 2026 is a partial month (data ends on November 19). The record count and coverage period describe the dataset snapshot used in this project. Update them if the source data is refreshed.

## Tools and Technologies

| Tool | Purpose |
|---|---|
| Python | Data collection, processing, and loading |
| Pandas | Data cleaning and transformation |
| SQLAlchemy | Loading data into PostgreSQL |
| PostgreSQL | Relational database and analytics warehouse |
| SQL | Data modeling, KPI calculations, queries, and views |
| Power BI | Interactive dashboards and reporting |
| Git & GitHub | Version control and project collaboration |

## Project Workflow

The project is organized into the following phases:

| Phase | Description | Tools | Status |
|---|---|---|---|
| 1. Data Collection | Download complaint records from the CFPB database | Python / CFPB API | Completed |
| 2. Data Cleaning | Remove unnecessary columns, handle missing values, correct data types, and standardize column names and values | Python, Pandas | Completed |
| 3. SQL Data Warehouse | Star schema with 1 fact and 6 dimension tables, primary/foreign keys, and indexes, loaded into PostgreSQL | PostgreSQL | Completed |
| 4. SQL Analysis | KPI queries, rankings, window functions, and dashboard views | SQL | Completed |
| 5. Power BI Dashboard | Connect to the star schema, build the data model and DAX measures, and design 5 report pages | Power BI | In Progress |
| 6. Insights and Presentation | Summarize findings, develop recommendations, and prepare the final presentation | Documentation / Presentation | Planned |

## Data Model

The warehouse uses a **star schema** in the PostgreSQL schema `complaints`:

- **Fact table:** `fact_complaints` (one row per complaint)
- **Dimensions:** `dim_date`, `dim_company`, `dim_product`, `dim_issue`, `dim_location`, `dim_response`

`dim_date` is linked to the fact table twice: by the date the complaint was received and by the date it was sent to the company.

## Key Performance Indicators

The following KPIs are used to evaluate complaint volume and company response performance.

| KPI | Definition |
|---|---|
| Total Complaints | Count of unique complaint IDs |
| Total Companies | Number of distinct companies receiving complaints |
| Average Daily Complaints | Average number of complaints received per day |
| Monthly Complaints Trend | Number of complaints received each month, with month-over-month change |
| Timely Response Rate | Percentage of complaints that receive a timely company response |
| In-Progress Rate | Percentage of complaints that remain in progress |
| Relief Rate | Percentage of closed complaints resulting in monetary or non-monetary relief |
| Average Days to Send to Company | Average time between the date a complaint is received and the date it is sent to the company |
| Top Products, Issues, Companies, and States | Rankings based on complaint volume |

## Dashboard Pages

The Power BI report is built on the star schema and contains five pages:

1. **Executive Overview:** KPI cards and monthly trend
2. **Trends and Products:** products, issues, and submission channels
3. **Geography:** complaints by state
4. **Company Performance:** complaint share, open complaints, and relief rate per company
5. **Excluding Credit Reporting:** companies and products once credit reporting is removed

## Key Findings So Far

- Credit reporting accounts for about **91%** of all complaints, and the three credit bureaus (Equifax, Experian, TransUnion) account for about **89%**.
- Texas, Florida, and California have the highest complaint volumes.
- The timely response rate is about **99.6%**, so relief rate is a better measure of company performance.
- Because credit reporting dominates the data, a dedicated page excludes it to reveal patterns in other products and companies.

## Team and Responsibilities

| # | Team Member | Role |
|---|---|---|
| 1 | Eslam Magdy | Team Lead |
| 2 | Eslam Magdy & Mohamed Nabil | Data Engineer — Data Collection and SQL Warehouse |
| 3 | Mohamed Nabil | Python Data Analyst — Data Cleaning and Exploratory Analysis |
| 4 | Maram Hamdey | SQL Analyst — KPIs, Queries, and Views |
| 5 | Sahar Mahmoud & Mahmoud Abdelaal | BI Developer — Power BI and Tableau |

### Completed Work
- **Data Collection, Cleaning, and SQL Warehouse:** Eslam Magdy and Mohamed Nabil
- **SQL Analyst, KPIs, Queries, and Views:** Maram Hamdey
  
### Role Details

- **Team Lead:** Plans tasks and deadlines, builds the Power BI data model and measures, reviews team deliverables, manages the GitHub repository, and coordinates the final presentation.
- **Power BI Developers:** Build the report pages, focusing on visual design, usability, and interactivity.

## Repository Structure

```text
cfpb-consumer-complaints-analytics/
│
├── data/                        # Not stored on GitHub (too large) - see Project Resources
│
├── notebooks/
│   └── complaints_data_cleaning.ipynb
│
├── sql/
│   ├── 01_schema_dimensions_fact.sql    # Star schema, keys, and indexes
│   ├── 02_kpi_queries.sql               # KPI and analysis queries
│   └── 03_dashboard_views.sql           # Dashboard views
│
├── powerbi/                     # Power BI report (.pbix)
├── docs/                        # Documentation, screenshots, and presentation
│
└── README.md
```

> Database credentials are stored in a local `.env` file that is **not** committed to the repository.

## Project Status

**Current status:** In Progress

- [x] Data collection
- [x] Data cleaning
- [x] PostgreSQL data warehouse
- [x] SQL analysis and KPI development
- [ ] Power BI dashboard
- [ ] Final insights and presentation

## Instructor

_Instructor name_

## Project Resources

- **Official data source:** [CFPB Consumer Complaint Database](https://www.consumerfinance.gov/data-research/consumer-complaints/)
- **Project files (Google Drive):** [Open project folder](https://drive.google.com/drive/folders/1t9YN8XZRleKrMgYsO20TRaq-fTv2zWpH)

---

*This README will be updated as the project progresses and additional analyses and dashboards are completed.*
