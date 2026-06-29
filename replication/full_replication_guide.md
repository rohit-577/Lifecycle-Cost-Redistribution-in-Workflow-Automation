# Full Replication Guide

## Overview

This guide provides detailed instructions for independently replicating the complete benchmark. The benchmark measures four lifecycle cost metrics across three paradigms and four tasks.

## Experimental Design

- **Independent variables**: Paradigm (Python, n8n, AI) × Task (T1–T4)
- **Dependent variables**: IC, MC, RC, VC (seconds)
- **Replications**: 5 per cell (60 total trials)
- **Evaluator**: Single (replicating evaluator)

## Before You Begin

1. Read the paper (Section 4: Methodology)
2. Ensure proficiency in Python 3.11, n8n, and LLM prompting
3. Set up measurement infrastructure (timestamp logging)

## Measurement Infrastructure

Use automated timestamp logging at sub-second precision. Record timestamps at:
- Start/end of each metric measurement
- Phase transitions within RC (localization, diagnosis, repair, revalidation)
- Start/end of each replication

## Per-Task Protocol

### T1: Data Aggregation Pipeline

1. Create input CSV with 100 records (10% malformed)
2. Implement in Python (pandas), n8n (CSV + Function + JSON nodes), AI (zero-shot prompt)
3. Measure IC for each paradigm
4. Apply maintenance modifications (Telegram notification, data source change)
5. Measure MC
6. Inject malformed records (10% rate)
7. Measure RC per failure event
8. Verify output against gold standard
9. Measure VC
10. Repeat 5 times

### T2: Fault-Tolerant Retry & Fallback

Follow same structure with retry-and-fallback logic.

### T3: Conditional Decision Workflow

Follow same structure with nested decision tree (4 leaves).

### T4: Multi-Agent Orchestration

Follow same structure with Saga pattern (parallel sub-services, compensation).

## Failure Injection

Apply failures identically across paradigms:
- T1: Malformed records in 10% of rows
- T2: API timeout (t > 5s) in 30% of runs, missing credential in 10%
- T3: Schema mismatch at decision node in 15% of runs
- T4: Random partial failure in 20% of runs

## Data Recording

Record each trial in the format:

```
task,paradigm,replication,IC_s,MC_s,RC_s,VC_s
```

Compute derived metrics:
- TWC = IC + MC + RC + VC
- LCRI = (MC + RC + VC) / TWC × 100%
- RCAF = RC(paradigm) / RC(Python)
- ICR = IC(Python) / IC(paradigm)

## Comparison with Published Results

Compare your means against Table 6. Expected patterns:
- AI IC: 28–42 s (80.9% reduction vs. Python)
- n8n RC at T4: ~102 s (20.4× escalation vs. T1)
- Python RC: 19–23 s across all tasks
- VC: 14–31 s across all conditions
