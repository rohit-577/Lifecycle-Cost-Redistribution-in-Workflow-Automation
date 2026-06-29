# Benchmark

This directory contains the benchmark definitions, task specifications, metric definitions, and measurement protocols used in the paper.

## Structure

| Directory | Description |
|-----------|-------------|
| `task_definitions/` | Full specifications for T1–T4 |
| `metrics/` | Definitions of IC, MC, RC, VC, TWC, LCRI |
| `protocols/` | Measurement and recovery protocols |

## Overview

The benchmark evaluates three workflow paradigms (Python, n8n, GPT-4 Turbo) across four tasks of escalating coordination demands:

1. **T1: Data Aggregation Pipeline** — Sequential linear data processing
2. **T2: Fault-Tolerant Retry & Fallback** — Error recovery with retry logic
3. **T3: Conditional Decision Workflow** — Nested decision tree branching
4. **T4: Multi-Agent Orchestration** — Parallel execution with Saga compensation

See the paper (Section 4) for complete methodology.
