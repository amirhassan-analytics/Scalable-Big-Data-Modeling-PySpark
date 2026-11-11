# NASA Asteroid Risk Analysis — PySpark Lakehouse

Distributed data pipeline for the NASA Jet Propulsion Laboratory asteroid
dataset: **958,524 records, 45 features**. A modern rebuild of the original
university project (`Scalable-Big-Data-Modeling-PySpark`), reframed from a
machine-learning notebook into a production-style PySpark lakehouse —
the same pattern used for large-scale data engineering work.

## What it does

| Layer | What happens |
|---|---|
| Bronze | Raw NASA JPL data ingested as-is into Parquet, with source row counts recorded |
| Silver | Cleaned data: missing values imputed (regression / statistical), duplicates removed, 45 features reduced to the top 17 by correlation, normalised and vectorised |
| Gold | Analytics tables: hazardous-asteroid (PHA) classification results and K-Means orbital clusters (K=6) |
| Quality | Row-count, null-rate and schema checks at every layer — the pipeline fails if a layer loses data unexpectedly |

Results from the original analysis, kept as the Gold-layer output:
- **PHA classification (Random Forest): 100% recall, ~90% precision** — hazardous asteroids are never missed
- **Clustering (K-Means, K=6):** orbital groupings that differ from NASA's own class labels
- **Final dataset: 938,597 rows, 17 features** after cleaning

## Architecture

```
data/raw/asteroids.csv  (NASA JPL Small-Body Database)
      │  extract.py
      ▼
data/bronze/  (raw Parquet)
      │  transform.py — clean, impute, select features
      ▼
data/silver/  (cleaned Parquet, 17 features)
      │  lakehouse.py — write Gold tables
      ▼
data/gold/pha_classification/  +  data/gold/clusters/
```

## Quick start

```bash
# 1. Place the NASA JPL dataset in data/raw/ (see data/README.md)
# 2. Install dependencies (needs Java 11+ for Spark)
pip install -r requirements.txt

# 3. Run the whole pipeline
python -m src.run_pipeline

# 4. Check the outputs
ls data/gold/
```

Or in Docker (Spark + Python, no local Java needed):

```bash
docker compose up --build
```

## Project structure

```
├── README.md
├── docker-compose.yml
├── Dockerfile
├── requirements.txt
├── .env.example
├── src/
│   ├── config.py
│   ├── extract.py
│   ├── transform.py
│   ├── lakehouse.py
│   ├── classify.py
│   ├── cluster.py
│   ├── data_quality.py
│   └── run_pipeline.py
├── tests/
│   └── test_transform.py
├── data/
│   └── README.md
└── .github/workflows/ci.yml
```

## How this maps to my experience

This is the project behind **Big Data Processing with Apache Spark** on my CV
(Aug – Dec 2024, Università di Pisa). The rebuild adds the engineering the
original notebook lacked: layered storage, reproducible runs, data-quality
gates, and code a teammate can run without opening a notebook.

## Tech

Python · Apache Spark (PySpark) · Parquet · Docker · scikit-learn ·
pyspark.ml · pandas
