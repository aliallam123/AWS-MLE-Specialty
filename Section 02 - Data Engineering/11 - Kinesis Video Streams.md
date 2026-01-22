# Amazon Kinesis Video Streams - Must Know for AWS MLE Specialty

---

### What is Kinesis Video Streams?  
- Service to **ingest, store, and process video (and related data) in real-time**  
- Producers = video/audio sources like security cameras, body cams, smartphone cams, DeepLens, RTSP cameras, RADAR data  
- Usually **1 producer per video stream** (e.g. 1000 cameras = 1000 streams)  
- Data retention: from 1 hour up to 10 years (good for security/compliance)  

---

### Consumers and Use Cases  
- Playback live video feeds to apps/users  
- Consume video for ML inference via frameworks: MXNet, TensorFlow, SageMaker  
- AWS services:  
  - SageMaker (ML inference on video)  
  - Amazon Rekognition Video (video analysis)  
- Example: security systems detecting intruders in real-time  

---

### Example Architecture  
1. Kinesis Video Stream ingests live video data  
2. Consumer app (e.g. running in Docker on EC2) reads stream  
3. Consumer checkpoints progress in DynamoDB (to resume on failures)  
4. Decoded frames sent to SageMaker for ML inference  
5. Inference results published into Kinesis Data Streams  
6. Lambda function consumes results for real-time notifications/actions  

---

### Exam Tips  
- Kinesis Video Streams = real-time video ingestion/storage/processing  
- One producer per video stream (many streams for many cameras)  
- Integrates with SageMaker and Rekognition for ML on video  
- Supports long retention (up to 10 years) for compliance/security  
- Think “video plus real-time ML inference and notifications”
