# AWS Architect Interview Question Bank  
## Domain 7: Landing Zone & Landing Zone Accelerator (LZA) – SUPER GRILL MODE

This document contains **enterprise-scale, governance-heavy, architect-level interview questions** focused on AWS Landing Zone, Control Tower, and Landing Zone Accelerator (LZA), designed for **10–15+ years experience** roles.

---

## 1. Landing Zone – Core Concepts

- What problem does an AWS Landing Zone actually solve?
- Why is a single AWS account a bad idea at scale?
- What are the core pillars of a Landing Zone?
- What decisions must be made before creating a Landing Zone?
- What Landing Zone mistakes are impossible to fix later?
- How do you design a Landing Zone for long-term scale?
- How do you align Landing Zone design with business units?

---

## 2. AWS Organizations & Account Strategy

- Why is multi-account the foundation of security?
- How do you decide account boundaries?
- Environment-based vs workload-based accounts — tradeoffs
- How many accounts is “too many”?
- How do you prevent account sprawl?
- How do you design account naming and metadata?
- How do you handle shared services accounts?
- How do you manage cross-account access securely?

---

## 3. Control Tower – Deep Dive

- What exactly does Control Tower set up?
- What Control Tower does NOT do?
- How does Control Tower enforce guardrails?
- Preventive vs detective guardrails — real differences
- What happens if guardrails conflict with workloads?
- How do you customize Control Tower safely?
- How do you upgrade Control Tower without disruption?
- Why do some enterprises avoid Control Tower?

---

## 4. Landing Zone Accelerator (LZA) – Fundamentals

- What is Landing Zone Accelerator on AWS?
- Why was LZA introduced when Control Tower exists?
- Control Tower vs LZA — real-world comparison
- When should LZA be chosen over Control Tower?
- What enterprise problems does LZA solve?
- What assumptions does LZA make?
- What skills are required to operate LZA?

---

## 5. LZA Architecture & Components

- How is LZA structured internally?
- What role does Infrastructure as Code play in LZA?
- How does LZA handle configuration drift?
- How does LZA manage upgrades?
- How does LZA enforce consistency across accounts?
- How does LZA scale to hundreds of accounts?
- What breaks when LZA is misconfigured?

---

## 6. Governance & Guardrails (Critical Section)

- SCPs vs Control Tower guardrails — enforcement differences
- What SCPs can and cannot restrict?
- How do you design SCPs safely?
- How do you test SCP changes?
- How do you avoid breaking workloads with SCPs?
- How do you handle exceptions to guardrails?
- How do you audit guardrail effectiveness?

---

## 7. Identity Architecture in a Landing Zone

- How do you design centralized identity?
- IAM Identity Center vs IAM roles — decision criteria
- How do you integrate Active Directory or SSO?
- How do you manage human vs machine access?
- How do you design permission boundaries?
- How do you prevent privilege escalation across accounts?
- How do you audit identity usage globally?

---

## 8. Network Architecture in a Landing Zone

- Centralized networking vs distributed networking
- How do you design hub-and-spoke networking?
- Transit Gateway placement strategies
- How do you isolate environments at network level?
- How do you share VPCs across accounts?
- How do you enforce network guardrails?
- How do you prevent shadow networking?

---

## 9. Security Architecture (Centralized)

- How do you design centralized logging?
- How do you aggregate security findings?
- How do you enforce mandatory security services?
- How do you prevent disabling security tools?
- How do you design centralized incident response?
- How do you manage encryption keys centrally?
- How do you audit security posture continuously?

---

## 10. Logging, Monitoring & Audit

- What logs are mandatory in a Landing Zone?
- How do you design centralized CloudTrail?
- How do you protect logs from tampering?
- How do you handle log retention and cost?
- How do you provide audit access safely?
- How do you detect suspicious activity across accounts?

---

## 11. CI/CD & Infrastructure Governance

- How do you manage IaC in a Landing Zone?
- GitOps vs pipeline-driven governance — tradeoffs
- How do you prevent manual changes?
- How do you detect and remediate drift?
- How do you promote changes safely across environments?
- How do you handle emergency changes?
- How do you roll back governance changes?

---

## 12. Compliance & Enterprise Controls

- How do you design for compliance from day one?
- How do you map AWS controls to compliance frameworks?
- How do you prove compliance continuously?
- How do you handle data residency requirements?
- How do you handle audits in large environments?
- How do you manage compliance exceptions?
- How do you handle conflicting regulatory needs?

---

## 13. Migration to Landing Zone

- How do you migrate existing accounts into a Landing Zone?
- Brownfield vs greenfield Landing Zone — challenges
- How do you onboard legacy workloads?
- How do you handle non-standard configurations?
- How do you minimize migration risk?
- How do you validate migration success?

---

## 14. Cost Management & Chargeback

- How do you design cost visibility across accounts?
- How do you enforce tagging standards?
- How do you prevent runaway costs?
- How do you implement chargeback or showback?
- How do you align cost with ownership?
- How do you report costs to leadership?

---

## 15. Failure & Edge Cases (Very Common)

- Guardrail blocked production change — what went wrong?
- SCP too strict caused outage — how do you recover?
- Account compromised — how does Landing Zone help?
- Logs missing during audit — what failed?
- Identity misconfiguration caused access outage — why?
- LZA deployment failed mid-way — how do you recover?

---

## 16. Operating LZA at Scale (Reality Check)

- What daily operations look like with LZA?
- How do you onboard new teams?
- How do you train engineers on Landing Zone constraints?
- How do you document governance decisions?
- How do you measure Landing Zone success?
- How do you evolve the Landing Zone over time?

---

## 17. Architect-Level Design Questions

- Design a Landing Zone for a Fortune 100 enterprise
- Design Landing Zone for regulated industries
- Design Landing Zone for multi-region workloads
- Design Landing Zone with zero-trust principles
- Design Landing Zone for 1000+ AWS accounts
- Design Landing Zone governance lifecycle
- Design Landing Zone disaster recovery

---
