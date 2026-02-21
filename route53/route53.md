# AWS Route 53 – Deep Dive Interview Questions

## 1. Basics

1. What is Route 53 and why is it called “53”?
2. Difference between a Domain Registrar and DNS Service?
3. What is a Hosted Zone?
4. Difference between Public Hosted Zone and Private Hosted Zone?
5. How does DNS resolution work end-to-end?
6. What is TTL and how does it impact performance?
7. What happens when TTL is set too high or too low?

---

## 2. DNS Resolution Flow (Scenario Based)

8. Explain what happens when a user types www.myapp.com in browser.
9. How does Route 53 integrate with TLD and Root servers?
10. What is recursive vs authoritative DNS?
11. What happens if DNS cache expires?

---

## 3. Record Types (Must Know Deep)

12. Difference between A, AAAA, CNAME, and Alias record?
13. Why can’t you create CNAME at root domain?
14. What is Alias record and why is it AWS specific?
15. How Alias record helps with ALB and CloudFront?
16. Difference between MX, NS, SOA, TXT records?
17. What is PTR record and where is it used?

---

## 4. Routing Policies (Very Important)

18. What are different routing policies in Route 53?
19. Difference between Simple and Weighted routing?
20. How does Weighted routing help in blue-green deployments?
21. What is Latency-based routing?
22. What is Geolocation routing?
23. What is Geoproximity routing?
24. What is Failover routing?
25. Can we combine routing policies?

---

## 5. Health Checks

26. How does Route 53 health check work?
27. What types of health checks are available?
28. What happens if all endpoints fail?
29. Can health checks monitor non-AWS resources?
30. How does Route 53 decide endpoint health globally?

---

## 6. High Availability & DR

31. How would you design multi-region active-passive architecture?
32. How to implement active-active using Route 53?
33. How Route 53 helps achieve 99.99% availability?
34. How to integrate Route 53 with Global Accelerator?
35. DNS based failover vs Load balancer failover?

---

## 7. Private DNS & Hybrid

36. How does Private Hosted Zone work?
37. How to resolve on-prem domain using Route 53?
38. What is Route 53 Resolver?
39. What are inbound and outbound endpoints?
40. How does hybrid DNS architecture work?

---

## 8. Security

41. How to secure DNS from DDoS?
42. What is DNSSEC?
43. How to enable DNSSEC in Route 53?
44. How to prevent domain hijacking?
45. IAM permissions best practices for DNS?

---

## 9. Cost Optimization

46. How is Route 53 priced?
47. How to reduce health check costs?
48. What increases query cost?
49. How does latency-based routing affect cost?

---

## 10. Troubleshooting (Real World)

50. Website not reachable but ALB healthy — what to check?
51. DNS propagation delay issue — how to debug?
52. How to check DNS from CLI?
53. Why dig/nslookup returns different results?
54. How to debug intermittent resolution failures?
55. How to reduce DNS failover time?

---

## 11. Advanced Architect Level

56. Difference between Route 53 and CloudFront?
57. When would you not use Route 53?
58. Design low latency global SaaS platform using Route 53.
59. How to handle 10M QPS DNS traffic?
60. How Route 53 scales globally?

---

## 12. Command Line / Practical

61. Command to check DNS resolution?
62. Command to check authoritative nameservers?
63. How to simulate DNS failure?
64. How to test latency-based routing?
65. How to verify DNSSEC working?
