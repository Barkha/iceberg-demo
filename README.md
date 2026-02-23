# Apache Iceberg Beginner Demo

A hands-on demo project using PySpark + Apache Iceberg in Jupyter Notebooks.

## Prerequisites

- **Python 3.9+**
- **Java 11+** (required by Spark)

Install Java if needed (Ubuntu):

```bash
sudo apt update && sudo apt install -y default-jdk
java -version
```

## Setup

```bash
cd iceberg-demo
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

## Running the Demo

```bash
source .venv/bin/activate   # if not already activated
jupyter lab
```

Open and run each notebook in order:

1. **01_setup_and_first_table** — Initialize Spark + Iceberg, create your first table
2. **02_crud_operations** — INSERT, UPDATE, DELETE, and MERGE INTO
3. **03_time_travel** — Query historical snapshots and rollback
4. **04_schema_evolution** — Add/drop/rename columns safely
5. **05_partitioning** — Hidden partitioning and partition evolution

Each notebook is self-contained — just run cells top to bottom.

## How It Works

- Uses **PySpark** with the Iceberg runtime JAR (downloaded automatically on first run)
- Uses a **Hadoop catalog** backed by a local `warehouse/` directory — no external services needed
- Sample e-commerce order data is generated inline in each notebook

## Cleanup

To reset everything, delete the warehouse directory:

```bash
rm -rf warehouse/
```
