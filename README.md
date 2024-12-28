# **YouTube Analysis Data Engineering Project**

## **Overview**

This project aims to securely manage, process, and analyze structured and semi-structured YouTube data based on video categories and trending metrics. The architecture leverages AWS services to ingest, store, transform, analyze, and visualize data efficiently and at scale.

---

## **Project Goals**

1. **Data Ingestion**: Build a robust mechanism to ingest data from multiple sources.
2. **ETL System**: Transform raw data into a clean, enriched, and usable format.

   <img width="928" alt="ytb2" src="https://github.com/user-attachments/assets/3fd70c21-ab0f-40e8-809f-fd71cbb1b5fd" />

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

     <img width="647" alt="image" src="https://github.com/user-attachments/assets/d351a15d-f65c-4a6d-8314-5d66a4e82e4d" />


### **2. AWS Glue**
**Purpose**: Serverless ETL service to clean, prepare, and transform data.
**Usage**:
   - Discovering schema

     <img width="308" alt="youtube-project-5" src="https://github.com/user-attachments/assets/f262f6f0-f3c1-466b-a89e-5dfde8b8c6a3" />

   - Joining  datasets.

     <img width="533" alt="youtube-project-11" src="https://github.com/user-attachments/assets/9ed3e13e-828f-40df-bcc2-11d4f10da993" />

   - Cataloging data for analytics.
     
   - Processing and enriching data.

### **3. AWS Lambda**
**Purpose**: Run code without managing servers.
**Usage**:
   - Triggered for automated data transformations.

     <img width="416" alt="youtube-project-8" src="https://github.com/user-attachments/assets/b189ace4-bcbd-48e8-9eb2-9374d5df58e8" />

   - Event-driven workflows.

### **4. AWS Step Functions**
**Purpose**: Orchestrate AWS services into serverless workflows.
**Usage**:
   - Coordinate the ETL pipeline for seamless data flow.

### **5. AWS Athena**
**Purpose**: Query S3-stored data using SQL.
**Usage**:
   - Interactive querying of processed data for insights.
     
   <img width="566" alt="youtube-project-2" src="https://github.com/user-attachments/assets/3d190fd7-772a-44e1-8b08-59e8c93ebfc4" />
     
   output:
     
   <img width="572" alt="youtube-project-1" src="https://github.com/user-attachments/assets/ea685c6b-3b70-4773-a132-4fc0927e2e47" />

We used AWS athena to join between dataset that comes from diffrents source a query example:

   <img width="584" alt="youtube-project-3" src="https://github.com/user-attachments/assets/6c797798-09ea-4261-8cc6-69a9386d78d5" />
   
   Output:
   
   <img width="575" alt="youtube-project-4" src="https://github.com/user-attachments/assets/bd57433f-c8da-43cc-af97-c9834066d552" />

### **6. AWS IAM**
**Purpose**: Manage access to AWS services securely.
**Usage**:
   - Control permissions for AWS services.

### **7. Amazon QuickSight**
**Purpose**: BI and analytics dashboard.
**Usage**:
   - Visualize trends, metrics, and insights.

     <img width="959" alt="youtube-project-14" src="https://github.com/user-attachments/assets/ba2f33be-51e0-4db2-be75-a92c06ae941c" />



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

5. **Monitoring**:
   - AWS CloudWatch monitors data flow, transformations, and system performance.

---

## **Technologies & Tools**

- **AWS Services**: S3, Glue, Lambda, Athena, QuickSight, CloudWatch, Step Functions, IAM.
- **Programming Language**: Python (for Glue and Lambda scripts).

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

## **Contacts**

- Najma el boutaheri
- Email: [najmaelboutaheri@gmail.com](najmaelboutaheri@gmail.com)
- link: [Linkedin Profile](https://www.linkedin.com/in/najma-el-boutaheri-8185a1267/)

---
