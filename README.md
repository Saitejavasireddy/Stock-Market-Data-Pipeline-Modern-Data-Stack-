# Stock-Market-Data-Pipeline-Modern-Data-Stack-
This is an end-to-end real-time data engineering pipeline that pulls live stock market data from the Finnhub API, streams it through Kafka, stores it in MinIO (S3-compatible), loads it into Snowflake via Airflow, transforms it with dbt, and visualizes it in Power BI. Fully containerized with Docker.

<img width="824" height="433" alt="image" src="https://github.com/user-attachments/assets/972f850f-0339-462a-a07c-3e77594797d2" />

Pipeline flow:

Python producer → fetches live stock prices from Finnhub API → publishes to a Kafka topic
Python consumer → reads from Kafka → stores raw JSON into MinIO buckets (Bronze layer)
Airflow DAG → runs every 1 minute → loads MinIO data into Snowflake staging tables
dbt → applies Bronze → Silver → Gold transformations inside Snowflake (cleaning, candlestick aggregations, KPIs, tree chart views)
Power BI → connects to Snowflake Gold layer via Direct Query for live dashboards
