# Methodology

## Overview

This document describes the experimental methodology used in the benchmark study. See the paper (Section 4) for the complete description.

## Benchmark Design

Four tasks were designed spanning increasing levels of coordination demands. Each task was implemented independently in three paradigms (Python, n8n, GPT-4 Turbo), and all implementations were evaluated on identical inputs, expected outputs, and failure scenarios.

### Workflow Paradigms

**Code-Based (Python)**:
- Python 3.11 with requests (HTTP), pandas (data processing), asyncio (concurrency for T4)
- Explicit exception handling for error recovery

**Visual Workflow (n8n)**:
- n8n cloud platform with HTTP Request, CSV, Function, IF, Switch, Merge, Split nodes
- Error handling via Error Trigger and Try/Catch nodes

**AI-Generated (LLM Prompt)**:
- Frozen zero-shot prompt submitted to GPT-4 Turbo (gpt-4-turbo-2024-04-09)
- Temperature=0.2, max_tokens=4096, no system prompt
- Generated output executed without modification

### Statistical Treatment

- Each task executed 5 times per paradigm
- Arithmetic means reported; standard deviations for within-condition variability
- 95% descriptive interval widths as precision-of-measurement indicators
- Cohen's d as descriptive effect-size indicators
- No formal significance testing (exploratory design)

### Design Limitations

- Single evaluator conducted all measurements
- Fixed execution order (Code → Visual → AI) — no randomization
- Fixed task order (T1 → T4) — no crossover
- Four tasks, one model per paradigm

See the paper (Sections 4.6, 4.7) and [threats_to_validity.md](threats_to_validity.md) for complete discussion.
