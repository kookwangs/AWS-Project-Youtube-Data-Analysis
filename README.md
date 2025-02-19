# AWS-Project-Youtube-Data-Analysis
Hands-on project exploring **AWS cloud** services to gain practical experience with its tools and platform. Learned from Darshil Parmar’s YouTube channel, covering key AWS concepts and best practices. ([Link VDO](https://www.youtube.com/watch?v=yZKJFKu49Dk&list=PLBJe2dFI4sguF2nU6Z3Od7BX8eALZN3mU&index=2))

## Project Diagram
![Blank diagram](https://github.com/user-attachments/assets/ca3fe65f-5512-406b-804a-56fe9b362a92)

This project processes the **Trending YouTube Video Statistics** dataset, which tracks daily trending YouTube videos across multiple regions, including the US, GB, DE, CA, FR, RU, MX, KR, JP, and IN. Each region has a separate file containing video details such as title, channel, views, likes, comments, and category IDs. Category mappings, which vary by region, are provided in the included JSON files.

## AWS Implementation

Firstly, I set up my AWS account and configured roles and permissions using **IAM** to enhance security. Then, I used the AWS CLI to upload the dataset from Kaggle to **Amazon S3** for storage.

To extract metadata and better understand the dataset structure (especially the complex JSON files with nested fields), I used **AWS Glue Data Catalog** with a **Crawler**. This allowed me to analyze the schema of the dataset.

After understanding the data structure, I used **Amazon Athena** to query the dataset and get an overview. I found that certain fields in the JSON files were not relevant for analysis and needed preprocessing before the next steps.

To clean and transform the data, I used **AWS Lambda** to create a Python function that filtered and reformatted the dataset. The cleaned data was then stored in a new **S3** bucket. Next, I used **AWS Glue ETL** to automate data transformation.

After obtaining the cleansed data, I performed an **ETL pipeline** using AWS Glue’s visual interface. I joined the trending video data with the category dataset (based on _category_id_) and stored the results in another S3 bucket.

<img width="1440" alt="ภาพถ่ายหน้าจอ 2568-02-19 เวลา 15 07 40" src="https://github.com/user-attachments/assets/4e353397-6aee-4fca-bb82-8f784ce9384f" />

With the processed data ready for analysis, I used **Amazon QuickSight** to create visualizations and gain insights into trending videos. I built an interactive dashboard to explore trends easily.

<img width="1440" alt="ภาพถ่ายหน้าจอ 2568-02-19 เวลา 15 39 43" src="https://github.com/user-attachments/assets/6261e0a4-49aa-4587-bc5a-680bc5de72b1" />

## Cost Breakdown  
This project was completed with a total cost of **USD 0.81**, utilizing **7 AWS services** efficiently:

| **Service**                 | **Cost (USD)** |
|-----------------------------|--------------|
| AWS Glue                    | 0.75         |
| Amazon Athena               | 0.01         |
| AWS CloudWatch              | 0.00         |
| AWS Data Transfer           | 0.00         |
| AWS Key Management Service  | 0.00         |
| AWS Lambda                  | 0.00         |
| Amazon S3                   | 0.00         |


