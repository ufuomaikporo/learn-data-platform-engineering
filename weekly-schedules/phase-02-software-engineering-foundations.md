# Phase 2 — Complete Eight-Week Study Schedule

**Track:** Software Engineering Foundations using C#  
**Time:** 8 weeks × 8 hours = 64 hours  
**Outcome:** A production-minded Job Management API with PostgreSQL, idempotency, optimistic concurrency, security, testing, CI, observability, and architecture evidence.

**Scope:** This is Phase 2 (Months 3–4) of the 26-month Staff/Principal roadmap. Weeks 1–4 are retained from the original schedule; Weeks 5–8 complete the phase.

This is a deepening track for someone already developing C# services, not a beginner syntax course. Keep the focus on reasoning, experiments, tests, and documentation. Daily checklist entries put the day and duration on their own line, then use italicized *Study* and *Project* labels to distinguish course work from building the Job Management API. Project time is allocated within each day's stated duration, not added on top of the 8-hour weekly budget. Each item links to its assigned lesson or documentation; project tasks also link to the corresponding workbook section.

Step-by-step procedures for Phase 2 experiments, implementation tasks, tests, and release work are in the [Phase 2 Lab and Guided Practice Workbook](../labs/phase-02-software-engineering-foundations.md). Project blocks below name the API work and its time allocation; use the linked workbook section for detailed steps.

## Weekly cadence

| Day | Duration | Format |
|---|---:|---|
| Monday | 1 hour | Course or documentation |
| Tuesday | 1 hour | Project experiments and application |
| Thursday | 1.5 hours | Course study and project experiments |
| Saturday | 3 hours | Portfolio implementation |
| Sunday | 1.5 hours | Project tests, documentation, and review |
| **Total** | **8 hours** | |

## Udemy course key and section selection

Use **two primary courses**, then fill the project-specific gaps with Microsoft documentation and experiments. Course content can change; use section titles rather than fixed lecture numbers. Section titles below were checked against the Udemy course pages on November 5, 2026.

