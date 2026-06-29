# Benchmark Design

## Task Suite Overview

| Task | Steps | Category | Coordination Pattern | Failure Model |
|------|-------|----------|---------------------|---------------|
| T1: Data Aggregation Pipeline | 5 | API / Data Chaining | Sequential linear | Malformed input |
| T2: Fault-Tolerant Retry & Fallback | 10 | Error Recovery | Linear with retry branches | API timeout, credential miss |
| T3: Conditional Decision Workflow | 12 | Branching Logic | Nested decision tree | Schema mismatch |
| T4: Multi-Agent Orchestration | 18 | Distributed Orchestration | Parallel join, compensation | Partial failure, race condition |

## Coordination Properties

| Dimension | T1 | T2 | T3 | T4 |
|-----------|----|----|----|----|
| Branch Count | 0 | 1 | 3 | 0 |
| Failure Paths | 1 | 3 | 4 | 4 |
| Parallel Paths | 1 | 1 | 1 | 2 |
| State Sync Points | 0 | 0 | 0 | 2 |
| Compensation Logic | 0 | 0 | 0 | 2 |

## Paradigm Comparison

All three paradigms implement identical task specifications. The benchmark isolates the effect of abstraction from confounding differences in problem definition.

## Metric Framework

Four time-based metrics (IC, MC, RC, VC) compose the Total Workflow Cost (TWC). The Lifecycle Cost Redistribution Index (LCRI) summarizes post-implementation cost proportion.

See the paper (Sections 3–4) for complete details.
