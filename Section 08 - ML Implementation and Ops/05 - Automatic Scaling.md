# SageMaker Automatic Scaling and AZ Resiliency Notes

## Automatic Scaling for Inference
- You can configure automatic scaling for SageMaker endpoints by defining scaling policies with target metrics, minimum and maximum instance counts, and cooldown periods.
- SageMaker works with CloudWatch to monitor inference performance and adjust capacity automatically.
- Scaling happens at the production variant level, not just for the entire model. Variants scale independently based on their own traffic patterns.

## Best Practices for Scaling
- Load test your scaling policy before production to ensure correct behavior.
- Incorrect scaling policies can lead to insufficient or excessive capacity, so validation in a test environment is essential.

## Availability Zones and Resiliency
- SageMaker automatically distributes endpoint instances across Availability Zones for high availability.
- You must deploy more than one instance for multi AZ distribution to function.
- If using a custom VPC, ensure it has at least two subnets in different Availability Zones so SageMaker can place instances across them.
