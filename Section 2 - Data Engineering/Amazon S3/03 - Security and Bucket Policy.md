# AWS S3 Security - Must Know for AWS MLE Specialty

---

### Ways to secure/access S3

1. **User-Based Security (IAM policies)**  
   - IAM policies define which API calls a specific IAM user/role can do  

2. **Resource-Based Security (Bucket Policies)**  
   - Bucket-wide rules attached to S3 buckets  
   - Can allow/deny access to users in same or different AWS accounts (cross-account)  
   - Used to make buckets public too  
   - JSON-based policies that specify:  
     - **Resource** (which bucket/objects)  
     - **Effect** (Allow or Deny)  
     - **Action** (which S3 API calls allowed/denied)  
     - **Principal** (who is allowed/denied)  
   - Example: public read policy granting `GetObject` for everyone (`Principal: *`)  
   - Important for cross-account access and managing public access  

3. **Access Control Lists (ACLs)**  
   - Fine-grained security on objects and buckets (less common now)  
   - Can be disabled (best practice is often to disable)  

---

### IAM User vs Role vs Bucket Policy for access  

- **IAM User**  
  - Attach IAM policy to user for access to S3 bucket  
- **IAM Role (e.g. EC2 Role)**  
  - Used to grant EC2 instance permissions to access S3  
  - Assign permissions to role used by EC2 instance  
- **Bucket Policy**  
  - Required to allow cross-account access (IAM user in another account)  
  - Define allow rules for specific principals  
  
---

### Bucket Public Access and Safety Features  

- **Block Public Access setting** (recommended ON)  
  - Prevents any public access to bucket even if bucket policy tries to allow it  
  - Protects from accidental data leaks  
  - Can be enabled per bucket or account wide  
- To intentionally make bucket public, this must be OFF  

---

### Exam key points:  

- S3 permissions = combination of IAM user/role policies + bucket policies + no explicit deny  
- Bucket policies are JSON documents specifying who can do what on which bucket/objects  
- Cross-account access requires bucket policy allowing external IAM principals  
- ACLs exist but less common, can be disabled  
- Block Public Access is a safety net to prevent accidental public exposure  
- EC2 instances get S3 access via IAM roles, NOT IAM users
