# Phase 1 — Enterprise DBA Lab Workbook

Use this workbook for step-by-step procedures for Phase 1 assignments, labs, guided exercises, and tabletops linked from the [Phase 1 weekly schedule](../../weekly-schedules/phase-01-enterprise-dba-bridge.md). Weekly time blocks and course sections remain in the schedule.

## Lab safety and evidence rules

- Use only environments, software, accounts, and data you are authorized to access.
- Do not run restore, failover, patch, or configuration-changing commands against production systems.
- Prefer disposable VMs, provided sandboxes, or official guided labs. Confirm versions and prerequisites before following commands.
- Do not create billable cloud resources unless you have an approved budget. Delete temporary resources and verify cleanup.
- Record each activity as **executed**, **observed**, **tabletop**, or **documentation-only**. Do not present simulations as production experience.
- Capture sanitized outputs and versions. Do not include credentials, personal data, proprietary data, or sensitive topology in portfolio artifacts.

## Free resource map

Prefer the local tools first. The links and terms below were checked on 2026-11-02; verify the current license and pricing page before downloading or provisioning.

| Skill | No/low-cost resource | Use and limits |
|---|---|---|
| Oracle administration and RMAN | [Oracle AI Database Free 26ai](https://www.oracle.com/database/free/) on Windows x64, Linux, or an authorized local container; [installation/connect quick start](https://www.oracle.com/database/free/get-started/); [Oracle Free Use Terms](https://www.oracle.com/downloads/licenses/oracle-free-license.html) | Free for development, testing, prototyping, and demonstration under Oracle Free Use Terms. Resource ceiling: 2 CPU threads, 2 GB database RAM, 12 GB user data. Use it for single-instance inspection and recovery only; it is not RAC, Data Guard, or ExaCC practice. The linked course covers earlier releases, so verify commands against the lab version. |
| Oracle RAC/Data Guard/ExaCC concepts | [Oracle LiveLabs](https://livelabs.oracle.com/) and the linked Udemy walkthroughs | Check the lab listing and launch page for account, capacity, and time limits. Do not create OCI compute/storage resources expecting them to be free. If an appropriate hosted lab is unavailable, use course demos plus the workbook tabletop; mark it not lab-tested. |
| SQL Server administration and performance | [SQL Server 2025 Developer](https://learn.microsoft.com/en-us/sql/sql-server/editions-and-components-of-sql-server-2025?view=sql-server-ver17) installed locally, or [Microsoft's SQL Server container guide](https://learn.microsoft.com/en-us/sql/linux/containers/deploy?view=sql-server-ver17) | Developer includes Enterprise features and is licensed for development/test, not production. Use it for local backup/restore, query-plan, security, and monitoring exercises. SQL Server Express is also free, but does not support Availability Groups. |
| SQL Server Always On | SQL Server Developer plus a local WSFC lab only if you already have sufficient hardware/VM capacity; [Windows Server Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-windows-server-2025) under its current terms; otherwise use the course walkthrough and tabletop | A traditional Windows Availability Group needs WSFC nodes, with each replica on a different node. Two VMs, Windows Server, and sufficient host RAM/storage may be needed. Windows Server evaluation is time-limited and governed by its terms. Do not spin up paid cloud VMs; if the host cannot support the cluster, document the procedure and label it not lab-tested. |
| Azure SQL | [Azure SQL Database free tier](https://learn.microsoft.com/en-us/azure/azure-sql/database/free-offer?view=azuresql) | Current offer: up to 100,000 vCore-seconds/month, 32 GB data, and 32 GB backup per database, up to 10 free-tier databases per subscription. Requires an Azure subscription and excludes Azure for Students Starter. Select the free-tier option and **AutoPause** both at idle and at quota exhaustion; never select paid overage. Verify `useFreeLimit=true` and monitor the free allowance. If uncertain, do the Week 5 service-selection exercise on paper. |
| Db2 | [IBM Db2 documentation](https://www.ibm.com/docs/en/db2) plus the Db2/CRUD courses already linked in the weekly schedule, if included in your existing Udemy subscription | I could not verify a currently downloadable, no-cost local Db2 Community edition from IBM's current product/documentation pages. Use course demonstrations and official docs for the required orientation; only use an IBM trial if its account page explicitly confirms $0 for the intended resource and you can verify billing controls. Otherwise mark the exercise documentation-only. |
| Containers for local integration tests | [Docker Personal](https://www.docker.com/pricing/) or [Podman Desktop for Windows](https://podman-desktop.io/docs/installation/windows-install); [Testcontainers for .NET + PostgreSQL](https://testcontainers.com/guides/getting-started-with-testcontainers-for-dotnet/) | Docker Personal is $0 for eligible individual use under its current terms. Podman Desktop is a free alternative but uses WSL2 or Hyper-V; its Windows guide lists a 6 GB RAM minimum for the Podman machine and setup requirements. If containers do not fit the computer, install PostgreSQL locally and run the same integration tests against a dedicated test database. |

## Week 1: Baseline and Platform Inventory

### Baseline self-assessment

1. Open the Phase 1 skill rows in [05 — Study tracker](../../05-study-tracker.md).
2. Treat existing Start scores as provisional. For each skill, keep or change the score based on your own experience; use 0 if unfamiliar.
3. Add a brief evidence note for scores above 0: what you performed, observed, or studied. Do not use a resume statement alone as evidence.
4. Mark uncertain or unsupported claims for review on Sunday.

### Database service path sketch

1. List the application, driver/connection pool, network, database endpoint/listener, database, storage, identity, and monitoring components.
2. Draw request, authentication, query, result, and response flow between components.
3. Add Oracle and SQL Server differences you can verify; label anything else unknown.
4. Save the diagram and source notes in the Phase 1 evidence folder.

### Windows/Linux and incident/change workflow

1. Create a Windows/Linux comparison table for service status, process inspection, disk capacity, permissions, and logs.
2. Draft an incident flow from alert to triage, escalation, mitigation, validation, and handoff.
3. Add change approval, maintenance-window, rollback, and notification checkpoints.
4. Mark which operating-system procedures you have used versus only studied.

### Four-platform inventory and comparison matrix

1. Create columns for Oracle, SQL Server, Azure SQL, and Db2.
2. Create rows for versions/exposure, HA/DR, backup/recovery, monitoring, security, patching, cloud, and automation.
3. Populate facts from work/project records and official product documentation. Use a resume only as an index, not as the sole source.
4. Label each entry personally performed, observed, studied, or unknown; do not infer experience.
5. Add a source or evidence note for each nonblank entry.

### Baseline and workflow review

1. Compare Monday's scores with Saturday's evidence labels; revise only scores that are unsupported or inaccurate.
2. Identify one authorized lab option for Oracle and SQL Server, plus documentation/tabletop alternatives for Azure SQL and Db2.
3. Finish the incident/change handoff flow and list the first three unknowns to resolve in Week 2.

## Week 2: Oracle Inspection and RMAN Recovery

### Oracle state inspection

1. Confirm the environment is authorized and identify the Oracle version, instance, database, and available PDBs.
2. Use approved read-only queries or tools to inspect PDB state, sessions, tablespaces, alert logs, and configured backups.
3. Capture sanitized command/output snippets and note which checks you performed versus only read about.
4. If no lab is available, annotate the equivalent official documentation and label every step **documentation-only**.

### Single-instance RMAN recovery

1. Use Oracle AI Database Free 26ai locally or an authorized Oracle LiveLabs single-instance environment. Record the version and define a recovery target before starting. Check the linked course steps against the selected version.
2. Inspect or create the backup, then run the applicable backup validation.
3. Follow the selected RMAN course's backup/restore and recovery demonstration for the same version. Stop if the lab differs materially from the instructions; do not improvise destructive steps.
4. Verify database state and expected data using approved queries.
5. Save sanitized commands, checkpoints, verification results, and cleanup actions.
6. If no suitable lab is available, write a tabletop sequence from the course/docs and label it **not lab-tested**.

**Scope limit:** A single-instance exercise does not demonstrate RAC, Data Guard, or ExaCC recovery.

### Monitoring signal comparison

1. Choose one availability, capacity, backup-health, and performance signal from the course or official documentation.
2. Record where each signal appears in OEM/OMS and in a monitoring tool you know, if applicable.
3. For each signal, write the operational question it answers and the follow-up action it should trigger.
4. Label each check personally used, observed, or only studied.

### Oracle backup/recovery runbook

1. State scope, prerequisites, roles, and the recovery objective.
2. List pre-checks and backup validation requirements.
3. Record the restore/recovery sequence with version-specific references.
4. Specify post-recovery verification, escalation, and stop/rollback conditions.
5. Mark each step tested, observed, or documentation-only.

## Week 3: Oracle HA and ExaCC Boundaries

### RAC and Data Guard failure map

1. Draw RAC nodes/instances and shared storage; separately draw a Data Guard primary and standby.
2. Mark node, storage, and site failure boundaries and identify which component detects each failure.
3. Trace node loss, transport/apply lag, switchover, failover, and reinstatement with arrows and expected state changes.
4. Label each path as conceptual, observed, or lab-tested. Cite the course or official documentation.

### HA walkthrough or tabletop

1. Choose one scenario: RAC node loss, planned Data Guard switchover, or Data Guard failover.
2. Record prerequisites, expected behavior, safety checks, recovery/rollback path, and verification criteria from the matching course section and docs.
3. Execute only if an authorized Oracle LiveLabs or existing lab environment supports the scenario. Oracle AI Database Free is single-instance practice, not a RAC/Data Guard lab. Capture version and sanitized evidence.
4. Otherwise, walk through the sequence on paper, label every action **not lab-tested**, and list the environment/access needed to test it.

### OCI/ExaCC responsibility diagram

1. Sketch tenancy, compartments, IAM, VCN/network, and database service boundaries from the selected OCI course sections.
2. Mark customer and provider responsibilities for access, maintenance, monitoring, and support.
3. Add the ExaCC service boundary and lifecycle/support notes; treat the result as an architecture orientation, not operational experience.
4. Draw a basic GoldenGate Extract-to-Replicat flow and identify monitoring/recovery concepts without attempting a full implementation.

### Oracle HA glossary

1. Capture a one-sentence purpose for Grid Infrastructure, RAC, ASM, Data Guard, broker, standby, and role transition from the course or official docs.
2. Group the terms under cluster, storage, standby, broker, and role transition.
3. Add one operational question each concept helps answer.

### Oracle HA decision tree and ExaCC boundary diagram

1. Start with service availability versus site disaster recovery; map the relevant Oracle options to RAC or Data Guard.
2. Add decision inputs such as failure domain, RPO/RTO, and operator ownership.
3. Mark the ExaCC provider/customer boundary and lifecycle responsibilities.
4. List untested operations and the authorized access or experience needed to validate them.

## Week 4: SQL Server Recovery and Always On

### Restore decision checklist

1. Choose a recovery scenario and required recovery point.
2. Identify the recovery model and required full, differential, and transaction-log backups.
3. Order the restore steps and specify validation queries, stop conditions, and escalation.
4. Cite product-version documentation and mark the checklist as studied or exercised.

### Availability Group failover

1. Use SQL Server Developer on authorized local systems and confirm the lab has the required WSFC topology, with each replica on a different node. Record SQL Server and Windows versions, replica roles, quorum, and failover mode. Do not provision cloud VMs for this exercise.
2. Capture baseline AG health, synchronization state, and a test application connection.
3. Follow the SQL Server 2025 course setup for the available lab; initiate a **planned** failover only.
4. Verify primary/secondary roles, database synchronization, listener connectivity, and application access.
5. Record the rollback/recovery path and clean up lab resources.
6. If the required topology is unavailable, perform these steps as a tabletop and label them **not lab-tested**. Do not simulate by changing a real cluster.

### Always On operations runbook

1. Add health pre-checks and failover decision criteria.
2. Document the action sequence, expected state transitions, and application validation.
3. Add backup/restore verification and a short performance triage checklist.
4. Mark procedures executed versus simulated and cite the course/docs.

## Week 5: Azure SQL Service Selection

### Service and migration exercise

1. Define a hypothetical workload: size, dependencies, availability, security, recovery objectives, and operational constraints.
2. Compare Azure SQL Database, Managed Instance, and SQL Server on Azure VMs for compatibility, control, HA, patching, backup, monitoring, and ownership.
3. Choose a target service and cite the documentation supporting the choice.
4. Sequence discovery, compatibility checks, data movement, testing, cutover, rollback, security, and monitoring.
5. Record cost and identity/network assumptions. Keep this as a paper exercise unless you have an authorized Azure subscription and select the free tier with AutoPause at both idle and quota exhaustion. Verify the free-limit setting and do not allow paid overages.

### Optional create/connect walkthrough

1. Confirm that the Azure SQL free-tier offer is available for your subscription, that the subscription is not an excluded type, and that no paid overage is enabled. If unsure, skip resource creation and use the paper exercise.
2. Follow the course sections for creating the database, configuring access, and connecting with SSMS.
3. Test the connection and permissions using non-sensitive sample data.
4. Delete temporary resources and verify cleanup; record actual costs if any.

### Azure SQL service comparison and migration decision

1. Create one column per service: Azure SQL Database, Managed Instance, and SQL Server on Azure VMs.
2. Compare compatibility, control, HA, patching, backup, and operational responsibility using official docs.
3. Select a simple example workload and identify the best-fit service; cite the reason.

### Azure SQL identity and network map

1. Draw the client-to-database connection path.
2. Mark identity/authentication and network boundaries, including private access where relevant.
3. Add encryption, access-control, and auditing points.
4. List assumptions that require confirmation in a real environment.

### Azure SQL architecture decision record

1. State the decision and requirements.
2. Summarize alternatives and rationale.
3. List failure/ownership assumptions and unresolved risks.
4. Add validation steps and rollback trigger.

## Week 6: Db2 Orientation and CRUD Lab

### Db2 capability comparison

1. Create a table with rows for architecture, connectivity, backup/recovery, monitoring, security, and HA/DR.
2. For each row, record Db2 terminology and the nearest Oracle/SQL Server analogue from IBM documentation.
3. Cite sources and mark anything not verified as an assumption or unknown.

### Db2 setup and CRUD walkthrough

1. Use the existing Udemy course walkthrough and IBM documentation by default. Only use a Db2 environment if its current account/license page explicitly confirms $0 for the intended resource and billing controls are clear. Confirm edition/version and permitted actions before setup; cap setup troubleshooting at 30 minutes.
2. Follow `DB2 Database Server Setup` and `Performing CRUD Operations and Data Manipulation` in the Db2 course, or `IBM DB2 Setup` and `Building CRUD App: Part 2: Python and DB2 Interaction` in the Python/Db2 course.
3. Create or connect to a sample database/table, then insert, read, update, and delete a harmless test record.
4. Capture sanitized connection/setup details, SQL, outputs, and cleanup steps.
5. If no verified no-cost environment is available or setup is blocked, trace the course's documented path and label it **documentation-only**; do not create an unbudgeted cloud resource or claim independent Db2 administration.

### Db2 operations primer

1. Summarize architecture and common operational vocabulary.
2. List documented backup, restore, monitoring, and escalation paths.
3. Add known unknowns and questions for a Db2 platform owner.
4. Link sources and label experience as studied or lab-tested.

## Week 7: Performance, Monitoring, Automation, and RCA

### Performance diagnosis

1. Choose a synthetic query/workload scenario or an authorized sanitized example.
2. Follow the selected Oracle sections on wait events/AWR or SQL Server sections on indexes/statistics/waits.
3. Record the baseline symptom and relevant metrics/plan evidence before proposing a change.
4. State a likely bottleneck, alternative explanations, and a validation method. Do not apply changes to production.

### Read-only health check and RCA

1. Select one synthetic or authorized availability/backup/status check.
2. Write a PowerShell, Bash, or Python script that only reads status and emits a timestamped report; do not add configuration changes or credentials.
3. Test normal output and unavailable/error cases. Confirm the script performs no writes.
4. Use a synthetic incident to create a timestamped event timeline.
5. Separate evidence, symptoms, contributing factors, root cause, corrective action, and prevention; label simulated evidence.

### Capacity worksheet

1. Choose a synthetic workload or authorized source.
2. Record current utilization and growth assumptions separately.
3. Calculate headroom for a stated planning period.
4. Propose peak-period and alert thresholds with rationale.

### Monitoring and security control map

1. Create rows for access, audit, vulnerability, availability, capacity, and performance.
2. Map a detection signal and tool to each row.
3. Add a safe change/approval check and a verification signal.

### Operational standard and RCA report

1. State scope, owner, prerequisites, and safe operating limits.
2. Document the read-only check, expected output, and escalation threshold.
3. Summarize RCA evidence and corrective actions.
4. Link alert/runbook sources and note risks of automating changes without approval.

## Week 8: Integrated Incident Tabletop

### Gap ranking

1. Mark each Phase 1 competency as studied, lab-tested, production-experienced, or unknown.
2. Rank gaps by operational risk and role breadth.
3. Choose one next topic based on hands-on feasibility and available access.

### Cross-platform HA/DR decision matrix

1. Define a service-criticality scenario and RPO/RTO.
2. Compare Oracle, SQL Server, Azure SQL, and Db2 recovery/HA options.
3. Record backup, failover, monitoring, owner, and validation evidence for each.
4. Mark unsupported assumptions.

### Change/migration plan and escalation scenario

1. Choose one database change or migration from the earlier labs.
2. Write pre-checks, approvals, communication, implementation, validation, rollback, and closeout steps.
3. Assign hypothetical application, infrastructure, cloud, security, and DBA roles to an escalation path.

### Phase retrospective

1. Check each phase gate against an evidence artifact.
2. Update tracker ratings only where new evidence supports a change.
3. List the next supervised production assignment or authorized lab needed.
4. Write a short retrospective separating demonstrated skills from remaining gaps.

### 90-minute exercise

1. Choose a failure scenario and assign facilitator, DBA, application, and infrastructure roles. Use a fictional or sanitized scenario only.
2. Spend 10 minutes on scope and service objectives; 10 on detection; 20 on triage and evidence; 20 on recovery decisions/actions; 10 on validation; 10 on communications; and 10 on debrief.
3. Record timestamps, decisions, assumptions, RPO/RTO impact, escalation points, and recovery evidence.
4. Debrief with actions, owners, and due dates. Label all activity **tabletop**, not production experience.
5. Link the runbooks used, note missing procedures, and turn the top gaps into the next supervised lab or work assignment.