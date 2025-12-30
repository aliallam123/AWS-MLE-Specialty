# AWS S3 Storage Classes - Must Know for AWS MLE Specialty

---

### Important concepts  
- **Durability** = how likely data is lost  
  - S3 has *11 nines* durability (99.999999999%) for ALL storage classes  
  - Means very very rare to lose data (1 object lost every 10,000 years if storing 10M objects)  
- **Availability** = how often data is accessible  
  - Varies by storage class (lower availability = more downtime/errors)

---

### Storage Classes Overview

| Class                         | Durability                 | Availability     | Use case                              | Notes                                                                                     |
|-------------------------------|----------------------------|------------------|-------------------------------------|-------------------------------------------------------------------------------------------|
| **S3 Standard**                | 11 nines (99.999999999%)   | 99.99%           | Frequently accessed data             | Default, low latency, high throughput, tolerates 2 concurrent AZ failures                 |
| **S3 Standard-IA (Infrequent Access)** | 11 nines (99.999999999%)   | 99.9%            | Rarely accessed but rapid retrieval | Lower cost than Standard, retrieval fees apply, used for backups/disaster recovery         |
| **S3 One Zone-IA**             | 11 nines (within ONE AZ)   | 99.5%            | Secondary backups or recreatable data | Data lost if AZ destroyed, lower cost                                                     |
| **Glacier Instant Retrieval** | 11 nines (99.999999999%)   | N/A              | Archival with milliseconds retrieval | Min storage 90 days, pay storage + retrieval cost                                         |
| **Glacier Flexible Retrieval**| 11 nines (99.999999999%)   | N/A              | Archival, retrieval minutes to hours| Retrieval options: Expedited (1-5 mins), Standard (3-5 hrs), Bulk (5-12 hrs, free), min 90 days storage |
| **Glacier Deep Archive**       | 11 nines (99.999999999%)   | N/A              | Long-term archival, lowest cost     | Retrieval: Standard (~12 hrs), Bulk (~48 hrs), min storage 180 days                        |
| **S3 Intelligent-Tiering**     | 11 nines (99.999999999%)   | ~Same as Standard| Auto moves objects between tiers    | Small monthly & auto-tiering fees, no retrieval fees, supports frequent, IA, archive tiers |

---

### Lifecycle & tiering notes
- Can set lifecycle policies to move objects automatically between storage classes  
- You choose storage class when uploading, can change manually or via lifecycle configs  
- Intelligent-Tiering is like "set and forget" auto-management of cost/performance tradeoff  

---

### Key points for exam  
- Durability is always 11 9's regardless of class  
- Availability varies: Standard > Standard-IA > One Zone-IA  
- Glacier classes = cold storage, cheaper but slow retrieval + retrieval cost  
- One Zone-IA stores data in only one zone → data loss risk if zone fails  
- Intelligent-Tiering saves cost by auto moving objects based on usage, no retrieval fees  
- Min storage durations matter for Glacier classes (90 or 180 days)  
- Retrieval costs apply except for Intelligent Tiering frequent and IA tiers  

---

**Do not try to memorize exact pricing or timings**  
Just understand use cases, durability vs availability, and storage class purpose
