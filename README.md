# Stock-Market-Data-Pipeline-Modern-Data-Stack-
This is an end-to-end real-time data engineering pipeline that pulls live stock market data from the Finnhub API, streams it through Kafka, stores it in MinIO (S3-compatible), loads it into Snowflake via Airflow, transforms it with dbt, and visualizes it in Power BI. Fully containerized with Docker.
