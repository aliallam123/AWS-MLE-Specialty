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

| Class                      | Durability       | Availability      | Use case                                   | Notes                             |
|----------------------------|------------------|-------------------|--------------------------------------------|----------------------------------|
| **S3 Standard**             | 11 nines         | 99.99%            | Frequently accessed data                    | Default, low latency, high throughput, 2 concurrent AZ failures tolerated |
| **S3 Standard-IA (Infrequent Access)** | 11 nines         | 99.9%             | Data accessed rarely but needs fast access | Lower cost than Standard, retrieval fees apply, use for backups/disaster recovery |
| **S3 One Zone-IA**          | 11 nines within ONE AZ only | 99.5%             | Secondary backups or recreatable data       | Data lost if AZ destroyed, even lower cost |
| **Glacier Instant Retrieval** | 11 nines       | N/A               | Archival but needs milliseconds retrieval  | Min storage 90 days, pay storage + retrieval cost |
| **Glacier Flexible Retrieval** | 11 nines     | N/A               | Archival, retrieval in minutes to hours    | Retrieval options:  
- Expedited: 1-5 mins  
- Standard: 3-5 hrs  
- Bulk: 5-12 hrs (free)  
Min storage 90 days |
| **Glacier Deep Archive**    | 11 nines         | N/A               | Long-term archival, cheapest               | Retrieval:  
- Standard: ~12 hrs  
- Bulk: ~48 hrs  
Min storage 180 days |
| **S3 Intelligent-Tiering**  | 11 nines         | ~Same as Standard  | Automatically moves objects between tiers based on access | Small monthly fee + auto-tiering fee, no retrieval fees; supports frequent, IA, archive instant, archive, deep archive tiers |

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
