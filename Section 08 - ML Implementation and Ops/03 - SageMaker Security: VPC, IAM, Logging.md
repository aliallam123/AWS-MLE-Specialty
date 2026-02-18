# SageMaker Security Notes: VPC, Networking, IAM, Monitoring

## VPC Considerations for SageMaker
- Training jobs can run inside a VPC, including a private VPC if stronger security is required.
- SageMaker still needs S3 access for training data and model artifacts.
- When using a private VPC, you must configure S3 VPC endpoints to allow SageMaker to communicate with S3.
- S3 endpoint policies and S3 bucket policies can be applied to maintain least‑privilege access.

## Notebook Internet Access
- SageMaker notebooks have internet access enabled by default.
- Internet access can be disabled for security, but SageMaker still requires connectivity to S3.
- If disabling internet access, you must provide outbound access using:
  - Interface endpoints (PrivateLink), or
  - A NAT Gateway
- Without these, training and hosting jobs will fail due to lack of S3 connectivity.

## Training and Inference Containers
- These containers also have internet access enabled by default.
- Network isolation can be enabled to block internet traffic.
- If network isolation is enabled, S3 access is lost unless explicitly restored via VPC endpoints or NAT.

## IAM Permissions for SageMaker
- IAM can control access to actions including:
  - Creating training jobs
  - Creating models
  - Creating endpoints
  - Creating hyperparameter tuning jobs
  - Creating notebooks
- IAM can restrict expensive actions such as large training jobs or tuning jobs.
- Predefined IAM policies include:
  - SageMaker Read Only Access
  - SageMaker Full Access
  - Administrator Access
  - Data Scientist policy

## Logging and Monitoring
- CloudWatch:
  - Monitors and alarms on endpoint invocation metrics such as latency and error rates.
  - Monitors underlying compute health (CPU, memory).
  - Can monitor Ground Truth labeling jobs, including number of active human workers.
- CloudTrail:
  - Audits all user, role, and service actions within SageMaker.
  - Logs are delivered to S3 for later auditing.
