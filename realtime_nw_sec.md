# 🔥 AWS Architect – Networking & Security WAR Room Scenarios
## Real-Time Incidents & How I Handled Them

---

# 1. Production API Not Reachable (ALB Healthy)

Issue:
Users reported 502 errors but ALB showed healthy targets.

How I handled it:
I immediately checked target group health and saw intermittent failures. Then I verified the application logs and found idle timeout mismatch between ALB (60s) and backend (30s). I aligned the timeout values and monitored connections. Issue stabilized.

Root Cause:
Connection reset due to timeout mismatch.

---

# 2. EC2 Instances Lost Internet Access

Issue:
Private subnet instances suddenly couldn’t access internet.

How I handled it:
I checked route tables and found NAT Gateway route missing after recent Terraform change. I restored the 0.0.0.0/0 route to NAT Gateway and validated with curl tests.

Root Cause:
Route table overwrite during infra deployment.

---

# 3. Two VPCs Not Communicating

Issue:
App in VPC-A couldn’t reach DB in VPC-B.

How I handled it:
I verified VPC peering status and discovered overlapping CIDR blocks. Since redesign was not possible immediately, I proposed Transit Gateway migration with proper CIDR reallocation in phased manner.

Root Cause:
CIDR overlap during acquisition integration.

---

# 4. Intermittent Packet Drops

Issue:
Application logs showed random timeout errors.

How I handled it:
Enabled VPC Flow Logs and noticed NACL blocking ephemeral ports on return traffic. Updated NACL to allow ephemeral port range 1024-65535.

Root Cause:
Stateless NACL misconfiguration.

---

# 5. Sudden Spike in Latency (CPU Normal)

Issue:
Latency increased but no CPU spike.

How I handled it:
Checked ELB metrics and found surge queue length increasing. Backend connections were exhausted. Increased connection pool size and scaled Auto Scaling group.

Root Cause:
Connection pool exhaustion.

---

# 6. Website Down Globally

Issue:
Users worldwide couldn’t resolve domain.

How I handled it:
Used dig +trace and discovered domain expired. Coordinated immediate renewal and updated DNSSEC signing.

Root Cause:
Domain renewal automation missing.

---

# 7. Route 53 Failover Not Triggering

Issue:
Primary region down but traffic not shifting.

How I handled it:
Reviewed health check configuration. It was pointing to root path instead of health endpoint. Corrected health check path and reduced TTL to improve failover time.

Root Cause:
Improper health check endpoint.

---

# 8. RDS Access Denied After Key Rotation

Issue:
Application failed after KMS rotation.

How I handled it:
Verified KMS key policy and noticed missing grant for application IAM role. Updated key policy and revalidated encryption context.

Root Cause:
Improper KMS permissions post rotation.

---

# 9. Security Team Reported Suspicious API Calls

Issue:
GuardDuty alert flagged abnormal S3 access.

How I handled it:
Checked CloudTrail logs, identified compromised access key. Disabled key immediately, rotated credentials, audited bucket access logs, and enforced MFA for IAM users.

Root Cause:
Exposed access key in CI logs.

---

# 10. On-Prem to AWS Connectivity Issue

Issue:
On-prem could ping AWS, but reverse traffic failed.

How I handled it:
Reviewed route advertisement via BGP. Found return route missing in on-prem firewall. Coordinated network team to update routing table.

Root Cause:
Asymmetric routing.

---

# 11. ALB Returning 504 Gateway Timeout

How I handled it:
Verified backend processing time exceeded idle timeout. Increased idle timeout and optimized query causing delay.

Root Cause:
Backend slow response.

---

# 12. Sudden Data Exfiltration Concern

How I handled it:
Enabled S3 access logs, checked unusual outbound traffic via VPC Flow Logs, restricted outbound traffic using NACL + AWS Network Firewall.

Root Cause:
Over-permissive outbound rules.

---

# 13. Bastion Host Compromise Risk

How I handled it:
Removed public SSH access. Migrated to SSM Session Manager and restricted inbound 22 entirely.

Root Cause:
Open SSH exposure.

