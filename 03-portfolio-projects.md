# Portfolio Projects and Capstone Specifications

[Back to overview](README.md)

## Shared project quality bar

Every repository should include: README, goals/non-goals, architecture diagram, ADRs, source, unit and integration tests, reproducible local environment, CI, threat notes, observability, failure tests, performance results, operational runbook, trade-offs, and lessons learned. Use synthetic/public data only.

Suggested structure:

```text
.github/workflows/
docs/architecture.md
docs/decisions/
docs/security.md
docs/testing-strategy.md
docs/operations.md
docs/performance.md
src/
tests/
infra/
scripts/
README.md
```

## P0 — Enterprise DBA Operations and HA/DR Readiness Lab

**Purpose:** Front-load evidence for enterprise DBA technical gaps across Oracle and SQL Server, with Azure SQL and Db2 orientation. ExaCC is a bounded architecture module, not the project's center. This is a learning lab and operations pack, not a claim of senior production ownership.

**Scope:** Practice Oracle RMAN recovery and, where authorized environments permit, RAC/ASM or Data Guard scenarios. Practice or document SQL Server Always On, backup/restore, and failover; compare Azure SQL service models, monitoring, security, and migration paths; and produce a Db2 operational comparison. Include monitoring, least privilege, patching, scripting, incident RCA, change controls, and a short ExaCC architecture/service-boundary overview.

**Evidence:** Cross-platform architecture comparison, lab/version notes, Oracle recovery and HA runbooks, SQL Server Always On/failover decision tree, Azure SQL service-selection and migration brief, Db2 comparison, tuning/RCA report, ExaCC boundary diagram, and a skills matrix distinguishing studied, lab-tested, and production experience.

**Limits:** Do not imply that a single-instance lab demonstrates RAC, Always On, or ExaCC production operations. Use only systems and data you are authorized to access. Production experience, on-call ownership, mentorship, and the posting's stated years requirement remain separate gaps.

## P1 — Job Management API (.NET)

**Purpose:** Demonstrate transferable software engineering fundamentals using a familiar language.

**Stack:** C#, ASP.NET Core, PostgreSQL, Dapper or EF Core, xUnit, Testcontainers, Docker, OpenTelemetry.

**Requirements:** POST/GET/cancel/retry jobs; explicit state machine; idempotency keys; optimistic concurrency; background worker; authentication; health; logs/metrics/traces; CI.

**Failure tests:** concurrent updates, duplicate submissions, database timeout, worker crash, cancelled request.

**Evidence:** API contract, architecture review, test report, concurrency explanation.

## P2 — Scala/JVM Foundations

**Purpose:** Build practical Scala and JVM fluency early, with a small deliverable that does not depend on Python.

**Stack:** Scala version compatible with the target Spark runtime, sbt, Scala test framework, Apache Spark.

**Requirements:** typed domain model; immutable transformations; case classes and pattern matching; Options/Eithers; unit tests; a small Spark DataFrame transformation; explain plan inspection; documented JVM/runtime observations.

**Evidence:** reproducible sbt build, test report, short explanation of type and collection choices, and Spark execution plan.

## P3 — Python Ingestion and Validation SDK

**Purpose:** Demonstrate production Python rather than notebook-only experience.

**Stack:** Python, `pyproject.toml`, pytest, mypy/pyright, ruff, PyArrow, Polars, Pydantic, optional FastAPI.

**Requirements:** installable package; CLI; streaming readers; schema validation; manifest generation; checkpoint/resume; typed interfaces; benchmark; CI.

**Failure tests:** malformed data, interrupted run, duplicate file, partial output, memory pressure.

**Evidence:** package installation guide, coverage, profiling, performance report.

## P4 — Dependency-Aware Scheduler

**Purpose:** Demonstrate CS fundamentals and algorithmic reasoning.

**Stack:** C# or Python (implement core algorithms yourself).

**Requirements:** graph dependencies, cycle detection, topological order, priority heap, concurrency limit, cancellation, retries.

**Evidence:** complexity table, property tests, benchmark and design rationale.

## P5 — Scala/PySpark/Spark SQL Benchmark

**Purpose:** Separate language overhead from distributed execution cost.

**Stack:** Scala, sbt, Spark, PySpark, Spark SQL, Parquet, synthetic datasets.

**Experiments:** equivalent built-in DataFrame expressions, Python UDF vs native expression, join types, skew, partition counts, shuffle sizes, memory/GC, explain plans.

**Metrics:** elapsed time, task time, shuffle bytes, spill, peak memory, number of tasks, file count, cluster settings.

