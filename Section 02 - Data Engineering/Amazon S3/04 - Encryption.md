# AWS S3 Object Encryption - Must Know for AWS MLE Specialty

---

### Types of S3 Encryption

1. **Server-Side Encryption (SSE)**  
   - Encryption done by AWS after upload, transparent to user  
   - 3 types:  

   **a) SSE-S3 (S3 Managed Keys)**  
   - Default for buckets/objects  
   - AWS manages keys (you don’t see or control them)  
   - Uses AES-256 encryption  
   - Use header `"x-amz-server-side-encryption": "AES256"` to request encryption  
   - Simple, automatic  

   **b) SSE-KMS (AWS KMS Managed Keys)**  
   - You manage keys via AWS KMS service  
   - More control and auditing (CloudTrail logs key usage)  
   - Use header `"x-amz-server-side-encryption": "aws:kms"` + specify KMS key ID  
   - Need permission to access both S3 object AND encrypted KMS key  
   - API calls to KMS (GenerateDataKey, Decrypt) count against KMS throughput limits (5,000 to 30,000 reqs/sec) → can be throttled in high throughput cases  
   - Good for tighter security/auditing  

   **c) SSE-C (Customer Provided Keys)**  
   - You provide encryption key on every upload/download request via HTTPS headers  
   - AWS uses your key to encrypt/decrypt but does NOT store it  
   - Must use HTTPS to secure key in transit  
   - You fully manage keys outside AWS, but encryption is still server-side  

2. **Client-Side Encryption**  
   - Data is encrypted by client BEFORE uploading to S3  
   - Client manages keys and encrypt/decrypt cycles  
   - Data stored encrypted in S3, S3 sees only encrypted blobs  
   - Use libraries like Client-Side Encryption Library to help  
   - Decryption happens on client  

---

### Encryption In Transit (Data-in-Flight)  
- S3 supports HTTP (no encryption) and HTTPS (SSL/TLS encrypted) endpoints  
- Always recommended to use **HTTPS** for secure transmission  
- SSE-C requires HTTPS because you send keys in headers  
- Can enforce HTTPS use by applying a **Bucket Policy** denying requests where `aws:SecureTransport` = false

Example bucket policy snippet to force HTTPS:

```json
{
  "Effect": "Deny",
  "Principal": "*",
  "Action": "s3:GetObject",
  "Resource": "arn:aws:s3:::your-bucket-name/*",
  "Condition": {
    "Bool": {"aws:SecureTransport": "false"}
  }
}
