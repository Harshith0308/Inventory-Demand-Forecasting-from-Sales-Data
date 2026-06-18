# Inventory Demand Forecasting from Sales Data
### An AWS Serverless Platform for a Multi-Store Retail Chain

A cloud-based inventory demand forecasting system built using AWS serverless architecture. This platform collects sales data from multiple retail stores, processes it through AWS services, and generates demand forecasts to optimize stock management and reduce overstock/understock situations.

> **About this repository.** The serverless backend (AWS Lambda, DynamoDB, API Gateway, S3, and IAM) was configured and operated directly in the AWS Console. This repository therefore contains the frontend and the architecture documentation, with the annotated console screenshots below serving as evidence of the working system, rather than infrastructure-as-code.

---

## System Architecture

AWS Architecture Diagram

> **System Architecture Overview** — The end-to-end AWS serverless pipeline. Sales data flows from multiple store sources into **AWS API Gateway**, triggers **Lambda functions** for processing, stores data in **DynamoDB**, and runs forecasting logic that outputs results consumed by the frontend dashboard. Services like **S3**, **CloudWatch**, and **IAM roles** support storage, monitoring, and access control respectively.

---

## Frontend Dashboard — Home Page

![Frontend Home Page](https://github.com/user-attachments/assets/f953f029-9d48-4432-96d1-83d95c075270)

> **Web Interface — Landing Page** — The frontend dashboard built in HTML/CSS/JS. This is the home screen where users land after opening the application. It provides navigation to key features: submitting sales data, generating forecasts, and viewing inventory reports across store locations.

---

## Sales Data Input Form

<img width="1920" height="938" alt="image" src="https://github.com/user-attachments/assets/93ef8a2a-2d8b-4ea4-9dcc-8eff110a7edf" />
<img width="1920" height="912" alt="image" src="https://github.com/user-attachments/assets/f953f029-9d48-4432-96d1-83d95c075270" />
> **Sales Data Submission Form** — A clean input form that allows store managers to enter sales data including product ID, store ID, date, and quantity sold. This data is sent via API Gateway to the backend Lambda function, which stores it in DynamoDB for further processing.

---

## Demand Forecast Output

<img width="1920" height="7298" alt="image" src="https://github.com/user-attachments/assets/35fac3e0-7756-4ae8-8305-1ad5aef6bfeb" />
> **Demand Forecast Results** — After processing historical sales data, the system generates demand forecasts for upcoming periods. The output displays predicted demand per product per store, helping managers make informed restocking decisions and avoid inventory shortfalls.

---

## AWS Services in Action
<img width="1920" height="912" alt="image" src="https://github.com/user-attachments/assets/237d0ce8-d787-4947-aafc-4fb4f2a6f9e1" />
<img width="1920" height="912" alt="image" src="https://github.com/user-attachments/assets/de4fb0c1-b42c-4bf5-bca6-52db13ceb7c0" />
> **AWS Console — Services Configuration** — A detailed view of the AWS services configured for this project. This includes the **Lambda function** setup with triggers, **DynamoDB** table structure with partition/sort keys for multi-store data, **API Gateway** endpoint configuration, and **CloudWatch** logs for monitoring invocations and errors in real time.

---

## DynamoDB Table — Sales Records

![DynamoDB Table](https://github.com/user-attachments/assets/7dc181f8-1297-429a-ab60-b1b92b58719a)

> **DynamoDB Table View** — The `SalesData` table in AWS DynamoDB storing records submitted by each store. Each item contains attributes like `storeId`, `productId`, `date`, and `quantitySold`. The table is queried by the forecasting Lambda to retrieve historical sales and compute predictions.

---

## Lambda Function — Forecast Logic

![Lambda Function](https://github.com/user-attachments/assets/6a745df1-210e-46ac-9cf8-68877b024681)

> **AWS Lambda — Forecasting Function** — The serverless compute layer that handles the core forecasting logic. This Lambda function reads historical sales records from DynamoDB, applies a moving average / trend-based forecasting algorithm, and returns predicted demand values. It is triggered via API Gateway on user request and logs execution details to CloudWatch.

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | HTML, CSS, JavaScript |
| API Layer | AWS API Gateway |
| Compute | AWS Lambda (Python) |
| Database | AWS DynamoDB |
| Storage | AWS S3 |
| Monitoring | AWS CloudWatch |
| Access Control | AWS IAM |

---

## Author

**Gottipati Harshith Sai**  
B.Tech CSE — SRM University-AP  
[GitHub](https://github.com/Harshith0308) • [LinkedIn](https://linkedin.com/in/harshith-sai-gottipati)
