<div align="center">

# 👋 Hi, I'm Maksim Kim

**Backend Software Engineer (Java)** · 3+ years building distributed systems, microservice architectures, and cloud-native applications

![Profile views](https://komarev.com/ghpvc/?username=KiMaksim&color=6DB33F&style=flat-square&label=profile+views)
[![GitHub followers](https://img.shields.io/github/followers/KiMaksim?style=flat-square&color=6DB33F&label=followers)](https://github.com/KiMaksim)

</div>

I specialize in **Java/Spring Boot**, **event-driven systems**, and **AWS serverless & containerized architectures** — and I build production-shaped side projects to stay sharp on system design, resilience, and observability end-to-end.

---

## 🏗️ Featured Project

### [RAG Platform](https://github.com/KiMaksim/rag-platform)
A production-shaped RAG chatbot (FastAPI + React) for answering questions over a document corpus — built to demonstrate real backend engineering, not just a wired-up demo. Every design call below was verified against the running stack, not assumed:

- **Resilience:** retries + circuit breakers (`tenacity`/`pybreaker`) around every external dependency (LLM, embeddings, Postgres). Verified by taking each one down for real — failed calls fail **fast** once a breaker trips (45ms vs. a 10s+ hang), and two real timeout bugs (missing `connect_timeout`, dual-stack DNS resolution) were found and fixed in the process, not just tested around.
- **Async ingestion:** document uploads queue onto Kafka and return immediately instead of blocking the request; a separate worker processes them with retry + dead-letter-queue routing, distinguishing transient failures (worth retrying) from poison documents (routed straight to the DLQ).
- **Caching:** Redis-backed exact-match + semantic answer caching in front of the LLM, with generation-based invalidation so a document update can never serve a stale cached answer.
- **Load testing (k6):** found the real capacity ceiling of the single-GPU serving setup empirically — 65% request failure at just 20 concurrent users, root-caused to the inference backend lacking continuous batching — and used that number to justify a documented migration path (vLLM + GPU-pool autoscaling) instead of guessing at scale.
- **Full observability:** Prometheus/Grafana, Jaeger tracing, and an ELK log pipeline, all correlated by request ID.

`FastAPI` `PostgreSQL/pgvector` `Redis` `Kafka` `React/TypeScript` `Docker Compose` `Prometheus/Grafana/Jaeger/ELK`

### [demo-graphql-java](https://github.com/KiMaksim/demo-graphql-java)
Java + GraphQL API demo.

---

## 🚀 Tech Stack

**Languages**

![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

**Backend & Frameworks**

![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)
![gRPC](https://img.shields.io/badge/gRPC-4285F4?style=for-the-badge&logo=google&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)

**Cloud & DevOps**

![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)
![ArgoCD](https://img.shields.io/badge/ArgoCD-EF7B4D?style=for-the-badge&logo=argo&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white)
![GitLab CI](https://img.shields.io/badge/GitLab_CI-FC6D26?style=for-the-badge&logo=gitlab&logoColor=white)

**Databases & Messaging**

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![Kafka](https://img.shields.io/badge/Apache_Kafka-231F20?style=for-the-badge&logo=apachekafka&logoColor=white)
![Amazon SQS](https://img.shields.io/badge/Amazon_SQS-FF4F8B?style=for-the-badge&logo=amazonsqs&logoColor=white)

**Observability**

![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white)
![Elastic](https://img.shields.io/badge/Elastic_Stack-005571?style=for-the-badge&logo=elastic&logoColor=white)

---

## 🧠 Learning & Goals
- 🚀 Mastering system design for large-scale backend systems
- 🔍 Improving algorithmic problem solving
- 🗣️ Advancing Korean language skills
- 🏗️ Building more side projects with Java/Go + cloud
