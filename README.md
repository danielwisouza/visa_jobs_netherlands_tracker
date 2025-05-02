
# 🇳🇱 visa_jobs_netherlands_tracker

A data pipeline to track tech job opportunities in the Netherlands 🇳🇱 that offer **visa sponsorship**, using **Databricks** for data processing and **Power BI** for visualization.

---

## 🎯 Purpose

This project helps international tech professionals identify and analyze job opportunities in the Netherlands by:

- Collecting job listings from multiple platforms
- Filtering jobs by companies that offer **visa sponsorship**
- Displaying results with filters (stack, location, remote, etc.) in **Power BI**
- (Coming soon) Summarizing and recommending jobs with **Generative AI**

---

## 🧰 Tech Stack

| Component        | Technology                |
|------------------|---------------------------|
| Pipeline Engine  | Databricks (PySpark + Delta Lake) |
| Job Sources      | Remote OK API, Landing.jobs API, Google search |
| Data Processing  | Python, PySpark, Pandas    |
| Storage          | Delta Tables, CSV, Parquet |
| Visualization    | Power BI                   |
| Automation       | Databricks Workflows, GitHub Actions |
| AI (Future)      | OpenAI API (LLMs)          |

---

## 📦 Project Structure (WIP)

```
visa-jobs-nl-tracker/
├── notebooks/
│   ├── 01_scrape_jobs_api.py
│   ├── 02_parse_visa_list.py
│   ├── 03_process_jobs_data.py
│   └── 04_export_powerbi.py
├── data/
│   ├── bronze/               # Raw job listings (original data from sources)
│   ├── silver/               # Processed data (cleaned, filtered, normalized)
│   └── gold/                 # Final, aggregated data ready for analysis
├── dashboards/
│   └── jobs_nl_powerbi.pbix
├── utils/
│   ├── api_remoteok.py
│   ├── api_landingjobs.py
│   └── visa_list_parser.py
├── requirements.txt
└── README.md
```

---

## 📌 Data Sources

- 🇳🇱 [IND – Recognized Sponsors List](https://ind.nl/en/public-register-recognised-sponsors)
- 🌐 [Remote OK API](https://remoteok.com/api)
- 🌐 [Landing.jobs API](https://api.landing.jobs/docs)
- 🔎 Google Search: LinkedIn, Glassdoor, Indeed.nl, Relocate.me, Jobbatical (filtered manually)

---

## 🏗️ Data Architecture

This project follows the **Medallion Architecture** for organizing the data pipeline:

- **Bronze Layer**: Raw data from job platforms is collected and stored in its original form.
- **Silver Layer**: Data is processed and cleaned (duplicates removed, visa sponsorship filtered, etc.).
- **Gold Layer**: Cleaned and aggregated data ready for analysis and Power BI consumption.

---

## 🚧 Roadmap

- [ ] Integrate Landing.jobs and Remote OK APIs
- [ ] Parse and match IND visa sponsor companies
- [ ] Run full pipeline in Databricks
- [ ] Create Power BI dashboard
- [ ] Add GenAI module for job summarization and recommendations

---

## 👨‍💻 Author

**Daniel Willians** — Data Engineer | Azure | Databricks | Building tools to connect global talent with real opportunities.

---

## 📄 License

MIT License