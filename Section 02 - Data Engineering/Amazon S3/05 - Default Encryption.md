# S3 Default Encryption vs Bucket Policies - Must Know for AWS MLE Specialty

---

### Default Encryption  
- All new buckets have **default encryption = SSE-S3** automatically enabled  
- Applies to new objects uploaded (auto encrypts them)  
- You can change default to other types, e.g. **SSE-KMS**  

---

### Forcing Encryption with Bucket Policy  
- Bucket policies can **deny any PUT request that does not have the correct encryption headers**  
- Example policies deny uploads if:  
  - No SSE-KMS encryption header (`x-amz-server-side-encryption: aws:kms`)  
  - No SSE-C (customer encryption) header  
- Bucket policies override default encryption → policy evaluated **before** default encryption setting  

---

### Key points  
- Default encryption simplifies encrypting all objects on upload  
- Bucket policy can be used to enforce/force specific encryption types (prevent unencrypted or wrong encryption)  
- Use bucket policies to enforce security/compliance rules strictly  
- Bucket policies evaluated before default encryption kicks in
