# Phase 2 — Software Engineering Foundations Lab Workbook

Use this workbook for the detailed implementation steps and guided experiments linked from the [Phase 2 weekly schedule](../../weekly-schedules/phase-02-software-engineering-foundations.md). The schedule retains course sections, weekly time blocks, and outcomes; course viewing is optional support for the hands-on work.

## Working rules

- Build the Job Management API incrementally in one repository; avoid copying a complete course project.
- Before adding a library or abstraction, write down the problem it solves and how you will verify it.
- Keep secrets out of source control. Use synthetic data and local disposable resources.
- Make one small change at a time; run the narrowest relevant test, then the full suite at each weekly gate.
- Save evidence: commands, test output, diagrams, measurements, and short decision notes. Do not claim a behavior was tested if it was only reasoned about.

## Week 1: Runtime, Domain Model, and API Skeleton

### Value/reference, records, boxing, and allocation experiment

1. Create a small console project in the solution or a separate `experiments/RuntimeSemantics` project.
2. Define a mutable reference type, a struct, and a record with the same few fields.
3. Assign each value to a second variable and mutate or reassign it; record which copy changes and why.
4. Assign a value type to `object` or an interface, then inspect the boxing example and its allocation implications.
5. Write a short note distinguishing value semantics, reference identity, stack/heap simplifications, and observable allocations. Avoid claiming all values of a type live in one memory region.

### GC and disposal inspection

1. Use a disposable local process or sample .NET app; do not attach profilers to production processes.
2. Observe process allocation/GC counters with `dotnet-counters` or a comparable profiler while the sample allocates objects.
3. Add a deterministic `IDisposable` resource example (such as a stream) and show disposal with `using`.
4. Compare the output before and after disposal; explain that disposal releases owned resources while GC manages managed-memory reclamation.
5. Save a brief measurement note with runtime version, command/tool, and limitations.

### Job API skeleton and first test

1. Create a repository and solution, then add an ASP.NET Core Web API project and a test project using the installed .NET SDK.
2. Add a minimal `Job` domain type with an identifier, submitted timestamp, and initial status. Keep persistence out of this first slice.
3. Add one endpoint that returns a simple health/status response and one endpoint that creates or returns a sample job in memory.
4. Run the API locally and call the endpoint with a browser, `curl`, or an HTTP client. Record the request and response.
5. Add a unit test for the Job type or its initial state; first observe the test fail, then implement the behavior and make it pass.
6. Add `docs/architecture.md` with the current project structure and a small request-flow sketch. Label in-memory behavior as temporary.

**Week 1 evidence:** runnable API, first test, runtime experiment note, and architecture sketch.

## Week 2: Generics, LINQ, and PostgreSQL Persistence

### `Result<T>` or generic collection exercise

1. Define a small generic `Result<T>` representing success with a value or failure with an error; do not add a package.
2. Write tests for success, failure, and access to the relevant value/error.
3. Add one example consumer that handles both cases explicitly.
4. Compare this with a small generic collection only if it better supports the concept; keep the exercise bounded.
5. Explain the type-safety and failure-handling trade-off in a short note.

### `IEnumerable<T>` vs `IQueryable<T>` experiment

1. Prepare the same small dataset in memory and through EF Core/PostgreSQL.
2. Write equivalent filter/order/projection queries using `IEnumerable<T>` and `IQueryable<T>`.
3. Inspect when each query executes and which part runs in the database versus application memory.
4. Capture generated SQL for the `IQueryable<T>` path and identify deferred execution or repeated enumeration risks.
5. Record the result without generalizing from a tiny dataset to production performance.

### Job persistence slice

1. Add PostgreSQL to the local development environment using an approved local container or existing authorized database.
2. Add a schema/migration for jobs and choose one data-access approach (Dapper or EF Core). Record why you chose it.
3. Implement create, get-by-id, list/filter, and basic validation operations.
4. Add a repository or equivalent persistence boundary only where it improves testability; avoid adding layers without a reason.
5. Verify the API against a clean database and inspect at least one generated SQL statement/query.

### Integration tests and query comparison

1. Configure a test database isolated from development data, using Testcontainers or another approved disposable test setup.
2. Add integration tests for create, retrieve, filter, invalid input, and database constraint behavior.
3. Ensure tests create and clean up their own data and can run repeatedly.
4. Compare one in-memory LINQ operation with its database-backed equivalent; capture generated SQL and note execution location.
5. Save test output and a short ORM/query trade-off note.

**Week 2 evidence:** typed-result tests, persisted job operations, integration test output, and a LINQ/SQL comparison.

## Week 3: Async, Cancellation, and Bounded Concurrency

