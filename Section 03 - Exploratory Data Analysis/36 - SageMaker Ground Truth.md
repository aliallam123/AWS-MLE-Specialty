# SageMaker Ground Truth – Key Points for AWS ML Specialty Exam

---

## What is SageMaker Ground Truth?
- Managed service for **human labeling of training data**, mostly for **missing labels**.
- Commonly used for **image classification, object detection**, and other labeling tasks.
- Manages a workforce of human labelers to **create high-quality labeled datasets** for ML.

---

## Key Features
- **Active learning integration:**  
  Ground Truth trains an automatic labeling model as humans label data.  
  Over time, it only sends **uncertain cases to human labelers**, reducing labeling cost by up to 70%.

- Workforce options:  
  - **Amazon Mechanical Turk:** Large, low-cost global crowd workforce.  
  - **Private teams:** Internal employees for sensitive data.  
  - **Professional third-party vendors:** Specialized labeling services.

---

## Related AWS Services for Labeling and Feature Generation
- **Amazon Rekognition:**  
  Pre-trained model for automated image/video recognition and labeling.
- **Amazon Comprehend:**  
  NLP service for text analysis (e.g., sentiment, topic modeling) used to generate labels or features from text data.

---

## Ground Truth Plus
- **Turnkey managed labeling solution by AWS experts.**  
- AWS handles project setup, coordination, and workforce management for you.  
- Useful if you want a **hands-off, managed labeling operation** (cost not publicly disclosed).

---

# Exam Focus Summary
- Ground Truth automates **human-in-the-loop labeling** for missing or complex labels.  
- Uses **active learning** to minimize labeling costs by only labeling uncertain data.  
- Multiple workforce options available (public, private, professional).  
- Pre-trained models (Rekognition, Comprehend) can help generate labels/features automatically.  
- Ground Truth Plus offers a fully managed, AWS-run labeling service.

---