---

# 14. Transit Gateway Traffic Blackhole

How I handled it:
Detected route table association mismatch in TGW. Corrected route propagation settings.

Root Cause:
Incorrect TGW route table association.

---

# 15. DNS Resolution Delay in Hybrid Setup

How I handled it:
Validated Route 53 Resolver inbound endpoint. Discovered missing conditional forwarding rule on on-prem DNS server. Added rule and verified resolution.

Root Cause:
Missing DNS forwarder rule.

---

# 16. IAM Role Suddenly Denied Access

How I handled it:
Checked SCP at OU level. Found explicit deny added during governance update. Modified SCP after impact review.

Root Cause:
Over-restrictive SCP.

---

# 17. Cross-Account S3 Access Failing

How I handled it:
Verified bucket policy and IAM trust relationship. Added correct principal ARN and validated via STS assume-role.

Root Cause:
Trust policy misconfiguration.

---

# 18. High NAT Gateway Cost Spike

How I handled it:
Analyzed VPC Flow Logs and found excessive egress traffic from misconfigured batch job. Restricted internet access and used VPC endpoints instead.

Root Cause:
Uncontrolled outbound traffic.

---

# 19. TLS Handshake Failure

How I handled it:
Reviewed ACM certificate expiration and ALB listener configuration. Renewed certificate and enforced TLS 1.2 policy.

Root Cause:
Expired certificate.

---

# 20. Sudden 403 on S3 Static Site

How I handled it:
Verified bucket policy and Block Public Access setting. Adjusted policy and revalidated CloudFront OAI.

Root Cause:
Policy misalignment.

---

# 21. Private Subnet Cannot Resolve DNS

How I handled it:
Verified VPC DNS hostnames and resolver settings. Enabled DNS resolution in VPC settings.

Root Cause:
DNS resolution disabled in VPC.

---

# 22. Excessive Failed Login Attempts

How I handled it:
Enabled WAF rate limiting and geo-blocking rules. Integrated with Shield Advanced for monitoring.

Root Cause:
Brute-force attack.

---

# 23. Multi-Region Active-Active Drift

How I handled it:
Detected replication lag. Verified DynamoDB Global Table sync. Adjusted write routing strategy.

Root Cause:
Write conflict and replication delay.

---

# 24. Unexpected Route Propagation

How I handled it:
Found dynamic propagation enabled unintentionally in TGW. Disabled unnecessary route propagation.

Root Cause:
Uncontrolled route propagation.

---

# 25. GuardDuty Critical Alert

How I handled it:
Isolated affected EC2 by removing from target group and applying quarantine security group. Investigated IAM activity.

Root Cause:
Compromised instance credentials.

---

# 26. KMS Throttling Errors

How I handled it:
Enabled data key caching and reduced excessive encryption API calls.

Root Cause:
High KMS API usage.

---

# 27. Traffic Mirroring Revealed MTU Issue

How I handled it:
Observed fragmentation issues. Adjusted MTU size to align with on-prem network.

Root Cause:
MTU mismatch.

---

# 28. Failed Blue-Green Deployment DNS Switch

How I handled it:
TTL was set high (300s). Reduced TTL before deployment and used weighted routing for gradual traffic shift.

Root Cause:
High TTL delay.

---

# 29. Cross-Zone Load Balancing Disabled

How I handled it:
Noticed uneven traffic distribution across AZs. Enabled cross-zone balancing.

Root Cause:
Unequal load across zones.

---

# 30. Incident Communication & Containment

Scenario:
Production impact across one region.

How I handled it:
Declared incident severity.
Identified blast radius.
Shifted traffic via Route 53 failover.
Engaged stakeholders.
Performed RCA and implemented preventive guardrails.

Key Focus:
Containment, communication, prevention.

---

# My Architect Approach in WAR Rooms

1. Stay calm.
2. Identify blast radius.
3. Validate recent changes.
4. Check DNS → Load Balancer → Routing → Security → Application.
5. Restore service first.
6. Perform root cause analysis.
7. Implement prevention controls.
