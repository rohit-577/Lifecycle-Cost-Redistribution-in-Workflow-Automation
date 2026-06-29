# Data Schemas

This directory contains schema definitions for the benchmark dataset.

## Raw Trial Data Schema

| Column | Type | Description |
|--------|------|-------------|
| `task` | string (T1–T4) | Task identifier |
| `paradigm` | string (python/n8n/ai) | Implementation paradigm |
| `replication` | integer (1–5) | Trial replication number |
| `IC_s` | float | Implementation Cost (seconds) |
| `MC_s` | float | Maintenance Cost (seconds) |
| `RC_s` | float | Recovery Cost (seconds) |
| `VC_s` | float | Verification Cost (seconds) |
| `TWC_s` | float | Total Workflow Cost = IC + MC + RC + VC (seconds) |
| `LCRI` | float | Lifecycle Cost Redistribution Index = (MC + RC + VC) / TWC × 100% |
| `RCAF` | float | Recovery Cost Amplification Factor = RC(paradigm) / RC(Python) for same task |
| `ICR` | float | Implementation Compression Ratio = IC(Python) / IC(paradigm) for same task |

## Summary Statistics Schema

| Column | Type | Description |
|--------|------|-------------|
| `task` | string (T1–T4) | Task identifier |
| `paradigm` | string (python/n8n/ai) | Implementation paradigm |
| `IC_mean` | float | Mean IC (seconds) |
| `IC_sd` | float | Standard deviation of IC |
| `MC_mean` | float | Mean MC (seconds) |
| `MC_sd` | float | Standard deviation of MC |
| `RC_mean` | float | Mean RC (seconds) |
| `RC_sd` | float | Standard deviation of RC |
| `VC_mean` | float | Mean VC (seconds) |
| `VC_sd` | float | Standard deviation of VC |
| `TWC_mean` | float | Mean TWC (seconds) |
| `TWC_sd` | float | Standard deviation of TWC |
| `LCRI` | float | LCRI computed from means |
| `RCAF` | float | RCAF computed from means |
| `ICR` | float | ICR computed from means |
