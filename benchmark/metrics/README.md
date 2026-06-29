# Metrics

This directory documents the lifecycle cost metrics used in the benchmark.

## Primary Metrics

All metrics are measured in seconds with sub-second precision using automated timestamps.

### Implementation Cost (IC)

Time to author, configure, and achieve a first successfully executing workflow from a zero-asset starting state.

**Included**: Planning, typing/node-drag/prompt-writing, debugging first-pass errors, execution.
**Excluded**: Reading spec, specification design, gold-standard creation, documentation writing.

### Maintenance Cost (MC)

Cumulative time to implement mandatory system modifications on the established asset.

**Modifications**: (1) Add Telegram notification step, (2) Replace data source provider.
**Included**: Understanding existing implementation, implementing two mandatory changes, re-validating output.
**Excluded**: Change-requirement design, parallel modification exploration.

### Recovery Cost (RC)

Total diagnostic and correction time to restore active workflow execution after each injected failure.

**Sub-phases**: Failure localization, root cause diagnosis, repair implementation, revalidation.
**Included**: Failure detection, diagnosis, repair implementation, revalidation.
**Excluded**: Root-cause analysis outside the workflow, system-level debugging.

### Verification Cost (VC)

Time spent validating output correctness against the gold standard, including edge-case testing and assertion of data-type invariants.

**Procedure**: (1) Compare output structure and values against gold standard, (2) Test ≥2 edge cases (empty input, missing field), (3) Verify type invariants.
**Included**: Output inspection, edge-case testing, gold-standard comparison.
**Excluded**: Test-suite creation, formal verification.

### Total Workflow Cost (TWC)

TWC = IC + MC + RC + VC

## Derived Metrics

### Lifecycle Cost Redistribution Index (LCRI)

LCRI = (MC + RC + VC) / TWC × 100%

Captures the fraction of total lifecycle cost that occurs after initial implementation.

### Recovery Cost Amplification Factor (RCAF)

RCAF(paradigm, task) = RC(paradigm, task) / RC(Code, task)

Measures how many times more recovery cost a non-code paradigm incurs relative to code.

### Implementation Compression Ratio (ICR)

ICR(paradigm, task) = IC(Code, task) / IC(paradigm, task)

Quantifies the upfront speed advantage of higher abstraction.

See paper Section 4.3 and 4.5 for complete details.
