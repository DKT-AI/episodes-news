# Episode #104: DKT104

## Introduction
Welcome to DevOps Kitchen Talks, episode #104! Today we're digging into a new class of AI models for decision-making, why the harness around a model matters more than the model itself, Kubernetes 1.37, and the fundamentals of high-load system design. We'll also go through the top Kubernetes interview questions.

## News

### 1. Jev is the FIRST of a Whole New Class of AI Models (Here's How to Actually Use It)
An overview of JEV from Typesafe, a "System 1 model" for decision-making. Instead of generating text like an LLM, it picks from predefined answer options and reports its confidence. It is trained with the RLCD algorithm, claims to be 20–200x faster and 40–1000x cheaper than LLMs with zero structured-output errors, and is available via OpenRouter.
**Link:** https://www.youtube.com/watch?is=3GWiVK5nst-AIUjc&v=bA8WeHYmJko&feature=youtu.be
**Talking Points:**
- Choosing instead of generating: how a "System 1" model differs from LLMs, and which tasks it suits (LLM request routing, PR triage, browser automation, game testing).
- Are the claims of 20–200x speed and 40–1000x lower cost realistic? What should we check before trusting these numbers?
- Where would such a model fit in a DevOps pipeline, for example as a cheap router or classifier in front of expensive LLM calls?

### 2. This week's news from Zed, Anthropic, and OpenRouter shows why better harnesses matter more than better models - The New Stack
A weekly roundup arguing that AI value is shifting from the models themselves to the harness: the software that supplies context, connects tools, and verifies results. Zed launched Delta (thread-based collaboration instead of pull requests), Anthropic is merging Claude Chat and Cowork, and OpenRouter introduced US in-region routing. On the Real-SWE benchmark the best agent solved only 38.8% of tasks, and LLM response caching cuts costs by 57.5%.
**Link:** https://thenewstack.io/ai-agent-harness-economics/
**Talking Points:**
- "Harness over model": what does the harness consist of, and why does it now determine the real value of AI tools?
- Zed Delta and threads instead of pull requests: will this change code review and team collaboration practices?
- 38.8% on Real-SWE and 57.5% savings from caching: what do these numbers mean for teams running agents in production?

### 3. БАЗА по ВЫСОКОНАГРУЖЕННЫМ СИСТЕМАМ. System Design
A review of the core concepts of high-load systems: microservices vs monolith, vertical and horizontal scaling, and stateless services. It covers interaction protocols (REST, gRPC, GraphQL, WebSocket), API Gateway, message brokers (Kafka, RabbitMQ), Service Discovery, distributed transactions (2PC, Saga), idempotency, relational and NoSQL databases, sharding, replication, caching (Redis), rate limiting, fault-tolerance patterns, and monitoring (logs, metrics, tracing).
**Link:** https://www.youtube.com/watch?si=FJR7xHP53Vk22pw3&v=YdZmV1URBoU&feature=youtu.be
**Talking Points:**
- Microservices or monolith: when does splitting a system actually pay off, and when does it only add complexity?
- Distributed transactions and idempotency (2PC vs Saga): the practical pitfalls teams run into.
- Observability as a foundation: how logs, metrics, and tracing complement each other in high-load systems.

### 4. Обзор Kubernetes 1.37: воскрешаем поды из снапшотов, планируем сложные workload и следим за здоровьем PV. Разбор 22 фич / Хабр
A review of Kubernetes 1.37 and its 22 alpha features. Highlights include Pod-Level Checkpoint/Restore for freezing and restoring pods from snapshots, DRA improvements, noexec/nosuid/nodev mount flags, TLS in gRPC probes, PV health monitoring via CSI, JWT authentication from the API server to admission webhooks, kube-proxy switching to nftables by default, and the deprecation of ipvs mode.
**Link:** https://habr.com/ru/companies/flant/articles/1071726/
**Talking Points:**
- Pod-Level Checkpoint/Restore: what scenarios does it open up (fast recovery, migration, debugging), and what are the limitations at the alpha stage?
- The kube-proxy move to nftables by default and the ipvs deprecation: what should cluster operators prepare for?
- DRA improvements and PV health monitoring: how they help with scheduling complex workloads such as GPU and ML.

### 5. ТОП 10 ВОПРОСОВ НА СОБЕСЕДОВАНИИ ПО KUBERNETES
A video walkthrough of 10 popular Kubernetes interview questions: pods and the pause container, container types in a pod (init, sidecar, ephemeral), cluster architecture (control plane and worker nodes), manifests (Deployment, StatefulSet, DaemonSet, Job), requests/limits (CPU throttling vs memory OOMKill), and HPA.
**Link:** https://www.youtube.com/watch?si=-oZ4ys7oelzCy6rH&v=9VyaUkwoLyk&feature=youtu.be
**Talking Points:**
- Which of these questions do we ask (or get asked) most often in interviews, and which answers reveal real experience?
- Requests and limits: CPU throttling vs OOMKill, and the common mistakes in configuring them.
- How interview questions have evolved: what should an engineer know about Kubernetes today beyond the basics?

### 6. Jev: как устроен его API решений и что на нём уже строят / Хабр
An analysis of the Jev API from TypeSafe: instead of generating text, it accepts a state and typed questions (Noul, Choice, Score) and returns probability distributions. The author studied around 100 projects, examined a browser agent, the "seven seconds" arithmetic, and the limits of applicability. Type safety guarantees the shape of the answer, not its correctness, and the author recommends piloting against the current solution on a labeled sample.
**Link:** https://habr.com/ru/articles/1084030/
**Talking Points:**
- The API design: state, typed questions, and probability distributions as output, and how this differs from working with LLM APIs.
- "Type safety guarantees shape, not correctness": how to validate quality before adopting it?
- The recommended pilot approach (comparing against the current solution on a labeled sample) and lessons from the ~100 projects the author reviewed.

## Conclusion
That's all for episode #104 of DevOps Kitchen Talks. Thanks for listening, see you next time!