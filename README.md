# 🇳🇱 visa_jobs_netherlands_tracker

A **data pipeline** to track **tech job opportunities in the Netherlands** 🇳🇱 that offer **visa sponsorship**, using **Databricks** for data processing and **Power BI** for visualization.

---

## 🎯 Purpose

This project supports international tech professionals by:

- 🔍 Collecting job listings from multiple platforms  
- ✅ Filtering companies that offer **visa sponsorship**  
- 📊 Displaying results in an interactive **Power BI** dashboard (with filters for stack, location, remote options, etc.)  
- 🤖 *(Coming soon)* Summarizing and recommending jobs using **Generative AI**

---

## 🧰 Tech Stack

| Component        | Technology                         |
|------------------|------------------------------------|
| Pipeline Engine  | Databricks (PySpark + Delta Lake)  |
| Job Sources      | Remote OK API, Landing.jobs API, Google Search |
| Data Processing  | Python, PySpark, Pandas            |
| Storage          | Delta Tables, CSV, Parquet         |
| Visualization    | Power BI                           |
| Automation       | Databricks Workflows, GitHub Actions |
| AI (Planned)     | OpenAI API (LLMs)                  |

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
## 📌 Data Sources

- 🇳🇱 [IND – Recognized Sponsors List](https://ind.nl/en/public-register-recognised-sponsors)
- 🌐 [Remote OK API](https://remoteok.com/api)
- 🌐 [Landing.jobs API](https://api.landing.jobs/docs)
- 🔎 Google Search: LinkedIn, Glassdoor, Indeed.nl, Relocate.me, Jobbatical (filtered manually)

---

## 🏗️ Data Architecture

This project follows the **Medallion Architecture** for organizing the data pipeline:

- **Bronze Layer**: Raw data from job platforms is collected and stored in its original form.
- **Silver Layer**: Data is cleaned and filtered (duplicates removed, visa sponsorship flagged, etc.).
- **Gold Layer**: Cleaned and aggregated data ready for analysis and Power BI.

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
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?logo=linkedin)](https://www.linkedin.com/in/danielwisouza/)

---

## 📄 License

MIT License
