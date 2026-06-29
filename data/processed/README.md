# Processed Data

This directory contains cleaned, analysis-ready measurement data derived from the published tables.

## Contents

- `benchmark_results_clean.csv` — All 60 trials with computed derived metrics (LCRI, RCAF, ICR)
- `summary_statistics.csv` — Aggregate statistics by task and paradigm

## Derived Metric Formulas

- **LCRI** = (MC + RC + VC) / TWC × 100%
- **RCAF** = RC(paradigm) / RC(Python) for the same task
- **ICR** = IC(Python) / IC(paradigm) for the same task
- **TWC** = IC + MC + RC + VC

## Origin

Source data is from Table 10 of the paper (per-trial raw measurements).
