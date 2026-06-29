# Replication Limitations

## Known Limitations for Independent Replication

### Platform Dependency

- The original benchmark uses a frozen snapshot of GPT-4 Turbo (gpt-4-turbo-2024-04-09). OpenAI may have updated this model since data collection, potentially affecting AI generation behavior.
- n8n cloud features may have changed since the benchmark was conducted (March 2025). Self-hosted n8n at the corresponding version may improve reproducibility.
- Python 3.11 library versions should be pinned to match the original environment.

### Evaluator Effects

- The original benchmark used a single evaluator with specific proficiency levels: 2 years Python, 18 months n8n, 12 months LLM prompting.
- Replication results may differ based on evaluator expertise.
- The fixed execution order (Code → Visual → AI) may have introduced learning effects that are difficult to reproduce identically.

### Task Specificity

- Failure injection timing and frequencies must match exactly.
- Gold-standard outputs must be produced identically.
- Network conditions during measurement affect API latency.

### Measurement Precision

- Phase transitions in RC measurement require subjective judgment.
- The VC checklist procedure must be applied consistently.
- Automated timestamp logging requires precise instrumentation.

### Reproducibility Boundaries

The following aspects are covered by the original artifact repository but may vary in replication:

1. Exact n8n node configurations
2. Python implementation details (variable names, structure)
3. Prompt formatting and exact wording
4. Failure injection scripts
5. Gold-standard output files

## What Can Be Reliably Reproduced

- The four lifecycle cost metrics and their definitions
- The measurement protocols (IC, MC, RC, VC)
- The recovery four-phase protocol
- The LCRI, RCAF, and ICR formulas
- The statistical treatment (means, SDs)
- The task specifications (inputs, expected outputs, success criteria)

## What Cannot Be Reproduced Exactly

- Absolute timing values (affected by hardware, network, evaluator)
- AI generation outputs (non-deterministic within temperature > 0)
- Exact learning/order effects

See the paper (Section 7) for complete threats to validity.