| Code | Course | Instructor | Link |
|---|---|---|---|
| **CS** | Ultimate C# Masterclass for 2027 | Elegant Code | [Udemy](https://www.udemy.com/course/ultimate-csharp-masterclass/) |
| **API** | Building ASP.NET Core REST APIs with an AI-Powered Workflow | Elegant Code | [Udemy](https://www.udemy.com/course/building-aspnet-core-rest-apis-with-an-ai-powered-workflow/) |
| **MT** *(optional)* | Master Multithreading & Asynchronous Programming in C#/.NET | Frank Liu | [Udemy](https://www.udemy.com/course/master-multithreading-asynchronous-programming-in-csharp-dotnet/) |
| **HP** *(optional)* | High Performance Coding with .NET Core and C# | Gergely Kalapos | [Udemy](https://www.udemy.com/course/high-performance-coding-with-net-core-and-csharp/) |
| **TD** *(optional)* | Test Driven Development in ASP.NET Core - The Handbook | Trevoir Williams | [Udemy](https://www.udemy.com/course/test-driven-development-in-net-core-the-handbook/) |
| **CA** *(optional)* | ASP.NET Core - SOLID and Clean Architecture | Trevoir Williams | [Udemy](https://www.udemy.com/course/aspnet-core-solid-and-clean-architecture-net-5-and-up/) |
| **DP** *(optional)* | Design Patterns in C# and .NET | Dmitri Nesteruk | [Udemy](https://www.udemy.com/course/design-patterns-csharp-dotnet/) |

**Selection rules:** Approximately **1.5–2 hours of video/documentation per week**, with **6–6.5 hours spent coding, testing, profiling, and explaining decisions**. The project blocks below allocate 6.25 hours in Weeks 1–2 and 6.5 hours in Weeks 3–8; all project and study time is within the 8-hour weekly cadence. Watch only the relevant sections. The API course directly covers PostgreSQL, EF Core, authentication, authorization, unit testing, and integration testing. Its AI-assisted workflow is optional; do not use generated code as a substitute for understanding. Course exercises are optional; implement the concepts in **your own Job Management API** instead.

The two primary courses do not fully teach idempotency, optimistic concurrency, worker recovery, Testcontainers, OpenTelemetry, Docker, or CI. Learn those through the Microsoft documentation links below and the experiments in this schedule. **MT, HP, TD, CA, and DP are optional specialist material**, not additional required courses. Choose at most one optional supplement for a study session, and use it only when a specific concept needs more explanation; project implementation and failure tests take priority over watching more videos.

## Week-by-week course map

| Week | Course sections to use | Approx. guided-study time |
|---|---|---:|
| 1 | **CS:** `C# Fundamentals`, `Basics of Object-Oriented Programming`, `Object-Oriented Programming: Polymorphism, Inheritance, Interfaces`, `Exceptions and error handling`, `Collections`, `.NET under the hood`. **API:** `Project setup and overview`, `Defining the first endpoint`, `Testing the API manually`. **TD (optional):** `Getting Started with Test Driven Development`. | 1.5–2 h |
| 2 | **CS:** `Generic types & advanced use of methods`, `LINQ`. **API:** `Database and Entity Framework Core`, `Entity Relationships in EF Core`, `Automated testing`. **HP (optional):** `Measure Performance During Development Part 2`, `Data Access Performance: Entity Framework Core`. **TD (optional):** `Unit Testing - Application Core`. | 1.5–2 h |
| 3 | **CS:** `Multithreading & asynchrony`. **MT (optional):** `Task based Asynchronous Programming`, `Async & Await`, `Threads Synchronization`, `Concurrent Collections`. **API:** `REST APIs`, `CRUD with Minimal APIs`, `Database and Entity Framework Core`. | 1.5–2 h |
| 4 | **CS:** `Object-Oriented Programming: Polymorphism, Inheritance, Interfaces`. **API:** `Service Layer`, `Project organization and refactoring`, `Automated testing`. **CA (optional):** `Preliminary Concepts`, `Setting up the Application Core`, `Setting up Infrastructure Projects`. **DP (optional):** `The SOLID Design Principles`. | 1.5–2 h |
| 5 | **API:** `Validation`, `ASP.NET Core request pipeline`, `Endpoint filters and action filters`, `User management with ASP.NET Core Identity`, `JWT authentication and authorization`. **CA (optional):** `Creating the API project`, `Securing API and UI`. | 1.5–2 h |
| 6 | **API:** `Database and Entity Framework Core`, `Entity Relationships in EF Core`, `Service Layer`. **CA (optional):** `Setting up the Application Core`, `Setting up Infrastructure Projects`. **DP (optional):** `State`, `Strategy`. | 1.5–2 h |
| 7 | **CS:** `.NET under the hood`, `Advanced C# types`, `Collections`, `Multithreading & asynchrony`. **MT (optional):** `Threads Synchronization`, `Concurrent Collections`. **HP (optional):** `Measure Performance During Development Part 1`, `Measure Performance During Development Part 2`, `Performance Monitoring in Production for .NET Core`. | 1.5–2 h |
| 8 | **API:** `Automated testing`. **TD (optional):** `Unit Testing - Application Core`, `Integration Testing - Testing the Data Access Layer`, `Using GitHub for Continuous Integration and Testing`. Supplement with current GitHub Actions, Docker, and .NET CI documentation. | 1.5–2 h |

The daily assignments below name the specific Udemy section and subsection titles. Use section titles rather than fixed lecture numbers because course content can change.

## Weekly schedule

## Week 1 — .NET runtime and types

**Goal:** Explain the CLR, JIT, type semantics, allocation, and garbage collection.

- [ ] **Monday (1h):**

  ***Study:*** [CS — Ultimate C# Masterclass](https://www.udemy.com/course/ultimate-csharp-masterclass/) → `C# Fundamentals`, `Basics of Object-Oriented Programming`, `Object-Oriented Programming: Polymorphism, Inheritance, Interfaces`, and `.NET under the hood` for types, OOP, CLR, and JIT; Microsoft's [CLR overview](https://learn.microsoft.com/en-us/dotnet/standard/clr).
- [ ] **Tuesday (1h):**

  ***Study (0.25h):*** [CS — Ultimate C# Masterclass](https://www.udemy.com/course/ultimate-csharp-masterclass/) → `C# Fundamentals` for types; review Microsoft's [C# types and records](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/types/).

  ***Project (0.75h of today's 1h):*** Run the value/reference, record, boxing, and allocation experiment; use the results to refine the Job model and capture a short runtime note in the [Week 1 workbook section](../labs/phase-02-software-engineering-foundations.md#week-1-runtime-domain-model-and-api-skeleton).

- [ ] **Thursday (1.5h):**

  ***Study (0.5h):*** [CS — Ultimate C# Masterclass](https://www.udemy.com/course/ultimate-csharp-masterclass/) → `.NET under the hood`, `Exceptions and error handling`, and `Collections`; [API — Building ASP.NET Core REST APIs with an AI-Powered Workflow](https://www.udemy.com/course/building-aspnet-core-rest-apis-with-an-ai-powered-workflow/) → `Project setup and overview`, `Defining the first endpoint`, and `Testing the API manually`. Optionally use [TD — Test Driven Development in ASP.NET Core](https://www.udemy.com/course/test-driven-development-in-net-core-the-handbook/) → `Getting Started with Test Driven Development`. Read [.NET garbage collection fundamentals](https://learn.microsoft.com/en-us/dotnet/standard/garbage-collection/fundamentals) for GC and `IDisposable`.

  ***Project (1h of today's 1.5h):*** Inspect allocation and disposal in a local sample, then record how the API will manage disposable resources in the [Week 1 workbook section](../labs/phase-02-software-engineering-foundations.md#week-1-runtime-domain-model-and-api-skeleton).

- [ ] **Saturday (3h):**

  ***Project (3h):*** Create the `dotnet-job-platform` solution, Job domain model, and running ASP.NET Core API skeleton using [API — Building ASP.NET Core REST APIs with an AI-Powered Workflow](https://www.udemy.com/course/building-aspnet-core-rest-apis-with-an-ai-powered-workflow/) → `Project setup and overview` and `Defining the first endpoint`, plus the [Week 1 workbook section](../labs/phase-02-software-engineering-foundations.md#week-1-runtime-domain-model-and-api-skeleton).
- [ ] **Sunday (1.5h):**

  ***Project (1.5h):*** Add the first Job model test, verify the endpoint, and document runtime concepts and initial architecture decisions using [TD — Test Driven Development in ASP.NET Core](https://www.udemy.com/course/test-driven-development-in-net-core-the-handbook/) → `Getting Started with Test Driven Development` and the [Week 1 workbook section](../labs/phase-02-software-engineering-foundations.md#week-1-runtime-domain-model-and-api-skeleton).

**Deliverables:** Running skeleton API with a manually verified endpoint, Job model and first test, `docs/architecture.md`, short runtime notes.

**Self-check:** Can you start the API and verify its endpoint, explain why a reference type does not necessarily imply every value lives on the heap, and describe when disposal differs from garbage collection?

## Week 2 — Generics, LINQ, and persistence

**Goal:** Understand language abstractions and their implications for data access.

- [ ] **Monday (1h):**

  ***Study:*** [CS — Ultimate C# Masterclass](https://www.udemy.com/course/ultimate-csharp-masterclass/) → `Generic types & advanced use of methods` and `LINQ` for generics, delegates, events, lambdas, and expression trees.
- [ ] **Tuesday (1h):**

  ***Study (0.25h):*** [CS — Ultimate C# Masterclass](https://www.udemy.com/course/ultimate-csharp-masterclass/) → `Generic types & advanced use of methods` for generics.

  ***Project (0.75h of today's 1h):*** Implement and test a small `Result<T>` or generic collection experiment; document whether it solves a real Job API need or should remain an isolated exercise in the [Week 2 workbook section](../labs/phase-02-software-engineering-foundations.md#week-2-generics-linq-and-postgresql-persistence).

- [ ] **Thursday (1.5h):**

  ***Study (0.5h):*** [API — Building ASP.NET Core REST APIs with an AI-Powered Workflow](https://www.udemy.com/course/building-aspnet-core-rest-apis-with-an-ai-powered-workflow/) → `Database and Entity Framework Core`, `Entity Relationships in EF Core`, and `Automated testing`; optionally use [HP — High Performance Coding with .NET Core and C#](https://www.udemy.com/course/high-performance-coding-with-net-core-and-csharp/) → `Measure Performance During Development Part 2` and `Data Access Performance: Entity Framework Core`, or [TD — Test Driven Development in ASP.NET Core](https://www.udemy.com/course/test-driven-development-in-net-core-the-handbook/) → `Unit Testing - Application Core`. Review `IEnumerable<T>` vs `IQueryable<T>` and deferred execution in Microsoft's [EF Core querying documentation](https://learn.microsoft.com/en-us/ef/core/querying/).

  ***Project (1h of today's 1.5h):*** Compare in-memory and PostgreSQL query behavior, inspect generated SQL, and record the data-access decision for the Job API using the [Week 2 workbook section](../labs/phase-02-software-engineering-foundations.md#week-2-generics-linq-and-postgresql-persistence).

- [ ] **Saturday (3h):**

  ***Project (3h):*** Implement Job creation, retrieval, filtering, validation, and PostgreSQL persistence using [API — Building ASP.NET Core REST APIs with an AI-Powered Workflow](https://www.udemy.com/course/building-aspnet-core-rest-apis-with-an-ai-powered-workflow/) → `Database and Entity Framework Core`, `Entity Relationships in EF Core`, `Pagination, Filtering & Sorting`, and `Service Layer`, plus the [Week 2 workbook section](../labs/phase-02-software-engineering-foundations.md#week-2-generics-linq-and-postgresql-persistence).
- [ ] **Sunday (1.5h):**

  ***Project (1.5h):*** Add PostgreSQL integration tests, inspect generated SQL, and document ORM/query trade-offs using [ASP.NET Core integration-testing documentation](https://learn.microsoft.com/en-us/aspnet/core/test/integration-tests), [Testcontainers for .NET](https://dotnet.testcontainers.org/), and the [Week 2 workbook section](../labs/phase-02-software-engineering-foundations.md#week-2-generics-linq-and-postgresql-persistence).

**Deliverables:** Working persistence, integration tests, a brief comparison of data-access approaches.

**Self-check:** Can you explain when LINQ runs in memory versus being translated to SQL, and how to detect repeated enumeration?

## Week 3 — Async, concurrency, and cancellation

**Goal:** Distinguish asynchronous I/O, concurrency, and parallel execution.

- [ ] **Monday (1h):**

  ***Study:*** [CS — Ultimate C# Masterclass](https://www.udemy.com/course/ultimate-csharp-masterclass/) → `Multithreading & asynchrony` for `Task`, `async`/`await`, and cancellation. If needed, use [MT — Master Multithreading & Asynchronous Programming in C#/.NET](https://www.udemy.com/course/master-multithreading-asynchronous-programming-in-csharp-dotnet/) → `Task based Asynchronous Programming` and `Async & Await`; Microsoft's [asynchronous programming guide](https://learn.microsoft.com/en-us/dotnet/csharp/asynchronous-programming/) covers CPU-bound vs I/O-bound work.
- [ ] **Tuesday (1h):**

  ***Project (1h):*** Compare synchronous and asynchronous file or HTTP calls, then apply asynchronous I/O and cancellation to one Job API operation using Microsoft's [asynchronous programming guide](https://learn.microsoft.com/en-us/dotnet/csharp/asynchronous-programming/) and the [Week 3 workbook section](../labs/phase-02-software-engineering-foundations.md#week-3-async-cancellation-and-bounded-concurrency).
- [ ] **Thursday (1.5h):**

  ***Study (0.5h):*** [CS — Ultimate C# Masterclass](https://www.udemy.com/course/ultimate-csharp-masterclass/) → `Multithreading & asynchrony`; [MT — Master Multithreading & Asynchronous Programming in C#/.NET](https://www.udemy.com/course/master-multithreading-asynchronous-programming-in-csharp-dotnet/) → `Threads Synchronization` and `Concurrent Collections` for thread safety and concurrency. Microsoft's [worker services documentation](https://learn.microsoft.com/en-us/dotnet/core/extensions/workers) covers `SemaphoreSlim`, `Channel<T>`, and bounded workers.

  ***Project (1h of today's 1.5h):*** Test cancellation, concurrency limits, and bounded queue behavior in the Job API worker using the [Week 3 workbook section](../labs/phase-02-software-engineering-foundations.md#week-3-async-cancellation-and-bounded-concurrency).

- [ ] **Saturday (3h):**

  ***Project (3h):*** Add the bounded background job processor and cancellation support using Microsoft's [hosted services documentation](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/host/hosted-services) and the [Week 3 workbook section](../labs/phase-02-software-engineering-foundations.md#week-3-async-cancellation-and-bounded-concurrency).
- [ ] **Sunday (1.5h):**

  ***Project (1.5h):*** Add tests for concurrency limits, cancellation, graceful shutdown, and failure cases using [worker services documentation](https://learn.microsoft.com/en-us/dotnet/core/extensions/workers) and the [Week 3 workbook section](../labs/phase-02-software-engineering-foundations.md#week-3-async-cancellation-and-bounded-concurrency).

**Deliverables:** Bounded background worker, tests, short concurrency experiment report.

**Self-check:** Can you explain why `async` is not the same as running work on another thread, and why an unbounded queue is risky?

## Week 4 — Design and architecture

**Goal:** Apply modular design and make architectural decisions explicit.

- [ ] **Monday (1h):**

  ***Study:*** [CS — Ultimate C# Masterclass](https://www.udemy.com/course/ultimate-csharp-masterclass/) → `Object-Oriented Programming: Polymorphism, Inheritance, Interfaces` for interfaces and dependency inversion. Optionally use [CA — ASP.NET Core - SOLID and Clean Architecture](https://www.udemy.com/course/aspnet-core-solid-and-clean-architecture-net-5-and-up/) → `Preliminary Concepts`, or [DP — Design Patterns in C# and .NET](https://www.udemy.com/course/design-patterns-csharp-dotnet/) → `The SOLID Design Principles`; supplement with Microsoft's [dependency-injection documentation](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/dependency-injection).
- [ ] **Tuesday (1h):**

  ***Project (1h):*** Refactor one tightly coupled Job API component into a testable interface and implementation; keep the boundary justified by the current requirements using [SOLID principles](https://www.udemy.com/course/aspnet-core-solid-and-clean-architecture-net-5-and-up/) and the [Week 4 workbook section](../labs/phase-02-software-engineering-foundations.md#week-4-design-boundaries-and-architecture).
- [ ] **Thursday (1.5h):**

  ***Study (0.5h):*** [CA — ASP.NET Core - SOLID and Clean Architecture](https://www.udemy.com/course/aspnet-core-solid-and-clean-architecture-net-5-and-up/) → `Setting up the Application Core` and `Setting up Infrastructure Projects` for application/infrastructure boundaries; [API — Building ASP.NET Core REST APIs with an AI-Powered Workflow](https://www.udemy.com/course/building-aspnet-core-rest-apis-with-an-ai-powered-workflow/) → `Service Layer` and `Project organization and refactoring`; compare the approaches for the Job API.

  ***Project (1h of today's 1.5h):*** Choose and document the simplest suitable Job API module boundaries; record dependency direction and test seams in the Week 4 architecture decision record using the [Week 4 workbook section](../labs/phase-02-software-engineering-foundations.md#week-4-design-boundaries-and-architecture).
- [ ] **Saturday (3h):**

  ***Project (3h):*** Refactor the Job Management API into clear modules and add focused boundary tests using [API — Building ASP.NET Core REST APIs with an AI-Powered Workflow](https://www.udemy.com/course/building-aspnet-core-rest-apis-with-an-ai-powered-workflow/) → `Service Layer`, `Project organization and refactoring`, and `Automated testing`, plus the [Week 4 workbook section](../labs/phase-02-software-engineering-foundations.md#week-4-design-boundaries-and-architecture).
- [ ] **Sunday (1.5h):**

  ***Project (1.5h):*** Run the full test suite, write an ADR, create an architecture diagram, and complete the retrospective using Microsoft's [dependency-injection documentation](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/dependency-injection) and the [Week 4 workbook section](../labs/phase-02-software-engineering-foundations.md#week-4-design-boundaries-and-architecture).

**Deliverables:** Modular API, module tests, ADR, architecture diagram, retrospective.

**Self-check:** Can you explain why each module boundary exists, what alternatives you rejected, and which abstractions may be unnecessary?

## Resources

The Udemy links and week-specific selections are in the **Udemy course key and section selection** and **Weekly schedule** sections above.


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

- [ ] **Monday (1h):**

  ***Study:*** [API — Building ASP.NET Core REST APIs with an AI-Powered Workflow](https://www.udemy.com/course/building-aspnet-core-rest-apis-with-an-ai-powered-workflow/) → `Validation`, `ASP.NET Core request pipeline`, and `Endpoint filters and action filters` for request errors and validation. Optionally use [CA — ASP.NET Core - SOLID and Clean Architecture](https://www.udemy.com/course/aspnet-core-solid-and-clean-architecture-net-5-and-up/) → `Creating the API project`; use Microsoft's [Problem Details guidance](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/error-handling-api) for HTTP semantics and error responses.
- [ ] **Tuesday (1h):**

  ***Project (1h):*** Implement and test correct DI lifetimes in the Job API, including a test or example that exposes a captive-dependency error, using Microsoft's [dependency-injection documentation](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/dependency-injection) and the [Week 5 workbook section](../labs/phase-02-software-engineering-foundations.md#week-5-api-contracts-validation-and-security).
- [ ] **Thursday (1.5h):**

  ***Study (0.5h):*** [API — Building ASP.NET Core REST APIs with an AI-Powered Workflow](https://www.udemy.com/course/building-aspnet-core-rest-apis-with-an-ai-powered-workflow/) → `User management with ASP.NET Core Identity` and `JWT authentication and authorization`; optionally use [CA — ASP.NET Core - SOLID and Clean Architecture](https://www.udemy.com/course/aspnet-core-solid-and-clean-architecture-net-5-and-up/) → `Securing API and UI`. Supplement with Microsoft's [authorization documentation](https://learn.microsoft.com/en-us/aspnet/core/security/authorization/introduction) for least privilege and authorization.

  ***Project (1h of today's 1.5h):*** Draft the Job API threat model, identify trust boundaries and authorization risks, and turn the highest risks into implementation or test tasks using the [Week 5 workbook section](../labs/phase-02-software-engineering-foundations.md#week-5-api-contracts-validation-and-security).

- [ ] **Saturday (3h):**

  ***Project (3h):*** Implement request DTOs, validation/error responses, OpenAPI, authentication, and authorization using [API — Building ASP.NET Core REST APIs with an AI-Powered Workflow](https://www.udemy.com/course/building-aspnet-core-rest-apis-with-an-ai-powered-workflow/) → `DTOs`, `Validation`, `Pagination, Filtering & Sorting`, `User management with ASP.NET Core Identity`, and `JWT authentication and authorization`, plus the [Week 5 workbook section](../labs/phase-02-software-engineering-foundations.md#week-5-api-contracts-validation-and-security).
- [ ] **Sunday (1.5h):**

  ***Project (1.5h):*** Write contract and authorization integration tests, update the OpenAPI contract, and document trust boundaries using Microsoft's [ASP.NET Core integration-testing documentation](https://learn.microsoft.com/en-us/aspnet/core/test/integration-tests) and the [Week 5 workbook section](../labs/phase-02-software-engineering-foundations.md#week-5-api-contracts-validation-and-security).

**Deliverables:** Versioned API contract, validation tests, authorization policy, `docs/security.md`, and an updated OpenAPI specification.

**Self-check:** Can you explain why authentication is not authorization, when a scoped dependency must not be captured by a singleton, and which failures should produce 409 versus 500?

## Week 6 — Transactions, idempotency, optimistic concurrency, and retries

**Goal:** Prevent duplicate business outcomes and lost updates when clients retry or workers race.

- [ ] **Monday (1h):**

  ***Study:*** [API — Building ASP.NET Core REST APIs with an AI-Powered Workflow](https://www.udemy.com/course/building-aspnet-core-rest-apis-with-an-ai-powered-workflow/) → `Database and Entity Framework Core`, `Entity Relationships in EF Core`, and `Service Layer` for persistence boundaries. Optionally use [CA — ASP.NET Core - SOLID and Clean Architecture](https://www.udemy.com/course/aspnet-core-solid-and-clean-architecture-net-5-and-up/) → `Setting up the Application Core` and `Setting up Infrastructure Projects`; use PostgreSQL's [transaction isolation documentation](https://www.postgresql.org/docs/current/transaction-iso.html) and Microsoft's [EF Core transactions documentation](https://learn.microsoft.com/en-us/ef/core/saving/transactions) for transactions, concurrency, and idempotency.
- [ ] **Tuesday (1h):**

  ***Project (1h):*** Reproduce a two-client optimistic-concurrency conflict and apply the chosen resolution behavior to a Job API state update using Microsoft's [EF Core concurrency documentation](https://learn.microsoft.com/en-us/ef/core/saving/concurrency) and the [Week 6 workbook section](../labs/phase-02-software-engineering-foundations.md#week-6-transactions-idempotency-and-optimistic-concurrency).
- [ ] **Thursday (1.5h):**

  ***Study (0.5h):*** [CS — Ultimate C# Masterclass](https://www.udemy.com/course/ultimate-csharp-masterclass/) → `Design Patterns`; optionally use [DP — Design Patterns in C# and .NET](https://www.udemy.com/course/design-patterns-csharp-dotnet/) → `State` and `Strategy` for job-state design. Use PostgreSQL's [transaction isolation documentation](https://www.postgresql.org/docs/current/transaction-iso.html) for transaction behavior and retries.

  ***Project (1h of today's 1.5h):*** Define and test allowed Job state transitions, idempotency behavior, and retry boundaries; record unresolved transaction decisions in the Week 6 decision note.
- [ ] **Saturday (3h):**

  ***Project (3h):*** Implement transactional idempotency, optimistic concurrency, safe state transitions, and bounded retries using [API — Building ASP.NET Core REST APIs with an AI-Powered Workflow](https://www.udemy.com/course/building-aspnet-core-rest-apis-with-an-ai-powered-workflow/) → `Database and Entity Framework Core`, `Entity Relationships in EF Core`, `Service Layer`, and `Advanced business logic`, Microsoft's [EF Core concurrency documentation](https://learn.microsoft.com/en-us/ef/core/saving/concurrency), and the [Week 6 workbook section](../labs/phase-02-software-engineering-foundations.md#week-6-transactions-idempotency-and-optimistic-concurrency).
- [ ] **Sunday (1.5h):**

  ***Project (1.5h):*** Test duplicate submissions, conflicting payloads, concurrent updates, rollback, and worker restart using Microsoft's [EF Core transactions](https://learn.microsoft.com/en-us/ef/core/saving/transactions) and [concurrency documentation](https://learn.microsoft.com/en-us/ef/core/saving/concurrency), plus the [Week 6 workbook section](../labs/phase-02-software-engineering-foundations.md#week-6-transactions-idempotency-and-optimistic-concurrency). Finish the idempotency ADR with observed results.

**Deliverables:** Idempotent job creation, tested job state transitions, concurrency-safe updates, transaction tests, and `docs/decisions/ADR-00X-idempotency.md`.

**Self-check:** Can you explain why a retry can be safe for a read but unsafe for a write, and how a database constraint protects against a race that an application-level check cannot?

## Week 7 — Observability, profiling, and resilience

**Goal:** Make failures diagnosable and demonstrate evidence-based performance improvement.

- [ ] **Monday (1h):**

  ***Study:*** [CS — Ultimate C# Masterclass](https://www.udemy.com/course/ultimate-csharp-masterclass/) → `.NET under the hood`, `Advanced C# types`, `Collections`, and `Multithreading & asynchrony`; optionally use [HP — High Performance Coding with .NET Core and C#](https://www.udemy.com/course/high-performance-coding-with-net-core-and-csharp/) → `Measure Performance During Development Part 1`, `Measure Performance During Development Part 2`, and `Performance Monitoring in Production for .NET Core`. Supplement with [OpenTelemetry for .NET](https://opentelemetry.io/docs/languages/net/) and Microsoft's [.NET diagnostics documentation](https://learn.microsoft.com/en-us/dotnet/core/diagnostics/) for logging, tracing, metrics, and service-level indicators.
- [ ] **Tuesday (1h):**

  ***Project (1h):*** Establish a repeatable Job API workload, capture a baseline with `dotnet-counters`, a profiler, or BenchmarkDotNet, and record the measurement limits using Microsoft's [.NET diagnostics documentation](https://learn.microsoft.com/en-us/dotnet/core/diagnostics/) and the [Week 7 workbook section](../labs/phase-02-software-engineering-foundations.md#week-7-observability-profiling-and-resilience).
- [ ] **Thursday (1.5h):**

  ***Study (0.5h):*** [CS — Ultimate C# Masterclass](https://www.udemy.com/course/ultimate-csharp-masterclass/) → `Multithreading & asynchrony` and `Advanced C# types`; optionally use [MT — Master Multithreading & Asynchronous Programming in C#/.NET](https://www.udemy.com/course/master-multithreading-asynchronous-programming-in-csharp-dotnet/) → `Threads Synchronization` and `Concurrent Collections`. Use Microsoft's [health-check documentation](https://learn.microsoft.com/en-us/aspnet/core/host-and-deploy/health-checks) and [hosted services documentation](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/host/hosted-services) for readiness, timeouts, and graceful shutdown.

  ***Project (1h of today's 1.5h):*** Select an evidence-backed improvement, implement or document it, and define a failure signal and recovery check using the [Week 7 workbook section](../labs/phase-02-software-engineering-foundations.md#week-7-observability-profiling-and-resilience).

- [ ] **Saturday (3h):**

  ***Project (3h):*** Add structured logs, correlation, tracing, metrics, health endpoints, timeouts, and a repeatable load-test script using [OpenTelemetry for .NET](https://opentelemetry.io/docs/languages/net/), Microsoft's [health-check documentation](https://learn.microsoft.com/en-us/aspnet/core/host-and-deploy/health-checks), and the [Week 7 workbook section](../labs/phase-02-software-engineering-foundations.md#week-7-observability-profiling-and-resilience).
- [ ] **Sunday (1.5h):**

  ***Project (1.5h):*** Run baseline and failure-injection tests; record latency, throughput, memory, errors, and recovery using [.NET diagnostics](https://learn.microsoft.com/en-us/dotnet/core/diagnostics/), [OpenTelemetry for .NET](https://opentelemetry.io/docs/languages/net/), and the [Week 7 workbook section](../labs/phase-02-software-engineering-foundations.md#week-7-observability-profiling-and-resilience).

**Deliverables:** Telemetry dashboard or captured traces, `docs/operations.md`, benchmark results, and a failure-mode table.

**Self-check:** Given one failed job, can you trace the request, identify its last successful transition, and distinguish a dependency timeout from an application defect?

## Week 8 — CI/CD, architecture review, hardening, and phase gate

**Goal:** Deliver a reproducible, reviewable portfolio project and verify understanding without relying on AI.

- [ ] **Monday (1h):**

  ***Study:*** [API — Building ASP.NET Core REST APIs with an AI-Powered Workflow](https://www.udemy.com/course/building-aspnet-core-rest-apis-with-an-ai-powered-workflow/) → `Automated testing`; optionally use [TD — Test Driven Development in ASP.NET Core](https://www.udemy.com/course/test-driven-development-in-net-core-the-handbook/) → `Integration Testing - Testing the Data Access Layer` and `Using GitHub for Continuous Integration and Testing`. Supplement with Microsoft's [.NET testing documentation](https://learn.microsoft.com/en-us/dotnet/core/testing/) and [GitHub Actions for .NET](https://docs.github.com/en/actions/automating-builds-and-tests/building-and-testing-net) for contract tests, review, and workflow practices.
- [ ] **Tuesday (1h):**

  ***Project (1h):*** Review the API without AI, create issues, and fix the highest-impact item using the [Week 8 design-review procedure](../labs/phase-02-software-engineering-foundations.md#design-review-without-ai) and Microsoft's [ASP.NET Core best practices](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/best-practices).
- [ ] **Thursday (1.5h):**

  ***Study (0.5h):*** [API — Building ASP.NET Core REST APIs with an AI-Powered Workflow](https://www.udemy.com/course/building-aspnet-core-rest-apis-with-an-ai-powered-workflow/) → `Automated testing`; [TD — Test Driven Development in ASP.NET Core](https://www.udemy.com/course/test-driven-development-in-net-core-the-handbook/) → `Unit Testing - Application Core` and `Integration Testing - Testing the Data Access Layer`. Review Microsoft's [.NET testing documentation](https://learn.microsoft.com/en-us/dotnet/core/testing/).

  ***Project (1h of today's 1.5h):*** Add or refine CI, analyzers, unit/integration tests, and dependency scanning using [GitHub Actions for .NET](https://docs.github.com/en/actions/automating-builds-and-tests/building-and-testing-net) and [.NET testing documentation](https://learn.microsoft.com/en-us/dotnet/core/testing/); build a container only if a free local runtime is available. Verify a clean checkout using the [Week 8 workbook section](../labs/phase-02-software-engineering-foundations.md#week-8-cicd-architecture-review-and-release).
- [ ] **Saturday (3h):**

  ***Project (3h):*** Finalize documentation, diagrams, ADRs, reproducible local PostgreSQL setup, and demo using Microsoft's [containerize a .NET application guide](https://learn.microsoft.com/en-us/dotnet/core/docker/introduction); Docker Compose is optional. Perform the worker-crash/recovery demonstration using the [Week 8 workbook section](../labs/phase-02-software-engineering-foundations.md#week-8-cicd-architecture-review-and-release).
- [ ] **Sunday (1.5h):**

  ***Project (1.5h):*** Complete the Phase 2 assessment and retrospective, update the skill matrix, and identify concepts to review before Phase 3 using [.NET testing documentation](https://learn.microsoft.com/en-us/dotnet/core/testing/) and the [Week 8 workbook section](../labs/phase-02-software-engineering-foundations.md#week-8-cicd-architecture-review-and-release).

**Deliverables:** Versioned release, passing CI or reproducible local checks, runnable local setup, architecture pack, failure demo, and Phase 2 retrospective.

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
- [ ] CI or recorded local checks run build, formatting/analyzers, and tests; container build is optional and uses a free local runtime if available. Public-repository GitHub Actions runners are free; verify included compute/billing before running private-repository workflows.
- [ ] Logs, metrics, and traces identify a failed job end to end.
- [ ] README, diagrams, ADRs, threat model, and runbook are understandable to a new contributor.
- [ ] You can reproduce a failure and demonstrate recovery.

### Staff-level practice (1 hour each week is included in the schedule)

At the end of each week, capture one engineering decision: **context → alternatives → decision → trade-offs → validation evidence**. At the phase review, present a short design proposal as though another team would depend on your API. Include an adoption path, compatibility risks, operational ownership, and the top three unresolved risks.

### Definition of done

Do not chase feature count. A small, robust API with demonstrated tests, clear boundaries, recovery behavior, and architectural reasoning is stronger evidence than an overbuilt service. Move to Phase 3 (Scala/JVM) once the essential gates are met; carry optional enhancements into a backlog.
