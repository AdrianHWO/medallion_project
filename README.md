🚀 Automated Medallion Data Pipeline on Databricks

This project demonstrates a production-grade Data Lakehouse architecture implemented on Azure Databricks, transitioning from manual data ingestion to a fully automated ETL pipeline.

🏗️ Architecture: The Medallion Framework

The pipeline follows the Medallion architecture to ensure data quality and reliability:

Bronze (Raw Layer): Ingests raw sales data from external CSV files into Delta tables with ingestion timestamps.

Silver (Cleaned Layer): Performs data type casting (String to Double), handles malformed records using try_cast, and filters out null values and low-value transactions.

Gold (Business Layer): Aggregates data to provide business-level insights, such as total revenue and average order value per product.

🛠️ Key Technical Challenges Solved

Data Type Mismatch: Resolved [CAST_INVALID_INPUT] errors by implementing robust casting strategies for dirty CSV data.

Schema Enforcement: Utilized .option("overwriteSchema", "true") to handle evolving data structures in the Gold layer.

Workflow Automation: Orchestrated the entire notebook execution using Databricks Jobs with automated scheduling and monitoring.

💻 Tech Stack

Language: PySpark (Python)

Platform: Databricks Lakehouse

Storage: Delta Lake

Orchestration: Databricks Workflows (Jobs)