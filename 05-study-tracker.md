# Study Tracker, Assessments and Templates

[Back to overview](README.md)

## Baseline self-assessment

Score 0 = unfamiliar, 1 = conceptual, 2 = guided practice, 3 = independent, 4 = can design/debug/teach.

| Skill | Start (0–4) | 6 months | 12 months | 18 months | Final |
|---|---|---|---|---|---|
| Oracle DBA / RMAN / OEM operations | | | | | |
| Oracle RAC / ASM / Data Guard | | | | | |
| Exadata / ExaCC architecture | | | | | |
| SQL Server Always On / backup / recovery | | | | | |
| Azure SQL services / migration | | | | | |
| Db2 operational fundamentals | | | | | |
| Cross-platform tuning / security / automation | | | | | |
| Incident RCA / change management / runbooks | | | | | |
| SQL and database internals | 3 | | | | |
| C#/.NET engineering | 2 | | | | |
| Python engineering | 2 | | | | |
| Scala/JVM | 0 | | | | |
| Data structures/algorithms | 1 | | | | |
| OS and concurrency | 1 | | | | |
| Networking | 1 | | | | |
| Distributed systems | 0 | | | | |
| Spark optimization | 0 | | | | |
| Parquet/Delta/Iceberg | 1 | | | | |
| Kafka/streaming | 0 | | | | |
| Kubernetes/Terraform | 1 | | | | |
| Observability/SRE | 0 | | | | |
| Applied AI/RAG | 0 | | | | |
| AI evaluation/security | 1 | | | | |
| Architecture communication | 1 | | | | |
| Technical leadership | 0 | | | | |

## Monthly milestone checklist

- [ ] M01: Oracle and SQL Server operations baseline; RMAN recovery and OEM; SQL Server HA/DR map
- [ ] M02: RAC/ASM, Data Guard, Always On, Azure SQL, Db2 orientation, tuning and ExaCC overview
- [ ] M03: Repository template, CI and first .NET domain model
- [ ] M04: Job API tests, security, telemetry and ADR
- [ ] M05: Scala types, collections, FP and sbt
- [ ] M06: JVM fundamentals and Spark Scala API exercise
- [ ] M07: Python packaging, typing, pytest and CLI
- [ ] M08: Python ingestion SDK, benchmarks and release
- [ ] M09: DSA foundations and complexity practice
- [ ] M10: Graph scheduler, tests and explanation
- [ ] M11: OS, memory, threading and I/O experiments
- [ ] M12: Network failure lab and bounded processor; extend Spark comparison
- [ ] M13: Messaging and idempotency
- [ ] M14: Outbox/inbox, retries and workflow design
- [ ] M15: Failure-injected distributed validation platform
- [ ] M16: Spark plans, shuffles, joins and skew
- [ ] M17: Parquet, Delta, Iceberg and distributed SQL
- [ ] M18: Lakehouse metadata, quality, lineage and benchmark
- [ ] M19: Kafka topics, schemas, offsets and event time
- [ ] M20: Flink/Structured Streaming state and recovery
- [ ] M21: Kubernetes deployment and secure configuration
- [ ] M22: Terraform, SLOs, tracing, restore and cost model
- [ ] M23: LLM APIs, embeddings, retrieval and RAG
- [ ] M24: Evaluation, AI security, observability and audit
- [ ] M25: Integrated capstone and architecture RFC
- [ ] M26: Demo, peer review, Staff-readiness assessment

## Weekly study template

```markdown
# Week YYYY-WW

## Focus

## Concept studied

## Exercise completed

## Project change / commit

## Test or measurement

## Design trade-off

## What I can explain without notes

## Weakness to revisit

## Next week
```

## ADR template

```markdown
# ADR-000: Decision title

Status: Proposed / Accepted / Superseded

## Context and requirements

## Options considered

## Decision and rationale

## Consequences and trade-offs

## Risks and mitigations

## Validation and evidence

## Revisit trigger
```

## Staff-level RFC template

```markdown
# RFC: Platform capability

## Executive summary
## Problem and affected teams
## Business outcomes and success metrics
## Functional and nonfunctional requirements
## Constraints and assumptions
## Proposed architecture
## Alternatives and build-vs-buy
## Security and governance
## Reliability and recovery
## Cost and capacity model
## Migration and adoption plan
## Rollout, rollback and compatibility
## Risks, unresolved decisions and owners
## Review feedback and decision log
```

## Performance experiment template

```markdown
# Benchmark: Hypothesis

## Hypothesis
## Hardware / runtime / versions
## Dataset generation and size
## Baseline configuration
## Changed variable
## Metrics collected
## Results and plots
## Confounders and limitations
## Conclusion
## Next experiment
```

## Phase exit gate

- [ ] I can explain the concepts without reading notes.
- [ ] The project builds from a clean checkout.
- [ ] Automated tests pass.
- [ ] Failure modes are demonstrated.
- [ ] Performance and resource use are measured where relevant.
- [ ] An ADR/RFC explains the major decisions.
- [ ] Security and operational risks are documented.
- [ ] I can present a five-minute technical walkthrough.
- [ ] I have identified the next weak area.

## Capstone final review

- [ ] Coherent architecture; no unnecessary microservices
- [ ] Reproducible deployment
- [ ] Data contracts and lineage
- [ ] Recovery, idempotency and observability
- [ ] Benchmarked data-processing design
- [ ] Streaming correctness evidence
- [ ] Secure AI retrieval and tool controls
- [ ] Evaluation report and known limitations
- [ ] Cost and capacity model
- [ ] Platform adoption and migration plan
- [ ] Architecture presentation and peer feedback
- [ ] Resume-ready, accurate impact statements