### Synchronous versus asynchronous I/O experiment

1. Select a harmless local file or mock HTTP endpoint; avoid load against external services.
2. Implement synchronous and asynchronous versions that perform equivalent I/O.
3. Measure elapsed time and thread usage for a small repeated workload; keep workload and environment constant.
4. Add cancellation to the asynchronous version and cancel it during an in-progress operation.
5. Explain why async I/O does not imply a dedicated thread per operation and note measurement limitations.

### Race and bounded-work experiments

1. Create a shared counter or job state updated by concurrent tasks without synchronization; run it repeatedly and observe incorrect outcomes.
2. Protect the operation with a suitable synchronization primitive and add a test or assertion for correctness.
3. Compare a bounded `SemaphoreSlim` approach with a bounded `Channel<T>` producer/consumer queue.
4. Track maximum in-flight work and verify the configured limit is never exceeded.
5. Record cancellation, exception propagation, and shutdown behavior.

### Background job worker

1. Define the job submission and status contract before implementing the worker.
2. Use a bounded queue so producers receive backpressure instead of allowing unbounded memory growth.
3. Run a hosted worker that dequeues jobs, updates their state, and observes cancellation tokens.
4. Handle worker exceptions explicitly and ensure a failed job does not silently disappear.
5. Implement graceful shutdown: stop accepting work, finish or safely abandon in-flight work according to the chosen policy, then exit.
6. Keep queue durability out of scope until later persistence work; document that limitation.

### Concurrency and failure tests

1. Test the maximum concurrency limit with more jobs than the limit.
2. Test cancellation before work begins and while work is running.
3. Test graceful host shutdown with queued and in-flight work.
4. Inject a worker exception and verify visible job state and logs.
5. Save the experiment measurements and test output.

**Week 3 evidence:** sync/async comparison, bounded worker, and passing concurrency/cancellation tests.

## Week 4: Design Boundaries and Architecture

### Refactor a tightly coupled component

1. Select one component that directly mixes HTTP, job rules, and persistence.
2. Write a characterization test for its current externally visible behavior.
3. Separate the smallest useful domain/application behavior from transport and persistence details.
4. Introduce an interface only at a boundary that needs independent testing or substitution.
5. Run the characterization and unit tests after each refactor step; avoid changing behavior in this exercise.

### Compare architecture options and module tests

1. Sketch the current structure and two alternatives (for example, a small layered structure and vertical slices).
2. Compare change locality, dependency direction, test setup, and complexity for the current API scope.
3. Choose the simplest structure that meets the stated requirements; do not add MediatR or multiple projects by default.
4. Add focused tests at the chosen module boundaries and run the complete test suite.
5. Write one ADR with context, options, decision, consequences, validation, and revisit trigger.
6. Draw an architecture diagram and complete a retrospective on abstractions kept or rejected.

**Week 4 evidence:** refactored module, tests, ADR, diagram, and retrospective.

## Week 5: API Contracts, Validation, and Security

### DI lifetime and captive-dependency lab

1. Create one small service for each lifetime: singleton, scoped, and transient.
2. Log or inspect instance identity across two requests and within one request.
3. Create a deliberately invalid singleton-to-scoped dependency in an isolated experiment and observe the failure/diagnostic.
4. Correct the lifetime or introduce an appropriate scope boundary; add a test or startup check proving the issue is resolved.
5. Record the ownership rule that prevents a scoped service from being captured by a singleton.

### Contract, validation, and authorization slice

1. Define request/response DTOs separately from persistence entities.
2. Add validation for required fields, length/range constraints, and invalid state transitions.
3. Return consistent Problem Details errors and preserve correct HTTP semantics (including 201, 202, 400, 401, 403, 404, and 409 where applicable).
4. Generate/update the OpenAPI contract and verify it matches actual responses.
5. Protect selected operations with authentication and authorization policies; keep secrets in local user-secrets/environment configuration, never source control.
6. Add pagination only if useful for the current API; document the contract and trust boundaries.

### API security/contract tests

1. Add integration tests for invalid input, missing authentication, insufficient authorization, duplicate/conflicting requests, and normal success.
2. Assert status codes and Problem Details shape, not just that a request fails.
3. Verify protected data is not returned to an unauthorized caller.
4. Update `docs/security.md` with assets, trust boundaries, threats, mitigations, and known limitations.
5. Save the OpenAPI file and test output.

**Week 5 evidence:** versioned API contract, validation and authorization tests, and security notes.

## Week 6: Transactions, Idempotency, and Optimistic Concurrency

### Two-client concurrency experiment

