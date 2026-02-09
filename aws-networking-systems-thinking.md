# AWS Architect – Networking & Systems Thinking Question Bank
## Senior / Staff / Architect Level

This document focuses on **real-world networking decisions, trade-offs, and failure scenarios**
commonly discussed in senior AWS, DevOps, SRE, and Platform Engineering interviews.

The goal is to test **mental models**, not service memorization.

---

## 1. VPC Mental Model (Foundational but Senior)

- How can an EC2 instance have **no internet access** but still be reachable?
- What *actually* makes a subnet public or private?
- Do subnets control access, or do route tables?
- What role does an Internet Gateway really play?
- Why is a “private subnet” not the same as a “blocked subnet”?
- What breaks if you remove the IGW but keep the NAT Gateway?
- Can traffic flow without any gateway at all?

---

## 2. Public vs Private Architecture (Real Production Design)

- When should an application **never** live in a public subnet?
- Why do production workloads usually live only in private subnets?
- How do you expose private workloads securely to the internet?
- Bastion host vs SSM Session Manager — when and why?
- How do you audit accidental public exposure?
- How do you design private-only architectures for compliance?

---

## 3. NAT Gateway: Cost, Scale, and Failure

- What exactly requires a NAT Gateway?
- What happens if the NAT Gateway goes down?
- What still works if NAT is removed?
- How do you reduce NAT Gateway costs at scale?
- How do you prevent NAT becoming a bottleneck?
- How do you log and audit outbound internet access?
- When is NAT Gateway the *wrong* solution?

---

## 4. S3 Access from Private Workloads (Classic Interview Trap)

> “S3 lives outside your VPC. Your workloads are private. How do they access S3?”

- Gateway Endpoint vs Interface Endpoint — why?
- Why is S3 Gateway Endpoint **free**, but Interface Endpoint is not?
- Why does Gateway Endpoint not need ENIs?
- Why does Interface Endpoint work across VPCs but Gateway does not?
- How does this decision impact **FinOps**?
- How can choosing the wrong endpoint cost thousands monthly?
- How do endpoint policies differ from IAM policies?

---

## 5. Private EKS Cluster – Real Interview Scenario

You have:
- EKS running **only in private subnets**
- No public endpoint
- No public node IPs
- Production workloads

Questions:
- How do developers access the cluster securely?
- Who actually pulls container images — pods or kubelet?
- How do nodes pull images from GitHub or ECR?
- Do pods need internet access?
- NAT Gateway vs VPC Endpoints — which and why?
- How do you block pod egress but still allow AWS APIs?
- How do you prevent data exfiltration if a pod is compromised?
- What breaks if NAT goes down?
- What still works without NAT?

---

## 6. VPC Endpoints & PrivateLink (Architect-Level)

- Gateway vs Interface endpoints — deep differences
- Why is PrivateLink ENI-based?
- How does DNS resolution work for Interface Endpoints?
- How do you expose a private service across accounts?
- Why is PrivateLink preferred for SaaS integrations?
- How do you design PrivateLink at scale?
- What are the operational limits?
- How do endpoint costs sneak up in large environments?

---

## 7. Multi-VPC & Hybrid Networking

- When does VPC Peering stop scaling?
- Why is transitive routing not allowed in peering?
- Transit Gateway vs Peering — real decision criteria
- How do you inspect traffic centrally?
- How do you isolate environments (prod, non-prod)?
- How do you design DNS across VPCs and on-prem?
- How do you avoid asymmetric routing?

---

## 8. Load Balancers, DNS, and Edge

- ALB vs NLB — beyond textbook answers
- Why put CloudFront in front of ALB?
- Route 53 vs Global Accelerator — real use cases
- How does latency-based routing actually behave?
- What happens during regional failure?
- How does DNS caching affect failover?
- How do WAF and Shield fit into the traffic flow?

---

## 9. Microservices & Networking Reality

- How do you define service boundaries?
- How do you detect a “distributed monolith”?
- Choreography vs orchestration — networking impact
- How do you prevent cascading failures?
- How do retries amplify outages?
- How do you control east–west traffic?
- How do you secure service-to-service communication?

---

## 10. SRE / DevOps System Thinking Questions

- Why can systems fail when CPU and memory look fine?
- CPU-bound vs I/O-bound — how do you prove it?
- Why do deployments succeed but users still see 5xx?
- When should you roll back vs hotfix?
- Metrics vs logs vs traces — what do you check first?
- How do you debug latency without errors?
- How do you avoid alert fatigue?
- How do you explain outages to non-technical stakeholders?

---

## 11. Architecture Ownership Questions (Very Senior)

- When should you say **no** to horizontal scaling?
- When does Infrastructure as Code become dangerous?
- How do you prevent configuration drift?
- How do you test failure without causing one?
- How do you design systems to survive bad deployments?
- How do you balance cost, security, and reliability?
- How do you know an architecture will fail *before* it does?

---

## Final Thought (Interview Signal)

These questions are not about:
- AWS services
- YAML files
- Terraform syntax

They are about:
- **Constraints**
- **Trade-offs**
- **Failure modes**
- **Cost vs security vs reliability**

This is what separates:
> *“Someone who uses AWS”*  
from  
> *“Someone who designs systems on AWS”*

---
