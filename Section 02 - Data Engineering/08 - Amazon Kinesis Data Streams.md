# Amazon Kinesis Data Streams - Must Know for AWS MLE Specialty

---

### What is Kinesis Data Streams?  
- Real-time data collection & storage service  
- Use for streaming data produced continuously (e.g. clickstream, IoT devices, server logs)  
- Data ingested by **producers** (apps, Kinesis Agent)  
- Data consumed by **consumers** (apps, Lambda, Firehose, Apache Flink)  

---

### Key Features  
- Data retention up to **365 days** (can replay/reprocess data)  
- Data can't be deleted manually, only expires based on retention  
- Max record size = 1 MB  
- Data ordering guaranteed per **Partition Key (ID)**  
- Security: encryption at rest (KMS) + encryption in transit (HTTPS)  

---

### Developer Tools  
- Use **Kinesis Producer Library (KPL)** for high-throughput producers  
- Use **Kinesis Client Library (KCL)** for consumer apps  

---

### Capacity Modes and Shards  
- **Shard** = throughput unit:  
  - Write: 1 MB/sec or 1000 records/sec per shard  
  - Read: 2 MB/sec per shard  
- **Provisioned Mode:**  
  - You specify number of shards  
  - Manually scale shards up/down as needed  
  - Pay per shard per hour  
- **On-demand Mode:**  
  - No shard management needed  
  - Auto scales based on traffic (last 30 days)  
  - Pay per data volume and stream hour  

---

### Exam Tips  
- Kinesis Data Streams = real-time streaming with replay capabilities  
- Understand shards and their throughput limits  
- Know difference between provisioned vs on-demand capacity modes  
- Use KPL/KCL for optimized producer/consumer performance
