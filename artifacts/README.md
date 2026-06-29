# Artifacts

This directory contains the implementation artifacts from the benchmark study.

## Available Artifacts

### Workflow Implementations

| Directory | Paradigm | Status |
|-----------|----------|--------|
| `workflows/python/` | Python 3.11 | Implementations for T1–T4 |
| `workflows/n8n/` | n8n visual | Node configurations for T1–T4 |

### Prompts

| Directory | Description |
|-----------|-------------|
| `prompts/` | Zero-shot GPT-4 Turbo prompts for T1–T4 |

## Unavailable Artifacts

Some artifacts from the original study are hosted at the original benchmark repository:

- **Gold-standard output files**: Available at [https://github.com/rohitr/wab-benchmark](https://github.com/rohitr/wab-benchmark) (commit a3f91e)
- **Failure-injection scripts**: Available at the original repository
- **Raw execution logs**: Available at the original repository
- **Analysis scripts**: Available at the original repository
- **n8n workflow screenshots**: Available at the original repository

## Reproduction Boundaries

The artifacts provided here are reference implementations based on the task specifications in the paper. Exact replication of the original measurements requires:

1. The original benchmark repository (linked above)
2. The same model snapshot (gpt-4-turbo-2024-04-09, temperature=0.2)
3. Comparable evaluator proficiency across all three paradigms
4. Identical failure-injection procedures and timing protocols

## Artifact License

All artifacts in this directory are released under the MIT License unless otherwise noted.
