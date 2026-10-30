# Phase 1 — Complete Eight-Week Study Schedule

**Track:** Software Engineering Foundations using C#  
**Time:** 8 weeks × 8 hours = 64 hours  
**Outcome:** A production-minded Job Management API with PostgreSQL, idempotency, optimistic concurrency, security, testing, CI, observability, and architecture evidence.

**Scope:** This is Phase 1 (Months 1–2) of the 24-month Staff/Principal roadmap. Weeks 1–4 are retained from the original schedule; Weeks 5–8 complete the phase.

This is a deepening track for someone already developing C# services, not a beginner syntax course. Keep the focus on reasoning, experiments, tests, and documentation.

## Weekly cadence

| Day | Duration | Format |
|---|---:|---|
| Monday | 1 hour | Course or documentation |
| Tuesday | 1 hour | Focused coding exercises |
| Thursday | 1.5 hours | Theory and experiments |
| Saturday | 3 hours | Portfolio implementation |
| Sunday | 1.5 hours | Tests, reading, review |
| **Total** | **8 hours** | |

## Udemy course key and section selection

These are **selected sections**, not a requirement to complete five courses. Course content can change; use the section *titles* to find material if numbering shifts. Sections were checked against public Udemy curricula in October 2026.

| Code | Course | Instructor | Link |
|---|---|---|---|
| **HP** | High Performance Coding with .NET Core and C# | Gergely Kalapos | [Udemy](https://www.udemy.com/course/high-performance-coding-with-net-core-and-csharp/) |
| **MA** | Master Multithreading & Asynchronous Programming in C#/.NET | Frank Liu | [Udemy](https://www.udemy.com/course/master-multithreading-asynchronous-programming-in-csharp-dotnet/) |
| **CA** | ASP.NET Core - SOLID and Clean Architecture | Trevoir Williams | [Udemy](https://www.udemy.com/course/aspnet-core-solid-and-clean-architecture-net-5-and-up/) |
| **TD** | Test Driven Development in ASP.NET Core - The Handbook | Trevoir Williams | [Udemy](https://www.udemy.com/course/test-driven-development-in-net-core-the-handbook/) |
| **DP** | Design Patterns in C# and .NET | Dmitri Nesteruk | [Udemy](https://www.udemy.com/course/design-patterns-csharp-dotnet/) |

**Selection rules:** Approximately **1.5–2 hours of video/documentation per week**, with **6–6.5 hours spent coding, testing, profiling, and explaining decisions**. Watch the specified lectures within a section, not necessarily every lecture. Where a subject is not taught adequately by these courses, use the linked Microsoft documentation. HP is based on older .NET versions: use it for enduring performance principles, but follow current .NET guidance for tools and APIs. Course exercises are optional; implement the concepts in **your own Job Management API** instead.

## Week-by-week course map

| Week | Course sections to use | Approx. guided-study time |
|---|---|---:|
| 1 | **HP:** *Setting the Stage* (overview only); *Measure Performance During Development Part 1* (especially **Measuring Memory** and profiler lectures). **TD:** *Getting Started with Test Driven Development* (create test project and first test). | 1.5–2 h |
| 2 | **HP:** *Measure Performance During Development Part 2* (**Micro Benchmarking with BenchmarkDotNet**, selected lectures); sections addressing **collections, value/reference types, and EF Core data-access performance** (select by topic). **TD:** *Unit Testing - Application Core* (mocking and business rules). | 1.5–2 h |
| 3 | **MA:** *Introduction* (**CPU, Thread and Thread Scheduler**, **Basic syntax to start a thread**); sections on **Tasks / Task Parallel Library** and **async/await** (select task lifecycle, exception/cancellation, async fundamentals). | 1.5–2 h |
| 4 | **CA:** *Preliminary Concepts* (**Review of S.O.L.I.D Principles**, **Dependency Inversion**, **Understanding Clean Architecture**); **DP:** *The SOLID Design Principles* (especially OCP, ISP, DIP). | 1.5–2 h |
| 5 | **CA:** sections on **validation**, **custom exceptions/global error handling**, **middleware**, and **JWT/Identity**; locate by lecture title in the current course curriculum. | 1.5–2 h |
| 6 | **CA:** sections on **CQRS/MediatR**, **application services**, and **EF Core/persistence** (selectively). **DP:** sections on **Strategy**, **State**, or **Decorator**, as relevant to the job lifecycle. | 1.5–2 h |
| 7 | **HP:** *Measure Performance During Development Part 1* and *Part 2* (CPU, memory, profiling, benchmarking); production-monitoring lectures. **MA:** *Threads Synchronization* (critical sections, locking), then concurrent collections/cancellation lectures as needed. | 1.5–2 h |
| 8 | **TD:** *Using GitHub for Continuous Integration and Testing* (**Protect main/master Branch**, **Create GitHub Build Action**, **Finalizing Continuous Integration Action**); revisit **TD: Unit Testing - Application Core** for test gaps. | 1.5–2 h |

**Important:** For courses where Udemy's section titles are not reliably exposed in public previews, the map deliberately identifies **topics or lecture titles rather than inventing exact section names/numbers**. You can locate these by expanding the course's *Course content* panel.

## Detailed weekly course assignments

## Week 1 — .NET runtime and types

**Goal:** Explain the CLR, JIT, type semantics, allocation, and garbage collection.

### Week 1 — Course assignments

**Monday (1h):** HP → *Setting the Stage*: Course Overview (skim), then *Measure Performance During Development Part 1*: **Measuring Memory**. Read Microsoft documentation on value/reference types and CLR/JIT for the remaining time.

**Thursday (1.5h):** HP → *Measure Performance During Development Part 1*: **Visual Studio Performance Tools - PerfTips and Profiler** and **The Diagnostic Tools Window**. TD → *Getting Started with Test Driven Development*: **Create Test Project** (as needed). Use the remaining time to profile allocations in a small sample.

**Skip:** HP's historical .NET Core 2.0 deployment details. **Evidence:** allocation snapshots and first failing/passing domain test.

- [ ] **Monday (1h):** Study CLR, JIT compilation, value vs reference types, stack vs heap.
- [ ] **Tuesday (1h):** Write experiments with classes, structs, records, boxing, and reference assignment; explain results.
- [ ] **Thursday (1.5h):** Study GC, `IDisposable`, and allocation; inspect an application with `dotnet-counters` or another profiler.
- [ ] **Saturday (3h):** Create `dotnet-job-platform` with solution structure, Job domain model, and initial endpoints.
- [ ] **Sunday (1.5h):** Write Job state-transition tests; document runtime concepts and initial architecture decisions.

**Deliverables:** Running skeleton API, first tests, `docs/architecture.md`, short runtime notes.

**Self-check:** Can you explain why a reference type does not necessarily imply every value lives on the heap, and when disposal differs from garbage collection?

## Week 2 — Generics, LINQ, and persistence

**Goal:** Understand language abstractions and their implications for data access.

### Week 2 — Course assignments

**Monday (1h):** HP → *Measure Performance During Development Part 2*: **Micro Benchmarking with BenchmarkDotNet**. Supplement with current Microsoft docs for generics, expression trees, and LINQ.

**Thursday (1.5h):** TD → *Unit Testing - Application Core*: **Create Booking Services**, **Unit Test: Save a Room Booking**, and **Unit Test: Check if Room Is Available** (adapt patterns to job persistence). Review HP's relevant EF Core/data-access performance lectures if time remains.

**Skip:** completing the course's booking application. **Evidence:** `Result<T>` tests, database integration test, SQL query comparison.

- [ ] **Monday (1h):** Study generics, delegates, events, lambdas, and expression-tree concepts.
- [ ] **Tuesday (1h):** Implement and test a reusable `Result<T>` or small generic collection.
- [ ] **Thursday (1.5h):** Study `IEnumerable<T>` vs `IQueryable<T>`, deferred execution, and LINQ performance; run examples.
- [ ] **Saturday (3h):** Add job creation, retrieval, filtering, validation, and PostgreSQL persistence.
- [ ] **Sunday (1.5h):** Add PostgreSQL integration tests, inspect SQL, and document ORM/query trade-offs.

**Deliverables:** Working persistence, integration tests, a brief comparison of data-access approaches.

**Self-check:** Can you explain when LINQ runs in memory versus being translated to SQL, and how to detect repeated enumeration?

## Week 3 — Async, concurrency, and cancellation

**Goal:** Distinguish asynchronous I/O, concurrency, and parallel execution.

### Week 3 — Course assignments

**Monday (1h):** MA → *Introduction*: **CPU, Thread and Thread Scheduler**, **Basic syntax to start a thread**, **Why threading: Offload long running tasks**. Contrast this with async I/O using Microsoft async guidance.

**Thursday (1.5h):** MA → course sections covering **Tasks**, **async/await**, **task cancellation**, and **exceptions** (select lectures, not entire sections). If time remains, MA → *Threads Synchronization*: **Critical Section and Atomic Operation**.

**Skip:** extensive GUI/thread-affinity examples. **Evidence:** async vs thread experiment, bounded worker, cancellation test.

- [ ] **Monday (1h):** Study `Task`, `async`/`await`, cancellation, and CPU-bound vs I/O-bound work.
- [ ] **Tuesday (1h):** Compare synchronous and asynchronous file or HTTP calls; record results.
- [ ] **Thursday (1.5h):** Study thread pools, `SemaphoreSlim`, `Channel<T>`, races, and bounded concurrency.
- [ ] **Saturday (3h):** Add a background job processor with a bounded queue and cancellation support.
- [ ] **Sunday (1.5h):** Test concurrency limits, cancellation, graceful shutdown, and failure cases.

**Deliverables:** Bounded background worker, tests, short concurrency experiment report.

**Self-check:** Can you explain why `async` is not the same as running work on another thread, and why an unbounded queue is risky?

## Week 4 — Design and architecture

**Goal:** Apply modular design and make architectural decisions explicit.

### Week 4 — Course assignments

**Monday (1h):** CA → *Preliminary Concepts*: **Review of S.O.L.I.D Principles**, **Dependency Inversion**, **Understanding Clean Architecture**.

**Thursday (1.5h):** DP → *The SOLID Design Principles*: **Open-Closed Principle**, **Interface Segregation Principle**, **Dependency Inversion Principle**. Use remaining time to compare layered and vertical-slice approaches for the Job API.

**Skip:** blindly adopting MediatR or five project layers. **Evidence:** one justified architecture ADR and refactored modules.

- [ ] **Monday (1h):** Study SOLID, cohesion, coupling, composition, and dependency inversion.
- [ ] **Tuesday (1h):** Refactor a tightly coupled component into testable interfaces and implementations.
- [ ] **Thursday (1.5h):** Study layered architecture, Clean Architecture trade-offs, DI lifetimes, and API boundaries.
- [ ] **Saturday (3h):** Refactor the Job Management API into clear modules; implement and test a job lifecycle state machine.
- [ ] **Sunday (1.5h):** Run the full test suite, write one ADR, create a diagram, and complete a month-one assessment.

**Deliverables:** Modular API, state-machine tests, ADR, architecture diagram, retrospective.

**Self-check:** Can you explain why each module boundary exists, what alternatives you rejected, and which abstractions may be unnecessary?

## Resources

The Udemy links and week-specific selections are in the **Udemy course key and section selection** and **Detailed weekly course assignments** sections above.


- [C# documentation](https://learn.microsoft.com/en-us/dotnet/csharp/)
- [.NET garbage collection fundamentals](https://learn.microsoft.com/en-us/dotnet/standard/garbage-collection/fundamentals)
- [Asynchronous programming](https://learn.microsoft.com/en-us/dotnet/csharp/asynchronous-programming/)
- [.NET diagnostics](https://learn.microsoft.com/en-us/dotnet/core/diagnostics/)
- [ASP.NET Core dependency injection](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/dependency-injection)
- Selected chapters: *Effective C#* and *A Philosophy of Software Design*.

## End-of-month assessment

- [ ] Explain CLR, JIT, GC, disposal, and type semantics.
- [ ] Explain deferred LINQ execution and query translation.
- [ ] Explain async I/O, thread pools, cancellation, and bounded concurrency.
- [ ] Demonstrate running API with PostgreSQL and tests.
- [ ] Show architecture diagram and at least one ADR.
- [ ] Demonstrate a failure case and how the application handles it.
- [ ] Write a one-page retrospective: strengths, gaps, and next month's priorities.

**Note:** This first month builds transferable engineering fundamentals in C#. Python and Scala remain dedicated later tracks in the full roadmap.

## Week 5 — API contracts, validation, security, and DI

**Goal:** Make the API predictable, secure, and independently testable.

### Week 5 — Course assignments

**Monday (1h):** CA → current course sections covering **validation**, **custom exceptions**, and **global error-handling middleware**. Find matching lecture titles in the Udemy outline.

**Thursday (1.5h):** CA → sections covering **Identity/JWT security** and **API documentation**. Supplement with current ASP.NET Core authorization and problem-details documentation.

**Skip:** Blazor client/UI implementation. **Evidence:** OpenAPI contract, standardized errors, authorization tests.

- [ ] **Monday (1h):** Study HTTP semantics (201/202/400/401/403/404/409), Problem Details, versioning, and dependency injection lifetimes.
- [ ] **Tuesday (1h):** Create a small lab demonstrating singleton/scoped/transient behavior and an unsafe captive dependency; fix it.
- [ ] **Thursday (1.5h):** Study authentication versus authorization, input validation, secrets management, and least privilege; draft a lightweight threat model.
- [ ] **Saturday (3h):** Implement request DTOs, centralized validation/error responses, OpenAPI, authentication for protected operations, and authorization policies. Add API pagination if not complete.
- [ ] **Sunday (1.5h):** Write integration tests for invalid inputs, 401/403, duplicate resource requests, and contract behavior; document trust boundaries.

**Deliverables:** Versioned API contract, validation tests, authorization policy, `docs/security.md`, and an updated OpenAPI specification.

**Self-check:** Can you explain why authentication is not authorization, when a scoped dependency must not be captured by a singleton, and which failures should produce 409 versus 500?

## Week 6 — Transactions, idempotency, optimistic concurrency, and retries

**Goal:** Prevent duplicate business outcomes and lost updates when clients retry or workers race.

### Week 6 — Course assignments

**Monday (1h):** CA → sections covering **CQRS/MediatR**, **application-layer boundaries**, and **EF Core**. Focus on architectural trade-offs rather than copying the course stack.

**Thursday (1.5h):** DP → **State** and **Strategy** pattern sections (choose relevant introductions and examples); optional **Decorator** if adding cross-cutting behavior. Read PostgreSQL transaction/isolation and EF Core concurrency documentation.

**Skip:** implementing patterns without a demonstrated need. **Evidence:** concurrency-safe job state changes, idempotency-key test, design trade-off note.

- [ ] **Monday (1h):** Study database transaction boundaries, isolation levels, optimistic concurrency, and idempotency keys.
- [ ] **Tuesday (1h):** Build a small concurrency experiment: two clients update the same job; observe lost updates and implement a version check.
- [ ] **Thursday (1.5h):** Study transient versus permanent errors, exponential backoff with jitter, timeouts, and why retries must respect idempotency.
- [ ] **Saturday (3h):** Implement durable idempotency records for `POST /jobs`, a unique constraint for the key within its intended scope, job version checks, safe state transitions, and a bounded retry policy. Keep state and idempotency writes transactional.
- [ ] **Sunday (1.5h):** Test repeated submissions, conflicting payloads for one key, concurrent updates, transaction rollback, and worker restart behavior.

**Deliverables:** Idempotent job creation, concurrency-safe updates, transaction tests, and `docs/decisions/ADR-00X-idempotency.md`.

**Self-check:** Can you explain why a retry can be safe for a read but unsafe for a write, and how a database constraint protects against a race that an application-level check cannot?

## Week 7 — Observability, profiling, and resilience

**Goal:** Make failures diagnosable and demonstrate evidence-based performance improvement.

### Week 7 — Course assignments

**Monday (1h):** HP → *Measure Performance During Development Part 1*: **Measuring CPU** and **Measuring Memory**; *Part 2*: **Micro Benchmarking with BenchmarkDotNet** (review).

**Thursday (1.5h):** MA → *Threads Synchronization*: **Threads Synchronization Overview**, **Critical Section and Atomic Operation**, **Exclusive Lock**; select later lectures on concurrent collections/cancellation. HP → production-monitoring material if time permits. Use current OpenTelemetry docs for modern instrumentation.

**Skip:** treating an old profiler walkthrough as current tooling guidance. **Evidence:** before/after performance measurements, trace/metric samples, failure test.

- [ ] **Monday (1h):** Study structured logging, log levels, correlation IDs, OpenTelemetry traces, metrics, and useful service-level indicators.
- [ ] **Tuesday (1h):** Use `dotnet-counters` or a profiler to inspect allocation, GC, CPU, and thread-pool behavior under a small workload.
- [ ] **Thursday (1.5h):** Study health checks, readiness versus liveness, timeout budgets, retry storms, and graceful shutdown; identify anti-patterns in the project.
- [ ] **Saturday (3h):** Add structured logs, request/job correlation, tracing, counters/histograms, health endpoints, timeout configuration, and a simple load-test script. Instrument the job lifecycle end to end.
- [ ] **Sunday (1.5h):** Run baseline and failure-injection tests (database delay, worker interruption, duplicate requests). Record latency, throughput, memory, errors, and recovery results.

**Deliverables:** Telemetry dashboard or captured traces, `docs/operations.md`, benchmark results, and a failure-mode table.

**Self-check:** Given one failed job, can you trace the request, identify its last successful transition, and distinguish a dependency timeout from an application defect?

## Week 8 — CI/CD, architecture review, hardening, and phase gate

**Goal:** Deliver a reproducible, reviewable portfolio project and verify understanding without relying on AI.

### Week 8 — Course assignments

**Monday (1h):** TD → *Using GitHub for Continuous Integration and Testing*: **Protect main/master Branch**, **Create GitHub Build Action**.

**Thursday (1.5h):** TD → same section: **Finalizing Continuous Integration Action**; revisit *Unit Testing - Application Core* for tests around state transitions and failures. Review GitHub Actions and .NET testing docs for current syntax.

**Skip:** beginner GitHub account setup. **Evidence:** passing PR workflow, documented architectural review, final demonstration.

- [ ] **Monday (1h):** Study test strategy (unit/integration/contract), code review, supply-chain security, and deployment/rollback basics.
- [ ] **Tuesday (1h):** Review the API without AI: identify three design weaknesses, one reliability risk, and one test gap; create issues and fix the highest-impact item.
- [ ] **Thursday (1.5h):** Add or refine GitHub Actions build, format/analyzer checks, unit tests, PostgreSQL integration tests, dependency scanning, and Docker build; verify a clean checkout works.
- [ ] **Saturday (3h):** Finalize README, architecture and sequence diagrams, ADRs, API examples, Docker Compose setup, security/operations notes, and a 5–10 minute demo. Perform a deliberate worker-crash and recovery demonstration.
- [ ] **Sunday (1.5h):** Complete the Phase 1 assessment below, write a retrospective, update the skill matrix, and decide which concepts need review before Phase 2 Python.

**Deliverables:** Versioned release, green CI, runnable Docker setup, architecture pack, failure demo, and Phase 1 retrospective.

**Self-check:** Can you defend your design choices and explain the runtime, transaction, concurrency, and reliability behavior without consulting AI-generated notes?

---

## Phase 1 final acceptance criteria

- [ ] `POST /jobs` accepts an idempotency key and avoids duplicate jobs on retries.
- [ ] `GET /jobs/{id}` and job history endpoints return consistent status information.
- [ ] Cancellation and retry operations obey an explicit state machine.
- [ ] PostgreSQL transactions and optimistic concurrency prevent lost updates.
- [ ] Worker concurrency is bounded; cancellation and graceful shutdown are tested.
- [ ] Authentication and authorization are applied where appropriate.
- [ ] Unit and PostgreSQL integration tests cover success and failure paths.
- [ ] CI runs build, formatting/analyzers, tests, and container build.
- [ ] Logs, metrics, and traces identify a failed job end to end.
- [ ] README, diagrams, ADRs, threat model, and runbook are understandable to a new contributor.
- [ ] You can reproduce a failure and demonstrate recovery.

### Staff-level practice (1 hour each week is included in the schedule)

At the end of each week, capture one engineering decision: **context → alternatives → decision → trade-offs → validation evidence**. At the phase review, present a short design proposal as though another team would depend on your API. Include an adoption path, compatibility risks, operational ownership, and the top three unresolved risks.

### Definition of done

Do not chase feature count. A small, robust API with demonstrated tests, clear boundaries, recovery behavior, and architectural reasoning is stronger evidence than an overbuilt service. Move to Phase 2 (Python) once the essential gates are met; carry optional enhancements into a backlog.
