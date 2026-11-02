# Courses, Books, Documentation and Certifications

[Back to overview](README.md)

## How to use your Udemy subscription

Select **one primary course per subject**, then use books, official docs and labs to fill gaps. Subscription inclusion varies by region and plan; verify availability and course freshness before starting. For fast-moving tools, prefer recent course updates and current official documentation. Avoid copy-along courses with no testing or design decisions.

For the enterprise DBA bridge, do not attempt every overlapping course. Prioritize Oracle and SQL Server HA/DR, then select targeted Azure SQL, Db2, and ExaCC sections. Prefer labs and operational runbooks over exam-only material. Courses cannot establish senior production ownership, on-call experience, or years of professional experience.

| Phase | Udemy search phrases | What the course must teach | Essential complementary resource |
|---|---|---|---|
| Enterprise DBA operations / HA/DR bridge | Oracle: [19c Backup and Recovery](https://www.udemy.com/course/oracle-database-backup-and-recovery/) (listing covers 12c, 19c, and 23ai), [RAC/Grid Infrastructure 19c](https://www.udemy.com/course/oracle-rac-and-grid-infrastructure-concepts/), [Data Guard](https://www.udemy.com/course/oracle-12c-data-guard-administration/), [Exadata Essentials](https://www.udemy.com/course/oracle-exadata-from-scratch-part-1-exadata-essentials/). Optional short modules: [OCI database foundations, including ExaCC](https://www.udemy.com/course/foundation-to-oracle-database-in-oracle-cloud-infrastructure/), [GoldenGate 19c](https://www.udemy.com/course/oracle-goldengate-19c-learn-and-master-oracle-goldengate-w/). Udemy search phrases: `SQL Server Always On Availability Groups hands-on`, `SQL Server backup restore performance tuning`, `Azure SQL Database administration migration`, `IBM Db2 database administration fundamentals`, `Oracle Enterprise Manager monitoring`. | Prioritize Oracle RMAN, RAC/ASM, Data Guard, OEM and SQL Server Always On/backup recovery; then Azure SQL PaaS/IaaS, Db2 operational concepts, cross-platform security, monitoring, tuning and automation. Keep ExaCC to architecture/service boundaries and lifecycle orientation. | Oracle Database and OCI documentation; [Oracle LiveLabs](https://livelabs.oracle.com/); Microsoft Learn SQL Server and Azure SQL documentation; IBM Db2 documentation; authorized lab access. Verify course freshness, lab prerequisites, version fit and subscription availability. |
| C# engineering | `advanced C# .NET async concurrency`; `ASP.NET Core integration testing clean architecture` | runtime, async, DI, testing, API, security | Microsoft Learn: C#/.NET/ASP.NET Core docs; *A Philosophy of Software Design* |
| Scala/JVM | `Scala 2 functional programming`; `Scala Spark DataFrame`; `JVM performance garbage collection` | types, immutability, sbt, JVM, Spark APIs | Scala docs; Spark Scala API; JVM tooling docs |
| Python | `advanced Python type hints pytest packaging`; `Python data engineering PyArrow Polars` | packaging, typing, testing, generators, profiling | Python docs; *Effective Python*; pytest docs |
| Algorithms | `data structures algorithms C#`; `graphs Big O` | complexity, heaps, hash tables, graph traversal | *Grokking Algorithms*; *A Common-Sense Guide to Data Structures and Algorithms* |
| OS/networking | `operating systems processes virtual memory`; `networking backend engineers TCP TLS` | processes, memory, I/O, TCP, DNS, TLS | *Operating Systems: Three Easy Pieces* (free); *Computer Networking: A Top-Down Approach* |
| Distributed systems | `distributed systems design`; `Kafka outbox saga microservices` | failure models, consistency, messaging, idempotency | *Designing Data-Intensive Applications* |
| Spark/lakehouse | `Apache Spark performance optimization`; `Delta Lake internals`; `Apache Iceberg` | physical plans, shuffles, storage and metadata | Spark, Parquet, Delta, Iceberg and Trino official docs |
| Streaming | `Apache Kafka fundamentals`; `Apache Flink stateful stream processing` | partitions, offsets, windows, checkpoints | Kafka and Flink official docs; *Streaming Systems* |
| Cloud/SRE | `Kubernetes hands on CKA`; `Terraform Azure`; `OpenTelemetry` | deploy, secure, observe, recover | Kubernetes, Terraform, Azure Architecture Center; Google SRE books |
| AI platform | `production RAG evaluation`; `LLMOps MLOps`; `AI agents security` | retrieval, evaluation, safe tools, observability | *Designing Machine Learning Systems*; OWASP LLM guidance |

## High-value books (suggested order)

1. **A Philosophy of Software Design** — complexity, interfaces, modularity.
2. **Operating Systems: Three Easy Pieces** — processes, memory, concurrency, persistence.
3. **Designing Data-Intensive Applications** — storage, replication, transactions, streams and distributed systems.
4. **Computer Networking: A Top-Down Approach** — networking foundations.
5. **Fundamentals of Data Engineering** — lifecycle, orchestration, governance, platform thinking.
6. **Learning Spark, 2nd Edition** — execution and practical distributed processing.
7. **Streaming Systems** — event time, watermarks, state and correctness.
8. **Release It!** — resilience and production failure modes.
9. **Site Reliability Engineering** and **The Site Reliability Workbook** — reliability and operations.
10. **Designing Machine Learning Systems** — operational ML and AI system design.
11. **Staff Engineer: Leadership beyond the management track** — influence and technical leadership.
12. **The Staff Engineer's Path** — staff-level scope, communication and strategy.

Use chapters relevant to each phase, not cover-to-cover reading quotas.

## Official documentation bookmarks

- [.NET documentation](https://learn.microsoft.com/dotnet/)
- [Python documentation](https://docs.python.org/3/)
- [Scala documentation](https://docs.scala-lang.org/)
- [Apache Spark documentation](https://spark.apache.org/docs/latest/)
- [Apache Kafka documentation](https://kafka.apache.org/documentation/)
- [Apache Flink documentation](https://flink.apache.org/what-is-flink/)
- [Apache Iceberg documentation](https://iceberg.apache.org/docs/latest/)
- [Delta Lake documentation](https://docs.delta.io/)
- [Apache Parquet documentation](https://parquet.apache.org/docs/)
- [Trino documentation](https://trino.io/docs/current/)
- [Kubernetes documentation](https://kubernetes.io/docs/home/)
- [Terraform documentation](https://developer.hashicorp.com/terraform/docs)
- [Azure Architecture Center](https://learn.microsoft.com/azure/architecture/)
- [OpenTelemetry documentation](https://opentelemetry.io/docs/)
- [OWASP LLM Top 10](https://genai.owasp.org/llm-top-10/)

## Certifications: optional and subordinate to projects

| Timing | Candidate | Reason |
|---|---|---|
| After Kubernetes phase | CKA or CKAD | Practical cloud-native operations or application deployment |
| After Terraform phase | Terraform Associate (current version) | Infrastructure as Code discipline |
| After Azure architecture experience | Current Microsoft Azure architecture credential | Cross-service cloud design |
| After AI phase | Current Microsoft Azure AI Apps/Agents or MLOps/GenAIOps credential | Applied AI platform evidence |

**Important:** Microsoft credential names, exams and retirement dates change. Verify directly on Microsoft Learn before paying or scheduling. Do not assume older AI-102 recommendations remain valid. Limit yourself to 1–2 certifications during the plan.

## Learning-quality checks

Before completing a phase, answer: Can I explain the concept without notes? Can I implement a minimal version? Can I describe failure modes? Can I compare alternatives? Can I test and measure the result? Can I explain why this tool is appropriate at petabyte scale?
