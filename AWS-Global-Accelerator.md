# AWS Architect Interview Question Bank
## Domain 9: AWS Global Accelerator (Ultra Deep)

This document contains **architect-level, scenario-driven interview questions** focused exclusively on AWS Global Accelerator, covering global traffic routing, failover, latency optimization, and failure handling.

---

## 1. Global Accelerator – Core Concepts

- What exact problem does Global Accelerator solve?
- Why is Global Accelerator not just “better Route 53”?
- How does Global Accelerator work at the network layer?
- What AWS infrastructure does Global Accelerator rely on?
- Why does Global Accelerator use Anycast IPs?
- What happens when a client connects to a Global Accelerator IP?
- How does Global Accelerator differ from CDN behavior?

---

## 2. Global Accelerator vs Route 53 (Very Common)

- Route 53 latency routing vs Global Accelerator — real differences
- Why Route 53 failover can be slow?
- How DNS caching affects Route 53 failover?
- When Route 53 is better than Global Accelerator?
- Can Global Accelerator completely replace Route 53?
- How do you design hybrid Route 53 + Global Accelerator?
- Why Global Accelerator failover is faster?

---

## 3. Global Accelerator Architecture & Components

- What is an Accelerator?
- What are listeners?
- What are endpoint groups?
- How does traffic flow from edge to endpoint?
- How does Global Accelerator choose the closest edge?
- How does Global Accelerator determine endpoint health?
- What happens if an endpoint group becomes unhealthy?

---

## 4. Endpoints & Supported Services

- Which AWS services can be endpoints?
- ALB vs NLB as Global Accelerator endpoints — tradeoffs
- Can EC2 instances be endpoints?
- Can EKS services be exposed via Global Accelerator?
- Can Global Accelerator front private endpoints?
- How do you design endpoint groups across regions?
- What happens if endpoints have uneven capacity?

---

## 5. Health Checks & Failover Behavior

- How do Global Accelerator health checks work?
- How often are health checks evaluated?
- What happens during partial endpoint failure?
- How does Global Accelerator react to AZ failures?
- How does Global Accelerator handle regional outages?
- Can Global Accelerator fail traffic instantly?
- How do you test failover safely?

---

## 6. Traffic Management & Traffic Dial

- What is traffic dials in Global Accelerator?
- How do you use traffic dials for gradual cutover?
- How do you perform blue/green using Global Accelerator?
- How do you handle canary traffic globally?
- How do you control traffic during incidents?
- How do traffic dials interact with health checks?

---

## 7. Global Accelerator + Load Balancers

- Why is NLB often preferred with Global Accelerator?
- ALB + Global Accelerator — common pitfalls
- How does connection draining behave with Global Accelerator?
- How are long-lived connections handled?
- How does Global Accelerator affect TLS termination?
- Where should TLS be terminated — edge or backend?
- How do you rotate certificates safely?

---

## 8. Global Accelerator + EKS

- How do you expose EKS services globally?
- NLB-backed services with Global Accelerator — design
- How do you handle pod-level failures?
- How do you handle uneven cluster capacity?
- How do you manage multi-cluster EKS with GA?
- How do you design zero-downtime global EKS deployments?
- How do you roll back globally?

---

## 9. Global Accelerator + DR (Critical)

- How does Global Accelerator fit into DR strategy?
- Ac
