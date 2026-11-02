# Curriculum and 18–24 Month Schedule

[Back to overview](README.md)

## Three concurrent tracks

| Track | Objective | Core subjects |
|---|---|---|
| A — CS and software engineering | Understand why software works and fails | C#, Python, DSA, OS, networking, concurrency, testing, architecture |
| B — Data and AI platform specialization | Build scalable, secure, economical data systems | Scala/JVM, Spark, SQL, Parquet, Delta/Iceberg, Kafka, Flink, orchestration, Kubernetes, Terraform, AI/MLOps |
| C — Staff/Principal practice | Lead technical direction across teams | ADRs, RFCs, platform product thinking, strategy, mentoring, adoption, cost, risk, communication |

Track C runs continuously: **one written design or leadership artifact every month**.

## Recommended phases (24-month default)

| Months | Phase | Technical outcomes | Proof of learning |
|---|---|---|---|
| 1–2 | 1. Software engineering foundations in C# | OOP, SOLID, modular design, .NET runtime, async, DI, testing, APIs, observability | Job Management API with tests and ADRs |
| 3–4 | 2. Scala, JVM and functional programming | Scala collections, immutability, types, pattern matching, sbt, JVM/GC, Spark Scala API | Typed Scala project and Spark API exercise |
| 5–6 | 3. Production Python | Type hints, pytest, packaging, generators, async, profiling, PyArrow/Polars, FastAPI | Installable ingestion/validation package |
| 7–8 | 4. Algorithms and CS reasoning | Big-O, hashes, trees, heaps, graphs, BFS/DFS, topological sort, recursion | Dependency scheduler and complexity report |
| 9–10 | 5. OS, networks and concurrency | Processes, memory, I/O, locks, backpressure, TCP, DNS, TLS, HTTP | Bounded file processor and network failure lab |
| 11–13 | 6. Distributed systems and architecture | Messaging, idempotency, outbox, consistency, replication, partitions, sagas | Event-driven validation platform |
| 14–16 | 7. Petabyte-scale data foundations | Spark plans/shuffles/skew, Parquet/Arrow, Delta/Iceberg, Trino, storage economics, incremental data | Metadata-driven lakehouse and performance report |
| 17–18 | 8. Streaming systems | Kafka, event time, windows, state, checkpoints, Flink vs Structured Streaming | Streaming pipeline with replay and late events |
| 19–20 | 9. Cloud platform and SRE | Docker, Kubernetes, Terraform, Azure, identity, CI/CD, tracing, SLOs, recovery | Deployed platform and disaster-recovery exercise |
| 21–22 | 10. Applied AI platform engineering | LLM APIs, embeddings, hybrid search, RAG, evaluations, safe tools, MLOps/GenAIOps | Governed AI data-platform assistant |
| 23–24 | 11. Capstone and Staff readiness | Integration, security, cost, adoption, architecture review, interview practice | Capstone demo, RFC, roadmap, operational scorecard |

### Accelerated 18-month alternative

Combine Months 1–4 into three months if the C# and Scala baselines are strong; combine algorithms and OS/networking into three months; combine streaming with distributed systems; overlap Kubernetes with the capstone. **Do not remove** architecture writing, failure tests, or AI evaluation. If workload becomes unsustainable, return to the 24-month pace.

## Phase 1 — Software engineering foundations (C# as the vehicle)

**Why C# remains first:** You already use it, so you can concentrate on engineering principles instead of syntax. This is not a plan to specialize exclusively in .NET.

Study: value/reference semantics, generics, async/await, cancellation, garbage collection, DI lifetimes, composition, SOLID, modular monoliths, clean boundaries, API design, security, testing with xUnit and Testcontainers, profiling, logging and tracing.

**Lab:** Job Management API with PostgreSQL, idempotency keys, optimistic concurrency, retries, cancellation, integration tests and CI. **Gate:** explain every architectural boundary and diagnose a concurrency failure without AI assistance.

## Phase 2 — Scala and JVM

Study: Scala version compatible with your Spark runtime, immutable collections, case classes, traits, pattern matching, higher-order functions, Options/Eithers, futures, sbt, JVM classloading, GC, serialization, executors, DataFrame/Dataset APIs.

**Lab:** Build a typed Scala project with immutable transformations, tests and sbt; use the Spark Scala API to inspect a basic execution plan. After Phase 3, extend it with equivalent PySpark and Spark SQL transformations and compare physical plans, Python UDF overhead, serialization, shuffle and memory. **Gate:** explain JVM and Scala trade-offs and when Scala helps. Do not assume Scala is faster for equivalent built-in Spark expressions.

## Phase 3 — Production Python

Study: data model, iterators/generators, decorators, context managers, type hints, mypy/pyright, virtual environments, `pyproject.toml`, packaging, pytest, fixtures, logging, configuration, async, multiprocessing, GIL implications, memory profiling, pandas, Polars, PyArrow, FastAPI.

