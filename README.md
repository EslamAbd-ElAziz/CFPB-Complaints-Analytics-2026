# CFPB Consumer Complaints Analytics

> An end-to-end data analytics project exploring U.S. consumer financial complaints using Python, PostgreSQL, Power BI, and Tableau.

## Table of Contents
- [Project Overview](#project-overview)
- [Business Questions](#business-questions)
- [Dataset](#dataset)
- [Tools and Technologies](#tools-and-technologies)
- [Project Workflow](#project-workflow)
- [Key Performance Indicators](#key-performance-indicators)
- [Team and Responsibilities](#team-and-responsibilities)
- [Repository Structure](#repository-structure)
- [Project Status](#project-status)
- [Instructor](#instructor)
- [Project Resources](#project-resources)

## Project Overview

The **CFPB Consumer Complaints Analytics** project analyzes consumer complaints submitted to the **Consumer Financial Protection Bureau (CFPB)** about financial products and services, including credit reporting, banking, debt collection, and lending.

The project uses an approximately **6.5 million-record dataset covering January 1 to November 19, 2026** to transform raw complaint data into meaningful business insights. The analysis focuses on complaint patterns, company response performance, geographic distribution, and response timeliness.

The overall objective is to build a complete analytics workflow, from data collection and preparation to database modeling, SQL analysis, and interactive business intelligence dashboards.

## Business Questions

This project aims to answer the following questions:

1. Which financial products and complaint issues receive the highest number of complaints?
2. How do complaint volumes change over time, particularly month over month?
3. Which financial companies receive the most complaints?
4. How do companies respond to complaints (for example, explanation, monetary relief, or complaints still in progress)?
5. Which U.S. states have the highest complaint volumes?
6. How long does it take for complaints to be sent to companies?
7. What percentage of complaints receive a timely response?

## Dataset

- **Source:** [CFPB Consumer Complaint Database](https://www.consumerfinance.gov/data-research/consumer-complaints/)
- **Coverage:** January 1 – November 19, 2026
- **Approximate volume:** 6.5 million complaints
- **Data type:** Consumer complaints about financial products and services

The dataset is collected from the CFPB public database and prepared for analysis through a Python-based data-cleaning process.

> **Data note:** The record count and coverage period describe the dataset snapshot used in this project. Update them if the source data is refreshed.

## Tools and Technologies

| Tool | Purpose |
|---|---|
| Python | Data collection, processing, and analysis |
| Pandas | Data cleaning and transformation |
| PostgreSQL | Relational database and analytics warehouse |
| SQL | Data modeling, KPI calculations, queries, and views |
| Power BI | Interactive dashboards and reporting |
| Tableau | Interactive data visualization |
| Git & GitHub | Version control and project collaboration |

## Project Workflow

The project is organized into the following phases:

| Phase | Description | Tools | Status |
|---|---|---|---|
| 1. Data Collection | Download complaint records from the CFPB database | Python / CFPB API | Completed |
| 2. Data Cleaning | Remove unnecessary columns, handle missing values, correct data types, and standardize column names and values | Python, Pandas | Completed |
| 3. SQL Data Warehouse | Design a star schema with fact and dimension tables, then load the cleaned data | PostgreSQL | In Progress |
| 4. SQL Analysis | Develop KPI queries, rankings, window functions, and reusable views | SQL | Planned |
| 5. Exploratory Data Analysis | Explore trends, distributions, leading products, issues, and companies | Python | Planned |
| 6. Dashboards | Build executive-level and detailed analytical dashboards | Power BI, Tableau | Planned |
| 7. Insights and Presentation | Summarize findings, develop recommendations, and prepare the final presentation | Documentation / Presentation | Planned |

## Key Performance Indicators

The following KPIs will be used to evaluate complaint volume and company response performance.

| KPI | Definition |
|---|---|
| Total Complaints | Count of unique complaint IDs |
| Total Companies | Number of distinct companies receiving complaints |
| Average Daily Complaints | Average number of complaints received per day |
| Monthly Complaints Trend | Number of complaints received each month |
| Timely Response Rate | Percentage of complaints that receive a timely company response |
| In-Progress Rate | Percentage of complaints that remain in progress |
| Relief Rate | Percentage of closed complaints resulting in monetary or non-monetary relief |
| Average Days to Send to Company | Average time between the date a complaint is received and the date it is sent to the company |
| Top Products, Issues, Companies, and States | Rankings based on complaint volume |

## Team and Responsibilities

Add the names of the project contributors in the table below.

| # | Team Member | Role |
|---|---|---|
| 1 | Eslam Magdy | Team Lead |
| 2 | Eslam Magdy & Mohamed Nabil | Data Engineer — Data Collection and SQL Warehouse |
| 3 | Mohamed Nabil | Python Data Analyst — Data Cleaning and Exploratory Analysis |
| 4 | _Name_ | SQL Analyst — KPIs, Queries, and Views |
| 5 | _Name_ | BI Developer — Power BI and Tableau |

### Role Details

- **Team Lead:** Plans tasks and deadlines, reviews team deliverables, manages the GitHub repository, and coordinates the final presentation.
- **Data Engineer:** Designs the star schema, loads the cleaned data into PostgreSQL, and documents the database.
- **Python Data Analyst:** Performs data cleaning and exploratory analysis, and prepares analytical charts and findings in notebooks.
- **SQL Analyst:** Develops KPI queries and reusable views, and validates SQL results against Python analysis.
- **BI Developer:** Builds the Power BI and Tableau dashboards, focusing on visual design, usability, and interactivity.

## Repository Structure

```text
cfpb-consumer-complaints-analytics/
│
├── data/
│   ├── raw/                     # Original source data
│   └── cleaned/                 # Cleaned and prepared data
│
├── notebooks/
│   └── complaints_data_cleaning.ipynb
│
├── sql/
│   ├── schema/                  # Database and table definitions
│   ├── load/                    # Data loading scripts
│   └── analysis/                # KPI queries and analytical views
│
├── powerbi/                     # Power BI reports (.pbix)
├── tableau/                     # Tableau workbooks (.twbx)
├── docs/                        # Documentation, screenshots, and presentation
│
└── README.md
```

> Keep large raw and cleaned datasets outside GitHub when repository size limits make direct storage impractical. Add instructions or a download link in this section when the data-sharing location is finalized.

## Project Status

**Current status:** In Progress

- [x] Data collection
- [x] Data cleaning
- [ ] PostgreSQL data warehouse
- [ ] SQL analysis and KPI development
- [ ] Exploratory data analysis
- [ ] Power BI and Tableau dashboards
- [ ] Final insights and presentation

## Instructor

_Instructor name_

## Project Resources

- **Official data source:** [CFPB Consumer Complaint Database](https://www.consumerfinance.gov/data-research/consumer-complaints/)
- **Project files (Google Drive):** [Open project folder](https://drive.google.com/drive/folders/1t9YN8XZRleKrMgYsO20TRaq-fTv2zWpH)

---

*This README will be updated as the project progresses and additional analyses, database objects, and dashboards are completed.*
