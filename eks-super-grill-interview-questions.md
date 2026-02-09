# AWS Architect Interview Question Bank  
## Domain 5: Security – SUPER GRILL MODE (AWS + Kubernetes)

This document contains **deep, real-world, production-grade security interview questions** across AWS and Kubernetes, designed for **10–15+ years experience** roles.

---

## 1. Cloud Security Architecture (Foundations)

- How do you design a secure AWS account from day one?
- Shared Responsibility Model — what do people misunderstand?
- How do you design security with blast-radius isolation?
- How do you balance security vs developer velocity?
- What security decisions are irreversible later?
- How do you design zero-trust in AWS?
- How do you prove security posture to auditors?

---

## 2. Identity & Access Management (IAM)

- Why IAM is the most critical AWS service?
- Users vs Roles vs Groups — architectural use cases
- Why should IAM users be avoided in production?
- How does STS actually work internally?
- What happens when role permissions change mid-session?
- How do you design least-privilege IAM at scale?
- How do you prevent privilege escalation?
- How do you audit IAM usage?
- How do you rotate credentials safely?

---

## 3. Organizations, SCPs & Multi-Account Security

- Why multi-account is more secure than single account?
- SCPs vs IAM policies — enforcement differences
- What SCPs cannot protect against?
- How do you prevent root account misuse?
- How do you restrict region usage?
- How do you enforce mandatory security services?
- How do you handle security exceptions?
- How do you design account vending securely?

---

## 4. Network Security (AWS Level)

- Security Groups vs NACLs — security implications
- How do you design east-west traffic security?
- How do you restrict outbound traffic?
- How do you prevent data exfiltration?
- How do you design private-only architectures?
- How do you inspect traffic centrally?
- How do you secure hybrid connectivity?
- How do you handle DNS-based attacks?

---

## 5. Data Security & Encryption

- Encryption at rest vs in transit — what’s not obvious?
- KMS vs CloudHSM — when and why?
- How does envelope encryption work?
- How do you design key rotation without outages?
- How do you manage customer-managed keys at scale?
- How do you prevent key misuse?
- How do you audit key access?
- What happens if a KMS key is deleted?

---

## 6. Secrets Management

- Why environment variables are dangerous?
- Secrets Manager vs Parameter Store — real-world decision
- How do you rotate secrets automatically?
- How do you prevent secrets leakage?
- How do you audit secret access?
- How do you manage secrets across accounts?
- How do you inject secrets securely into workloads?

---

## 7. Logging, Detection & Response

- What logs are mandatory in a secure AWS setup?
- CloudTrail vs CloudWatch Logs vs VPC Flow Logs
- How do you design centralized logging?
- How do you detect compromised credentials?
- How do you detect suspicious API usage?
- How do you design automated incident response?
- How do you reduce false positives?
- How do you test detection mechanisms?

---

## 8. Threat Detection Services

- GuardDuty — what does it actually detect?
- Inspector vs GuardDuty — differences
- Security Hub — value vs noise
- Macie — when is it worth it?
- How do you tune findings at scale?
- How do you respond to findings automatically?
- How do you avoid alert fatigue?

---

## 9. Kubernetes Security – Control Plane & Auth

- How does Kubernetes authentication work?
- EKS authentication vs authorization — differences
- Why is `aws-auth` ConfigMap dangerous?
- How do you manage cluster access securely?
- How do you revoke access immediately?
- How do you audit Kubernetes API access?
- How do you secure the Kubernetes API server?

---

## 10. Kubernetes Authorization (RBAC)

- How does RBAC actually evaluate permissions?
- Role vs ClusterRole — design use cases
- How do you design least-privilege RBAC?
- How do you prevent RBAC privilege escalation?
- How do you audit RBAC permissions?
- Why RBAC becomes unmanageable?
- How do you manage RBAC across clusters?

---

## 11. Pod & Workload Security

- Why containers are not secure by default?
- How do you prevent running privileged containers?
- Pod Security Standards vs PSP — migration strategy
- How do you enforce non-root containers?
- How do you control Linux capabilities?
- How do you scan container images?
- How do you block vulnerable images at deploy time?

---

## 12. Network Security in Kubernetes

- Why Kubernetes networking is insecure by default?
- How do Network Policies actually work?
- Why network policies often fail?
- How do you enforce zero-trust networking?
- How do you secure ingress vs egress traffic?
- How do you inspect pod-to-pod traffic?
- How do you implement service mesh securely?

---

## 13. Secrets in Kubernetes

- Why Kubernetes Secrets are not encrypted by default?
- How does etcd encryption work?
- External Secrets vs Sealed Secrets — tradeoffs
- How do you rotate secrets without pod restarts?
- How do you prevent secrets from leaking in logs?
- How do you audit secret access?
- How do you secure secrets in CI/CD pipelines?

---

## 14. Supply Chain & CI/CD Security

- How do you secure CI/CD pipelines?
- How do you prevent credential leakage in pipelines?
- How do you validate build artifacts?
- How do you implement image signing?
- How do you prevent dependency confusion?
- How do you secure Git repositories?
- How do you enforce policy-as-code?

---

## 15. Runtime Security & Incident Response

- How do you detect compromised containers?
- How do you isolate infected pods?
- How do you capture forensic evidence?
- How do you respond to active attacks?
- How do you design automated containment?
- How do you recover from breaches?
- How do you run post-incident reviews?

---

## 16. Compliance & Governance

- How do you meet SOC2 / ISO / PCI requirements?
- How do you prove compliance continuously?
- How do you enforce data residency?
- How do you handle right-to-be-forgotten?
- How do you design immutable audit trails?
- How do you manage policy exceptions?
- How do you balance compliance and agility?

---

## 17. Security Failure Scenarios (Interview Favorites)

- Permissions correct but access denied — why?
- Everything private but data leaked — how?
- Logs missing during an incident — what failed?
- Security tool deployed but breach happened — why?
- Attack detected late — what went wrong?
- All controls in place but auditor not satisfied — why?

---

## 18. Architect-Level Security Design Questions

- Design a zero-trust AWS + EKS platform
- Design security for multi-tenant Kubernetes
- Design security for regulated industries
- Design end-to-end encryption strategy
- Design secure multi-region architecture
- Design automated incident response
- Design security posture for exec reporting

---
