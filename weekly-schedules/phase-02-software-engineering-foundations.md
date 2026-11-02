# Phase 2 — Complete Eight-Week Study Schedule

**Track:** Software Engineering Foundations using C#  
**Time:** 8 weeks × 8 hours = 64 hours  
**Outcome:** A production-minded Job Management API with PostgreSQL, idempotency, optimistic concurrency, security, testing, CI, observability, and architecture evidence.

**Scope:** This is Phase 2 (Months 3–4) of the 26-month Staff/Principal roadmap. Weeks 1–4 are retained from the original schedule; Weeks 5–8 complete the phase.

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

Use **two primary courses**, then fill the project-specific gaps with Microsoft documentation and experiments. Course content can change; use section titles rather than fixed lecture numbers. Sections were checked against public Udemy curricula in October 2026.

| Code | Course | Instructor | Link |
|---|---|---|---|
| **CS** | Ultimate C# Masterclass for 2027 | Elegant Code | [Udemy](https://www.udemy.com/course/ultimate-csharp-masterclass/) |
| **API** | Building ASP.NET Core REST APIs with an AI-Powered Workflow | Elegant Code | [Udemy](https://www.udemy.com/course/building-aspnet-core-rest-apis-with-an-ai-powered-workflow/) |
| **MT** *(optional)* | Master Multithreading & Asynchronous Programming in C#/.NET | Frank Liu | [Udemy](https://www.udemy.com/course/master-multithreading-asynchronous-programming-in-csharp-dotnet/) |
| **HP** *(optional)* | High Performance Coding with .NET Core and C# | Gergely Kalapos | [Udemy](https://www.udemy.com/course/high-performance-coding-with-net-core-and-csharp/) |
| **TD** *(optional)* | Test Driven Development in ASP.NET Core - The Handbook | Trevoir Williams | [Udemy](https://www.udemy.com/course/test-driven-development-in-net-core-the-handbook/) |
| **CA** *(optional)* | ASP.NET Core - SOLID and Clean Architecture | Trevoir Williams | [Udemy](https://www.udemy.com/course/aspnet-core-solid-and-clean-architecture-net-5-and-up/) |
| **DP** *(optional)* | Design Patterns in C# and .NET | Dmitri Nesteruk | [Udemy](https://www.udemy.com/course/design-patterns-csharp-dotnet/) |

**Selection rules:** Approximately **1.5–2 hours of video/documentation per week**, with **6–6.5 hours spent coding, testing, profiling, and explaining decisions**. Watch only the relevant sections. The API course directly covers PostgreSQL, EF Core, authentication, authorization, unit testing, and integration testing. Its AI-assisted workflow is optional; do not use generated code as a substitute for understanding. Course exercises are optional; implement the concepts in **your own Job Management API** instead.

The two primary courses do not fully teach idempotency, optimistic concurrency, worker recovery, Testcontainers, OpenTelemetry, Docker, or CI. Learn those through the Microsoft documentation links below and the experiments in this schedule. **MT, HP, TD, CA, and DP are optional specialist material**, not additional required courses. Choose at most one optional supplement for a study session, and use it only when a specific concept needs more explanation; project implementation and failure tests take priority over watching more videos.

## Week-by-week course map

| Week | Course sections to use | Approx. guided-study time |
|---|---|---:|
| 1 | **CS:** fundamentals, OOP, exceptions, collections. **API:** project setup, first endpoint, and manual API testing. **HP (optional):** memory measurement. **TD (optional):** TDD foundations. | 1.5–2 h |
| 2 | **CS:** generics and LINQ. **API:** persistence and data-access testing. **HP (optional):** benchmarking or EF Core performance. **TD (optional):** application-core unit testing. | 1.5–2 h |
| 3 | **CS:** async/await and cancellation. **MT (optional):** task-based asynchronous programming and async/await. **API:** REST design, endpoints, and persistence. | 1.5–2 h |
| 4 | **CS:** async and multithreading review. **API:** service boundaries and testing. **CA (optional):** SOLID and application core. **DP (optional):** SOLID principles. | 1.5–2 h |
| 5 | **API:** validation, errors, middleware, Identity, JWT, and authorization. **CA (optional):** API structure and security. | 1.5–2 h |
| 6 | **API:** EF Core, persistence, unit testing, and integration testing. **CA (optional):** infrastructure and testing. **DP (optional):** State and Strategy. | 1.5–2 h |
| 7 | **CS:** performance and concurrency. **MT (optional):** synchronization and concurrent collections. **HP (optional):** profiling and production monitoring. | 1.5–2 h |
| 8 | **API:** testing review. **TD (optional):** integration testing and GitHub Actions CI. Supplement with current GitHub Actions, Docker, and .NET CI documentation. | 1.5–2 h |

The detailed weekly assignments below contain the specific Udemy section and subsection names. Use section titles rather than fixed lecture numbers because course content can change.

## Detailed weekly course assignments

## Week 1 — .NET runtime and types

**Goal:** Explain the CLR, JIT, type semantics, allocation, and garbage collection.

### Week 1 — Course assignments

**Monday (1h):** CS → `C# Fundamentals`, `Basics of Object-Oriented Programming`, and `Object-Oriented Programming: Polymorphism, Inheritance, Interfaces` → types, records, value/reference semantics, and OOP subsections. Read Microsoft documentation on the CLR/JIT for the remaining time.

**Thursday (1.5h):** CS → `Exceptions and error handling` and `Collections` → exception, interface, and collection subsections. API → `Project setup and overview`, `Defining the first endpoint`, and `Testing the API manually` → scaffold the API and verify a simple endpoint. Optionally use TD → `Getting Started with Test Driven Development` → Red-Green-Refactor, to create the test project. Defer profiling until the API is running if needed.

**Skip:** advanced C# sections that are unrelated to the API. **Evidence:** allocation snapshots and first failing/passing domain test.

- [ ] **Monday (1h):** Study CLR, JIT compilation, value vs reference types, stack vs heap.
- [ ] **Tuesday (1h):** Write experiments with classes, structs, records, boxing, and reference assignment; explain results.
- [ ] **Thursday (1.5h):** Study GC, `IDisposable`, and allocation; inspect an application with `dotnet-counters` or another profiler.
- [ ] **Saturday (3h):** Create `dotnet-job-platform` with solution structure and Job domain model; scaffold the ASP.NET Core API, add one simple endpoint, run it, and verify the response manually.
- [ ] **Sunday (1.5h):** Write the first Job model test; document runtime concepts and initial architecture decisions.

**Deliverables:** Running skeleton API with a manually verified endpoint, Job model and first test, `docs/architecture.md`, short runtime notes.

**Self-check:** Can you start the API and verify its endpoint, explain why a reference type does not necessarily imply every value lives on the heap, and describe when disposal differs from garbage collection?

## Week 2 — Generics, LINQ, and persistence

**Goal:** Understand language abstractions and their implications for data access.

### Week 2 — Course assignments

**Monday (1h):** CS → `Generic types & advanced use of methods` and `LINQ` → generics, delegates, lambdas, and LINQ subsections. Supplement with current Microsoft documentation for expression trees and query translation.

**Thursday (1.5h):** API → persistence, EF Core, and data-access testing sections in the expanded outline. Optionally use HP → `Measure Performance During Development Part 2` → BenchmarkDotNet or `Data Access Performance: Entity Framework Core`, and TD → `Unit Testing - Application Core`. Read the ASP.NET Core integration-testing and Testcontainers documentation; adapt the examples to PostgreSQL job persistence and review EF Core query behavior.

**Skip:** completing the course's booking application. **Evidence:** `Result<T>` tests, database integration test, SQL query comparison.

- [ ] **Monday (1h):** Study generics, delegates, events, lambdas, and expression-tree concepts.
- [ ] **Tuesday (1h):** Implement and test a reusable `Result<T>` or small generic collection.
- [ ] **Thursday (1.5h):** Study `IEnumerable<T>` vs `IQueryable<T>`, deferred execution, and LINQ performance; run examples.
- [ ] **Saturday (3h):** Add job creation, retrieval, filtering, validation, and PostgreSQL persistence.
- [ ] **Sunday (1.5h):** Add PostgreSQL integration tests using the documented test approach, inspect generated SQL, and document ORM/query trade-offs.

**Deliverables:** Working persistence, integration tests, a brief comparison of data-access approaches.

**Self-check:** Can you explain when LINQ runs in memory versus being translated to SQL, and how to detect repeated enumeration?

## Week 3 — Async, concurrency, and cancellation

**Goal:** Distinguish asynchronous I/O, concurrency, and parallel execution.

### Week 3 — Course assignments

**Monday (1h):** CS → `.NET under the hood` → async/await and task fundamentals. If the distinction is unclear, use MT → `Task based Asynchronous Programming` and `Async & Await` → task execution and async/await basics. Contrast asynchronous I/O with threads using Microsoft async guidance.

**Thursday (1.5h):** CS → `.NET under the hood` → cancellation, task exceptions, and multithreading subsections. Optionally use MT → `Threads Synchronization` → critical sections and thread safety. Supplement with Microsoft guidance on `SemaphoreSlim`, `Channel<T>`, and hosted services.

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

**Monday (1h):** CS → `Object-Oriented Programming: Polymorphism, Inheritance, Interfaces` → interfaces and dependency inversion subsections. Optionally use CA → `Preliminary Concepts` → SOLID and dependency inversion, or DP → `The SOLID Design Principles`. Supplement with Microsoft dependency-injection documentation.

**Thursday (1.5h):** API → review the project-structure and testing sections in the expanded outline, focusing on service boundaries and test placement. Optionally use CA → `Setting up the Application Core` and `Setting up Infrastructure Projects` → application/infrastructure boundaries. Use the remaining time to compare layered and vertical-slice approaches for the Job API.

**Skip:** blindly adopting MediatR or five project layers. **Evidence:** one justified architecture ADR and refactored modules.

- [ ] **Monday (1h):** Study SOLID, cohesion, coupling, composition, and dependency inversion.
- [ ] **Tuesday (1h):** Refactor a tightly coupled component into testable interfaces and implementations.
- [ ] **Thursday (1.5h):** Study layered architecture, Clean Architecture trade-offs, DI lifetimes, and API boundaries.
- [ ] **Saturday (3h):** Refactor the Job Management API into clear modules and add focused tests for the module boundaries.
- [ ] **Sunday (1.5h):** Run the full test suite, write one ADR, create a diagram, and complete a month-one assessment.

**Deliverables:** Modular API, module tests, ADR, architecture diagram, retrospective.

**Self-check:** Can you explain why each module boundary exists, what alternatives you rejected, and which abstractions may be unnecessary?

## Resources

The Udemy links and week-specific selections are in the **Udemy course key and section selection** and **Detailed weekly course assignments** sections above.


- [C# documentation](https://learn.microsoft.com/en-us/dotnet/csharp/)
- [.NET garbage collection fundamentals](https://learn.microsoft.com/en-us/dotnet/standard/garbage-collection/fundamentals)
- [Asynchronous programming](https://learn.microsoft.com/en-us/dotnet/csharp/asynchronous-programming/)
- [Worker services in .NET](https://learn.microsoft.com/en-us/dotnet/core/extensions/workers)
- [ASP.NET Core hosted services](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/host/hosted-services)
- [.NET diagnostics](https://learn.microsoft.com/en-us/dotnet/core/diagnostics/)
- [ASP.NET Core dependency injection](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/dependency-injection)
- [EF Core concurrency handling](https://learn.microsoft.com/en-us/ef/core/saving/concurrency)
- [EF Core transactions](https://learn.microsoft.com/en-us/ef/core/saving/transactions)
- [ASP.NET Core integration tests](https://learn.microsoft.com/en-us/aspnet/core/test/integration-tests)
- [ASP.NET Core health checks](https://learn.microsoft.com/en-us/aspnet/core/host-and-deploy/health-checks)
- [OpenTelemetry for .NET](https://opentelemetry.io/docs/languages/net/)
- [Testcontainers for .NET](https://dotnet.testcontainers.org/)
- [Containerize a .NET application](https://learn.microsoft.com/en-us/dotnet/core/docker/introduction)
- [Build and test .NET with GitHub Actions](https://docs.github.com/en/actions/automating-builds-and-tests/building-and-testing-net)
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

**Monday (1h):** API → validation, error handling, middleware, and Problem Details sections in the expanded outline. If more detail is needed, use CA → `Creating the API project` → custom exceptions, global error handling, and middleware subsections. Match the current lecture titles rather than relying on lecture numbers.

**Thursday (1.5h):** API → Identity, JWT, authorization, and API documentation sections in the expanded outline. Optionally use CA → `Securing API and UI` → JWT and Identity subsections. Supplement with current ASP.NET Core authorization and Problem Details documentation.

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

**Monday (1h):** API → EF Core, persistence, and application-layer sections in the expanded outline. Optionally use CA → `Setting up the Application Core` and `Setting up Infrastructure Projects` → application core, infrastructure, and EF Core subsections. Focus on architectural trade-offs rather than copying either course's stack.

**Thursday (1.5h):** CS → design-pattern material only when it clarifies the job lifecycle. Optionally use DP → behavioral-pattern sections → `State` and `Strategy`; do not study the full Gang of Four catalogue. Read PostgreSQL transaction/isolation and EF Core concurrency documentation.

**Skip:** implementing patterns without a demonstrated need. **Evidence:** concurrency-safe job state changes, idempotency-key test, design trade-off note.

- [ ] **Monday (1h):** Study database transaction boundaries, isolation levels, optimistic concurrency, and idempotency keys.
- [ ] **Tuesday (1h):** Build a small concurrency experiment: two clients update the same job; observe lost updates and implement a version check.
- [ ] **Thursday (1.5h):** Study transient versus permanent errors, exponential backoff with jitter, timeouts, and why retries must respect idempotency.
- [ ] **Saturday (3h):** Implement durable idempotency records for `POST /jobs`, a unique constraint for the key within its intended scope, job version checks, safe state transitions, and a bounded retry policy. Keep state and idempotency writes transactional.
- [ ] **Sunday (1.5h):** Test repeated submissions, conflicting payloads for one key, concurrent updates, transaction rollback, and worker restart behavior.

**Deliverables:** Idempotent job creation, tested job state transitions, concurrency-safe updates, transaction tests, and `docs/decisions/ADR-00X-idempotency.md`.

**Self-check:** Can you explain why a retry can be safe for a read but unsafe for a write, and how a database constraint protects against a race that an application-level check cannot?

## Week 7 — Observability, profiling, and resilience

**Goal:** Make failures diagnosable and demonstrate evidence-based performance improvement.

### Week 7 — Course assignments

**Monday (1h):** CS → `.NET under the hood`, `Advanced C# types`, and `Collections` → CPU, memory, and allocation subsections. Optionally use HP → `Measure Performance During Development Part 1`, `Measure Performance During Development Part 2`, and `Performance Monitoring in Production for .NET Core`. Supplement with current .NET diagnostics and BenchmarkDotNet documentation because HP uses older .NET-era tooling.

**Thursday (1.5h):** CS → `.NET under the hood` and `Advanced C# types` → concurrency and synchronization subsections. If the race or locking experiment needs more depth, use MT → `Threads Synchronization` and `Concurrent Collections` → thread safety and collection-selection subsections. Use current OpenTelemetry, health-check, and Testcontainers documentation for modern tooling.

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

**Monday (1h):** API → unit and integration-testing sections in the expanded outline. Optionally use TD → `Integration Testing - Testing the Data Access Layer` and `Using GitHub for Continuous Integration and Testing` → data-access integration tests and CI subsections. Read current GitHub Actions documentation and create the initial build workflow.

**Thursday (1.5h):** API → revisit the unit and integration-testing sections for state transitions and failures. Use TD → `Unit Testing - Application Core` or `Integration Testing - Testing the Data Access Layer` only for unresolved testing gaps, then review current GitHub Actions and .NET testing documentation.

**Skip:** beginner GitHub account setup. **Evidence:** passing PR workflow, documented architectural review, final demonstration.

- [ ] **Monday (1h):** Study test strategy (unit/integration/contract), code review, supply-chain security, and deployment/rollback basics.
- [ ] **Tuesday (1h):** Review the API without AI: identify three design weaknesses, one reliability risk, and one test gap; create issues and fix the highest-impact item.
- [ ] **Thursday (1.5h):** Add or refine GitHub Actions build, format/analyzer checks, unit tests, PostgreSQL integration tests, dependency scanning, and Docker build; verify a clean checkout works.
- [ ] **Saturday (3h):** Finalize README, architecture and sequence diagrams, ADRs, API examples, Docker Compose setup, security/operations notes, and a 5–10 minute demo. Perform a deliberate worker-crash and recovery demonstration.
- [ ] **Sunday (1.5h):** Complete the Phase 2 assessment below, write a retrospective, update the skill matrix, and decide which concepts need review before Phase 3 Scala/JVM.

**Deliverables:** Versioned release, green CI, runnable Docker setup, architecture pack, failure demo, and Phase 2 retrospective.

**Self-check:** Can you defend your design choices and explain the runtime, transaction, concurrency, and reliability behavior without consulting AI-generated notes?

---

## Phase 2 final acceptance criteria

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

Do not chase feature count. A small, robust API with demonstrated tests, clear boundaries, recovery behavior, and architectural reasoning is stronger evidence than an overbuilt service. Move to Phase 3 (Scala/JVM) once the essential gates are met; carry optional enhancements into a backlog.
