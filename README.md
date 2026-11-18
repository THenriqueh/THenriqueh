# Thallis Ferreira

**Backend Engineer — Java · Spring Boot · Event-Driven Architecture**
Building backend systems for the financial sector · Recife, Brazil

[LinkedIn](https://www.linkedin.com/in/thallis-ferreira-dev-java/) · [Email](mailto:thallis.ferreira2019@gmail.com)

---

### About

Backend engineer at **Accenture**, with 4 years building services for banks and large enterprises
(previously at **NTT DATA**, working with Bradesco, Banco PAN and AB InBev).
My work sits where reliability matters most: payment flows, credit products, customer notifications and
system integrations that can't afford to lose a message.

I focus on **hexagonal architecture**, **asynchronous messaging** and **systems that are easy to change**,
and I care about understanding *why* an architectural decision is made, not just how to implement it.

→ Full experience on [LinkedIn](https://www.linkedin.com/in/thallis-ferreira-dev-java/).

---

### Featured project

#### 💳 [payments](https://github.com/THenriqueh/pagamentos) — asynchronous payment processing, PIX-style

A reference implementation of how I'd design an instant-payment backend: idempotent, event-driven,
observable, and built so the domain doesn't depend on any framework.

```mermaid
flowchart LR
    C[Client] -->|POST /pagamentos| API[REST adapter]
    API --> UC[Use case<br/>domain core]
    UC -->|publish| K[(Kafka<br/>pagamentos.solicitados)]
    K --> P[Processor]
    P --> DB[(PostgreSQL<br/>write model)]
    P -->|events| Q[(MongoDB<br/>read model)]
```

**Design decisions documented in the repo:** hexagonal architecture (ports & adapters) · CQRS with separate
read/write models · idempotency keys · retries and circuit breakers with Resilience4j ·
partitioning strategy for ordering guarantees · observability with Prometheus, Grafana and ELK.

**Stack:** Java 21 · Spring Boot · Kafka (KRaft) · PostgreSQL · MongoDB · Docker · AWS (ECS, RDS)

**Status:** 🚧 in active development

- [x] Local infrastructure with Docker Compose (Kafka KRaft, PostgreSQL, Kafka UI)
- [x] Topic design — `pagamentos.solicitados`, 3 partitions
- [x] Domain model and hexagonal package structure
- [x] Payment use cases + REST adapter
- [x] Kafka consumer, idempotency and retries
- [ ] CQRS read model
- [ ] Observability stack
- [ ] AWS deployment

---

### Tech

| Area | Tools |
| --- | --- |
| **Languages & frameworks** | Java (8 → 21), Spring Boot, Spring Data JPA / Hibernate |
| **Messaging & integration** | Apache Kafka, Apache Camel, RabbitMQ, REST, OpenAPI |
| **Data** | PostgreSQL, MongoDB, SQL |
| **Security** | OAuth2, JWT, Keycloak |
| **Cloud & DevOps** | AWS, Docker, Jenkins, Git (GitHub, GitLab, Bitbucket) |
| **Observability** | Datadog, Prometheus, Grafana |
| **Architecture** | Hexagonal / Clean Architecture, microservices, event-driven design |

---

### Certifications & education

- **AWS Certified Cloud Practitioner** — Amazon Web Services
- *In progress:* AWS Certified Developer – Associate
- Systems for Internet — Universidade Católica de Pernambuco (UNICAP)

---

<sub>Currently studying distributed systems, system design and Kubernetes. Open to conversations about backend roles in fintech and banking.</sub>
