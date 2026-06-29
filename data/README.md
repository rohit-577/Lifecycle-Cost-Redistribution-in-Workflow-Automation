# Benchmark Data

This directory contains the experimental dataset from the paper.

## Structure

| Directory | Description |
|-----------|-------------|
| `published/` | Published benchmark tables from the paper (CSV) |
| `processed/` | Cleaned, analysis-ready measurement data |
| `schemas/` | Data schemas and column definitions |

## Dataset Overview

The raw dataset consists of 60 trials (4 tasks × 3 paradigms × 5 replications). Each trial records four time-based metrics in seconds:

- **IC** — Implementation Cost
- **MC** — Maintenance Cost
- **RC** — Recovery Cost
- **VC** — Verification Cost
- **TWC** — Total Workflow Cost (IC + MC + RC + VC)

Derived metrics are computed from these base measurements:

- **LCRI** — Lifecycle Cost Redistribution Index = (MC + RC + VC) / TWC × 100%
- **RCAF** — Recovery Cost Amplification Factor = RC(paradigm) / RC(code)
- **ICR** — Implementation Compression Ratio = IC(code) / IC(paradigm)

## Data Sources

All data are transcribed directly from the published paper (Table 6 and Table 10). The original per-trial raw data with gold-standard outputs and analysis scripts are available at:

[https://github.com/rohitr/wab-benchmark](https://github.com/rohitr/wab-benchmark) (commit a3f91e)
