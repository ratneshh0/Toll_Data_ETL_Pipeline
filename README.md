# Toll Data ETL Pipeline with Apache Airflow and Kafka

## Introduction
The Toll Data ETL Pipeline project is a data engineering endeavor aimed at alleviating congestion on national highways through the analysis of road traffic data collected from various toll plazas. This project addresses the challenge of disparate data formats and sources by implementing an Extract, Transform, Load (ETL) process using Apache Airflow for batch processing and Kafka for streaming data ingestion.

## Objective
The primary objective of the Toll Data ETL Pipeline project is to consolidate road traffic data from different toll operators, each with unique IT setups utilizing varied file formats. This involves both batch processing of historical data using Apache Airflow and real-time processing of streaming data using Kafka. By extracting, transforming, and loading data into a unified format, the project enables comprehensive analysis of traffic patterns, aiding in the identification of congestion hotspots and the formulation of effective traffic management strategies.

## Tech Stacks Used
The project leverages the following technologies:

- **Apache Airflow**: Utilized for batch processing and workflow orchestration.
- **Kafka**: Employed for real-time streaming data ingestion.
- **Python**: Used for sng tasks, data manipulation, and workflow definition within Apache Airflow.
- **MySQL Database**: Utilized as the storage backend for batch processed and streamed data.

With these technologies, the Toll Data ETL Pipeline project ensures efficient data extraction, transformation, and loading, both in batch and real-time scenarios, paving the way for insightful analysis and informed decision-making in traffic management.

## Environment Setup

**Tasks:**

1. **Define DAG Arguments:**
   - Define necessary arguments for Directed Acyclic Graph (DAG) in Airflow to orchestrate ETL tasks.
     
     ![image](https://github.com/harsh0701Xd/Toll-Data-ETL-Pipeline-with-Apache-Airflow-and-Kafka/assets/89227170/19bc50dd-f01f-4b6c-9718-acac6b5bcd7e)

2. **Define the DAG:**
   - Establish the DAG structure outlining data pipeline workflow in Airflow.
     
     ![image](https://github.com/harsh0701Xd/Toll-Data-ETL-Pipeline-with-Apache-Airflow-and-Kafka/assets/89227170/e426d6d3-bd84-46bb-ad2e-41ebbf85bffa)
     
3. **Extract Data from CSV, TSV, Fixed Width Files:**
   - Create tasks for extracting data from various file formats commonly used by toll operators.

     ![image](https://github.com/harsh0701Xd/Toll-Data-ETL-Pipeline-with-Apache-Airflow-and-Kafka/assets/89227170/daa9718d-fb2a-40bc-984e-36818233db23)

     ![image](https://github.com/harsh0701Xd/Toll-Data-ETL-Pipeline-with-Apache-Airflow-and-Kafka/assets/89227170/7086b1ae-6ee1-48e5-8551-6c787bc467b5)

     ![image](https://github.com/harsh0701Xd/Toll-Data-ETL-Pipeline-with-Apache-Airflow-and-Kafka/assets/89227170/6592abc3-5f04-4ec0-8c09-1a9ed845102a)

     ![image](https://github.com/harsh0701Xd/Toll-Data-ETL-Pipeline-with-Apache-Airflow-and-Kafka/assets/89227170/91fcfe41-554f-4371-9dc7-c11cd4f5347c)

4. **Consolidate Data:**
   - Merge extracted data from different sources into a single file for further processing.

     ![image](https://github.com/harsh0701Xd/Toll-Data-ETL-Pipeline-with-Apache-Airflow-and-Kafka/assets/89227170/78117b3a-4437-4561-b1a6-2e6f5eed18c0)

5. **Transform Data:**
   - Apply transformations as needed to harmonize data format and structure.

     ![image](https://github.com/harsh0701Xd/Toll-Data-ETL-Pipeline-with-Apache-Airflow-and-Kafka/assets/89227170/360bbd8e-51d4-49c2-802d-da2f1bf13efe)

6. **Define Task Pipeline:**
   - Define the sequential flow of tasks to ensure smooth execution of the ETL process.
     
     ![image](https://github.com/harsh0701Xd/Toll-Data-ETL-Pipeline-with-Apache-Airflow-and-Kafka/assets/89227170/94546341-333c-4950-95bb-6783958fbd1c)

     ![image](https://github.com/harsh0701Xd/Toll-Data-ETL-Pipeline-with-Apache-Airflow-and-Kafka/assets/89227170/57a4e70e-e10a-4aaf-9d7b-62dd3547bca8)

7. **Submit DAG:**
   - Submit the configured DAG for execution within Airflow environment.

8. **Unpause DAG:**
   - Activate the DAG to initiate scheduled or triggered execution.

9. **Monitor DAG:**
    - Ensure DAG execution progress and monitor for any issues or failures.

      ![image](https://github.com/harsh0701Xd/Toll-Data-ETL-Pipeline-with-Apache-Airflow-and-Kafka/assets/89227170/9c4bc05f-7f99-4002-a133-0038f31d5c24)

10. **Setup Kafka Environment:**
    - Start Zookeeper and Kafka server, and create a Kafka topic named "toll" for data streaming.
      
      ```
      $ bin/zookeeper-server-start.sh config/zookeeper.properties
      ```
      ```
      $ bin/kafka-server-start.sh config/server.properties
      ```
      ```
      $  bin/kafka-topics.sh --create --topic toll --bootstrap-server localhost:9092
      ```

11. **Configure Toll Traffic Simulator:**
    - Download and configure the Toll Traffic Simulator to generate simulated traffic data.

12. **Run Toll Traffic Simulator:**
    - Execute the configured Toll Traffic Simulator to generate simulated streaming data.

      ![image](https://github.com/harsh0701Xd/Toll-Data-ETL-Pipeline-with-Apache-Airflow-and-Kafka/assets/89227170/d4cc0829-aa82-4b10-99c3-3a829f92a3ce)

13. **Configure Streaming Data Reader:**
    - Configure the sresponsible for reading streaming data from Kafka topic "toll".

14. **Run Streaming Data Reader:**
    - Execute the sto start consuming streaming data from Kafka and processing it.

      ![image](https://github.com/harsh0701Xd/Toll-Data-ETL-Pipeline-with-Apache-Airflow-and-Kafka/assets/89227170/4b5486da-4bf3-4e53-ad6b-af14eb5f6ac4)

15. **Health Check of Streaming Data Pipeline:**
    - Verify the integrity and performance of the streaming data pipeline to ensure continuous operation.

**Results:**
- Successfully designed and executed ETL tasks to collect, consolidate, and transform traffic data from multiple toll plazas.
- Established a robust streaming data pipeline using Kafka to ingest and process real-time traffic data.
- Monitored the pipeline for health and performance, ensuring the continuous flow of data for analysis and decision-making.