**Lab:** Publish a locally installable Python package with a CLI and API for streaming ingestion, schema validation, checkpointing and manifests. **Gate:** clean install, typed public API, tests, performance benchmark, reproducible build.

## Phase 4 — Algorithms and CS reasoning

Study: Big-O, memory complexity, arrays, stacks, queues, hash tables, trees, heaps, graphs, sorting, binary search, BFS/DFS, topological sorting, cycle detection, greedy and dynamic programming basics; sets, logic and probability as needed.

**Lab:** Dependency-aware scheduler with priority queue and cycle detection. **Gate:** document time/space complexity and explain trade-offs.

## Phase 5 — OS, networking and concurrency

Study: processes vs threads, scheduling, virtual memory, paging, file systems, I/O, durability, locking, deadlocks, bounded queues, backpressure, sockets, TCP, DNS, TLS, proxies, load balancing, connection pooling, HTTP, OAuth/OIDC.

**Lab:** Streaming file processor; compare sequential, async, bounded and unbounded parallel modes; inject latency, DNS, TLS and connection-pool failures. **Gate:** explain measured bottlenecks.

## Phase 6 — Distributed systems

Study: partial failure, delivery guarantees, idempotency, outbox/inbox, retries/jitter, leases, fencing, sagas, consistency, transactions, replication, partitioning, caching, versioned events, security and observability.

**Lab:** Event-driven validation platform with broker, registry, PostgreSQL, object storage, retries, dead letters and trace propagation. **Gate:** survive duplicate events, consumer crashes and broker outages.

## Phase 7 — Large-scale data engineering

Study: Spark driver/executor architecture, jobs/stages/tasks, Catalyst, AQE, joins, shuffles, skew, partitioning, Parquet row groups/statistics, Arrow, small-file compaction, Delta transaction log, Iceberg metadata/snapshots, Trino distributed SQL, object-store characteristics, data contracts, schema evolution, lineage, lakehouse governance.

**Lab:** Metadata-driven Bronze/Silver/Gold pipeline with synthetic data. Benchmark 10 GB → 100 GB as resources allow, then model petabyte scale through partition, file, throughput and cost estimates. **Gate:** justify partitioning, file layout, engine selection and operational cost.

## Phase 8 — Streaming

Study: Kafka topics/partitions/consumer groups, retention, offsets, schemas, CDC, event time vs processing time, watermarks, late events, windows, stateful operations, checkpoints, replay, exactly-once boundaries; compare Flink and Spark Structured Streaming.

**Lab:** Stream synthetic telemetry through Kafka to a stateful processor and lakehouse sink. **Gate:** replay after crash, handle late events and show idempotent outputs.

## Phase 9 — Cloud and reliability

Study: containers, Kubernetes Jobs/Deployments/StatefulSets, probes, requests/limits, networking, identity, Terraform modules/state, Azure networking/storage, CI/CD, GitOps, OpenTelemetry, Prometheus/Grafana, SLOs, incident response, DR, FinOps.

**Lab:** Deploy the event-driven platform locally and optionally to Azure. **Gate:** reproduce deployment, recover from failure, restore database, estimate cost and show trace-driven diagnosis.

## Phase 10 — AI platform

Study: ML basics, LLM APIs, structured outputs, tool calling, embeddings, chunking, hybrid retrieval, reranking, RAG, eval datasets, groundedness, citations, prompt injection, access-aware retrieval, model/prompt versioning, traces, cost, MLOps and GenAIOps.

**Lab:** AI assistant over public/synthetic architecture docs and manifests, with pgvector, citations, read-only tools, evaluation, authorization and audit. **Gate:** show evaluation improvements and block cross-tenant retrieval.

## Phase 11 — Capstone and leadership

Integrate only where meaningful; avoid a needless microservice zoo. Produce a coherent design, architecture review, adoption plan, migration strategy, operational scorecard, cost model, incident drill and 10–15 minute demo. See project briefs and Staff/Principal guide.

## Weekly rhythm

| Activity | Hours |
|---|---:|
| Courses/books | 2 |
| Focused exercises | 1.5 |
| Project implementation | 2.5 |
| Tests, measurement, debugging | 1 |
| ADR/RFC, reflection and leadership practice | 1 |

At 6 hours/week, reduce lecture time and project scope, **not** tests or design reasoning.

## Quarterly gates

- **Q1:** Production .NET service with tests and documented design; begin Scala/JVM fundamentals.
- **Q2:** Scala/JVM lab + Python package evidence.
- **Q3:** Algorithms evidence + OS/network experiments.
- **Q4:** OS/network failure analysis + tested messaging and recovery.
- **Q5:** Spark/lakehouse performance and storage-layout evidence.
- **Q6:** Streaming correctness + reliable platform deployment.
- **Q7:** AI retrieval evaluation, security and observability.
- **Q8:** Cross-system architecture, cost, strategy and Staff-readiness review.
