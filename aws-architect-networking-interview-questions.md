# AWS Architect Interview Question Bank  
## Domain 2: Networking (VPC-Centric Architecture)

This document contains **service-by-service, situational, architect-level interview questions** focused on AWS Networking, designed for **10–15+ years experience** roles.

---

## 1. VPC – Core Architecture Design

- How do you design a VPC from scratch for a production workload?
- How do you decide CIDR ranges for long-term growth?
- What mistakes in VPC design are impossible to fix later?
- How do you design VPCs to avoid IP exhaustion?
- Single VPC vs multiple VPCs — decision criteria?
- How do you design blast-radius isolation using VPCs?
- How do you design VPCs for multi-region expansion?
- How do you handle overlapping CIDRs across environments?
- How do you migrate workloads to a new VPC without downtime?

---

## 2. Subnets (Public / Private / Isolated)

- What actually makes a subnet public or private?
- How do you design subnet layout across AZs?
- How many subnets per AZ is too many?
- When would you use isolated subnets?
- How do you design subnets for EKS vs EC2?
- How do you handle subnet IP exhaustion in production?
- How do you resize subnets after production launch?
- How do you segregate tiers using subnets?

---

## 3. Route Tables & Routing

- How does AWS routing precedence work?
- What happens when multiple routes match?
- How do you design route tables for complex environments?
- How do you debug blackhole routes?
- How do you safely change route tables in production?
- What happens if a route points to a deleted target?
- How do you design routing for east-west traffic?

---

## 4. Internet Gateway (IGW)

- What role does IGW actually play?
- Can private instances talk to IGW?
- What happens if IGW is detached?
- How do you design internet access for public workloads?
- How do you restrict inbound vs outbound internet traffic?
- How do you audit internet exposure?

---

## 5. NAT Gateway / NAT Instance

- NAT Gateway vs NAT Instance — real-world decision
- What happens when a NAT Gateway fails?
- How do you design NAT for high availability?
- How do you reduce NAT Gateway costs?
- How do you debug private subnet internet failures?
- How do you control outbound traffic from private subnets?
- How do you log outbound internet access?

---

## 6. Security Groups

- How do security groups actually work internally?
- Stateful vs stateless — real implications
- How do you design least-privilege security groups?
- How do you manage security groups at scale?
- How do you audit unused rules?
- How do you debug security group issues?
- Can security groups cause performance issues?
- How do security groups behave during scaling?

---

## 7. Network ACLs (NACLs)

- When would you use NACLs over security groups?
- How do NACL rule numbers affect traffic?
- Common NACL misconfigurations?
- How do you debug NACL-related outages?
- How do you use NACLs for compliance requirements?
- How do NACLs impact ephemeral ports?

---

## 8. VPC Peering

- How does VPC peering actually work?
- Why is transitive peering not allowed?
- How do you design peering at scale?
- How do you handle overlapping CIDRs?
- How do you secure traffic over VPC peering?
- How do you manage routing across many peerings?
- When does VPC peering become unmanageable?

---

## 9. Transit Gateway (TGW)

- Why was Transit Gateway introduced?
- TGW vs VPC peering — real-world tradeoffs
- How does TGW routing work?
- How do TGW route tables differ from VPC route tables?
- How do you design hub-and-spoke architecture?
- How do you isolate environments using TGW?
- How do you scale TGW across regions?
- How do you control traffic inspection with TGW?
- How do you troubleshoot TGW routing issues?

---

## 10. AWS Global Accelerator

- What problem does Global Accelerator solve?
- Global Accelerator vs Route 53 — when and why?
- How does Global Accelerator route traffic?
- What happens during regional failure?
- How does Global Accelerator improve latency?
- What AWS services integrate with Global Accelerator?
- How do you design multi-region failover using GA?
- How do you monitor GA performance?

---

## 11. Route 53 (DNS Architecture)

- How does Route 53 resolve DNS queries?
- Public vs private hosted zones — use cases
- How does Route 53 health checking work?
- Active-active vs active-passive DNS designs
- Latency-based vs geolocation routing
- How do you design DNS failover for DR?
- How do you handle DNS caching during failover?
- How do you migrate DNS with zero downtime?

---

## 12. VPC Endpoints (PrivateLink)

- Gateway vs Interface endpoints — differences
- Why use VPC endpoints instead of NAT?
- How does PrivateLink work internally?
- How do you expose private services across accounts?
- How do you secure PrivateLink connections?
- How do you control endpoint access?
- How do you design PrivateLink at scale?
- Limitations of VPC endpoints?

---

## 13. Hybrid Networking (On-Prem ↔ AWS)

- Site-to-Site VPN vs Direct Connect — decision criteria
- How does VPN failover work?
- How do you design HA VPN?
- How do you integrate Direct Connect with TGW?
- How do you design hybrid DNS?
- How do you handle asymmetric routing?
- How do you monitor hybrid connectivity?
- How do you secure on-prem to AWS traffic?

---

## 14. Multi-Account Networking

- How do you design networking for many AWS accounts?
- Centralized networking vs decentralized networking
- How do you share subnets across accounts?
- How do you enforce network guardrails?
- How do you prevent shadow networking?
- How do you audit network changes across accounts?

---

## 15. Networking for EKS & Containers

- How does AWS VPC CNI work?
- Why do EKS pods consume VPC IPs?
- How do you handle IP exhaustion in EKS?
- How do you design EKS networking for scale?
- Pod-to-pod vs service-to-service traffic
- How do you secure east-west traffic in EKS?
- How do you expose EKS services privately?

---

## 16. Networking Failures & Edge Cases

- VPC looks correct but traffic fails — why?
- Security groups open but traffic blocked — why?
- DNS resolves but service unreachable — why?
- NAT Gateway up but internet not working — why?
- TGW routes correct but packets dropped — why?
- Intermittent connectivity issues — how do you debug?
- Latency spikes with no errors — why?

---
