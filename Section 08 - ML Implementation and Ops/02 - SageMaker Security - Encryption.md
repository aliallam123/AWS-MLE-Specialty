# SageMaker Security – MLS-C01 Exam Notes

## Core AWS Security Best Practices
- Use IAM extensively for identity and access management. Apply least privilege and restrict users/services to only what they need.
- Use MFA on all admin and root accounts.
- Always use SSL/TLS when connecting to services.
- Use CloudTrail for auditing API calls and user actions.
- Know the difference:
  - CloudTrail: auditing and historical logs.
  - CloudWatch: monitoring, metrics, alarms, log ingestion.
- Encrypt sensitive data (especially PII) at rest and in transit.

## SageMaker Security: Data at Rest
- SageMaker supports KMS‑based encryption for:
  - Notebooks
  - Training jobs
  - Hyperparameter tuning jobs
  - Batch transform jobs
  - Endpoint artifacts
- Everything stored under `/opt/ml` or `/tmp` inside containers can be encrypted with KMS.
- Training and model hosting data stored in S3 can be encrypted via:
  - SSE‑S3
  - SSE‑KMS
  - CSE (client‑side encryption, less common for exam)

## SageMaker Security: Data in Transit
- All internal SageMaker communication supports SSL/TLS.
- IAM roles are used to grant SageMaker access to S3, ECR, CloudWatch Logs, etc.
  - Follow the principle of least privilege.

## Inter‑Node (Distributed Training) Encryption
- Optional feature to encrypt traffic between training nodes (inter‑container traffic encryption).
- Required in highly regulated environments.
- Comes with a performance cost due to encryption overhead.
- Can be enabled through the console or API when creating training/tuning jobs.

## Exam Tips
- Expect questions on IAM roles for SageMaker and S3 access.
- Understand KMS integration with training jobs, endpoints, and notebooks.
- Know which components are encrypted at rest vs in transit.
- Remember CloudTrail vs CloudWatch differences.
``
