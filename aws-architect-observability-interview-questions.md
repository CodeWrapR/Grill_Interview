# AWS Architect Interview Question Bank
## Domain 8: Observability – ULTRA DEEP (Prometheus / Grafana / Loki)

This document contains **production-grade, scale-driven, architect-level observability interview questions** covering metrics, logs, traces, alerting, and SLOs.

---

## 1. Observability Fundamentals (Signal Design)

- What problem does observability solve that monitoring does not?
- Metrics vs logs vs traces — when does each fail you?
- Why “collect everything” is a bad strategy?
- How do you design observability before incidents happen?
- What signals matter most to users vs engineers?
- How do you avoid vanity metrics?
- How do you design observability for unknown failure modes?

---

## 2. Metrics Architecture (Prometheus Core)

- Why is Prometheus pull-based?
- When does pull-based break down?
- How does Prometheus store time-series data internally?
- What limits Prometheus scalability?
- Cardinality — why it kills Prometheus?
- How do labels explode memory usage?
- How do you design metric naming conventions?
- How do you decide scrape intervals?
- When should metrics be dropped at source?

---

## 3. Prometheus in Kubernetes (Deep Internals)

- How does Prometheus discover targets in EKS?
- ServiceMonitor vs PodMonitor — real use cases
- Why targets show UP but data missing?
- Why metrics disappear after pod restarts?
- How do relabeling rules actually work?
- How do you secure Prometheus scraping?
- What breaks when namespaces scale?
- How do you isolate tenants in Prometheus?

---

## 4. Scaling Prometheus (Hard Problems)

- Single Prometheus vs sharded Prometheus — tradeoffs
- Federation — when it works and when it fails
- Thanos vs Mimir vs Cortex — decision criteria
- How does long-term storage really work?
- What happens during compaction?
- How do you handle query fan-out?
- How do you design HA Prometheus?
- How do you prevent data gaps?

---

## 5. Alerting (Where Most Teams Fail)

- Why alerting on CPU is useless?
- Symptoms vs causes — how do you choose?
- What is alert fatigue?
- How do you design actionable alerts?
- How do you tune alerts over time?
- How do you design alerts for autoscaling systems?
- How do you prevent alert storms?
- How do you handle alerts during deployments?
- Who owns alerts?

---

## 6. SLOs, SLIs & Error Budgets (Senior Favorite)

- Why SLOs are harder than alerts?
- What makes a good SLI?
- Latency vs availability SLIs — tradeoffs
- How do you measure user experience?
- How do error budgets influence deployments?
- What happens when error budget is exhausted?
- How do you align SLOs with business goals?
- How do you enforce SLOs culturally?

---

## 7. Grafana (Beyond Dashboards)

- Why dashboards lie?
- How do you design dashboards for incidents?
- Golden signals — how do you visualize them?
- How many dashboards are too many?
- How do you design dashboards for executives?
- How do you prevent dashboard sprawl?
- How do you version dashboards?
- How do you handle multi-tenant Grafana?

---

## 8. Logs Architecture (Loki Deep Dive)

- Why logs don’t scale like metrics?
- How does Loki index logs?
- Labels vs log content — design tradeoffs
- Why high-cardinality labels break Loki?
- How do you design log retention policies?
- How do you reduce log ingestion costs?
- How do you handle bursty logs?
- How do you secure logs?

---

## 9. Logs in Kubernetes (Real-World)

- How do container logs flow in EKS?
- DaemonSet log collectors — failure modes
- Filebeat vs Fluent Bit vs Promtail — tradeoffs
- How do you handle multi-line logs?
- How do you correlate logs with pods and nodes?
- Why logs disappear during pod crashes?
- How do you debug missing logs?

---

## 10. Tracing (Often Misunderstood)

- Why tracing is harder than metrics?
- OpenTelemetry — what problem does it solve?
- How do you propagate trace context?
- Sampling strategies — head vs tail
- How do you trace async systems?
- Why traces lie under load?
- How do you correlate traces with logs and metrics?
- When is tracing not worth it?

---

## 11. Correlation & Debugging (Real Incidents)

- CPU normal, latency high — what do you check?
- Errors low, users complaining — why?
- Metrics green, logs empty — how?
- One AZ slow, others fine — how do you see it?
- Why autoscaling hides problems?
- How do you debug intermittent failures?
- How do you debug issues that don’t reproduce?

---

## 12. Observability for Distributed Systems

- Why microservices amplify observability problems?
- How do you detect cascading failures?
- How do you detect retry storms?
- How do you observe queues and backpressure?
- How do you observe async workflows?
- How do you detect partial failures?
- How do you visualize service dependencies?

---

## 13. Security & Observability

- How do you prevent sensitive data in logs?
- How do you secure metrics endpoints?
- How do you audit observability access?
- How do you prevent data exfiltrat
