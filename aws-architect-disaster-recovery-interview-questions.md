# AWS Architect Interview Question Bank  
## Domain 6: Disaster Recovery – SUPER GRILL MODE

This document contains **real-world, failure-driven, architect-level disaster recovery interview questions**, designed for **10–15+ years experience** roles.

---

## 1. DR Fundamentals & Decision Framework

- What exactly qualifies as a disaster?
- RTO vs RPO — why teams get this wrong?
- How do you choose the right DR strategy?
- Why is “backup exists” not equal to “recoverable”?
- How do you align DR with business impact?
- How do you design DR for unknown failures?
- What DR assumptions commonly fail in production?

---

## 2. DR Strategies (AWS Reference)

- Backup & Restore — when is it sufficient?
- Pilot Light — what actually runs?
- Warm Standby — what stays warm and why?
- Active-Active — when is it justified?
- Cost vs recovery tradeoffs across strategies
- How do you migrate between DR strategies?
- What workloads should never be active-active?

---

## 3. Multi-AZ vs Multi-Region DR

- Why Multi-AZ is not DR?
- What failures Multi-AZ does not protect against?
- When is Multi-Region mandatory?
- How do you justify Multi-Region cost?
- How do you prevent regional blast radius?
- How do you keep regions in sync?

---

## 4. Compute DR (EC2 / ASG / EKS)

- How do you recover EC2 workloads in another region?
- AMI-based recovery vs infrastructure recreation
- How do you recover Auto Scaling Groups?
- How do you design EKS cluster DR?
- Can Kubernetes workloads fail over cleanly?
- How do you handle node groups in DR?
- How do you test compute recovery regularly?

---

## 5. Data DR – Storage

- How do you recover S3 data?
- S3 replication vs backup — tradeoffs
- How do you handle replication lag?
- How do you recover EBS-backed workloads?
- Crash-consistent vs app-consistent recovery
- How do you restore EFS data?
- How do you validate restored data integrity?

---

## 6. Database DR (Always Asked)

- RDS Multi-AZ vs Read Replicas — DR implications
- Aurora Global Database — what does it really solve?
- How do you handle split-brain scenarios?
- How do you recover from logical corruption?
- How do you test database failover?
- How do you keep DR data consistent?
- How do you minimize data loss?

---

## 7. Networking & DNS in DR

- Route 53 failover vs Global Accelerator — when and why?
- How does DNS TTL affect recovery?
- How do you design instant traffic failover?
- How do you handle cached DNS during disasters?
- How do you design private DR connectivity?
- How do you recover networking safely?

---

## 8. Application-Level DR

- Why infra recovery doesn’t equal app recovery?
- How do you handle config drift?
- How do you manage feature flags during DR?
- How do you prevent cascading failures?
- How do you test application DR realistically?
- How do you handle partial recovery?

---

## 9. CI/CD & DR

- How do pipelines behave during disasters?
- How do you promote artifacts during DR?
- How do you prevent bad deploys during incidents?
- How do you redeploy safely into DR region?
- How do you freeze changes during incidents?
- How do you validate builds post-recovery?

---

## 10. Security & DR

- How do you manage secrets in DR?
- How do you rotate keys post-incident?
- How do you ensure IAM parity across regions?
- How do you prevent security drift in DR?
- How do you audit access during DR?
- How do you handle compromised credentials during disasters?

---

## 11. Observability During Disasters

- Why monitoring often fails during incidents?
- How do you monitor both regions?
- How do you detect silent failures?
- How do you alert during partial outages?
- How do you avoid alert storms?
- How do you validate recovery success?

---

## 12. Testing & DR Drills (Highly Valued)

- How often should DR be tested?
- Game days vs real incidents
- How do you test without impacting prod?
- What usually breaks during DR tests?
- How do you measure DR readiness?
- How do you improve DR iteratively?

---

## 13. Human & Process Failures

- Why humans cause most DR failures?
- How do you prevent panic-driven mistakes?
- Who has authority during incidents?
- How do you communicate during disasters?
- How do you document DR runbooks?
- How do you onboard new responders?

---

## 14. Cost Optimization for DR

- Why DR costs spiral unexpectedly?
- How do you keep DR cheap but effective?
- How do you justify DR spend to leadership?
- What DR components can be on-demand?
- How do you decommission unused DR resources?

---

## 15. DR Failure Scenarios (Interview Killers)

- DR plan exists but failed — why?
- Failover succeeded but app broken — why?
- Data restored but incorrect — why?
- Traffic switched but users still impacted — why?
- Recovery slow despite automation — why?
- Everything recovered but business still down — why?

---

## 16. Architect-Level DR Design Questions

- Design DR for a tier-1 banking platform
- Design DR for global e-commerce
- Design DR for EKS-based microservices
- Design DR with strict RTO/RPO
- Design DR for regulatory environments
- Design DR for unknown failure modes
- Design DR testing and governance

---
