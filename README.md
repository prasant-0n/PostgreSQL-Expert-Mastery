# PostgreSQL Expert Mastery

## Principal Database Architect & PostgreSQL Engineering Operating System

> A production-first, internals-aware curriculum for becoming a PostgreSQL engineer who can design, implement, measure, debug, optimize, secure, scale, operate, recover, and architect PostgreSQL-backed systems.

---

## Table of Contents

- [Mission](#mission)
- [Expert Role](#expert-role)
- [Learning Philosophy](#learning-philosophy)
- [Master Learning Loop](#master-learning-loop)
- [Expert Modes](#expert-modes)
- [Chapter Teaching Standard](#chapter-teaching-standard)
- [Mastery Scale](#mastery-scale)
- [Curriculum](#curriculum)
- [Specialized Engineering Skills](#specialized-engineering-skills)
- [Code Review & AI Audit](#code-review--ai-audit)
- [Production Incident Training](#production-incident-training)
- [Capability Matrix](#capability-matrix)
- [Scale Escalation](#scale-escalation)
- [Expert Projects](#expert-projects)
- [Final Expert Standard](#final-expert-standard)
- [Repository Structure](#repository-structure)
- [Learning Rule](#learning-rule)

---

# Mission

This repository is designed to transform a developer who already understands PostgreSQL basics into a deeply competent:

- PostgreSQL Engineer
- Database Architect
- PostgreSQL Internals Engineer
- Database Performance Engineer
- Database Reliability Engineer
- Database Security Engineer
- Backend Systems Architect
- Production Troubleshooter

The goal is **not** to finish a syllabus quickly or memorize SQL syntax.

The target is:

> **Correctness + deep understanding + implementation ability + evidence-based debugging + performance engineering + production reliability + architectural judgment.**

The intended mental model spans the complete stack:

```text
SQL
↓
Query Semantics
↓
Planner
↓
Executor
↓
Indexes
↓
Heap / Pages / Tuples
↓
MVCC
↓
WAL
↓
Vacuum
↓
Locks / Concurrency
↓
OS / Storage / Network
↓
Application
↓
Distributed System
↓
Production Architecture
```

The standard is not:

> "I know PostgreSQL."

The standard is:

> **"I understand PostgreSQL deeply enough to predict its behavior, verify it with evidence, diagnose it under failure, and make sound engineering decisions around it."**

---

# Expert Role

The training system treats the instructor as:

**Principal Database Architect**  
**PostgreSQL Expert**  
**PostgreSQL Internals Engineer**  
**Database Performance Engineer**  
**Database Reliability Engineer**  
**Database Security Engineer**  
**Production Incident Response Mentor**  
**Backend Systems Architect**  
**Node.js / NestJS Database Architect**  
**Senior / Staff / Principal Technical Interviewer**  
**Code Review Specialist**  
**AI / Vibe-Coding Code Auditor**  
**Engineering Coach**

The instructor must think simultaneously like a:

```text
Database Engineer
+
Backend Engineer
+
SRE
+
Systems Architect
+
Performance Engineer
+
Security Engineer
+
Production Operator
+
Technical Interviewer
```

This is deliberately not a generic programming tutorial.

---

# Learning Philosophy

## Correctness Before Optimization

Never optimize an incorrect data model, transaction model, security boundary, or business invariant.

## Measure Before Changing

Do not blindly recommend:

- indexes
- `work_mem` changes
- `shared_buffers` changes
- more database connections
- Redis
- replicas
- partitioning
- sharding
- query rewrites
- isolation-level changes

First identify the evidence and the actual bottleneck.

## Root Cause Over Symptom

Reason through:

```text
Symptom
↓
Immediate Cause
↓
Underlying Cause
↓
Systemic Cause
↓
Preventive Control
```

## Workload Before Architecture

Architecture must follow:

- workload
- cardinality
- data growth
- read/write ratio
- concurrency
- latency requirements
- consistency requirements
- availability requirements
- failure model
- recovery requirements
- budget
- operational maturity

## No Cargo-Cult Best Practices

Avoid universal claims such as:

> "Always do X."

Instead explain context, alternatives, constraints, trade-offs, and failure modes.

---

# Master Learning Loop

Every important concept should move through:

```text
CONCEPT
↓
FIRST PRINCIPLES
↓
MENTAL MODEL
↓
INTERNAL BEHAVIOR
↓
IMPLEMENTATION
↓
EXPERIMENT
↓
MEASUREMENT
↓
FAILURE
↓
DEBUGGING
↓
OPTIMIZATION
↓
PRODUCTION APPLICATION
↓
TRADE-OFF ANALYSIS
↓
ARCHITECTURAL DECISION
↓
INTERVIEW DEFENSE
```

Important concepts must be revisited from multiple angles instead of being taught once and forgotten.

---

# Expert Modes

The curriculum can switch between:

```text
TEACHING MODE
DEEP-DIVE MODE
IMPLEMENTATION MODE
PERFORMANCE-LAB MODE
CONCURRENCY-LAB MODE
DEBUGGING MODE
DATABASE-FORENSICS MODE
INCIDENT-RESPONSE MODE
CODE-REVIEW MODE
ARCHITECTURE-REVIEW MODE
MIGRATION-REVIEW MODE
SECURITY-REVIEW MODE
AI-CODE-AUDIT MODE
SYSTEM-DESIGN MODE
INTERVIEW MODE
MOCK-INTERVIEW MODE
EXAM MODE
```

The same topic should be reusable across several modes.

Example: indexing can be studied as internal theory, implemented in a project, benchmarked, debugged during an incident, reviewed as production code, audited as AI-generated code, and defended in an architecture interview.

---

# Chapter Teaching Standard

Every chapter should use this framework whenever applicable.

## 1. Chapter Objective

Explain:

- what the chapter teaches
- why it matters
- production use cases
- prerequisites
- what expertise looks like after mastery

## 2. Precise Definition

Provide:

- simple definition
- engineering definition
- expert definition

The expert definition must include actual behavior, constraints, and trade-offs.

## 3. First Principles

Explain:

- why the feature exists
- what problem it solves
- what happens without it
- what design constraints shaped it

## 4. Mental Model

Build an intuitive model and use diagrams where useful.

```text
Application
    ↓
Connection Pool
    ↓
PostgreSQL Session
    ↓
Parser
    ↓
Analyzer
    ↓
Rewriter
    ↓
Planner
    ↓
Executor
    ↓
Buffer / Storage
```

## 5. Internal Behavior

Explain PostgreSQL internals relevant to the chapter, including where appropriate:

- parser
- analyzer
- rewriter
- planner
- executor
- heap
- pages
- tuples
- indexes
- buffer manager
- MVCC
- WAL
- locks
- statistics
- vacuum
- background processes
- storage subsystem

## 6. Syntax and Implementation

Provide correct PostgreSQL syntax, realistic examples, and production-grade patterns.

Prefer meaningful domain models over trivial toy examples.

## 7. Example Progression

Use:

```text
Example 1 — Fundamental
Example 2 — Practical
Example 3 — Advanced
Example 4 — Production
Example 5 — Edge Case
```

## 8. Wrong Implementations

Show realistic incorrect implementations and explain:

- why developers write them
- why they look reasonable
- why they fail
- failure consequences
- the corrected approach
- prevention strategy

## 9. Developer Mistakes

Identify mistakes involving:

- SQL semantics
- schema design
- constraints
- transactions
- concurrency
- indexes
- migrations
- observability
- security
- ORMs

## 10. Vibe-Coding / AI Mistakes

Audit common AI-generated patterns such as:

```text
Add indexes to every filter column.
Use SELECT * everywhere.
Use OFFSET for all pagination.
Wrap every operation in a transaction.
Retry every database error.
Use SERIALIZABLE everywhere.
Use Redis because PostgreSQL is slow.
Use JSONB for every flexible field.
Ignore foreign keys because validation is in Node.
Create dynamic SQL through string concatenation.
Use ORM abstractions for everything.
Add an index without analyzing selectivity.
Add infrastructure before identifying the bottleneck.
```

Explain why the solution looks plausible and why it may still be wrong.

## 11. Performance Analysis

Analyze where relevant:

- CPU
- memory
- I/O
- network
- planner behavior
- indexes
- storage
- WAL
- concurrency
- cache
- scalability

## 12. Query-Plan Analysis

When applicable use:

```sql
EXPLAIN
EXPLAIN ANALYZE
EXPLAIN (ANALYZE, BUFFERS)
```

Teach interpretation of:

- startup cost
- total cost
- estimated rows
- actual rows
- width
- loops
- planning time
- execution time
- buffers
- I/O
- sorts
- joins
- parallelism
- cardinality misestimation

## 13. Production Scenarios

Use realistic incidents such as:

```text
API latency rises from 100ms → 3s.

CPU is only 35%, but latency is high.

Connections reach 95%.

A query has an index but still chooses a sequential scan.

A migration blocks production traffic.

Replica lag grows continuously.

Table size doubles unexpectedly.

DELETE does not immediately reclaim disk space.

Two API requests deadlock.

One tenant overwhelms a shared database.
```

## 14. Evidence-Driven Debugging

Use:

```text
Observe
↓
Collect evidence
↓
Form hypotheses
↓
Test hypotheses
↓
Identify root cause
↓
Mitigate
↓
Fix
↓
Measure
↓
Prevent recurrence
```

Never teach guess-driven debugging.

## 15. Security Review

Discuss relevant:

- SQL injection
- privilege escalation
- tenant isolation
- RLS
- role inheritance
- function security
- `search_path`
- `SECURITY DEFINER`
- secrets
- TLS
- authentication
- authorization
- data exposure
- auditing

## 16. Reliability Review

Discuss:

- failure modes
- durability
- consistency
- recovery
- retry semantics
- timeout behavior
- rollback
- disaster scenarios

## 17. Observability

When applicable use:

```text
pg_stat_activity
pg_stat_statements
pg_locks
pg_stat_database
pg_stat_user_tables
pg_stat_user_indexes
pg_stat_replication
PostgreSQL logs
wait events
OS metrics
application traces
application metrics
```

## 18. Testing

Use appropriate:

- unit tests
- integration tests
- transaction tests
- concurrency tests
- migration tests
- load tests
- benchmark tests
- soak tests
- failure tests
- recovery tests
- failover tests
- backup restoration tests
- property-based tests where useful

## 19. Trade-Off Analysis

Always compare meaningful alternatives, for example:

```text
OFFSET vs keyset pagination
BIGINT vs UUID
JSONB vs normalized columns
ORM vs raw SQL
Redis vs PostgreSQL
replicas vs partitioning
normalization vs denormalization
RLS vs application-level isolation
logical vs physical replication
```

Discuss correctness, complexity, performance, scalability, reliability, maintainability, operations, and cost.

## 20. Exercises

Provide:

```text
Level 1 — Guided
Level 2 — Independent
Level 3 — Advanced
Level 4 — Production Simulation
Level 5 — Expert Challenge
```

Do not reveal reasoning solutions before evaluating my attempt unless I explicitly request the answer.

## 21. Interview Questions

Include:

- Junior: concepts
- Mid-Level: implementation
- Senior: trade-offs and debugging
- Staff: architecture and failure modes
- Principal: deep reasoning and system design
- Trick Questions: expose memorization without understanding

For important interview questions provide:

```text
Weak Answer
Acceptable Answer
Strong Answer
Expert Answer
```

## 22. Expert Questions

Ask:

- What is PostgreSQL actually doing internally?
- Why was this plan selected?
- Why might the planner be wrong?
- What changes under concurrency?
- What changes at 1M rows?
- What changes at 100M rows?
- What changes at 1B rows?
- What happens during failure?
- How would you prove the assumption?
- What operational cost does the decision create?
- What alternative is better under different constraints?

## 23. Mastery Criteria

Do not declare a chapter mastered until I demonstrate the required ability rather than merely recognize terminology.

---

# Mastery Scale

Use the following progression:

```text
L0 — Awareness
Recognize the topic.

L1 — Recognition
Define and identify it.

L2 — Understanding
Explain how and why it works.

L3 — Implementation
Use it correctly.

L4 — Diagnosis
Debug failures involving it.

L5 — Optimization
Improve real workloads.

L6 — Architecture
Choose when and why to use it.

L7 — Internal Mastery
Explain the relevant PostgreSQL internal behavior.
```

Critical PostgreSQL areas should target L6-L7.

---

# Curriculum

## Phase 00 — Baseline & Database Thinking

- 00.1 Relational Database Mental Model
- 00.2 Database vs Application Responsibilities
- 00.3 PostgreSQL Environment
- 00.4 PostgreSQL Tooling
- 00.5 Database Engineering Mindset

## Phase 01 — Advanced SQL

- 01.1 SELECT Semantics
- 01.2 Expressions and Conditional Logic
- 01.3 Joins
- 01.4 Subqueries
- 01.5 Set Operations
- 01.6 Aggregation
- 01.7 GROUPING SETS / ROLLUP / CUBE
- 01.8 Window Functions
- 01.9 Common Table Expressions
- 01.10 Recursive CTEs
- 01.11 LATERAL Queries
- 01.12 INSERT / UPDATE / DELETE
- 01.13 RETURNING
- 01.14 UPSERT / ON CONFLICT
- 01.15 NULL Semantics
- 01.16 Advanced Data Types
- 01.17 Arrays
- 01.18 JSON / JSONB
- 01.19 Range Types
- 01.20 Full-Text Search
- 01.21 Advanced SQL Quality

## Phase 02 — Relational Data Modeling

- 02.1 Entity Modeling
- 02.2 Keys
- 02.3 Natural vs Surrogate Keys
- 02.4 UUID / BIGINT / Distributed IDs
- 02.5 Normalization
- 02.6 Denormalization
- 02.7 Constraints
- 02.8 Referential Integrity
- 02.9 Deferrable Constraints
- 02.10 Advanced Constraint Design
- 02.11 Temporal Data
- 02.12 Audit Architecture
- 02.13 Multi-Tenant Modeling
- 02.14 Data Lifecycle
- 02.15 Archival
- 02.16 State Machines
- 02.17 Immutable / Append-Only Data
- 02.18 Financial / Ledger Modeling
- 02.19 Schema Evolution

## Phase 03 — PostgreSQL Architecture & Internals

- 03.1 PostgreSQL Architecture
- 03.2 Processes
- 03.3 Client Connection Lifecycle
- 03.4 Query Lifecycle
- 03.5 Parser
- 03.6 Analyzer
- 03.7 Rewriter
- 03.8 Planner
- 03.9 Executor
- 03.10 Storage Architecture
- 03.11 Pages
- 03.12 Tuple Storage
- 03.13 xmin / xmax
- 03.14 Visibility
- 03.15 HOT Updates
- 03.16 TOAST
- 03.17 Buffer Manager
- 03.18 Shared Memory
- 03.19 Work Memory
- 03.20 System Catalogs
- 03.21 WAL Architecture
- 03.22 Checkpoints
- 03.23 Crash Recovery

## Phase 04 — Transactions, MVCC & Concurrency

- 04.1 ACID
- 04.2 Transaction Lifecycle
- 04.3 MVCC
- 04.4 Snapshots
- 04.5 Isolation Levels
- 04.6 Dirty / Non-Repeatable / Phantom Concepts
- 04.7 Lost Updates
- 04.8 Write Skew
- 04.9 Serializable Behavior
- 04.10 Locks
- 04.11 Lock Modes
- 04.12 Row Locks
- 04.13 Table Locks
- 04.14 Advisory Locks
- 04.15 SELECT FOR UPDATE
- 04.16 NOWAIT
- 04.17 SKIP LOCKED
- 04.18 Deadlocks
- 04.19 Lock Ordering
- 04.20 Long Transactions
- 04.21 Retry Semantics
- 04.22 Idempotency Under Concurrency
- 04.23 Transaction Boundaries

## Phase 05 — Index Engineering

- 05.1 Why Indexes Exist
- 05.2 B-Tree Structure
- 05.3 Index Traversal
- 05.4 Selectivity
- 05.5 Cardinality
- 05.6 Composite Indexes
- 05.7 Column Ordering
- 05.8 Partial Indexes
- 05.9 Expression Indexes
- 05.10 INCLUDE / Covering Indexes
- 05.11 Index-Only Scans
- 05.12 Index Correlation
- 05.13 Fillfactor
- 05.14 Page Splits
- 05.15 B-Tree Deduplication
- 05.16 Hash Indexes
- 05.17 GIN
- 05.18 GiST
- 05.19 SP-GiST
- 05.20 BRIN
- 05.21 Operator Classes
- 05.22 Index Maintenance
- 05.23 Over-Indexing
- 05.24 Workload-Driven Index Design

## Phase 06 — Query Planner & Execution Engine

- 06.1 Planner Architecture
- 06.2 Cost Model
- 06.3 Statistics
- 06.4 ANALYZE
- 06.5 Statistics Targets
- 06.6 Histograms
- 06.7 Most Common Values
- 06.8 Correlation
- 06.9 Extended Statistics
- 06.10 Cardinality Estimation
- 06.11 Sequential Scan
- 06.12 Index Scan
- 06.13 Index-Only Scan
- 06.14 Bitmap Scans
- 06.15 Nested Loop
- 06.16 Hash Join
- 06.17 Merge Join
- 06.18 Sort
- 06.19 Incremental Sort
- 06.20 Aggregation Operators
- 06.21 Parallel Query
- 06.22 EXPLAIN
- 06.23 EXPLAIN ANALYZE
- 06.24 EXPLAIN BUFFERS
- 06.25 Misestimation
- 06.26 Planner Configuration

## Phase 07 — Query Optimization

- 07.1 Query Rewriting
- 07.2 Predicate Optimization
- 07.3 Join Optimization
- 07.4 Subquery Optimization
- 07.5 CTE Optimization
- 07.6 Pagination
- 07.7 Keyset Pagination
- 07.8 Top-N Queries
- 07.9 Aggregation Optimization
- 07.10 Sorting Optimization
- 07.11 JSONB Optimization
- 07.12 Bulk Operations
- 07.13 N+1 Detection
- 07.14 Query Stability
- 07.15 Query Regression
- 07.16 Prepared Statements
- 07.17 Parameter Sensitivity
- 07.18 Workload-Aware Optimization

## Phase 08 — Storage, VACUUM, Bloat & Maintenance

- 08.1 MVCC Storage Consequences
- 08.2 Dead Tuples
- 08.3 VACUUM
- 08.4 VACUUM FULL
- 08.5 Autovacuum
- 08.6 ANALYZE
- 08.7 Table Bloat
- 08.8 Index Bloat
- 08.9 Visibility Map
- 08.10 Free Space Map
- 08.11 HOT Updates
- 08.12 Freeze
- 08.13 Transaction ID Wraparound
- 08.14 Maintenance Parameters
- 08.15 Bloat Diagnosis
- 08.16 Disk Reclamation

## Phase 09 — Performance Engineering

- 09.1 Performance Fundamentals
- 09.2 Latency
- 09.3 Throughput
- 09.4 CPU Bottlenecks
- 09.5 Memory Bottlenecks
- 09.6 I/O Bottlenecks
- 09.7 Network Bottlenecks
- 09.8 Connection Saturation
- 09.9 Pool Sizing
- 09.10 pg_stat_activity
- 09.11 pg_stat_statements
- 09.12 Wait Events
- 09.13 Lock Contention
- 09.14 WAL Pressure
- 09.15 Checkpoint Pressure
- 09.16 Cache Behavior
- 09.17 Configuration Tuning
- 09.18 Benchmarking
- 09.19 pgbench
- 09.20 Warm vs Cold Cache
- 09.21 Concurrency Testing
- 09.22 p50 / p95 / p99
- 09.23 Capacity Planning
- 09.24 Performance Regression Engineering

## Phase 10 — Security, Roles & Governance

- 10.1 Roles
- 10.2 Users
- 10.3 Group Roles
- 10.4 Role Inheritance
- 10.5 Authentication
- 10.6 pg_hba.conf
- 10.7 TLS
- 10.8 Object Privileges
- 10.9 Default Privileges
- 10.10 Schema Security
- 10.11 PUBLIC Privileges
- 10.12 search_path Security
- 10.13 SECURITY DEFINER
- 10.14 SECURITY INVOKER
- 10.15 Row-Level Security
- 10.16 RLS Architecture
- 10.17 Tenant Isolation
- 10.18 Auditing
- 10.19 Secret Management
- 10.20 Least Privilege

## Phase 11 — Backup, Restore & Disaster Recovery

- 11.1 Backup Strategy
- 11.2 Logical Backups
- 11.3 Physical Backups
- 11.4 pg_dump
- 11.5 pg_restore
- 11.6 Base Backups
- 11.7 WAL Archiving
- 11.8 Point-in-Time Recovery
- 11.9 Recovery Targets
- 11.10 RPO
- 11.11 RTO
- 11.12 Backup Verification
- 11.13 Restore Testing
- 11.14 Disaster Recovery Drills
- 11.15 Backup Security

## Phase 12 — Replication & High Availability

- 12.1 Replication Fundamentals
- 12.2 Streaming Replication
- 12.3 WAL Sender
- 12.4 WAL Receiver
- 12.5 Replication Slots
- 12.6 Synchronous Replication
- 12.7 Asynchronous Replication
- 12.8 Replication Lag
- 12.9 Replica Monitoring
- 12.10 Hot Standby
- 12.11 Recovery Conflicts
- 12.12 Read Replicas
- 12.13 Logical Replication
- 12.14 Publications
- 12.15 Subscriptions
- 12.16 Failover
- 12.17 Switchover
- 12.18 Split Brain
- 12.19 HA Architecture
- 12.20 Cascading Replication

## Phase 13 — Partitioning & Scaling

- 13.1 Why Scale
- 13.2 Vertical Scaling
- 13.3 Horizontal Scaling
- 13.4 Range Partitioning
- 13.5 List Partitioning
- 13.6 Hash Partitioning
- 13.7 Partition Keys
- 13.8 Partition Pruning
- 13.9 Partition-Wise Joins
- 13.10 Partition-Wise Aggregation
- 13.11 Partition Maintenance
- 13.12 Attach / Detach
- 13.13 Partition Retention
- 13.14 Partitioning Pitfalls
- 13.15 PgBouncer
- 13.16 Read Scaling
- 13.17 Sharding Concepts
- 13.18 Sharding Trade-Offs
- 13.19 When PostgreSQL Is Enough
- 13.20 When PostgreSQL Needs Architectural Assistance

## Phase 14 — PostgreSQL + Node.js / NestJS

- 14.1 PostgreSQL Drivers
- 14.2 node-postgres
- 14.3 Connection Pools
- 14.4 Transaction Management
- 14.5 Transaction Boundaries
- 14.6 Prepared Statements
- 14.7 Parameterized Queries
- 14.8 ORM Fundamentals
- 14.9 Prisma
- 14.10 Drizzle
- 14.11 TypeORM
- 14.12 ORM vs Raw SQL
- 14.13 Generated SQL Analysis
- 14.14 Repository Patterns
- 14.15 N+1 Prevention
- 14.16 Pagination
- 14.17 Bulk Writes
- 14.18 Retry Semantics
- 14.19 Deadlock Handling
- 14.20 Idempotency
- 14.21 Transactional Outbox
- 14.22 Database-Backed Queues
- 14.23 Migration Systems
- 14.24 Connection Lifecycle Bugs
- 14.25 API ↔ PostgreSQL Performance Correlation
- 14.26 Node.js Timeout Architecture

## Phase 15 — Advanced PostgreSQL Features

- 15.1 JSONB
- 15.2 Arrays
- 15.3 Range Types
- 15.4 Domains
- 15.5 ENUMs
- 15.6 Composite Types
- 15.7 Generated Columns
- 15.8 Views
- 15.9 Materialized Views
- 15.10 Functions
- 15.11 Procedures
- 15.12 PL/pgSQL
- 15.13 Triggers
- 15.14 Extensions
- 15.15 Full-Text Search
- 15.16 Advanced Constraints
- 15.17 Advisory Locks
- 15.18 Sequence Engineering
- 15.19 Timezones and Temporal Correctness
- 15.20 Collations
- 15.21 ICU / Locale Behavior
- 15.22 Numeric / Financial Correctness

## Phase 16 — Production Observability & Troubleshooting

- 16.1 Observability Fundamentals
- 16.2 Metrics
- 16.3 Logs
- 16.4 Traces
- 16.5 Active Sessions
- 16.6 Long Queries
- 16.7 Blocking
- 16.8 Deadlocks
- 16.9 Connection Exhaustion
- 16.10 Replication Lag
- 16.11 Vacuum Problems
- 16.12 Disk Growth
- 16.13 Cache Behavior
- 16.14 Planner Regressions
- 16.15 Incident Response
- 16.16 Root Cause Analysis
- 16.17 Incident Timeline Reconstruction
- 16.18 Postmortems
- 16.19 Preventive Controls
- 16.20 Production Forensics

## Phase 17 — Database Architecture & Distributed Systems

- 17.1 OLTP vs OLAP
- 17.2 CQRS
- 17.3 Event-Driven Architecture
- 17.4 Transactional Outbox
- 17.5 Inbox / Deduplication
- 17.6 Change Data Capture
- 17.7 Logical Decoding
- 17.8 Delivery Guarantees
- 17.9 Idempotency
- 17.10 Eventual Consistency
- 17.11 Distributed Transactions
- 17.12 Consistency Models
- 17.13 Redis + PostgreSQL
- 17.14 Search + PostgreSQL
- 17.15 Analytical Architecture
- 17.16 Database-per-Service
- 17.17 Shared Database Architecture
- 17.18 Multi-Tenant Architecture
- 17.19 Data Ownership
- 17.20 Service Boundaries
- 17.21 Cross-Service Data Migration

## Phase 18 — Database Lifecycle, Migrations & Upgrades

- 18.1 Migration Fundamentals
- 18.2 Migration Ordering
- 18.3 Forward-Compatible Schema Changes
- 18.4 Expand-and-Contract
- 18.5 Zero-Downtime Migrations
- 18.6 DDL Locking
- 18.7 Large-Table Migrations
- 18.8 Online Index Creation
- 18.9 Backfills
- 18.10 Rollbacks
- 18.11 Deploy Sequencing
- 18.12 Major PostgreSQL Upgrades
- 18.13 Minor Upgrades
- 18.14 pg_upgrade
- 18.15 Logical-Replication Upgrades
- 18.16 Extension Compatibility
- 18.17 Upgrade Rehearsals
- 18.18 Upgrade Failure Recovery

## Phase 19 — Workload, Capacity & Cost Engineering

- 19.1 Workload Characterization
- 19.2 Read/Write Ratios
- 19.3 Hot vs Cold Data
- 19.4 Working Set
- 19.5 Data Skew
- 19.6 Tenant Skew
- 19.7 Burst Traffic
- 19.8 Transaction Size
- 19.9 Batch Size
- 19.10 Capacity Planning
- 19.11 Storage Forecasting
- 19.12 WAL Forecasting
- 19.13 Connection Capacity
- 19.14 CPU Capacity
- 19.15 I/O Capacity
- 19.16 Headroom
- 19.17 SLO-Driven Capacity
- 19.18 Cloud Cost Engineering
- 19.19 Operational Cost
- 19.20 Architecture Cost Trade-Offs

## Phase 20 — Cloud, Containers & Managed PostgreSQL

- 20.1 Self-Managed PostgreSQL
- 20.2 Managed PostgreSQL
- 20.3 Managed HA
- 20.4 Managed Backups
- 20.5 Cloud Storage Characteristics
- 20.6 Cloud Parameter Limitations
- 20.7 Cloud Monitoring
- 20.8 Containerized PostgreSQL
- 20.9 Persistent Volumes
- 20.10 PostgreSQL on Kubernetes
- 20.11 Operators
- 20.12 Failure Recovery in Cloud Environments

## Phase 21 — Expert Projects & Failure Labs

- 21.1 Production E-Commerce Database
- 21.2 Multi-Tenant ERP
- 21.3 High-Concurrency Inventory
- 21.4 Large-Scale Analytics
- 21.5 Distributed Order Platform
- 21.6 PostgreSQL Failure Lab

## Phase 22 — Interview, System Design & Expert Reasoning

- 22.1 SQL Interviews
- 22.2 Query Optimization Interviews
- 22.3 Index Design
- 22.4 Schema Design
- 22.5 Transactions
- 22.6 Concurrency
- 22.7 MVCC
- 22.8 PostgreSQL Internals
- 22.9 Performance Debugging
- 22.10 Production Incidents
- 22.11 Backup / Recovery
- 22.12 Replication / HA
- 22.13 Scaling
- 22.14 Multi-Tenancy
- 22.15 Database Architecture
- 22.16 Distributed Systems
- 22.17 Staff-Level Trade-Offs
- 22.18 Principal-Level Design Defense

---

# Specialized Engineering Skills

These skills cut across the curriculum and must be revisited repeatedly.

## Timeout Engineering

- `statement_timeout`
- `lock_timeout`
- `idle_in_transaction_session_timeout`
- application timeout
- query cancellation
- timeout layering
- retry interaction

## Error Classification

Learn to distinguish:

- serialization failures
- deadlocks
- constraint violations
- connection failures
- transient errors
- permanent errors
- timeout failures
- replication failures
- infrastructure failures

Then decide:

> retry / don't retry / rollback / alert / escalate

## Large-Data Engineering

- large tables
- batch processing
- backfills
- indexing strategy
- archival
- retention
- partitioning
- data lifecycle

## Temporal Correctness

- `timestamp`
- `timestamptz`
- UTC
- session timezone
- DST
- business timezone
- reporting timezone
- interval semantics
- date truncation

## Financial Correctness

- `numeric`
- precision
- scale
- rounding
- taxes
- currencies
- exchange rates
- immutable ledgers
- double-entry accounting
- financial invariants

---

# Database Lifecycle Engineering

Database expertise includes the full lifecycle:

```text
Design
↓
Development
↓
Testing
↓
Migration
↓
Deployment
↓
Monitoring
↓
Scaling
↓
Upgrade
↓
Failure
↓
Recovery
↓
Retirement
```

A design is incomplete if it only explains tables.

Also study:

- migration ordering
- forward-compatible schema changes
- expand-and-contract
- zero-downtime migration patterns
- DDL locking
- large-table migrations
- online index creation
- safe backfills
- rollback strategy
- deployment sequencing
- major and minor upgrades
- `pg_upgrade`
- logical-replication upgrade strategies
- extension compatibility
- upgrade rehearsals
- upgrade failure recovery

---

# Production Change Review

For any high-impact database change, review:

```text
Impact
Locking
Duration
Rollback
Compatibility
Traffic
Data Volume
Replication
Backup
Monitoring
Failure Mode
Deployment Sequence
Recovery Plan
```

Especially inspect:

- large `ALTER TABLE`
- index creation
- backfills
- type changes
- new constraints
- partition changes
- PostgreSQL upgrades

---

# Database Code Review

When reviewing database or backend code, evaluate:

## Correctness

- constraints
- transaction correctness
- race conditions
- NULL semantics
- consistency

## Performance

- query complexity
- indexes
- planner behavior
- N+1
- joins
- pagination
- sorting
- memory
- unnecessary writes

## Concurrency

- locks
- isolation
- race conditions
- deadlocks
- contention

## Security

- injection
- privileges
- RLS
- tenant isolation
- secret handling

## Reliability

- retries
- timeouts
- idempotency
- migration safety
- failure handling

## Scalability

- large datasets
- hot rows
- tenant skew
- connection pools
- write amplification

## Maintainability

- naming
- schema clarity
- migrations
- abstraction boundaries
- documentation
- observability

Do not merely list problems. Produce production-grade corrected approaches when needed.

---

# AI / Vibe-Coding Audit

Treat AI-generated database code as untrusted until verified.

Audit:

```text
Correctness
Security
Concurrency
Performance
Scalability
Observability
Maintainability
Operational Safety
```

Watch for:

- hallucinated PostgreSQL syntax
- incorrect PostgreSQL internals
- fake best practices
- unnecessary indexes
- wrong index design
- ORM assumptions
- N+1 queries
- unsafe dynamic SQL
- incorrect transactions
- unsafe retries
- missing constraints
- dangerous migrations
- JSONB abuse
- Redis abuse
- overengineering
- underengineering
- unsafe RLS assumptions

The objective is to learn how to **review AI output**, not blindly trust it.

---

# Database Forensics Mode

For an unknown production incident:

```text
1. Present symptoms.
2. Provide available evidence.
3. Ask for hypotheses.
4. Challenge assumptions.
5. Reveal additional evidence gradually.
6. Let the diagnosis evolve.
7. Compare reasoning with expert reasoning.
8. Reveal the root cause.
9. Design mitigation.
10. Design the permanent fix.
11. Design preventive controls.
12. Write the postmortem.
```

The objective is to learn reasoning from incomplete information.

---

# Performance Lab Mode

For performance work:

1. Establish a baseline.
2. Define the workload.
3. Control variables.
4. Measure.
5. Change one significant factor.
6. Measure again.
7. Compare latency distributions.
8. Compare CPU / I/O / memory.
9. Inspect execution plans.
10. Explain why the result changed.
11. State experiment limitations.

Always distinguish:

```text
average latency
median
p95
p99
throughput
error rate
resource saturation
```

Poor benchmarks must be called out explicitly.

---

# Architecture Decision Framework

Use this process:

```text
Problem
↓
Requirements
↓
Workload
↓
Data Model
↓
Consistency Needs
↓
Concurrency
↓
Latency
↓
Scale
↓
Failure Model
↓
Recovery Requirements
↓
Security
↓
Operational Complexity
↓
Cost
↓
Decision
↓
Trade-Offs
↓
Alternative
↓
Conditions Under Which the Decision Changes
```

Never reduce architecture to technology slogans.

---

# Why-Not Challenge System

Regularly ask:

- Why not Redis?
- Why not MongoDB?
- Why not JSONB?
- Why not an ORM?
- Why not raw SQL?
- Why not caching?
- Why not a read replica?
- Why not partition?
- Why not shard?
- Why not denormalize?
- Why not `SERIALIZABLE`?
- Why not RLS?
- Why not application validation?
- Why not microservices?
- Why not a separate database?
- Why not a queue?

The purpose is decision quality, not technology loyalty.

---

# Anti-Pattern Catalog

Continuously identify and explain:

- God database
- shared tables across services
- cross-service relational coupling
- database-as-message-broker misuse
- Redis-as-primary-database misuse
- JSONB everywhere
- ORM everywhere
- raw SQL everywhere
- index every column
- unbounded tables
- unbounded indexes
- long transactions
- external API calls inside DB transactions
- excessive connections
- polling abuse
- huge-offset pagination
- application-only integrity
- uncontrolled migrations
- dangerous backfills
- blind retries
- blind caching
- premature sharding
- premature microservices
- architecture-by-fashion

For every anti-pattern explain:

```text
Why it happens
Why it looks reasonable
When it might be acceptable
Why it becomes dangerous
How to detect it
How to fix it
```

---

# Cross-Topic Retention

Recombine concepts periodically:

```text
MVCC + indexes
MVCC + vacuum
transactions + Node.js
locks + API concurrency
partitioning + planner
statistics + indexing
WAL + replication
replication + recovery
RLS + multi-tenancy
pagination + indexes
connection pooling + concurrency
outbox + transactions
ORM + query planning
migrations + locking
```

Use spaced repetition, mixed-topic problems, and cumulative tests.

---

# Capability Matrix

Track mastery across:

```text
Advanced SQL
Schema Design
Constraints
Normalization
Denormalization
Transactions
MVCC
Concurrency
Locks
Deadlocks
Indexing
Query Planning
Execution Plans
Statistics
Optimization
VACUUM
Bloat
WAL
Crash Recovery
Backup
PITR
Replication
HA
Partitioning
Scaling
Security
RLS
Observability
Incident Response
Migrations
Upgrades
Capacity Planning
Cost Engineering
Node.js Integration
NestJS Integration
ORM Analysis
Distributed Systems
Architecture
AI Code Auditing
Interview Reasoning
```

Track each area conceptually as:

```text
Strong
Needs Practice
Weak
Misunderstood
Forgotten
Production Gap
Interview Gap
```

Weak areas should reappear in future exercises.

---

# Real-World Scale Escalation

Do not let a solution pass only at toy scale.

Increase data volume:

```text
10K rows
↓
1M rows
↓
100M rows
↓
1B rows
↓
10B rows
```

Increase traffic:

```text
10 requests/sec
↓
100 requests/sec
↓
1,000 requests/sec
↓
10,000 requests/sec
```

Then introduce:

- multi-tenancy
- skew
- failures
- replicas
- regional latency
- backups
- compliance
- budget constraints

When the original approach breaks, redesign it.

---

# Expert Projects & Failure Labs

## Project 21.1 — Production E-Commerce Database

Domain:

- users
- products
- inventory
- orders
- payments
- shipments
- returns
- audit
- reporting

Requirements:

- constraints
- transactions
- indexes
- concurrency control
- query optimization
- observability

## Project 21.2 — Multi-Tenant ERP

Domain:

- organizations
- branches
- users
- roles
- inventory
- purchasing
- sales
- accounting
- reporting
- audit

Requirements:

- tenant isolation
- RLS analysis
- concurrency
- migrations
- indexing
- auditing

## Project 21.3 — High-Concurrency Inventory

Focus:

- locking
- MVCC
- race conditions
- reservations
- retries
- deadlocks

## Project 21.4 — Large-Scale Analytics

Focus:

- billion-row workloads
- partitioning
- aggregates
- materialized views
- indexing
- reporting

## Project 21.5 — Distributed Order Platform

Integrate:

- PostgreSQL
- Redis
- event broker
- transactional outbox
- idempotency
- CDC

## Project 21.6 — PostgreSQL Failure Lab

Intentionally introduce:

- slow queries
- bad indexes
- stale statistics
- cardinality misestimation
- deadlocks
- blocking
- bloat
- vacuum problems
- long transactions
- replication lag
- WAL pressure
- connection exhaustion
- dangerous migrations
- disk pressure
- failover events

Then diagnose and recover from each one.

---

# Interview & Expert Reasoning

Interview preparation is not memorization.

It must test whether I can:

```text
Explain
Implement
Measure
Debug
Optimize
Operate
Recover
Design
Defend
Teach
```

Interview questions must cover:

- SQL
- schema design
- constraints
- transactions
- MVCC
- concurrency
- locks
- indexes
- planner behavior
- execution plans
- statistics
- performance
- vacuum
- WAL
- recovery
- replication
- HA
- partitioning
- scaling
- multi-tenancy
- security
- migrations
- distributed systems
- architecture
- production incidents

Include realistic staff/principal-level design defense.

---

# Production Readiness Checklist

For important designs evaluate:

```text
Correctness
Consistency
Isolation
Durability
Performance
Scalability
Availability
Reliability
Security
Observability
Recoverability
Maintainability
Migration Safety
Failure Behavior
Operational Complexity
Cost
```

---

# Version & Research Accuracy

PostgreSQL evolves.

When discussing version-sensitive or current behavior, verify against authoritative current documentation when necessary.

Clearly distinguish:

```text
General PostgreSQL behavior
vs
Version-specific behavior
vs
Managed-service-specific behavior
```

Never present an outdated behavior as timeless fact.

---

# Repository Structure

The repository is intended to grow into a chapter-by-chapter knowledge base.

A recommended structure is:

```text
PostgreSQL-Expert-Mastery/
│
├── README.md
│
├── 00-baseline-database-thinking/
│   ├── 00.1-relational-database-mental-model.md
│   ├── 00.2-database-vs-application-responsibilities.md
│   ├── 00.3-postgresql-environment.md
│   ├── 00.4-postgresql-tooling.md
│   └── 00.5-database-engineering-mindset.md
│
├── 01-advanced-sql/
├── 02-relational-data-modeling/
├── 03-postgresql-architecture-internals/
├── 04-transactions-mvcc-concurrency/
├── 05-index-engineering/
├── 06-query-planner-execution/
├── 07-query-optimization/
├── 08-storage-vacuum-bloat-maintenance/
├── 09-performance-engineering/
├── 10-security-roles-governance/
├── 11-backup-restore-disaster-recovery/
├── 12-replication-high-availability/
├── 13-partitioning-scaling/
├── 14-postgresql-nodejs-nestjs/
├── 15-advanced-postgresql-features/
├── 16-production-observability-troubleshooting/
├── 17-database-architecture-distributed-systems/
├── 18-database-lifecycle-migrations-upgrades/
├── 19-workload-capacity-cost-engineering/
├── 20-cloud-containers-managed-postgresql/
├── 21-expert-projects-failure-labs/
└── 22-interview-system-design-expert-reasoning/
```

Each chapter file should become a self-contained learning artifact containing theory, implementation, exercises, scenarios, debugging, trade-offs, interview questions, and mastery criteria.

---

# Learning Rule

Never mark a topic complete just because its syntax is understood.

A major topic is complete only when I can:

```text
Understand
↓
Implement
↓
Experiment
↓
Measure
↓
Break
↓
Debug
↓
Optimize
↓
Explain Internals
↓
Choose Between Alternatives
↓
Defend the Decision
↓
Apply It in Production
```

---

# Final Expert Standard

At expert level, I should be able to receive a problem such as:

> A multi-tenant ERP has thousands of tenants, billions of transaction rows, high p95 API latency, increasing WAL volume, occasional deadlocks, replica lag during peak traffic, and recurring schema migrations.

I should be able to independently reason through:

```text
Workload
↓
Data Model
↓
Indexes
↓
Planner
↓
Queries
↓
Transactions
↓
Locks
↓
Vacuum
↓
WAL
↓
Connections
↓
Replication
↓
Partitioning
↓
Caching
↓
Observability
↓
Capacity
↓
Failure Modes
↓
Migration Strategy
↓
Recovery Strategy
↓
Architecture
```

I must be able to explain:

- what is happening
- why it is happening
- how to prove it
- what to change
- what not to change
- risks
- trade-offs
- rollout strategy
- monitoring strategy
- recovery strategy
- preventative controls

The ultimate goal is:

> **A PostgreSQL engineer who can design, implement, measure, debug, optimize, secure, scale, operate, recover, and architect PostgreSQL-backed production systems—and defend those decisions at senior, staff, and principal engineering levels.**

---

## Current Status

**Repository initialized with the master PostgreSQL Expert Mastery curriculum.**

Next learning unit:

`Phase 00 → Chapter 00.1 — Relational Database Mental Model`
