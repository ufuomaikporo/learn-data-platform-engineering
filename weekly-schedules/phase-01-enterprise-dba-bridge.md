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

Choose only the course sections relevant to the week's outcome. Course recommendations and links are in [02 — Courses and reading](../02-courses-and-reading.md). Course availability, versions, labs, and subscription inclusion change; verify before enrolling. Use the [Phase 1 free resource map](../labs/phase-01-enterprise-dba-bridge.md#free-resource-map) to select local, hosted, or tabletop options. Avoid incurring cloud charges without a budget, and do not download or use licensed software outside its terms.

Step-by-step procedures for Phase 1 tasks, labs, guided exercises, and tabletops are in the [Phase 1 Lab Workbook](../labs/phase-01-enterprise-dba-bridge.md). This schedule retains the weekly time blocks, course sections, and task outcomes.

## Course and walkthrough map

Use about **1–2 hours of course/video material per week**; these courses are longer than the schedule, so watch only the sections that support that week's lab. Complete the project work in the daily plan rather than watching an entire course. Course ratings, curriculum, and subscription access can change.

| Week | Guided course or walkthrough | Apply it to |
|---|---|---|
| 1 | [Complete Microsoft SQL Server Database Administration Course](https://www.udemy.com/course/complete-microsoft-sql-server-database-administration-course/) — cover `Introduction` (database/RDBMS/SQL Server overview); selected topics from `Microsoft SQL Database Administration and System databases` (management tools, SSMS, system databases); `MSSQL User Management` (authentication, roles, permissions); and `SQL Server Agent` (alerts, Activity Monitor). | Build the four-platform inventory and compare operations responsibilities. |
| 2 | [Oracle Database 19c Backup and Recovery](https://www.udemy.com/course/oracle-database-backup-and-recovery/) — listing covers 12c, 19c, and 23ai. Select from `Backup and Recovery Overview`, `Backup and Recovery Configuration`, `Recovery Manager (RMAN)`, `Creating Database Backups`, `Monitoring an RMAN Backup`, `Recovery Catalog`, and `Managing Target Database Using Recovery Catalog`; use the course's recovery demonstrations that match the lab version. | Perform or trace a single-instance RMAN recovery and write the runbook. Match commands to the lab version and verify current course coverage. |
| 3 | [Oracle Grid Infrastructure and RAC using Oracle Database 19c](https://www.udemy.com/course/oracle-rac-and-grid-infrastructure-concepts/) — select `Introduction / Concepts Overview`, `Introduction to Grid Infrastructure 19c`, `Setup Shared Storage`, `Install Grid Infrastructure - 2 Nodes`, `Explore Grid Infrastructure`, and `Introduction to RAC`. [Oracle Database Data Guard Administration (12c and 19c)](https://www.udemy.com/course/oracle-12c-data-guard-administration/) — select `Introduction to Oracle Data Guard`, `Implementing Oracle Data Guard using SQL*Plus`, `Oracle Data Guard Broker`, `Managing Physical and Logical Standby Databases`, and `Perform Role Transitions`. For bounded ExaCC/OCI orientation, use `Oracle Cloud Infrastructure (Gen2 Cloud)` and `Database Cloud Services` in [Foundation to Oracle Database in OCI](https://www.udemy.com/course/foundation-to-oracle-database-in-oracle-cloud-infrastructure/), including its ExaCC lecture. | Draw RAC/Data Guard failure flows; complete a guided HA lab if authorized, otherwise a labeled tabletop. Treat OCI/ExaCC as orientation only. |
| 4 | [SQL Server 2025: Build Always On HA & DR Solutions](https://www.udemy.com/course/sqlserverag/) — cover `Introduction to SQL Server 2025 Always On`, selected setup lessons from `Essential SQL Server 2025 Always On High Availability Solution - Up and Running`, plus `Monitoring` and `Backup and Restore`. Cross-check prerequisites with Microsoft's [Availability Group tutorial](https://learn.microsoft.com/en-us/sql/database-engine/availability-groups/windows/availability-group-tutorial-prerequisites?view=sql-server-ver17). | Build or tabletop a two-replica AG, planned failover, application verification, and rollback. |
| 5 | [Introduction to Azure SQL Database for Beginners](https://www.udemy.com/course/introduction-to-azure-sql-database/) — cover `Introducing the Azure Portal`, `Creating your First Azure SQL Database`, `Accessing Azure SQL Database`, and selected tasks from `Managing your Azure SQL Database Server` and `Managing your Azure SQL Database`. Use official docs for Managed Instance and SQL Server on Azure VMs. | Use the Azure SQL free tier with AutoPause and verified free-limit settings if eligible; otherwise complete the service-selection and migration exercise on paper. |
| 6 | [DB2 For Beginners](https://www.udemy.com/course/db2-for-beginners/) — cover `DB2 Database Server Setup` and selected topics from `Performing CRUD Operations and Data Manipulation`. For the guided application build, use [Python and DB2 App Development: Build a CRUD Application](https://www.udemy.com/course/python-and-db2-app-development-build-a-crud-application/): `IBM DB2 Setup`, `Building CRUD App: Part 1: Building the user interface`, and `Building CRUD App: Part 2: Python and DB2 Interaction`. | Create or trace a Db2 CRUD workflow and map backup, monitoring, and recovery tasks. The CRUD course has a small review base; verify its lab setup before investing time. |
| 7 | [Oracle Database Performance Tuning](https://www.udemy.com/course/oracle-database-performance-tuning/) — select `Introduction to Oracle Database Performance Tuning`, `Using Time Model`, `Wait Events`, `Using AWR`, and `Metrics, Event Histograms and Server-generated Alerts`. [SQL Server Performance Tuning Part 1](https://www.udemy.com/course/sql-server-performance-tuning-part-1/) — select `INDEXES`, `STATISTICS`, `What is blocking?`, `DEADLOCKS`, and `WAIT STATISTICS`; this course is older, so cross-check version-specific steps with current docs. | Analyze a reproducible query/performance scenario, then write the capacity worksheet, monitoring map, automation check, and RCA. |
| 8 | No new course. Choose the weakest skill and revisit its mapped sections: RMAN `Recovery Manager (RMAN)` and the restore/recovery demonstrations; RAC `Explore Grid Infrastructure` or Data Guard `Perform Role Transitions`; Always On `Monitoring` and `Backup and Restore`; Azure SQL `Managing your Azure SQL Database`; Db2 `Performing CRUD Operations and Data Manipulation`; Oracle tuning `Wait Events`/`Using AWR`; or SQL Server tuning `STATISTICS`/`WAIT STATISTICS`. | Run the integrated tabletop, finalize runbooks and the technical briefing, and record remaining experience gaps. |

## Week 1 — Enterprise DBA operations baseline

**Goal:** Map the four database platforms and establish an honest, evidence-based baseline.

- [ ] **Monday (1h):** Complete the Phase 1 baseline using the [Week 1 workbook procedure](../labs/phase-01-enterprise-dba-bridge.md#baseline-self-assessment). Use the remaining 45 minutes to start the linked SQL Server DBA course's introductory administration and monitoring sections.
- [ ] **Tuesday (1h):** Sketch the database service path using the [Week 1 workbook procedure](../labs/phase-01-enterprise-dba-bridge.md#database-service-path-sketch).
- [ ] **Thursday (1.5h):** Review Windows/Linux service, process, storage, permissions, and log basics; draft the incident/change handoff using the [Week 1 workbook procedure](../labs/phase-01-enterprise-dba-bridge.md#windowslinux-and-incidentchange-workflow).
- [ ] **Saturday (3h):** Build the four-platform inventory and comparison matrix using the [Week 1 workbook procedure](../labs/phase-01-enterprise-dba-bridge.md#four-platform-inventory-and-comparison-matrix). Use work/project evidence and official documentation; do not infer experience.
- [ ] **Sunday (1.5h):** Reconcile baseline scores and finish the operations workflow using the [Week 1 workbook procedure](../labs/phase-01-enterprise-dba-bridge.md#baseline-and-workflow-review).

**Deliverables:** Platform comparison, skills baseline, incident/change workflow.  
**Self-check:** Can you describe what you have actually operated, what you have only studied, and the path an application request takes to each database?

## Week 2 — Oracle administration, monitoring, and recovery

**Goal:** Strengthen Oracle operational foundations and demonstrate a bounded recovery workflow.

- [ ] **Monday (1h):** Study Oracle instance/database architecture, CDB/PDB concepts, services, listener connectivity, and basic operational views.
- [ ] **Tuesday (1h):** Complete the [Oracle state inspection exercise](../labs/phase-01-enterprise-dba-bridge.md#oracle-state-inspection). Capture sanitized evidence or label the work documentation-only if no lab is available.
- [ ] **Thursday (1.5h):** Study OEM/OMS monitoring, alert triage, patching lifecycle, and RMAN backup validation; compare signals using the [Week 2 monitoring procedure](../labs/phase-01-enterprise-dba-bridge.md#monitoring-signal-comparison).
- [ ] **Saturday (3h):** Complete the [single-instance RMAN recovery lab](../labs/phase-01-enterprise-dba-bridge.md#single-instance-rman-recovery) in an authorized environment, or use its tabletop alternative. Do not describe this as RAC or ExaCC recovery.
- [ ] **Sunday (1.5h):** Write the Oracle backup/recovery runbook using the [Week 2 workbook procedure](../labs/phase-01-enterprise-dba-bridge.md#oracle-backuprecovery-runbook).

**Deliverables:** Lab record and Oracle recovery runbook.  
**Self-check:** Can you explain what was actually restored, how you verified it, and which production safeguards were not represented in the lab?

## Week 3 — Oracle HA and bounded ExaCC orientation

**Goal:** Understand Oracle HA choices and ExaCC responsibility boundaries without making engineered systems the center of the phase.

- [ ] **Monday (1h):** Study Grid Infrastructure, RAC, ASM, and Data Guard purposes, then create the glossary using the [Week 3 workbook procedure](../labs/phase-01-enterprise-dba-bridge.md#oracle-ha-glossary).
- [ ] **Tuesday (1h):** Draw RAC/ASM and Data Guard failure domains using the [Week 3 Oracle HA guide](../labs/phase-01-enterprise-dba-bridge.md#week-3-oracle-ha-and-exacc-boundaries). Label paths as conceptual, observed, or lab-tested.
- [ ] **Thursday (1.5h):** Watch the selected OCI/ExaCC and GoldenGate course sections; complete the architecture and provider/customer responsibility diagram using the [Week 3 workbook procedure](../labs/phase-01-enterprise-dba-bridge.md#ociexacc-responsibility-diagram).
- [ ] **Saturday (3h):** Complete one authorized RAC or Data Guard walkthrough, or follow the [Week 3 tabletop](../labs/phase-01-enterprise-dba-bridge.md#week-3-oracle-ha-and-exacc-boundaries) if no lab is available.
- [ ] **Sunday (1.5h):** Create the Oracle HA decision tree and ExaCC boundary diagram using the [Week 3 workbook procedure](../labs/phase-01-enterprise-dba-bridge.md#oracle-ha-decision-tree-and-exacc-boundary-diagram).

**Deliverables:** Oracle HA decision tree, bounded ExaCC/OCI brief, and tested-or-tabletop evidence.  
**Self-check:** Can you distinguish RAC availability from Data Guard disaster recovery and explain who operates which ExaCC components?

## Week 4 — SQL Server HA/DR and performance

**Goal:** Build practical SQL Server availability, backup/recovery, and performance fundamentals used in enterprise DBA roles.

- [ ] **Monday (1h):** Study Always On Availability Groups: replicas, synchronous/asynchronous commit, failover modes, quorum, listeners, and availability databases.
- [ ] **Tuesday (1h):** Study SQL Server backup types, restore sequences, recovery models, log shipping/mirroring context, and RPO/RTO trade-offs; build the [restore decision checklist](../labs/phase-01-enterprise-dba-bridge.md#restore-decision-checklist).
- [ ] **Thursday (1.5h):** Study AG health signals, wait statistics/query plans, capacity indicators, and common failover constraints. Use official documentation or course sections linked in the course guide.
- [ ] **Saturday (3h):** Complete the [Always On failover lab](../labs/phase-01-enterprise-dba-bridge.md#week-4-sql-server-recovery-and-always-on) only in an authorized lab; otherwise use its tabletop alternative.
- [ ] **Sunday (1.5h):** Write the Always On operations runbook using the [Week 4 workbook procedure](../labs/phase-01-enterprise-dba-bridge.md#always-on-operations-runbook).

**Deliverables:** Always On failover runbook, recovery checklist, and lab/tabletop record.  
**Self-check:** Can you explain the failover mode, quorum implications, expected data-loss boundary, and how you prove the application recovered?

## Week 5 — Azure SQL and modernization

**Goal:** Compare Azure SQL service models and make a supportable migration choice.

- [ ] **Monday (1h):** Compare Azure SQL Database, Managed Instance, and SQL Server on Azure VMs using the [Week 5 service-comparison procedure](../labs/phase-01-enterprise-dba-bridge.md#azure-sql-service-comparison-and-migration-decision).
- [ ] **Tuesday (1h):** Map identity, network connectivity, private access, permissions, encryption, and least privilege using the [Week 5 identity/network procedure](../labs/phase-01-enterprise-dba-bridge.md#azure-sql-identity-and-network-map).
- [ ] **Thursday (1.5h):** Study Azure monitoring, performance diagnostics, backup/restore options, maintenance boundaries, and migration assessment. Use official documentation; avoid creating billable resources without an approved budget.
- [ ] **Saturday (3h):** Complete the [Azure SQL service-selection and migration exercise](../labs/phase-01-enterprise-dba-bridge.md#week-5-azure-sql-service-selection). Use a paper exercise unless you have an authorized, cost-controlled subscription.
- [ ] **Sunday (1.5h):** Produce the one-page architecture decision record using the [Week 5 workbook procedure](../labs/phase-01-enterprise-dba-bridge.md#azure-sql-architecture-decision-record).

**Deliverables:** Azure SQL service comparison, migration/cutover plan, and decision record.  
**Self-check:** Can you justify PaaS vs IaaS for the workload and explain the operational tasks that shift to Microsoft versus remain with the team?

## Week 6 — Db2 and cross-platform operations

**Goal:** Build useful Db2 literacy while being explicit about the limits of a short orientation.

- [ ] **Monday (1h):** Study Db2 architecture, instances, databases, storage, logs, client connectivity, and core terminology.
- [ ] **Tuesday (1h):** Complete the [Db2 capability comparison](../labs/phase-01-enterprise-dba-bridge.md#db2-capability-comparison) using IBM documentation.
- [ ] **Thursday (1.5h):** Follow the [Db2 setup guided lab](../labs/phase-01-enterprise-dba-bridge.md#db2-setup-and-crud-walkthrough) if available; otherwise trace the documentation-only recovery scenario.
- [ ] **Saturday (3h):** Follow the Db2 setup/CRUD walkthrough or its documented fallback in the [Week 6 lab guide](../labs/phase-01-enterprise-dba-bridge.md#db2-setup-and-crud-walkthrough). Keep setup troubleshooting to 30 minutes and record blockers.
- [ ] **Sunday (1.5h):** Write the Db2 operations primer using the [Week 6 workbook procedure](../labs/phase-01-enterprise-dba-bridge.md#db2-operations-primer).

**Deliverables:** Db2 comparison and operations primer.  
**Self-check:** Can you navigate Db2 terminology and identify the correct documentation or owner without claiming independent administration experience?

## Week 7 — Performance, security, automation, and RCA

**Goal:** Apply portable DBA practices across platforms and create reusable operational evidence.

- [ ] **Monday (1h):** Study query-plan and workload signals for Oracle and SQL Server; distinguish symptoms, bottlenecks, and capacity constraints.
- [ ] **Tuesday (1h):** Build the capacity worksheet using the [Week 7 workbook procedure](../labs/phase-01-enterprise-dba-bridge.md#capacity-worksheet).
- [ ] **Thursday (1.5h):** Review least privilege, auditing, vulnerability remediation, monitoring/diagnostic tools, and safe change practices; create the map using the [Week 7 workbook procedure](../labs/phase-01-enterprise-dba-bridge.md#monitoring-and-security-control-map).
- [ ] **Saturday (3h):** Complete the [read-only health check and RCA exercise](../labs/phase-01-enterprise-dba-bridge.md#week-7-performance-monitoring-automation-and-rca) using synthetic or authorized data.
- [ ] **Sunday (1.5h):** Write the operational standard and RCA report using the [Week 7 workbook procedure](../labs/phase-01-enterprise-dba-bridge.md#operational-standard-and-rca-report).

**Deliverables:** Capacity worksheet, read-only automation, monitoring/security map, RCA and corrective-action record.  
**Self-check:** Can you support each conclusion with measured or cited evidence and separate a contributing factor from the root cause?

## Week 8 — Integrated operations and technical leadership

**Goal:** Combine technical breadth into a credible enterprise operations pack.

- [ ] **Monday (1h):** Review the skills matrix and rank remaining gaps using the [Week 8 workbook procedure](../labs/phase-01-enterprise-dba-bridge.md#gap-ranking).
- [ ] **Tuesday (1h):** Draft the cross-platform HA/DR decision matrix using the [Week 8 workbook procedure](../labs/phase-01-enterprise-dba-bridge.md#cross-platform-hadr-decision-matrix).
- [ ] **Thursday (1.5h):** Prepare the change/migration plan and escalation scenario using the [Week 8 tabletop guide](../labs/phase-01-enterprise-dba-bridge.md#week-8-integrated-incident-tabletop).
- [ ] **Saturday (3h):** Run the [90-minute integrated incident/recovery tabletop](../labs/phase-01-enterprise-dba-bridge.md#week-8-integrated-incident-tabletop), then finalize the operations pack. Treat mentorship as a scenario, not a claimed outcome.
- [ ] **Sunday (1.5h):** Complete the phase exit gate and retrospective using the [Week 8 workbook procedure](../labs/phase-01-enterprise-dba-bridge.md#phase-retrospective).

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