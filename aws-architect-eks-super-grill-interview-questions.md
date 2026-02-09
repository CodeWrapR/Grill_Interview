# AWS Architect Interview Question Bank  
## Domain 4: EKS – SUPER GRILL MODE (Production, Scale, Failure)

This document contains **extreme, real-world, production-grade EKS interview questions**, designed for **10–15+ years AWS / Kubernetes / Platform Architect roles**.

---

## 1. EKS – Control Plane Deep Dive

- What exactly is managed by AWS in EKS control plane?
- What components are still your responsibility?
- How does EKS achieve multi-AZ control plane availability?
- What happens if the EKS API server is unreachable?
- How does EKS handle etcd failures?
- Can you lose the control plane? What happens to workloads?
- How does EKS authenticate requests internally?
- What are EKS control plane scaling limits?
- How do you monitor control plane health?

---

## 2. EKS Cluster Architecture Design

- Single cluster vs multiple clusters — decision criteria
- One large cluster vs many small clusters — blast radius tradeoffs
- How do you design EKS for multi-tenant workloads?
- How do you isolate teams safely inside one cluster?
- Namespace isolation vs account isolation — when and why?
- How do you design EKS for regulated workloads?
- How do you design EKS for 1000+ microservices?
- How do you design EKS across multiple regions?

---

## 3. Worker Nodes & Compute (EC2 / Managed Node Groups)

- Managed Node Groups vs self-managed — real-world tradeoffs
- What happens when a worker node fails?
- How does EKS drain nodes?
- What happens if a node dies mid-request?
- How do you handle kernel upgrades?
- How do you design node groups per workload type?
- How do you avoid noisy neighbors on nodes?
- How do you debug nodes that are Ready but broken?
- How do you handle spot interruptions gracefully?

---

## 4. Pod Scheduling & Placement (Very Common)

- How does Kubernetes decide where to place a pod?
- How do requests and limits actually affect scheduling?
- What happens when limits are exceeded?
- How do you prevent critical pods from being evicted?
- PodAffinity vs NodeAffinity vs Taints/Tolerations — real scenarios
- How do you spread pods evenly across AZs?
- How do you handle uneven pod distribution?
- Why are pods Pending even when nodes have capacity?

---

## 5. EKS Networking – VPC CNI (Grill Zone 🔥)

- How does AWS VPC CNI work internally?
- Why do pods consume VPC IPs?
- What happens when subnets run out of IPs?
- Secondary CIDRs — when and how?
- Prefix delegation — how does it help?
- How do you design EKS networking at scale?
- Pod-to-pod traffic path explanation
- Pod-to-service traffic path explanation
- Service-to-external traffic flow
- How do you debug intermittent network drops?

---

## 6. Services, Ingress & Traffic Flow

- ClusterIP vs NodePort vs LoadBalancer — real use cases
- How does kube-proxy actually route traffic?
- What happens if kube-proxy fails?
- ALB Ingress Controller vs NGINX Ingress — tradeoffs
- How does AWS Load Balancer Controller work?
- What happens during ALB target deregistration?
- How do you do zero-downtime deployments in EKS?
- How do you handle long-lived connections?
- How do you debug 502/503 errors from Ingress?

---

## 7. Scaling – HPA, VPA, Cluster Autoscaler

- How does HPA actually calculate scaling?
- Why does HPA not scale when CPU is high?
- Custom metrics scaling — real implementation challenges
- VPA in production — why most teams avoid it?
- How does Cluster Autoscaler work internally?
- Why does Cluster Autoscaler scale slowly?
- HPA vs KEDA — when and why?
- How do you prevent scaling storms?
- How do you design predictable scaling?

---

## 8. Deployments, Rollouts & Failures

- What happens during a rolling deployment?
- maxUnavailable vs maxSurge — real impact
- Why do deployments hang?
- What causes CrashLoopBackOff?
- Liveness vs Readiness — how they break production
- Init containers — real-world use cases
- How do you roll back instantly?
- How do you detect bad deployments automatically?
- Why do pods restart even when code didn’t change?

---

## 9. Storage in EKS (Stateful Nightmares 😈)

- EBS CSI vs EFS CSI — when and why?
- How does Kubernetes handle volume attachment?
- What happens when a pod moves to another AZ?
- Why do StatefulSets break during failures?
- How do you design multi-AZ stateful workloads?
- How do you handle storage resizing?
- How do you back up Kubernetes volumes?
- How do you restore stateful apps safely?

---

## 10. Security – EKS Deep Dive

- How does EKS authentication work with IAM?
- aws-auth ConfigMap — why is it dangerous?
- IAM Roles for Service Accounts (IRSA) — internals
- How do you prevent privilege escalation in EKS?
- Pod Security Standards vs PSP — migration strategy
- Network Policies — why they often don’t work
- How do you isolate namespaces securely?
- How do you audit access in EKS?
- How do you detect compromised pods?

---

## 11. Secrets & Configuration

- Kubernetes Secrets — why they’re not really secret
- How do you manage secrets at scale?
- External Secrets vs Sealed Secrets — tradeoffs
- How do you rotate secrets without downtime?
- How do you inject secrets securely?
- How do you prevent secrets leakage in logs?
- How do you audit secret access?

---

## 12. Observability (Prometheus / Grafana / Logs)

- Why node metrics look fine but pods fail?
- How do you design Prometheus for large clusters?
- Single Prometheus vs Thanos/Mimir — decision criteria
- How do you prevent Prometheus overload?
- How do you debug missing metrics?
- How do you correlate logs, metrics, and traces?
- Why alerts fire but nothing is wrong?
- How do you design SLO-based alerts?

---

## 13. Upgrades & Day-2 Operations (Interview Favorite)

- How do you upgrade EKS safely?
- Control plane upgrade vs node upgrade — order?
- How do you avoid downtime during upgrades?
- What breaks during Kubernetes version upgrades?
- How do you test upgrades safely?
- How do you handle deprecated APIs?
- How do you roll back a failed upgrade?
- How do you automate cluster lifecycle?

---

## 14. Multi-Cluster & Multi-Region EKS

- Why run multiple clusters?
- How do you route traffic across clusters?
- Global Accelerator + EKS — design scenarios
- How do you sync configs across clusters?
- How do you manage secrets across clusters?
- How do you handle failover?
- How do you observe multi-cluster health?

---

## 15. Cost Optimization (Often Ignored, Always Asked)

- Why is EKS expensive even when idle?
- How do you reduce node costs?
- Spot instances in EKS — safe patterns
- Overprovisioning vs right-sizing
- How do you detect wasted resources?
- How do you enforce resource quotas?
- How do you show cost savings to leadership?

---

## 16. Failure Scenarios (Interview Killers)

- Pods running but traffic failing — why?
- Service healthy but endpoints empty — why?
- Nodes Ready but pods failing — why?
- DNS works sometimes — why?
- HPA scaled but app still down — why?
- Cluster looks healthy but users see errors — why?
- Everything green but latency high — what now?

---

## 17. Architect-Level Design Questions

- Design a production-grade EKS platform for 100+ teams
- Design EKS for fintech / healthcare compliance
- Design EKS for extreme traffic spikes
- Design EKS with zero-trust networking
- Design EKS for zero-downtime deployments globally
- Design EKS observability for executives
- Design EKS disaster recovery

---
