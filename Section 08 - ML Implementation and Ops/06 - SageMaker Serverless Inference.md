# SageMaker Serverless Inference and Inference Recommender

## SageMaker Serverless Inference

- You specify the container, memory requirements, and concurrency requirements
- AWS automatically provisions and scales the underlying infrastructure
- Capacity scales down to zero when there are no requests (pay per usage)
- Best for **infrequent or unpredictable traffic** patterns
- Optimizes costs by only charging based on actual usage

### CloudWatch Metrics for Serverless Inference

- **ModelSetupTime** -- how long it took to deploy new inference models during scaling
- **Invocations** -- number of invocation requests
- **Invocation errors** -- failed invocations
- **Memory utilization** -- validates if container memory and concurrency settings are accurate

## SageMaker Inference Recommender

- Recommends **optimal instance types and configurations** for deploying inference endpoints
- Automates load testing and model tuning
- Can deploy automatically to the optimal inference endpoint based on test results

### How It Works

1. Register your SageMaker model to the **Model Registry**
2. Benchmarks different endpoint configurations
3. Collect and visualize metrics (cost per hour, cost per inference, latency)
4. Choose instance type based on your optimization priority (cost vs. latency)

### Two Modes

| Mode | Also Called | What It Does | Duration |
|------|-----------|--------------|----------|
| **Instance Recommendations** | Default | Runs load tests on recommended instance types automatically | ~45 minutes |
| **Endpoint Recommendations** | Custom Load Test | You specify instance types, expected traffic patterns, and latency/throughput requirements | ~2 hours |

- **Endpoint recommendations** are for tailored results matching specific SLAs

## Inference Deployment Options Summary

| Option | Use Case |
|--------|----------|
| **Serverless Inference** | Do not want to manage infrastructure at all; infrequent/unpredictable traffic |
| **Automatic Scaling** | Middle ground; you manage some config but scaling is automatic |
| **Inference Recommender** | Helps decide instance types when setting up endpoints manually |