1. Create a job row with a version/concurrency token.
2. Load the same version from two clients or test tasks.
3. Update the row from the first client and commit.
4. Attempt to commit the stale update from the second client; observe the lost-update risk without protection.
5. Add optimistic concurrency and assert the stale write is rejected with a conflict outcome.
6. Record the transaction boundary and test output.

### Durable idempotency and safe transitions

1. Define the scope and retention of an idempotency key and what makes a repeated request equivalent.
2. Add a database table/unique constraint for the key and store the result needed to return a stable response.
3. In one transaction, insert the idempotency record and create the job so partial success cannot leave inconsistent state.
4. Handle duplicate-key races by returning the original result for an equivalent retry and rejecting a conflicting payload according to the contract.
5. Add an explicit job state machine; validate every allowed transition and reject illegal transitions.
6. Implement a bounded retry policy only for transient failures, with timeout and jitter. Do not retry non-idempotent operations blindly.
7. Write an ADR describing key scope, transaction boundary, concurrency behavior, and trade-offs.

### Transaction and worker-recovery tests

1. Test repeated identical submissions and verify only one job is created.
2. Test reuse of a key with a conflicting payload and assert the documented response.
3. Test concurrent updates and verify stale writes fail safely.
4. Force a database/transaction failure between idempotency and job persistence; verify rollback leaves no partial record.
5. Restart the worker around queued/in-flight work and verify the documented recovery behavior.
6. Test state transition validity and retry limits.

**Week 6 evidence:** transaction-safe idempotency, concurrency-safe state changes, tests, and ADR.

## Week 7: Observability, Profiling, and Resilience

### Profile the service

1. Establish a repeatable small workload and capture a baseline for latency, throughput, CPU, allocations, and GC.
2. Use `dotnet-counters`, a profiler, or BenchmarkDotNet on a local/disposable environment.
3. Identify one measured hotspot or allocation source; state a hypothesis before changing code.
4. Make one targeted change and rerun the same workload.
5. Compare results and record runtime, hardware, workload, and confounders. Keep the change only if measurements and tests support it.

### End-to-end observability

1. Add structured logs with job ID and correlation/trace ID; avoid secrets and sensitive payloads.
2. Instrument request and worker spans with OpenTelemetry and propagate context across the job lifecycle.
3. Add counters/histograms for submitted, completed, failed jobs, queue depth, and processing duration.
4. Add readiness and liveness checks with distinct meanings; do not report ready while required dependencies are unavailable.
5. Configure timeout budgets and graceful shutdown behavior; document retry limits and avoid retry storms.
6. Capture a trace and metrics sample for both a successful job and a failed job.

### Load and failure-injection tests

1. Run a repeatable baseline load and record latency, throughput, memory, errors, and recovery time.
2. Inject one failure at a time: database delay, worker interruption, or duplicate request.
3. Follow the trace/logs to locate the last successful job transition.
4. Verify the job reaches a safe, visible state and the service recovers without duplicate effects.
5. Save the failure-mode table and benchmark results in `docs/operations.md`.

**Week 7 evidence:** captured traces/metrics, operations notes, before/after profile, and failure-test results.

## Week 8: CI/CD, Architecture Review, and Release

### Design review without AI

1. Review the API unaided and list three design weaknesses, one reliability risk, and one test gap.
2. Create issues with impact, reproduction/evidence, and acceptance criteria.
3. Select the highest-impact fix that fits the session and implement it.
4. Run focused tests and the full suite; record what changed and what remains.

### CI and reproducible environment

1. Add a GitHub Actions workflow for restore, build, format/analyzers, unit tests, PostgreSQL integration tests, dependency scanning, and Docker build.
2. Ensure PostgreSQL test dependencies are ephemeral and credentials are supplied through CI secrets/variables, not committed files.
3. Add Docker Compose or equivalent local instructions for the API and PostgreSQL.
4. Clone or check out into a clean directory and follow the README from scratch.
5. Fix reproducibility gaps and verify the pipeline passes on a pull request.

### Portfolio release and recovery demonstration

1. Finalize README, API examples, architecture/sequence diagrams, ADRs, security notes, operations runbook, and known limitations.
2. Tag a versioned release only after clean build, tests, and local startup pass.
3. Demonstrate a deliberate worker crash and recovery using a disposable environment; capture expected behavior and evidence.
4. Prepare a 5–10 minute demonstration: problem, design, key trade-offs, tests, failure behavior, and next steps.
5. Complete the phase acceptance criteria and retrospective; update the tracker only where evidence supports a change.

**Week 8 evidence:** reproducible release, green CI, architecture pack, recovery demo, and retrospective.