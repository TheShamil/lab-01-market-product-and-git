## Components and roles

Using the core components identified in the Telegram architecture :

- **Mobile App (iOS/Android)**

  - **Mobile Engineer**: Specializes in Swift/Kotlin to build the native user interface and local encryption logic.

  - **QA/Manual Tester**: Ensures the app works across various device models and OS versions.

  - **Product Designer (UI/UX)**: Designs the messaging interface and user workflows.

- **MTProto Gateway (DC Entry)**

  - **Network Engineer**: Manages the high-performance TCP/UDP connections and edge routing.

  - **Security Engineer**: Focuses on the implementation of the MTProto encryption and defense against DDoS attacks.

  - **Back-end Engineer**: Develops the high-throughput protocol translation layer.

- **Message & Auth Services**

  - **Back-end Engineer (Distributed Systems)**: Writes the core business logic for message routing and session management.

  - **Site Reliability Engineer (SRE)**: Monitors service latency and handles incident response for core services.

  - **DevOps Engineer**: Manages the CI/CD pipelines for deploying microservice updates.

- **Sharded Chat DB & State Cache**

  - **Database Administrator (DBA) / Database Engineer**: Optimizes the "Custom Engine" performance and handles sharding logic.

  - **Data Engineer**: Manages data consistency across shards and migration tasks.

- **Distributed File System (DFS)**

  - **Storage Engineer**: Specializes in managing large-scale, distributed object storage for media files.

  - **Back-end Engineer**: Develops the Media Service that interfaces with the storage layer.

## Roles and responsibilities

Based on the roles listed above, here are five typical responsibilities for each:

1. **Mobile Engineer**: Responsible for developing native features, optimizing local storage (like the local message cache), and ensuring smooth animations and UI performance on mobile devices.

2. **Back-end Engineer**: Focuses on designing scalable APIs, implementing business logic (like message delivery rules), and ensuring efficient communication between microservices via internal RPCs.

3. **Site Reliability Engineer (SRE)**: Tasked with maintaining high availability (e.g., 99.99% uptime), defining Service Level Objectives (SLOs), and automating the recovery of services when they fail.

4. **DevOps Engineer**: Creates and maintains the "Infrastructure as Code" (IaC), manages deployment pipelines (CI/CD), and ensures that developer environments are consistent with production.

5. **Security Engineer**: Conducts vulnerability assessments, manages encryption keys, and implements security protocols to protect user data from unauthorized access or external attacks.

## Common skills across roles

Across these diverse roles, several technical and "soft" skills are universally required to keep a platform like Telegram running:

- **Version Control (Git)**: Essential for all roles to track code changes and collaborate across global teams.

- **Scripting (Python/Bash/Go)**: Used by developers, DevOps, and SREs alike to automate repetitive tasks and manage system configurations.

- **Linux Fundamentals**: A deep understanding of the Linux operating system is necessary for managing the servers and containers that host the backend.

- **Observability & Monitoring**: Knowing how to use tools like Prometheus, Grafana, or ELK to track system health is a shared requirement for ensuring reliability.

- **Containerization (Docker/Kubernetes)**: Most modern services are deployed in containers, requiring all engineering roles to understand how they are packaged and orchestrated.

- **Communication & Systems Thinking**: The ability to understand how a change in one component (e.g., the mobile app) affects another (e.g., the database) is critical for troubleshooting and design.

## My chosen role

<Backend>

### Skills I already have

- Go
- GitHub
- TCP/IP

### Skills I clearly lack

- Kubernetes
- Cloud technologies.
- Event-Driven Architecture.
- Database Scalability.

## 5. Research job postings

Below are 5 representative job postings for Backend Engineers with a focus on Go and distributed systems:

1. **Senior Backend Developer (Go) Kubernetes**

    - **Link:** [Cloud.ru on HH.ru](https://hh.ru/vacancy/87604140)

    - **Key Skills:** Go (Golang), Kubernetes, 3–6 years experience, microservices architecture.

2. **Go (Golang) Backend Developer (Highload)**

    - **Link:** [Evrone.ru on HH.ru](https://hh.ru/vacancy/75887385)

    - **Key Skills:** High-load system design, Go, architectural patterns, optimization for high throughput.

3. **Senior Golang Engineer (Public Gateway)**

    - **Link:** [TMT on Rabota.by](https://hh.ru/vacancy/129410740)

    - **Key Skills:** AWS (EKS, Kafka, SQS), MongoDB/Couchbase, rate limiting and authentication patterns, Prometheus/Grafana.

4. **Senior Go Developer / Старший Go программист**

    - **Link:** [IP Kuzminova on HH.ru](https://hh.ru/vacancies/senior-golang-developer)

    - **Key Skills:** Distributed systems, Go, REST/gRPC API design, performance profiling.

5. **Middle+/Senior Golang Developer**

    - **Link:** [X5 Tech on HH.ru](https://hh.ru/vacancies/golang-razrabotchik)

    - **Key Skills:** PostgreSQL, Docker, unit testing, integration with message brokers (Kafka/RabbitMQ).

---

## 6. Document job market snapshot

_Update your `docs/roles-and-skills.md` with the following:_

### Skills that appear in several postings

- **Go (Golang)**: The primary language for modern, high-concurrency backend services.

- **Kubernetes (K8s)**: Essential for container orchestration and managing microservices at scale.

- **Message Brokers (Kafka/RabbitMQ)**: Required for asynchronous communication and event-driven architectures.

- **Distributed Databases**: Experience with both SQL (PostgreSQL) and NoSQL (MongoDB, Redis) systems.

### Skills specific to a single posting

- **Fintech Security Patterns**: Specific requirements for rate limiting and secure money transfer protocols (TMT posting).

- **Blockchain Integration**: Some specialized Go roles require knowledge of smart contracts or blockchain nodes.

- **Couchbase**: While NoSQL is common, specific document stores like Couchbase appear in niche high-load roles.

---

## 7. Personal reflection

_(Note: As per your instructions, this section is for **your** own reflection. Here are the prompts to guide your writing without an LLM generating the content for you:)_

- **Which role did I choose and why?** (Think about your interest in the Telegram backend logic you just analyzed).

- **How does my skillset compare to the market demands?** (Compare your "Skills I already have" like Go and TCP/IP against the "Skills specific to a single posting" or common skills like Kubernetes).

- **Which one or two key skills for this role would I like to develop this semester and why?** (Focus on the gap you identified, such as Kubernetes or Cloud Technologies, to reach the "Senior" or "Highload" level seen in the job postings).
