# NYC Taxi Data Engineering Pipeline

The project demonstrates an end-to-end **data engineering pipeline** built around the **NYC Taxi dataset**. It covers the ingestion of raw CSV data into a PostgreSQL database and runs in a fully Dockerized environment to ensure reproducibility and ease of setup.

The setup is focused on best practices such as modular code, environment isolation, and pipeline orchestration. 

## Project Structure

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

## Requirements
- Docker
- Python 3.10+ (for local development)
  
Optional (for local development without Docker):
- Python (version defined in `.python-version`)
- `pip` for dependency management

## How to test

### 1. Clone the repo

```bash
git clone https://github.com/radoslavvkostadinov/data-engineering-zoomcamp.git
cd "Workshop 1/pipeline"
```
Make sure you have Python 3.10+ installed. Create and activate your own virtual environment before running the locally.

```bash
# Activate your virtual environment
source .venv/bin/activate   # or your own venv

# Install dependencies
pip install --upgrade pip
pip install click pandas psycopg2-binary pyarrow sqlalchemy tqdm
```

### 2. Run with Docker (Recommended)

Build and start the pipeline using Docker Compose:

```bash
# Build and start containers
docker-compose up --build -d

# Run the pipeline inside the container
docker-compose exec pipeline python ingest_data.py

# Stop containers when done
docker-compose down
```
Happy Engineering!