**Critical insight:** Scala does not automatically outperform PySpark when both produce equivalent optimized physical plans. Explain where Python UDF or driver-side code changes the comparison.

## P6 — Event-Driven Validation Platform

**Purpose:** Demonstrate distributed-system correctness and resilience.

**Stack:** .NET and/or Python services, PostgreSQL, RabbitMQ or Kafka, object storage emulator, OpenTelemetry.

**Flow:** upload → durable event/outbox → validation worker → dataset registry → notification → status API.

**Requirements:** idempotent consumers, outbox/inbox, retries/jitter, dead-letter queue, versioned contracts, state transitions, audit, tenant context, trace propagation.

**Failure tests:** broker outage, crash before/after acknowledgment, duplicate events, poison message, service timeout, out-of-order events.

**Evidence:** event catalogue, sequence diagrams, recovery tests, SLO draft, security review.

## P7 — Metadata-Driven Lakehouse and Scale Lab

**Purpose:** Demonstrate practical petabyte-scale design without petabyte-scale spending.

**Stack:** Spark, Scala/PySpark/SQL, Parquet, Delta Lake; compare Iceberg and Trino where feasible; object storage.

**Requirements:** Bronze/Silver/Gold; dataset and schema registry; versioned manifests; incremental processing; lineage; quarantine; data-quality checks; compaction; performance dashboard.

**Scale experiments:** begin 1–10 GB; increase toward 100 GB only if hardware/budget permits. Generate skewed distributions and many small files. Compare partitioning, joins, compaction, Z-order/data-skipping where supported, and checkpoint/restart.

**Petabyte extrapolation:** estimate data arrival rate, partition cardinality, object count, metadata overhead, network throughput, compute-hour cost, recovery time, and retention. Clearly label extrapolations, not measured petabyte benchmarks.

**Evidence:** benchmark notebook, physical plans, architecture decision on Delta vs Iceberg, cost model, lineage example.

## P8 — Streaming Analytics

**Purpose:** Demonstrate correctness of continuous distributed data processing.

**Stack:** Kafka, Flink or Spark Structured Streaming, schema format, Parquet/Delta/Iceberg sink.

**Requirements:** event-time windows, watermarks, late events, checkpointing, state management, replay, deduplication, backpressure, sink idempotency.

**Failure tests:** restart processor, duplicate events, out-of-order data, delayed messages, broker outage.

**Evidence:** end-to-end lag metrics, checkpoint recovery demo, semantics explanation.

## P9 — Cloud Platform and Reliability

**Purpose:** Demonstrate operations, security and infrastructure as code.

**Stack:** Docker, Kubernetes, Helm/Kustomize, Terraform, Azure or local equivalent, OpenTelemetry, Prometheus/Grafana.

**Requirements:** automated deploy, least privilege, secret handling, probes, scaling, metrics, traces, backup/restore, SLO dashboard, rollback.

**Failure tests:** pod kill, resource throttling, failed deployment, database restore, identity failure.

**Evidence:** runbooks, DR exercise, cost estimate, operational review.

## P10 — Governed AI Data Platform Assistant

**Purpose:** Demonstrate applied AI engineering with data-platform governance.

**Stack:** Python or .NET, LLM API, PostgreSQL + pgvector, hybrid search, evaluation harness, OpenTelemetry.

**Requirements:** ingest docs/DDL/manifests; chunk and embed; metadata filters; citations; safe read-only tools; SQL suggestions without automatic execution; human approval; prompt/model versioning; cost and latency tracking; evaluation.

**Failure/security tests:** prompt injection, unsupported answer, wrong citation, cross-tenant retrieval, destructive SQL, malformed tool call, rate limit.

**Evidence:** golden dataset, retrieval metrics, answer-evaluation report, audit log, threat model.

## Capstone — Governed Data & AI Platform

```text
Public / Synthetic Data Sources
            |
       Upload / CDC
            |
     Object Storage
            |
   Validation + Registry  <----> Metadata / Schema / Lineage
            |
    Batch + Streaming
            |
 Bronze -> Silver -> Gold
            |
 Analytics / SQL / APIs
            |
   Governed AI Assistant

Cross-cutting: Identity, CI/CD, Observability, Reliability, Cost
```

**Architecture rule:** Start as a modular monolith plus workers. Split services only for justified scaling, isolation, ownership or deployment needs.

**Staff-level deliverables:** RFC, stakeholder needs, nonfunctional requirements, alternative designs, adoption plan, migration phases, cost model, threat model, operating model, SLOs, metrics, decision log, and a 10–15-minute demo.

**Definition of done:** A stranger can clone, run, test, understand and critique the platform; failures are demonstrated, not merely described.
