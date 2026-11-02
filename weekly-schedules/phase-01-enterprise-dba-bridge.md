# Phase 1 — Enterprise DBA Operations and HA/DR Bridge

**Duration:** 8 weeks · **Time:** 8 hours/week · **Total:** 64 hours  
**Purpose:** Build durable technical breadth for future senior enterprise DBA roles within the roadmap's existing weekly study budget. Oracle and SQL Server operations are the core; Azure SQL and Db2 receive focused coverage, and ExaCC is a bounded architecture/lifecycle module. This is foundational study and lab evidence, not a substitute for senior production experience.

## Weekly cadence

| Activity | Hours/week |
|---|---:|
| Course sections and official documentation | 2 |
| Authorized hands-on lab / guided exercises | 4 |
| Runbooks, diagrams, and evidence notes | 1 |
| Review and skills matrix | 1 |
| **Total** | **8** |

Choose only the course sections relevant to the week's outcome. Course recommendations and links are in [02 — Courses and reading](../02-courses-and-reading.md). Course availability, versions, labs, and subscription inclusion change; verify before enrolling. Use Oracle LiveLabs, Microsoft Learn sandboxes, or another authorized environment where available. Avoid incurring cloud charges without a budget, and do not download or use licensed software outside its terms.

## Course and walkthrough map

Use about **1–2 hours of course/video material per week**; these courses are longer than the schedule, so watch only the sections that support that week's lab. Complete the project work in the daily plan rather than watching an entire course. Course ratings, curriculum, and subscription access can change.

| Week | Guided course or walkthrough | Apply it to |
|---|---|---|
| 1 | [Complete Microsoft SQL Server Database Administration Course](https://www.udemy.com/course/complete-microsoft-sql-server-database-administration-course/) — choose introductory administration, security, and monitoring sections. | Build the four-platform inventory and compare operations responsibilities. |
| 2 | [Oracle Database 19c Backup and Recovery](https://www.udemy.com/course/oracle-database-backup-and-recovery/) — its listing covers 12c, 19c, and 23ai; focus on backup validation, restore, recovery, and verification sections. | Perform or trace a single-instance RMAN recovery and write the runbook. Match commands to the lab version and verify current course coverage. |
| 3 | [Oracle Grid Infrastructure and RAC using Oracle Database 19c](https://www.udemy.com/course/oracle-rac-and-grid-infrastructure-concepts/) and [Oracle Database Data Guard Administration (12c and 19c)](https://www.udemy.com/course/oracle-12c-data-guard-administration/) — select RAC/ASM and Data Guard setup/failure sections. For the bounded ExaCC module, use the Exadata Cloud@Customer section in [Foundation to Oracle Database in OCI](https://www.udemy.com/course/foundation-to-oracle-database-in-oracle-cloud-infrastructure/). | Draw RAC/Data Guard failure flows; complete a guided HA lab if authorized, otherwise a labeled tabletop. Treat OCI/ExaCC as orientation only. |
| 4 | [SQL Server 2025: Build Always On HA & DR Solutions](https://www.udemy.com/course/sqlserverag/) — follow the Availability Group setup and test-failover walkthrough. Cross-check prerequisites with Microsoft's [Availability Group tutorial](https://learn.microsoft.com/en-us/sql/database-engine/availability-groups/windows/availability-group-tutorial-prerequisites?view=sql-server-ver17). | Build or tabletop a two-replica AG, planned failover, application verification, and rollback. |
| 5 | [Introduction to Azure SQL Database for Beginners](https://www.udemy.com/course/introduction-to-azure-sql-database/) — use the create/connect and management walkthroughs. | Create and connect to a database only in an authorized, cost-controlled environment; then produce the service-selection and migration brief. |
| 6 | [Database Engineer/DBA: PostgreSQL, IBM Db2, MariaDB, NoSQL](https://www.udemy.com/course/database-engineerdba-postgresql-ibm-db2-mariadbnosql/) — select Db2 administration sections. For a small build, use [Python and DB2 App Development: Build a CRUD Application](https://www.udemy.com/course/python-and-db2-app-development-build-a-crud-application/). | Create or trace a Db2 CRUD workflow and map backup, monitoring, and recovery tasks. The CRUD course has a small review base; verify its lab setup before investing time. |
| 7 | [Oracle Database Performance Tuning](https://www.udemy.com/course/oracle-database-performance-tuning/) and [SQL Server Performance Tuning Part 1](https://www.udemy.com/course/sql-server-performance-tuning-part-1/) — select plan, metrics, and diagnosis sections only. | Analyze a reproducible query/performance scenario, then write the capacity worksheet, monitoring map, automation check, and RCA. |
| 8 | No new course. Revisit the relevant course sections and official docs from Weeks 2–7. | Run the integrated tabletop, finalize runbooks and the technical briefing, and record remaining experience gaps. |

## Week 1 — Enterprise DBA operations baseline

**Goal:** Map the four database platforms and establish an honest, evidence-based baseline.

- [ ] **Monday (1h):** Spend 15 minutes completing the Phase 1 baseline in [05 — Study tracker](../05-study-tracker.md). Treat existing Start scores as provisional: for each skill, keep or change the score to match your own evidence; use 0 if unfamiliar and note any uncertainty. Use the remaining 45 minutes to start the linked SQL Server DBA course's introductory administration and monitoring sections; note unfamiliar concepts for the week's comparison and lab work.
- [ ] **Tuesday (1h):** Sketch a typical database service path. **Steps:** 1) List the application, driver/connection pool, network, database endpoint/listener, database, storage, identity, and monitoring. 2) Draw arrows showing request, authentication, query, and response flow. 3) Mark where Oracle and SQL Server differ or where you need to verify details.
- [ ] **Thursday (1.5h):** Review Windows/Linux service, process, storage, permissions, and log basics, then draft a generic incident/change handoff. **Steps:** 1) Make a two-column Windows/Linux note for service status, process inspection, disk capacity, permissions, and logs. 2) Write the incident flow from alert to triage, escalation, mitigation, validation, and handoff. 3) Add change approval, maintenance window, rollback, and notification checkpoints.
- [ ] **Saturday (3h):** Build a platform inventory and comparison matrix. **Steps:** 1) Create columns for Oracle, SQL Server, Azure SQL, and Db2; create rows for versions/exposure, HA/DR, backup/recovery, monitoring, security, patching, cloud, and automation. 2) Populate facts from your work/project records and official product documentation; use the resume only as an index, not as the sole source. 3) Label each entry as personally performed, observed, studied, or not yet known; do not infer experience. 4) Add a source or evidence note for each nonblank entry.
- [ ] **Sunday (1.5h):** Reconcile the baseline and finish the operations workflow. **Steps:** 1) Compare Monday's scores with Saturday's evidence labels; revise only unsupported scores. 2) Identify one authorized lab option for Oracle and SQL Server, plus documentation/tabletop alternatives for Azure SQL and Db2. 3) Finish the incident/change handoff flow and list the first three unknowns to resolve in Week 2.

