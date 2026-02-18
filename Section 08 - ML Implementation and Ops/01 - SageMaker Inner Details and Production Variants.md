# SageMaker Implementation and Operations (MLS-C01 Exam Notes)

## Core Principle: SageMaker Uses Docker for All Training and Inference
- Every SageMaker training job and endpoint runs inside a Docker container.
- Containers must be stored in Amazon Elastic Container Registry (ECR).
- You can use:
  - Prebuilt framework containers (TensorFlow, PyTorch, MXNet, Chainer, scikit-learn, SparkML)
  - Prebuilt SageMaker algorithm containers
  - Completely custom containers with your own code

## Distributed Training
- TensorFlow does not distribute automatically across multiple machines.
- Names to know for the exam:
  - Horovod: framework for distributed deep learning across multiple machines.
  - Parameter servers: alternative distributed training architecture for TensorFlow.

## Training and Inference Containers Structure
### Training Container File Structure
Everything must live under /opt/ml:
- /opt/ml/input contains:
  - config, hyperparameters, resource configuration
  - training data (train, test, validation channels)
- /opt/ml/code contains:
  - The training script (for example, train.py)
- /opt/ml/output contains:
  - Errors and output artifacts
- /opt/ml/model contains:
  - Model artifacts that SageMaker will upload to S3 after training

### Inference Container Structure
- /opt/ml/model contains artifacts needed for runtime inference.

## Typical Full Docker Image Layout
- nginx.conf: NGINX configuration for serving requests
- predictor.py: Flask app implementing inference logic
- serve directory: launches Gunicorn server running the Flask app
- train directory: contains training code invoked during training mode
- wsgi.py: wrapper to expose the Flask app

## Minimal Dockerfile Requirements for SageMaker
- FROM <framework base image>
- Install sagemaker-containers (if using older pattern)
- COPY training script to /opt/ml/code
- Define environment variable:
  - SAGEMAKER_PROGRAM: the training entrypoint script name (for example, train.py)
- Important environment variables to know:
  - SM_MODEL_DIR: where model checkpoints go before being pushed to S3
  - SM_CHANNEL_TRAIN, SM_CHANNEL_TEST, SM_CHANNEL_VALIDATION: input channels
  - HPS: hyperparameters passed in from SageMaker

## Using Your Custom Docker Image
- Build locally using docker build -t <name> .
- Push to ECR.
- Use inside SageMaker with Estimator(image_name=...).

## Production Variants
- Used to deploy multiple models behind one endpoint and split traffic.
- Variant weights control percentage of traffic sent to each model.
- Useful for:
  - A/B testing
  - Gradual rollout of improved model versions
  - Recommender systems and other models where offline validation is weak
- You can easily roll back by adjusting variant weights.

