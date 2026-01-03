# Misc AWS Topics for Machine Learning Exam - Must Know

---

### AWS DataSync  
- Service to **migrate large amounts of data from on-premises to AWS** (usually S3)  
- Uses a **DataSync Agent** (VM on-prem) to connect via NFS, SMB, or HDFS  
- Transfers data securely over AWS Direct Connect (dedicated line) or internet (encrypted)  
- Validates data integrity during transfer  
- Common use case: move big training datasets from company storage to S3 for ML training (e.g., SageMaker)  

---

### MQTT (Message Queuing Telemetry Transport)  
- **Standard IoT messaging protocol** (not AWS-specific)  
- Used for **reliable transfer of sensor/device data** in Internet of Things (IoT) applications  
- AWS IoT devices use MQTT protocol to send data to cloud  
- On ML exam:  
  - Seeing MQTT = think IoT sensor data streaming for ML model training or analytics  

---

### Exam Tips  
- DataSync = data migration from on-prem to AWS (especially S3)  
- MQTT = IoT messaging protocol for sensor data, often feeding ML pipelines  
- Neither are core ML services but often part of ML data ingestion stories