**Deliverables:** Platform comparison, skills baseline, incident/change workflow.  
**Self-check:** Can you describe what you have actually operated, what you have only studied, and the path an application request takes to each database?

## Week 2 — Oracle administration, monitoring, and recovery

**Goal:** Strengthen Oracle operational foundations and demonstrate a bounded recovery workflow.

- [ ] **Monday (1h):** Study Oracle instance/database architecture, CDB/PDB concepts, services, listener connectivity, and basic operational views.
- [ ] **Tuesday (1h):** In an authorized lab, inspect basic Oracle state. **Steps:** 1) Record Oracle version, instance/database identity, and available PDBs. 2) Inspect PDB state, sessions, tablespaces, alert log, and configured backups using approved read-only queries/tools. 3) Save command/output snippets with secrets and sensitive data removed. If no lab is available, annotate official examples and label every step unexecuted.
- [ ] **Thursday (1.5h):** Study OEM/OMS monitoring, alert triage, patching lifecycle, and RMAN backup validation; compare monitoring signals with tools you have used before. **Steps:** 1) Choose one availability, capacity, backup-health, and performance signal from the course/docs. 2) Record where each appears in OEM/OMS and in a monitoring tool you know, if applicable. 3) Write the operational question and follow-up action for each signal. 4) Mark checks as personally used, observed, or only studied.
- [ ] **Saturday (3h):** In an authorized single-instance environment, perform a bounded RMAN recovery exercise. **Steps:** 1) Record environment/version and confirm the recovery target and permitted operations. 2) Inspect or create the backup and run the applicable validation. 3) Follow the course/documentation restore and recovery walkthrough. 4) Verify database state and expected data using approved queries. 5) Capture commands, checkpoints, outputs, and any failure/cleanup steps. Do not describe this as RAC or ExaCC recovery. If no lab is available, produce a tabletop walkthrough and mark it untested.
- [ ] **Sunday (1.5h):** Write an Oracle backup/recovery runbook. **Steps:** 1) State scope, prerequisites, roles, and recovery objective. 2) List pre-checks and backup validation. 3) Record restore/recovery sequence with version-specific references. 4) Specify post-recovery verification, escalation, and stop/rollback conditions. 5) Mark each step tested, observed, or documentation-only.

