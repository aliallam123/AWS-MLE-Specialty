# Amazon FSx - Must Know for AWS MLE Specialty

---

### What is FSx?  
- Fully managed high-performance file systems on AWS (like RDS but for filesystems)  
- Launch 3rd party file systems as managed service  

---

### 4 main FSx types to know:  

1. **FSx for Windows File Server**  
- Managed Windows file share (SMB, NTFS)  
- Supports MS Active Directory & ACLs  
- Can mount on Linux EC2 too  
- Integrate with on-prem Windows DFS  
- Scale: tens of GB/s, millions IOPS, hundreds PB data  
- Storage: SSD (low latency apps) or HDD (cheaper, home dirs)  
- Multi-AZ option + daily backup to S3  
- Access from on-prem private connection  

2. **FSx for Lustre**  
- High-performance distributed Linux-based filesystem for HPC and ML  
- Use cases: video processing, financial modeling, big compute workloads  
- Scale: hundreds GB/s, millions IOPS, sub-ms latency  
- Storage: SSD (low latency random IO) or HDD (throughput intensive sequential IO)  
- Integrates seamlessly with S3 (read/write as FS)  
- Accessible from on-prem via VPN/Direct Connect  
- Deployment:  
  - Scratch FS (temporary, no replication, super high performance, cost optimized)  
  - Persistent FS (data replicated within one AZ, long-term, transparent recovery)  

3. **FSx for NetApp ONTAP**  
- Enterprise-grade file system compatible with NFS, SMB, iSCSI  
- Migration path for existing ONTAP or NAS workloads on-prem  
- Supports Linux, Windows, macOS, VMware, ECS, EKS, Workspaces  
- Features: auto-scaling storage, snapshots, replication, compression, deduplication, instant clones  
- Good for advanced storage mgmt & testing  

4. **FSx for OpenZFS**  
- Managed OpenZFS on AWS, NFS protocol only  
- For migrating ZFS workloads on Linux/Mac/Windows  
- Performance: up to 1 million IOPS, <0.5 ms latency  
- Features: snapshots, compression, instant clones (no deduplication)  
- Low cost and great for test/dev environments  

---

### Key exam tips:  
- FSx = managed high perf shared file systems for diverse workloads  
- Match FSx type to workload:  
  - Windows file shares → FSx for Windows File Server  
  - HPC & ML, big compute → FSx for Lustre  
  - Enterprise NAS migration & features → FSx for NetApp ONTAP  
  - ZFS workloads → FSx for OpenZFS  
- Know deployment types for Lustre: scratch (temp, max perf) vs persistent (replicated, reliable)  
- FSx integrates with on-prem and AWS via VPN/Direct Connect/private connections
