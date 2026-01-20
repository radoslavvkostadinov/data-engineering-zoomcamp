# NYC Taxi Data Engineering Pipeline

The project demonstrates an end-to-end **data engineering pipeline** built around the **NYC Taxi dataset**. It covers the ingestion of raw CSV data into a PostgreSQL database and runs in a fully Dockerized environment to ensure reproducibility and ease of setup.

The setup is focused on best practices such as modular code, environment isolation, and pipeline orchestration. 

## 📁 Project Structure

```
└── pipeline/
    ├── .python-version        # Python version pinning
    ├── Dockerfile             # Docker image definition
    ├── docker-compose.yaml    # Multi-container orchestration
    ├── ingest_data.py         # Raw data ingestion logic
    ├── notebook.ipynb         # Initial setup for ingestion before transformed on ingest_data.py script
    ├── pyproject.toml         # Python dependencies and project config
    ├── uv.lock                # Locked dependency versions
    └── README.md              # Project documentation
```
