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
│   ├── bronze/
│   │   ├── scrape_visa_companies.py            # Lista empresas patrocinadoras de visto (bronze)
│   │   ├── scrape_remoteok_jobs.py              # Busca vagas Remote OK (bronze)
│   │   ├── scrape_landingjobs_jobs.py           # Busca vagas Landing.jobs (bronze)
│   │   └── scrape_google_jobs.py                 # Busca vagas via Google Search (LinkedIn, Glassdoor, Indeed, etc)
│   │
│   ├── silver/
│   │   ├── clean_visa_companies.py              # Limpeza de lista de empresas de visto
│   │   ├── clean_remoteok_jobs.py                # Limpeza e padronização vagas Remote OK
│   │   ├── clean_landingjobs_jobs.py             # Limpeza vagas Landing.jobs
│   │   ├── clean_google_jobs.py                   # Limpeza vagas extraídas por Google Search
│   │   └── match_jobs_with_visa.py               # Cruzar vagas com empresas que patrocinam visto
│   │
│   ├── gold/
│   │   └── export_to_powerbi.py                  # Exporta dados finais para visualização
│   │
│   └── utils/
│       ├── mount_storage.py
│       ├── spark_helpers.py
│       └── filters.py
│
├── utils/
│   ├── api_remoteok.py                           # API client Remote OK
│   ├── api_landingjobs.py                        # API client Landing.jobs
│   ├── google_search_jobs.py                      # Scripts para scraping/google search (manual ou semi automatizado)
│   └── visa_list_parser.py
│
├── config/
│   ├── mount_config.py
│   ├── constants.py
│   └── secrets_template.json
│
├── data/
│   ├── bronze/
│   │   ├── company_skilled_migrants/
│   │   ├── jobs_remoteok_raw/
│   │   ├── jobs_landingjobs_raw/
│   │   └── jobs_google_search_raw/
│   │
│   ├── silver/
│   │   ├── visa_companies_clean/
│   │   ├── jobs_remoteok_clean/
│   │   ├── jobs_landingjobs_clean/
│   │   └── jobs_google_search_clean/
│   │
│   └── gold/
│       └── jobs_with_visa_support/
│
├── dashboards/
│   └── jobs_nl_powerbi.pbix
│
├── tests/
│   ├── test_api_remoteok.py
│   ├── test_visa_cleaning.py
│   └── test_google_search_jobs.py
│
├── requirements.txt
├── README.md
└── .gitignore
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
