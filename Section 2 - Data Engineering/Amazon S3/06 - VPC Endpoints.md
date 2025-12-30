# AWS S3 VPC Endpoint Gateway - Must Know for AWS MLE Specialty

---

### Default S3 Access  
- S3 buckets live in AWS cloud with **public endpoints**  
- By default, instances (e.g. in public subnets) access S3 via **internet gateway** over public internet  
- Bucket policies can restrict access by **AWS:SourceIp** (public IP addresses)  

---

### Private S3 Access with VPC Endpoint Gateway  
- To avoid public internet, launch instances in **private subnets**  
- Create a **VPC Endpoint Gateway** for S3 inside your VPC  
- This provides a **private connection** between VPC and S3 (no internet traffic)  
- More secure and potentially lower cost  

---

### Bucket Policy with VPC Endpoint  
- Can restrict bucket access only from your VPC endpoint using condition:
  - `aws:SourceVpce` (specific VPC endpoint IDs)  
  - or `aws:SourceVpc` (all endpoints within a VPC)  
- Example: bucket policy denies requests not coming from your VPC Endpoint  

---

### Key points  
- Default S3 access goes over internet, unless you use VPC Endpoint Gateway  
- Use VPC Endpoint & bucket policy to enforce private, secure access to S3  
- Preferred for security & cost purposes when accessing S3 from within AWS VPC 
