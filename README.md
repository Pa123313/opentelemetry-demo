🌌 Cloud-Native Observability: OpenTelemetry Microservices Demo

A comprehensive implementation of OpenTelemetry (OTel) across a distributed microservices architecture. This project showcases the ability to instrument, collect, and visualize the "Three Pillars of Observability" (Metrics, Logs, and Traces) in a complex, real-world environment.

🚀 Project Overview

This project utilizes the Astronomy Shop microservice suite to demonstrate how to achieve full-stack visibility. By integrating Prometheus, Grafana, and Locust, I’ve established a proactive monitoring system capable of detecting latency spikes and resource exhaustion.

🛠️ Observability & SRE Stack

Instrumentation: OpenTelemetry SDKs (Java, Python, Go, Node.js).

Telemetry Collection: OpenTelemetry Collector (Contrib) for processing and exporting data.

Metrics & Storage: Prometheus for time-series data.

Visualization: Grafana (Custom Dashboards for Span Metrics and Service Health).

Load Testing: Locust (Distributed load generation to simulate real-user traffic).

Infrastructure: Kubernetes / Docker-Compose.

📊 Performance Analysis & Insights
1. Real-Time Distributed Tracing & Span Metrics
I configured custom Grafana dashboards to monitor Service Latency (P95) and Mean Rate across 10+ microservices. This allows for immediate identification of "hot paths" in the distributed system.

<img width="1345" height="702" alt="span-metrics-analysis png" src="https://github.com/user-attachments/assets/63face1c-1a2c-4dd2-b09f-b5b25f563b76" />


2. OTel Collector Health & Throughput
Monitoring the OpenTelemetry Collector itself to ensure zero data loss. This dashboard tracks spans/sec and logs/sec being processed through the pipeline.

<img width="1347" height="634" alt="otel-collector-telemetry png" src="https://github.com/user-attachments/assets/d4429670-99fa-4865-af4b-ef06e5fdac2f" />


3. Automated Load Testing
Using Locust, I simulated concurrent user behavior to stress-test the /api/checkout and /api/cart endpoints, capturing failure rates and response times under load.

<img width="1335" height="682" alt="locust-load-test-results png" src="https://github.com/user-attachments/assets/a21ee713-66b6-4ee3-839a-adf1891bc0c8" />


4. Resource Utilization (SRE View)
Monitoring CPU and Memory consumption per service (e.g., product-catalog, frontend) to establish performance baselines and right-size Kubernetes resource limits.

<img width="1356" height="688" alt="service-resource-monitoring png" src="https://github.com/user-attachments/assets/ad07dbd7-b964-4f4f-bd84-329fcf537975" />


💡 Key Accomplishments

Bottleneck Identification: Used Span Metrics to identify that the accounting service had a P95 latency of 15s during peak load.

Unified Pipeline: Successfully routed logs and metrics through a single OTel Collector, reducing agent overhead on the infrastructure.

Stress Resilience: Verified system stability up to 50+ RPS with a 78% success rate on high-complexity transaction paths.

🛠️ How to Deploy

Clone the Repo: git clone <repo-link>

Launch Stack: docker-compose up -d (or kubectl apply -f ./k8s)

Access Dashboards:

Grafana: http://localhost:8080/grafana

Locust: http://localhost:8080/loadgen
