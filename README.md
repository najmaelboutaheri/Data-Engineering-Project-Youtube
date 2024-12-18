# **YouTube Analysis Data Engineering Project**

## **Overview**

This project aims to securely manage, process, and analyze structured and semi-structured YouTube data based on video categories and trending metrics. The architecture leverages AWS services to ingest, store, transform, analyze, and visualize data efficiently and at scale.

---

## **Project Goals**

1. **Data Ingestion**: Build a robust mechanism to ingest data from multiple sources.
2. **ETL System**: Transform raw data into a clean, enriched, and usable format.
3. **Centralized Data Lake**: Store data from multiple sources in a unified and scalable repository.
4. **Scalability**: Ensure that the system can handle growing data volumes seamlessly.
5. **Cloud Processing**: Use AWS cloud infrastructure for efficient data handling and processing.
6. **Reporting**: Build a dashboard for insightful analysis and visualization.

---

## **Architecture Diagram**

![image](https://github.com/user-attachments/assets/bf684093-10f3-471f-893c-07298e7cc0dd)


---

## **Services Used**

### **1. Amazon S3**
 **Purpose**: Object storage for raw, cleansed, and processed data.
 **Components**:
   - **Landing Area**: Raw data ingestion zone.
   - **Cleansed/Enriched**: Transformed and cleaned data storage.
   - **Analytics/Reporting**: Final processed data for analysis and reporting.

### **2. AWS Glue**
**Purpose**: Serverless ETL service to clean, prepare, and transform data.
**Usage**:
   - Discovering schema.
   - Cataloging data for analytics.
   - Processing and enriching data.

### **3. AWS Lambda**
**Purpose**: Run code without managing servers.
**Usage**:
   - Triggered for automated data transformations.
   - Event-driven workflows.

### **4. AWS Step Functions**
**Purpose**: Orchestrate AWS services into serverless workflows.
**Usage**:
   - Coordinate the ETL pipeline for seamless data flow.

### **5. AWS Athena**
**Purpose**: Query S3-stored data using SQL.
**Usage**:
   - Interactive querying of processed data for insights.

### **6. AWS IAM**
**Purpose**: Manage access to AWS services securely.
**Usage**:
   - Control permissions for AWS services.

### **7. Amazon QuickSight**
**Purpose**: BI and analytics dashboard.
**Usage**:
   - Visualize trends, metrics, and insights.

### **8. AWS CloudWatch**
**Purpose**: Monitor and alert on AWS services.
**Usage**:
   - Monitor ETL jobs, Lambda executions, and other resources.

---

## **Dataset Used**

The dataset consists of daily trending YouTube videos for multiple regions and contains:
- **Fields**: Video title, channel title, views, likes, dislikes, tags, comment counts, and more.
- **Additional Files**: A `category_id` mapping in a JSON file.

**Source**: [YouTube Trending Videos Dataset on Kaggle](https://www.kaggle.com/datasets/datasnaek/youtube-new)

<img width="193" alt="image" src="https://github.com/user-attachments/assets/23aa9c4d-be71-4a01-a16b-20151a11235b" />

---

## **Data Pipeline Workflow**

1. **Data Ingestion**:
   - Bulk data ingested into S3 Landing Area using S3 APIs.

2. **Data Processing**:
   - AWS Glue performs ETL operations to clean and transform data.
   - AWS Lambda triggers processing jobs for automation.

3. **Storage**:
   - Cleaned and transformed data stored in S3 under Cleansed/Enriched and Analytics zones.

4. **Query & Access**:
   - AWS Athena provides SQL-based query capabilities on data stored in S3.
   - Analytical access provided via APIs.

5. **Visualization**:
   - Data insights visualized using Amazon QuickSight, optionally Power BI or other tools.

6. **Monitoring**:
   - AWS CloudWatch monitors data flow, transformations, and system performance.

---

## **Target Analytics**

- **Video Trends**: Top trending videos based on views, likes, and comment counts.
- **Regional Analysis**: Comparison of trending videos across different regions.
- **Category Insights**: Performance metrics of video categories.
- **Channel Performance**: Identify high-performing YouTube channels.

---

## **Technologies & Tools**

- **AWS Services**: S3, Glue, Lambda, Athena, QuickSight, CloudWatch, Step Functions, IAM.
- **Programming Language**: Python (for Glue and Lambda scripts).
- **Visualization**: QuickSight, Power BI (Optional).

---

## **How to Run the Project**

1. Set up an **AWS account** and configure the necessary services (IAM roles, S3 buckets, Glue jobs, Athena).
2. Upload the **raw dataset** to the **S3 Landing Area**.
3. Configure **AWS Glue jobs** and triggers using **Lambda** for processing.
4. **Query** processed data using **Athena** or **Redshift**.
5. Visualize results on **QuickSight** or other BI tools.

---

## **Future Enhancements**

- Automate pipeline orchestration using **Airflow**.
- Integrate real-time streaming using **Kinesis**.
- Include **anomaly detection** and **recommendation systems**.

---

## **Contributors**

- Najma el boutaheri
- Email: [najmaelboutaheri@gmail.com](najmaelboutaheri@gmail.com)
- link: [Linkedin Profile](https://www.linkedin.com/in/najma-el-boutaheri-8185a1267/)

---
