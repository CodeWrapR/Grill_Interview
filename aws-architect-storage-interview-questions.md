# AWS Architect Interview Question Bank  
## Domain 3: Storage (Data, Durability, Performance, Cost)

This document contains **service-by-service, situational, architect-level interview questions** focused on AWS Storage, designed for **10–15+ years experience** roles.

---

## 1. Storage Architecture – Core Design

- How do you choose the right storage service for a new workload?
- How do you design storage for durability vs performance?
- How do you design storage for cost optimization at scale?
- How do you separate hot, warm, and cold data?
- How do you handle storage growth that was underestimated?
- How do you design storage to survive AZ failure?
- How do you design storage for multi-region architectures?
- What storage decisions are hardest to reverse later?

---

## 2. Amazon S3 – Core Concepts

- Why is S3 considered eventually consistent (and where)?
- How does S3 achieve 11 nines of durability?
- How does S3 scale without provisioning?
- What happens if you upload the same object key twice?
- How does S3 handle concurrent writes?
- How do you design object naming for performance?
- What happens during S3 service disruption?
- How do you design S3 access for least privilege?

---

## 3. S3 + Security

- How do bucket policies differ from IAM policies?
- How do you prevent public access accidentally?
- How do you design cross-account S3 access?
- How do you secure S3 for regulated data?
- How does S3 encryption work (SSE-S3 vs SSE-KMS vs SSE-C)?
- How do you rotate KMS keys for S3?
- How do you audit S3 access?
- How do you detect data exfiltration from S3?

---

## 4. S3 + Performance & Scale

- How do you optimize S3 for high request rates?
- How do multipart uploads work internally?
- How do you handle very large objects?
- How do you design S3 for millions of small files?
- How do you reduce S3 request costs?
- How do you cache S3 content effectively?
- How do you use S3 with CloudFront properly?

---

## 5. S3 + Lifecycle & Cost Management

- How do S3 lifecycle policies actually work?
- How do you design lifecycle rules without data loss?
- S3 Standard vs IA vs One Zone IA — decision scenarios
- When should you use Glacier vs Glacier Deep Archive?
- How do you restore data from Glacier at scale?
- How do you estimate long-term S3 storage costs?
- How do you handle compliance retention requirements?

---

## 6. S3 + Data Protection & DR

- How do you design backup strategy using S3?
- Versioning enabled — what problems does it create?
- How do you recover from accidental deletion?
- How does S3 replication actually work?
- Same-region vs cross-region replication — tradeoffs
- How do you design S3-based DR?
- How do you test S3 recovery plans?

---

## 7. Amazon EBS – Architecture & Performance

- EBS vs instance store — when and why?
- gp3 vs io1 vs io2 — real-world decision scenarios
- How does EBS deliver consistent IOPS?
- What happens when EBS bursts are exhausted?
- How do you design EBS for databases?
- How do you handle EBS volume saturation?
- How do you monitor EBS performance bottlenecks?

---

## 8. EBS + Operations

- How do you resize EBS volumes without downtime?
- How do you change volume type in production?
- How do you back up EBS safely?
- Crash-consistent vs application-consistent snapshots
- How do you recover corrupted EBS volumes?
- How do you encrypt unencrypted EBS volumes?
- How do you migrate EBS data across regions?

---

## 9. Amazon EFS – Shared File Systems

- EFS vs EBS vs S3 — comparison scenarios
- How does EFS scale automatically?
- General Purpose vs Max I/O — when and why?
- How does EFS handle concurrent access?
- How do you design EFS for performance?
- How do you control EFS costs?
- How do you secure EFS access?
- How does EFS behave during AZ failures?

---

## 10. Amazon FSx (Managed File Systems)

- FSx for Windows vs FSx for Lustre vs FSx for NetApp — use cases
- When would you choose FSx over EFS?
- How does FSx integrate with on-prem systems?
- How do you design high-performance workloads with FSx?
- How do you back up FSx data?
- How do you handle failover in FSx?

---

## 11. Storage for Databases (Architect Perspective)

- Why databases prefer EBS over S3?
- How do you design storage for RDS performance?
- How do you scale storage without downtime?
- How do you design read-heavy vs write-heavy storage?
- How do you prevent storage becoming the bottleneck?
- How do you design backups without impacting performance?

---

## 12. Storage + Containers (EKS / Kubernetes)

- How does Kubernetes persistent storage work on AWS?
- EBS CSI vs EFS CSI — when and why?
- How do you design storage for stateful pods?
- How do you handle pod rescheduling with storage?
- How do you manage PV lifecycle?
- How do you handle storage failures in Kubernetes?
- How do you design multi-AZ storage for EKS?

---

## 13. AWS Backup & Centralized Protection

- Why use AWS Backup instead of custom scripts?
- How does AWS Backup work across services?
- How do you design centralized backup across accounts?
- How do you enforce backup compliance?
- How do you audit backups?
- How do you test backup restores regularly?

---

## 14. Storage + Compliance & Governance

- How do you enforce data retention policies?
- How do you implement legal hold?
- How do you design immutable backups?
- How do you meet audit requirements?
- How do you track data lineage?
- How do you handle GDPR/PII data deletion?

---

## 15. Storage Failures & Edge Cases

- Storage is full but monitoring didn’t alert — why?
- Performance degraded without errors — why?
- Snapshots succeeded but restore failed — why?
- S3 replication lag caused outage — how?
- EFS latency spikes intermittently — why?
- Storage costs exploded unexpectedly — how do you debug?
- Application healthy but data missing — what do you check?

---
