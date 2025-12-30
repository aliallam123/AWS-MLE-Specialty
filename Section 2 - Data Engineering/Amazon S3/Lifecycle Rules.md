# S3 Object Lifecycle & Transitions - Must Know for AWS MLE Specialty

---

### Moving objects between storage classes (transitions)  
- Can move objects Standard → Standard-IA → Intelligent-Tiering → One Zone-IA  
- From One Zone-IA → Glacier Flexible Retrieval or Glacier Deep Archive  
- Use case: infrequent access → move to cheaper classes automatically  
- Archival → move to Glacier classes  

---

### Lifecycle rules automate transitions & expirations  
- **Transition actions:** move object to another storage class after X days  
  - e.g. move to Standard-IA after 60 days  
  - e.g. move to Glacier after 6 months  
- **Expiration actions:** delete objects after X days  
  - e.g. delete access logs after 365 days  
  - delete old versions if versioning enabled  
  - delete incomplete multipart uploads older than e.g. 14 days  

---

### Lifecycle rule scope  
- Can apply to whole bucket or specific prefixes (folder paths)  
- Can apply only to objects with specific tags (e.g. `department=finance`)  

---

### Exam scenario examples  
1. **Images & thumbnails:**  
   - Source images: S3 Standard with lifecycle to Glacier after 60 days  
   - Thumbnails: One Zone-IA, expire after 60 days (can be recreated easily)  
   - Use prefixes to differentiate (e.g. `source/` vs `thumbnails/`)  

2. **Deleted object recovery requirement:**  
   - Retain deleted objects for 30 days retrievable immediately  
   - Then for up to 365 days retrievable within 48 hours  
   - Solution:  
     - Enable S3 Versioning (deleted objects hidden by delete marker)  
     - Lifecycle rule to transition non-current versions → Standard-IA  
     - Later transition them to Glacier Deep Archive  

---

### Finding optimal transition timing  
- Use **Amazon S3 Analytics** to analyze access patterns  
- Works for Standard and Standard-IA only  
- Generates CSV reports updated daily (starts after 24-48 hrs collection)  
- Helps decide when to transition objects to save costs  

---

### Summary  
- Lifecycle rules = automate transitions + expirations based on time, prefix, tags  
- Transitions reduce cost by moving objects to cheaper storage when infrequently accessed  
- Expirations clean up old/unneeded data automatically  
- Versioning + lifecycle = retain deleted versions + move to cheaper storage  
- Analytics helps build smarter lifecycle rules
