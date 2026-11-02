# Phase 1 — Enterprise DBA Operations and HA/DR Bridge

**Duration:** 8 weeks · **Time:** 8 hours/week · **Total:** 64 hours  
**Purpose:** Front-load technical gaps from enterprise DBA postings while keeping the roadmap's existing weekly study budget. Oracle and SQL Server operations are the core; Azure SQL and Db2 receive focused coverage, and ExaCC is a bounded architecture/lifecycle module. This is foundational study and lab evidence, not a substitute for senior production experience.

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
| 3 | [Oracle 12C R2 RAC Administration and Data Guard](https://www.udemy.com/course/oracle-12c-r2-rac-administration-and-data-guard-for-12c-r2/) — select RAC/ASM and Data Guard setup/failure sections. For the bounded ExaCC module, use the Exadata Cloud@Customer section in [Foundation to Oracle Database in OCI](https://www.udemy.com/course/foundation-to-oracle-database-in-oracle-cloud-infrastructure/). | Draw RAC/Data Guard failure flows; complete a guided HA lab if authorized, otherwise a labeled tabletop. Treat OCI/ExaCC as orientation only. |
| 4 | [SQL Server 2025: Build Always On HA & DR Solutions](https://www.udemy.com/course/sqlserverag/) — follow the Availability Group setup and test-failover walkthrough. Cross-check prerequisites with Microsoft's [Availability Group tutorial](https://learn.microsoft.com/en-us/sql/database-engine/availability-groups/windows/availability-group-tutorial-prerequisites?view=sql-server-ver17). | Build or tabletop a two-replica AG, planned failover, application verification, and rollback. |
| 5 | [Introduction to Azure SQL Database for Beginners](https://www.udemy.com/course/introduction-to-azure-sql-database/) — use the create/connect and management walkthroughs. | Create and connect to a database only in an authorized, cost-controlled environment; then produce the service-selection and migration brief. |
| 6 | [Database Engineer/DBA: PostgreSQL, IBM Db2, MariaDB, NoSQL](https://www.udemy.com/course/database-engineerdba-postgresql-ibm-db2-mariadbnosql/) — select Db2 administration sections. For a small build, use [Python and DB2 App Development: Build a CRUD Application](https://www.udemy.com/course/python-and-db2-app-development-build-a-crud-application/). | Create or trace a Db2 CRUD workflow and map backup, monitoring, and recovery tasks. The CRUD course has a small review base; verify its lab setup before investing time. |
| 7 | [Oracle Database Performance Tuning](https://www.udemy.com/course/oracle-database-performance-tuning/) and [SQL Server Performance Tuning Part 1](https://www.udemy.com/course/sql-server-performance-tuning-part-1/) — select plan, metrics, and diagnosis sections only. | Analyze a reproducible query/performance scenario, then write the capacity worksheet, monitoring map, automation check, and RCA. |
| 8 | No new course. Revisit the relevant course sections and official docs from Weeks 2–7. | Run the integrated tabletop, finalize runbooks and the technical briefing, and record remaining experience gaps. |

## Week 1 — Enterprise DBA operations baseline

**Goal:** Map the four database platforms and establish an honest, evidence-based baseline.

- [ ] **Monday (1h):** Read the target requirements and compare Oracle, SQL Server, Azure SQL, and Db2 at a high level. Tag every skill as studied, lab-tested, production-experienced, or unknown.
- [ ] **Tuesday (1h):** Sketch a typical database service path: application, driver/connection pool, network, database listener/endpoint, storage, identity, and monitoring. Note where Oracle and SQL Server differ.
- [ ] **Thursday (1.5h):** Review Windows/Linux service, process, storage, permissions, and log basics. Draft a generic incident, escalation, change approval, and on-call handoff flow.
- [ ] **Saturday (3h):** Build a platform inventory and comparison matrix covering versions, HA/DR, backup, monitoring, security, patching, and cloud options. Use only resume facts and official documentation; do not infer experience.
- [ ] **Sunday (1.5h):** Write the initial skills matrix and a one-page operations workflow. Identify which labs can be run with authorized access and which need a paper-based alternative.

**Deliverables:** Platform comparison, skills baseline, incident/change workflow.  
**Self-check:** Can you describe what you have actually operated, what you have only studied, and the path an application request takes to each database?

## Week 2 — Oracle administration, monitoring, and recovery

**Goal:** Strengthen Oracle operational foundations and demonstrate a bounded recovery workflow.

- [ ] **Monday (1h):** Study Oracle instance/database architecture, CDB/PDB concepts, services, listener connectivity, and basic operational views.
- [ ] **Tuesday (1h):** In an authorized lab, inspect database identity, PDB state, sessions, tablespaces, alert logs, and backup configuration. If no lab is available, annotate official examples and label them as unexecuted.
- [ ] **Thursday (1.5h):** Study OEM/OMS monitoring, alert triage, patching lifecycle, and RMAN backup validation. Compare monitoring signals with the tools you have used before.
- [ ] **Saturday (3h):** In an authorized single-instance environment, take or inspect a backup, validate it, and perform a documented restore/recovery exercise. Record commands, versions, checkpoints, and verification queries. Do not describe this as RAC or ExaCC recovery.
- [ ] **Sunday (1.5h):** Write an Oracle backup/recovery runbook covering prerequisites, recovery objective, restore steps, validation, escalation, and rollback/stop conditions.

**Deliverables:** Lab record and Oracle recovery runbook.  
**Self-check:** Can you explain what was actually restored, how you verified it, and which production safeguards were not represented in the lab?

## Week 3 — Oracle HA and bounded ExaCC orientation

**Goal:** Understand Oracle HA choices and ExaCC responsibility boundaries without making engineered systems the center of the phase.

- [ ] **Monday (1h):** Study Grid Infrastructure, RAC, ASM, and Data Guard purposes. Create a glossary of cluster, storage, standby, broker, and role-transition terms.
- [ ] **Tuesday (1h):** Draw RAC/ASM and Data Guard failure domains. Trace node loss, storage failure, transport/apply lag, switchover, failover, and reinstatement at a conceptual level.
- [ ] **Thursday (1.5h):** Complete a focused OCI/ExaCC module: tenancy, compartments, IAM, VCN/network foundations, ExaCC service boundaries, customer-vs-provider responsibilities, maintenance, and support. Spend only a short orientation segment on GoldenGate Extract/Replicat flow.
- [ ] **Saturday (3h):** If authorized RAC or Data Guard labs are available, follow one guided HA/role-transition exercise and capture the environment and limits. Otherwise, produce a tabletop failure walkthrough with explicit "not lab-tested" labels.
- [ ] **Sunday (1.5h):** Create an Oracle HA decision tree and an ExaCC architecture/service-boundary diagram. List the access and experience needed to validate each untested operation.

**Deliverables:** Oracle HA decision tree, bounded ExaCC/OCI brief, and tested-or-tabletop evidence.  
**Self-check:** Can you distinguish RAC availability from Data Guard disaster recovery and explain who operates which ExaCC components?

## Week 4 — SQL Server HA/DR and performance

**Goal:** Cover the posting's SQL Server availability, backup/recovery, and performance requirements.

- [ ] **Monday (1h):** Study Always On Availability Groups: replicas, synchronous/asynchronous commit, failover modes, quorum, listeners, and availability databases.
- [ ] **Tuesday (1h):** Review SQL Server backup types, restore sequences, recovery models, log shipping/mirroring context, and RPO/RTO trade-offs. Build a restore decision checklist.
- [ ] **Thursday (1.5h):** Study AG health signals, wait statistics/query plans, capacity indicators, and common failover constraints. Use official documentation or course sections linked in the course guide.
- [ ] **Saturday (3h):** In an authorized multi-instance lab, inspect AG health and perform a planned failover plus application/DB validation. If no lab is available, create a detailed failover tabletop with prerequisites, decision points, validation, and rollback.
- [ ] **Sunday (1.5h):** Write an Always On operations runbook and record exactly which steps were executed versus simulated. Add backup/restore verification and a short performance triage checklist.

**Deliverables:** Always On failover runbook, recovery checklist, and lab/tabletop record.  
**Self-check:** Can you explain the failover mode, quorum implications, expected data-loss boundary, and how you prove the application recovered?

## Week 5 — Azure SQL and modernization

**Goal:** Compare Azure SQL service models and make a supportable migration choice.

- [ ] **Monday (1h):** Compare Azure SQL Database, Azure SQL Managed Instance, and SQL Server on Azure VMs by compatibility, control, HA, patching, backup, and operational responsibility.
- [ ] **Tuesday (1h):** Map identity, network connectivity, private access, permissions, encryption, and least-privilege considerations for an Azure SQL workload.
- [ ] **Thursday (1.5h):** Study Azure monitoring, performance diagnostics, backup/restore options, maintenance boundaries, and migration assessment. Use official documentation; avoid creating billable resources without an approved budget.
- [ ] **Saturday (3h):** Build a service-selection and migration plan for a hypothetical SQL Server workload. Include discovery, compatibility, data movement, testing, cutover, rollback, security, monitoring, and cost assumptions. Use a free/authorized lab only if available.
- [ ] **Sunday (1.5h):** Review failure and operational ownership assumptions; produce a one-page architecture decision record with unresolved risks clearly marked.

**Deliverables:** Azure SQL service comparison, migration/cutover plan, and decision record.  
**Self-check:** Can you justify PaaS vs IaaS for the workload and explain the operational tasks that shift to Microsoft versus remain with the team?

## Week 6 — Db2 and cross-platform operations

**Goal:** Build useful Db2 literacy while being explicit about the limits of a short orientation.

- [ ] **Monday (1h):** Study Db2 architecture, instances, databases, storage, logs, client connectivity, and core terminology.
- [ ] **Tuesday (1h):** Compare Db2 backup/recovery, monitoring, security, and HA/DR concepts with Oracle and SQL Server using IBM documentation.
- [ ] **Thursday (1.5h):** Follow an authorized Db2 guided lab if one is readily available. Otherwise, trace a documented backup/recovery and incident scenario and mark it as paper-based.
- [ ] **Saturday (3h):** Complete a small authorized Db2 exercise or create a platform comparison for provisioning, connectivity, monitoring, backup, restore, patching, and escalation. Do not let environment setup consume the full session.
- [ ] **Sunday (1.5h):** Write a Db2 operations primer with known unknowns and questions to ask a platform owner during a real incident or change.

**Deliverables:** Db2 comparison and operations primer.  
**Self-check:** Can you navigate Db2 terminology and identify the correct documentation or owner without claiming independent administration experience?

## Week 7 — Performance, security, automation, and RCA

**Goal:** Apply portable DBA practices across platforms and create reusable operational evidence.

- [ ] **Monday (1h):** Study query-plan and workload signals for Oracle and SQL Server; distinguish symptoms, bottlenecks, and capacity constraints.
- [ ] **Tuesday (1h):** Build a small capacity worksheet covering utilization, growth, headroom, peak periods, and alert thresholds. Label assumptions versus measured values.
- [ ] **Thursday (1.5h):** Review least privilege, auditing, vulnerability remediation, monitoring/diagnostic tools, and safe change practices. Map OEM and equivalent SQL Server/Azure monitoring capabilities.
- [ ] **Saturday (3h):** Use a synthetic or authorized scenario to automate a read-only health/reporting check with PowerShell, Bash, or Python. Conduct a short incident RCA: timeline, evidence, contributing factors, corrective action, and prevention.
- [ ] **Sunday (1.5h):** Write an operational standard and RCA report. Include alert/runbook links, verification steps, and the risks of automating changes without approval.

**Deliverables:** Capacity worksheet, read-only automation, monitoring/security map, RCA and corrective-action record.  
**Self-check:** Can you support each conclusion with measured or cited evidence and separate a contributing factor from the root cause?

## Week 8 — Integrated operations and technical leadership

**Goal:** Combine technical breadth into a credible enterprise operations pack.

- [ ] **Monday (1h):** Review the skills matrix and rank the remaining gaps by role importance, hands-on feasibility, and risk. Revisit only the weakest technical topic.
- [ ] **Tuesday (1h):** Draft a cross-platform HA/DR decision matrix with service criticality, RPO/RTO, backup, failover, monitoring, ownership, and recovery validation.
- [ ] **Thursday (1.5h):** Prepare a change/migration plan and a tabletop escalation scenario involving application, infrastructure, cloud, security, and database teams.
- [ ] **Saturday (3h):** Run a 90-minute simulated incident/recovery review, then use the remaining time to finalize standards, runbooks, evidence links, and a concise technical briefing for a mixed audience. Include a mentoring/escalation scenario without claiming real mentorship outcomes.
- [ ] **Sunday (1.5h):** Complete the phase exit gate, update the tracker, and write a retrospective with concrete next steps for supervised production experience or further labs.

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