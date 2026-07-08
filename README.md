# AWS Certified Machine Learning – Specialty (MLS-C01) Study Notes 🚀

Welcome to my comprehensive study notes and guide for the **AWS Certified Machine Learning – Specialty (MLS-C01)** exam. This repository houses detailed summaries, architectural diagrams, lab notes, and service breakdowns compiled during my preparation journey.

[![AWS Certified Machine Learning - Specialty Badge](https://github.com/user-attachments/assets/83f22ef7-8719-40f4-ab64-957e3f9be39c)](https://www.credly.com/badges/b88d9b4d-0912-4f57-96bc-d7dbc4cdec49/public_url)

👉 **[Verify my Credly Certification Credential 🎓](https://www.credly.com/badges/b88d9b4d-0912-4f57-96bc-d7dbc4cdec49/public_url)**

---

## 🗺️ Study Path & Folder Structure

The notes are structured logically following the core domains of the AWS Machine Learning Specialty exam syllabus:

| Section | Domain / Directory | Key Concepts & Services Covered |
| :---: | :--- | :--- |
| **01** | **[Introduction](./Section%2001%20-%20Introduction/)** | Exam guide overview, syllabus breakdown, and how to use these notes. |
| **02** | **[Data Engineering](./Section%2002%20-%20Data%20Engineering/)** | **Storage:** S3, Glacier, lifecycle rules, VPC endpoints, KMS encryption.<br>**Ingestion & Streaming:** Kinesis Data Streams, Firehose, Flink, Video Streams.<br>**ETL & Pipelines:** Glue (ETL, Catalog, DataBrew), DMS, Step Functions, DataSync, Batch, MQTT. |
| **03** | **[Exploratory Data Analysis](./Section%2003%20-%20Exploratory%20Data%20Analysis/)** | **Data Analysis & Viz:** Athena, QuickSight, EMR (Hadoop, Spark, Security).<br>**Feature Engineering:** Data types, distributions, handling missing data (imputation), normalization, encoding, SageMaker Ground Truth. |
| **04** | **[Modelling (Part 1)](./Section%2004%20-%20Modelling%20Part%201/)** | **Deep Learning Foundations:** Activation functions, CNNs, RNNs, Modern NLP (BERT, GPT), optimization/regularization (L1/L2, dropout, batch size, learning rates).<br>**Evaluation Metrics:** Confusion Matrix, Precision, Recall, F1, ROC-AUC, P-R curves, Bagging vs. Boosting. |
| **07** | **[Modelling (Part 4 - Labs)](./Section%2007%20-%20Modelling,%20Part%204/)** | **Lab Activities:** Setting up Deep Learning on EC2, practical CNN training, handling overfitting, tuning batch size and learning rate. |
| **08** | **[ML Implementation & Ops](./Section%2008%20-%20ML%20Implementation%20and%20Ops/)** | **Production & MLOps:** SageMaker hosting, production variants, autoscaling, serverless inference.<br>**SageMaker Security:** VPC configurations, IAM, KMS/Encryption, CloudTrail logging, Managed Spot Training. |

---

## 🛠️ Main AWS Services Covered

* **Storage & Data Lakes:** Amazon S3, S3 Glacier, FSx (Lustre/ONTAP).
* **Data Processing & ETL:** AWS Glue, AWS Glue DataBrew, Amazon EMR (Spark/Hadoop), Athena.
* **Streaming Analytics:** Amazon Kinesis (Streams, Firehose, Analytics, Video Streams).
* **Core Machine Learning:** Amazon SageMaker (Training, Ground Truth, Processing, Endpoints, Spot Training, Autoscaling).
* **Integration & Orchestration:** AWS Step Functions, AWS Batch, AWS DMS, AWS DataSync.

---

## 🎯 How to Use These Notes

1. **Follow the sequence:** The sections are designed to be read in order, starting from Data Engineering and progressing to Modeling and MLOps.
2. **Deep Dive into Labs:** Check out **Section 07** to see the practical commands and steps for setting up neural networks and environments on AWS EC2.
3. **Reference for Revision:** Use the summaries under **Section 08** for quick review on security (KMS/VPC) and deployment strategies (production variants/canary deployments) right before the exam.

---

*Disclaimer: These notes represent my personal study path and are shared for educational purposes. All product names, logos, and brands are property of their respective owners.*