**Deliverables:** Lab record and Oracle recovery runbook.  
**Self-check:** Can you explain what was actually restored, how you verified it, and which production safeguards were not represented in the lab?

## Week 3 — Oracle HA and bounded ExaCC orientation

**Goal:** Understand Oracle HA choices and ExaCC responsibility boundaries without making engineered systems the center of the phase.

- [ ] **Monday (1h):** Study Grid Infrastructure, RAC, ASM, and Data Guard purposes, then create a glossary. **Steps:** 1) Capture each term's one-sentence purpose from the course or official docs. 2) Group terms under cluster, storage, standby, broker, and role transition. 3) Add one operational question each concept helps answer.
- [ ] **Tuesday (1h):** Draw RAC/ASM and Data Guard failure domains. **Steps:** 1) Draw database instances/nodes, shared storage, primary, and standby. 2) Mark node, storage, and site failure boundaries. 3) Trace node loss, transport/apply lag, switchover, failover, and reinstatement with arrows. 4) Label which paths are conceptual versus lab-tested.
- [ ] **Thursday (1.5h):** Complete the focused OCI/ExaCC and GoldenGate orientation. **Steps:** 1) Sketch tenancy, compartments, IAM, VCN/network, and database service boundaries. 2) Mark customer and provider responsibilities for maintenance and support. 3) Draw the basic GoldenGate Extract-to-Replicat flow and identify monitoring/recovery concepts. Keep this to orientation, not a full implementation track.
- [ ] **Saturday (3h):** Complete one authorized RAC or Data Guard HA/role-transition walkthrough, or a tabletop if no lab is available. **Steps:** 1) Choose a single scenario (node loss, standby switchover, or failover). 2) Record prerequisites, expected behavior, commands/actions, and safety checks from the course/docs. 3) Execute only in an authorized environment; capture version, outputs, and verification. 4) For tabletop work, label every step "not lab-tested" and identify what access would be needed.
- [ ] **Sunday (1.5h):** Create an Oracle HA decision tree and ExaCC boundary diagram. **Steps:** 1) Start with service availability versus site disaster recovery and map each to RAC or Data Guard. 2) Add decision inputs such as failure domain, RPO/RTO, and operator ownership. 3) Mark the ExaCC provider/customer boundary and lifecycle responsibilities. 4) List untested operations and the access/experience needed to validate them.

**Deliverables:** Oracle HA decision tree, bounded ExaCC/OCI brief, and tested-or-tabletop evidence.  
**Self-check:** Can you distinguish RAC availability from Data Guard disaster recovery and explain who operates which ExaCC components?

## Week 4 — SQL Server HA/DR and performance

**Goal:** Build practical SQL Server availability, backup/recovery, and performance fundamentals used in enterprise DBA roles.

- [ ] **Monday (1h):** Study Always On Availability Groups: replicas, synchronous/asynchronous commit, failover modes, quorum, listeners, and availability databases.
- [ ] **Tuesday (1h):** Review SQL Server backup types, restore sequences, recovery models, log shipping/mirroring context, and RPO/RTO trade-offs; build a restore decision checklist. **Steps:** 1) Choose a recovery scenario and required recovery point. 2) List required full, differential, and log backups for the applicable recovery model. 3) Order the restore steps and add validation and stop conditions. 4) Cite the product-version documentation used.
- [ ] **Thursday (1.5h):** Study AG health signals, wait statistics/query plans, capacity indicators, and common failover constraints. Use official documentation or course sections linked in the course guide.
- [ ] **Saturday (3h):** In an authorized multi-instance lab, inspect AG health and perform a planned failover plus application/DB validation. **Steps:** 1) Confirm lab topology, prerequisites, health, and permitted failover mode. 2) Capture baseline replica/AG state. 3) Follow the course tutorial to initiate planned failover. 4) Verify primary/secondary roles, database synchronization, and a test application connection. 5) Record rollback/recovery path. If no lab is available, complete the same sequence as a tabletop and label it untested.
- [ ] **Sunday (1.5h):** Write an Always On operations runbook. **Steps:** 1) Add health pre-checks and the failover decision criteria. 2) Document action sequence, expected state transitions, and application validation. 3) Add backup/restore verification and a performance triage checklist. 4) Mark which procedures were executed versus simulated and cite the course/docs.

