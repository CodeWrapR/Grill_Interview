
# AWS Architect Interview Question Bank  
## Domain 1: Compute (EC2-Centric Architecture)

This document contains **service-by-service, situational, architect-level interview questions** focused on AWS Compute, designed for **10–15+ years experience** roles covering AWS, DevOps, CI/CD, Observability, and DR.

---

## 1. EC2 – Core Architecture Scenarios

- Design an EC2-based architecture for 10x traffic growth without downtime
- How do you decide instance family and size for a new workload with unknown traffic?
- When would you avoid EC2 even if the workload is long-running?
- How do you design EC2 workloads for AZ failure tolerance?
- How do you isolate noisy-neighbor issues in EC2?
- How do you handle kernel-level tuning in production EC2 instances?
- What happens if an EC2 instance becomes unreachable but not stopped?
- How do you recover EC2 instances stuck in an impaired state?
- How do you handle stateful workloads on EC2 at scale?
- How do you safely patch EC2 instances in production?

---

## 2. EC2 + AMI + Launch Template

- How do you design immutable EC2 deployments using AMIs?
- What goes into an AMI vs user-data?
- How do you version AMIs across environments?
- How do you roll back a bad AMI in production?
- How do you bake secrets into AMIs safely (or avoid it)?
- How do you manage AMI sprawl across accounts?
- How do you test AMIs before production rollout?

---

## 3. EC2 + Auto Scaling Group (ASG)

- How does ASG decide when to scale?
- Difference between target tracking, step scaling, and scheduled scaling?
- How do you prevent scale-in during traffic spikes?
- What happens when ASG replaces an unhealthy instance?
- How do you design ASG for stateful applications?
- How do you warm up instances before they receive traffic?
- How do you handle slow-start applications in ASG?
- What happens if scaling causes database overload?
- How do you cap runaway scaling?
- How do you debug ASG not scaling when metrics look correct?

---

## 4. EC2 + Load Balancers (ALB / NLB)

- ALB vs NLB — real production decision scenarios
- Why would you put an NLB in front of an ALB?
- How does ALB health check failure actually work?
- What happens if targets are healthy but users see 5xx errors?
- How do you handle connection draining during deployments?
- How do you design zero-downtime deployments with ALB?
- How does ALB handle sudden traffic spikes?
- What happens if an ALB node fails?
- How do you handle long-lived TCP connections?
- How do you protect ALB from DDoS attacks?

---

## 5. EC2 + ASG + ALB (Classic Architecture Scenarios)

- Design a highly available web application using EC2, ASG, and ALB
- What happens during:
  - Instance crash
  - Availability Zone failure
  - Sudden traffic spike
- How do you deploy new versions without downtime?
- How do you roll back instantly if error rates increase?
- How do you handle sticky sessions?
- How do you design session management correctly?
- How do you ensure logs survive instance termination?
- How do you detect partial outages?
- How do you handle uneven traffic distribution?
- How do you implement blue/green deployments using EC2?

---

## 6. EC2 + EBS

- gp3 vs io2 — when and why?
- What happens when an EBS volume is full?
- How do you resize EBS volumes without downtime?
- How do you back up EBS volumes consistently?
- How do you recover from EBS corruption?
- How do you design high-IO workloads on EC2?
- What happens if an EBS volume is deleted accidentally?
- How do snapshots impact performance?
- How do you encrypt existing unencrypted EBS volumes?
- How do you migrate EC2 + EBS workloads across regions?

---

## 7. EC2 + Instance Store

- When would you use instance store over EBS?
- What happens to data on stop/start?
- How do you protect data stored on instance store?
- What workloads are best suited for instance store?
- How do you design fault tolerance around instance store?

---

## 8. EC2 + Networking (VPC Level)

- Public vs private EC2 design considerations
- How does EC2 get internet access from a private subnet?
- What happens if a NAT Gateway fails?
- How do security groups and NACLs interact?
- How do you restrict outbound traffic from EC2?
- How do you debug EC2 connectivity issues?
- How do you expose EC2 privately to another AWS account?
- How do you design east-west traffic security?

---

## 9. EC2 + IAM

- Why should EC2 never use long-term access keys?
- How do instance profiles work internally?
- What happens if IAM role permissions change at runtime?
- How do you audit EC2 role usage?
- How do you prevent privilege escalation from EC2?

---

## 10. EC2 + Security

- How do you harden EC2 operating systems?
- How do you protect against SSH brute-force attacks?
- How do you manage SSH access at scale?
- How do you remove SSH access entirely?
- How do you rotate access credentials?
- How do you detect compromised EC2 instances?
- How do you isolate infected instances in production?

---

## 11. EC2 + Observability (Prometheus / Grafana / CloudWatch)

- Why can CPU be normal while the application is slow?
- Which EC2 metrics actually matter in production?
- Node Exporter vs CloudWatch Agent — why and when?
- How do you detect memory leaks?
- How do you alert on symptoms rather than raw metrics?
- How do you correlate logs, metrics, and traces?
- How do you reduce alert noise?
- How do you monitor ASG scaling effectiveness?

---

## 12. EC2 + CI/CD

- How do you deploy applications to EC2 using CI/CD?
- Push-based vs pull-based deployment models
- How do you avoid SSH access in CI/CD pipelines?
- How do you deploy across multiple Auto Scaling Groups?
- How do you handle database migrations safely?
- How do you implement automated rollback?
- How do you prevent partial or inconsistent deployments?

---

## 13. EC2 + Disaster Recovery (DR)

- Backup & Restore strategy for EC2 workloads
- AMI-based DR vs snapshot-based DR
- Cross-region EC2 recovery design
- How fast can EC2-based workloads realistically recover?
- How do you test DR without impacting production?
- How do you handle DNS failover during DR?
- How do you control DR costs?

---

## 14. EC2 + Global Architecture

- How do you design EC2 workloads for global users?
- Route 53 vs Global Accelerator — when and why?
- How do you design active-active EC2 across regions?
- How do you handle data consistency challenges?
- How do you automate regional failover?
- How do you optimize latency globally?

---

## 15. Failure & Edge-Case Scenarios

- Instances are healthy but users see errors — why?
- ASG scaled out but traffic didn’t distribute — why?
- Load balancer healthy but backend failing — why?
- Scaling event caused an outage — how?
- Deployment succeeded but application broke — why?
- All metrics are green but customers are complaining — what do you do?

---