**Deliverables:** Always On failover runbook, recovery checklist, and lab/tabletop record.  
**Self-check:** Can you explain the failover mode, quorum implications, expected data-loss boundary, and how you prove the application recovered?

## Week 5 — Azure SQL and modernization

**Goal:** Compare Azure SQL service models and make a supportable migration choice.

- [ ] **Monday (1h):** Compare Azure SQL Database, Azure SQL Managed Instance, and SQL Server on Azure VMs. **Steps:** 1) Create one column per service. 2) Compare compatibility, control, HA, patching, backup, and operational responsibility using official docs. 3) Mark which service fits a simple example workload and cite why.
- [ ] **Tuesday (1h):** Map identity, network connectivity, private access, permissions, encryption, and least-privilege considerations. **Steps:** 1) Draw the client-to-database connection path. 2) Mark identity/authentication and network boundaries. 3) Add encryption, access-control, and auditing points. 4) List assumptions requiring confirmation in a real environment.
- [ ] **Thursday (1.5h):** Study Azure monitoring, performance diagnostics, backup/restore options, maintenance boundaries, and migration assessment. Use official documentation; avoid creating billable resources without an approved budget.
- [ ] **Saturday (3h):** Build a service-selection and migration plan for a hypothetical SQL Server workload. **Steps:** 1) Define workload size, dependencies, availability, security, and recovery needs. 2) Assess service compatibility and choose Azure SQL Database, Managed Instance, or VM-based SQL Server. 3) Sequence discovery, data movement, testing, cutover, and rollback. 4) Assign security, monitoring, backup, and operational owners. 5) Record cost assumptions; use a lab only if authorized and cost-controlled.
- [ ] **Sunday (1.5h):** Produce a one-page architecture decision record. **Steps:** 1) State the decision and requirements. 2) Summarize alternatives and rationale. 3) List failure/ownership assumptions and unresolved risks. 4) Add validation steps and rollback trigger.

**Deliverables:** Azure SQL service comparison, migration/cutover plan, and decision record.  
**Self-check:** Can you justify PaaS vs IaaS for the workload and explain the operational tasks that shift to Microsoft versus remain with the team?

## Week 6 — Db2 and cross-platform operations

**Goal:** Build useful Db2 literacy while being explicit about the limits of a short orientation.

- [ ] **Monday (1h):** Study Db2 architecture, instances, databases, storage, logs, client connectivity, and core terminology.
- [ ] **Tuesday (1h):** Compare Db2 backup/recovery, monitoring, security, and HA/DR concepts with Oracle and SQL Server using IBM documentation. **Steps:** 1) Make a comparison table with one row per capability. 2) Record the Db2 terminology and the nearest Oracle/SQL Server analogue. 3) Cite IBM documentation and flag anything not confirmed.
- [ ] **Thursday (1.5h):** Follow an authorized Db2 guided lab if one is readily available. **Steps:** 1) Confirm the lab's Db2 edition/version and permitted actions. 2) Follow the setup and connect steps. 3) Perform one documented administrative task and capture output. 4) Record cleanup steps. Otherwise, trace a documented backup/recovery incident and mark each step paper-based.
- [ ] **Saturday (3h):** Complete a small authorized Db2 exercise or create a platform comparison. **Steps:** 1) Set a 30-minute cap for environment setup. 2) If the lab works, complete one CRUD or administration walkthrough and record results. 3) If it does not, compare provisioning, connectivity, monitoring, backup, restore, patching, and escalation from official docs. 4) Record setup blockers and do not claim unexecuted practice.
- [ ] **Sunday (1.5h):** Write a Db2 operations primer. **Steps:** 1) Summarize architecture and common operational vocabulary. 2) List documented backup, restore, monitoring, and escalation paths. 3) Add known unknowns and questions for a Db2 platform owner. 4) Link sources and label experience as studied or lab-tested.

**Deliverables:** Db2 comparison and operations primer.  
**Self-check:** Can you navigate Db2 terminology and identify the correct documentation or owner without claiming independent administration experience?

## Week 7 — Performance, security, automation, and RCA

**Goal:** Apply portable DBA practices across platforms and create reusable operational evidence.

- [ ] **Monday (1h):** Study query-plan and workload signals for Oracle and SQL Server; distinguish symptoms, bottlenecks, and capacity constraints.
- [ ] **Tuesday (1h):** Build a capacity worksheet. **Steps:** 1) Choose a synthetic workload or authorized source. 2) Record current utilization and growth assumptions separately. 3) Calculate headroom for a stated planning period. 4) Propose peak-period and alert thresholds with rationale.
- [ ] **Thursday (1.5h):** Review least privilege, auditing, vulnerability remediation, monitoring/diagnostic tools, and safe change practices; map OEM and SQL Server/Azure equivalents. **Steps:** 1) Create rows for access, audit, vulnerability, availability, capacity, and performance. 2) Map a detection signal and tool to each row. 3) Add a safe change/approval check and a verification signal.
- [ ] **Saturday (3h):** Automate a read-only health/reporting check and conduct a short incident RCA. **Steps:** 1) Choose a synthetic or authorized database status check. 2) Write a PowerShell, Bash, or Python script that only reads status and emits a timestamped report. 3) Test normal and unavailable/error cases; confirm it makes no changes. 4) Build an incident timeline from a supplied/synthetic scenario. 5) Separate evidence, symptoms, contributing factors, root cause, corrective action, and prevention.
- [ ] **Sunday (1.5h):** Write an operational standard and RCA report. **Steps:** 1) State scope, owner, prerequisites, and safe operating limits. 2) Document the read-only check, expected output, and escalation threshold. 3) Summarize the RCA evidence and corrective actions. 4) Link alert/runbook sources and note risks of automating changes without approval.

**Deliverables:** Capacity worksheet, read-only automation, monitoring/security map, RCA and corrective-action record.  
**Self-check:** Can you support each conclusion with measured or cited evidence and separate a contributing factor from the root cause?

## Week 8 — Integrated operations and technical leadership

**Goal:** Combine technical breadth into a credible enterprise operations pack.

- [ ] **Monday (1h):** Review the skills matrix and rank remaining gaps. **Steps:** 1) Mark each Phase 1 competency as studied, lab-tested, production-experienced, or unknown. 2) Rank gaps by operational risk and role breadth. 3) Choose one next topic based on hands-on feasibility and available access.
- [ ] **Tuesday (1h):** Draft a cross-platform HA/DR decision matrix. **Steps:** 1) Define a service-criticality scenario and RPO/RTO. 2) Compare Oracle, SQL Server, Azure SQL, and Db2 recovery/HA options. 3) Record backup, failover, monitoring, owner, and validation evidence for each. 4) Mark unsupported assumptions.
- [ ] **Thursday (1.5h):** Prepare a change/migration plan and tabletop escalation scenario. **Steps:** 1) Choose one database change or migration from the earlier labs. 2) Write pre-checks, approvals, communication, implementation, validation, rollback, and closeout steps. 3) Assign hypothetical application, infrastructure, cloud, security, and DBA roles to an escalation path.
- [ ] **Saturday (3h):** Run a 90-minute simulated incident/recovery review, then finalize the operations pack. **Steps:** 1) Choose a failure scenario and assign facilitator, DBA, application, and infrastructure roles. 2) Walk through detection, triage, decision, recovery, validation, and communication; record timestamps and decisions. 3) Hold a short debrief and capture follow-up actions. 4) Use remaining time to finalize standards, runbooks, evidence links, and a mixed-audience technical briefing. Treat mentorship as a scenario, not a claimed outcome.
- [ ] **Sunday (1.5h):** Complete the phase exit gate and retrospective. **Steps:** 1) Check each gate against an evidence artifact. 2) Update tracker ratings only where new evidence supports a change. 3) List the next supervised production assignment or authorized lab needed. 4) Write a short retrospective separating demonstrated skills from remaining gaps.

**Deliverables:** Enterprise DBA operations pack, final skills matrix, technical briefing, and phase retrospective.  
**Self-check:** Can you explain platform-specific trade-offs, what you personally executed, what was simulated, and where you still need production experience?

## Phase exit gate

- [ ] Explain Oracle RAC/ASM, Data Guard, RMAN, OEM, and the ExaCC service boundary at an appropriate foundational level.
- [ ] Explain SQL Server Always On, backup/restore, Azure SQL service models, and Db2 operational foundations.
- [ ] Demonstrate the HA/DR or recovery steps actually tested in authorized labs, with versions and limitations recorded.
- [ ] Produce a cross-platform operations pack with monitoring, security, automation, RCA, migration, and change-management evidence.
- [ ] Keep ExaCC and Db2 claims proportional to the limited time and hands-on access available.
- [ ] Distinguish course knowledge, lab experience, and production experience in the skills matrix and resume.
- [ ] Identify the next real supervised assignment or authorized lab needed to build hands-on depth.

**Expectation:** This phase improves technical breadth and makes the learning gaps concrete. It cannot satisfy a 7+ year experience requirement, establish senior production ownership, or substitute for real on-call and mentorship experience.