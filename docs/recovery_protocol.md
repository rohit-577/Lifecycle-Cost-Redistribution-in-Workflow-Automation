# Recovery Protocol

## Four-Phase Recovery Timing Protocol

Recovery Cost (RC) was measured according to a fixed four-phase protocol applied identically across all paradigms.

### Phase 1: Failure Localization

**Start**: Clock starts at failure detection — the evaluator observes the workflow has not produced the expected output within the expected time, or an error signal is received.

**End**: The evaluator identifies the specific step or node where the failure originated.

### Phase 2: Root Cause Diagnosis

**Start**: Immediately after localization.

**End**: The evaluator determines why the failure occurred (e.g., missing API key, schema mismatch, race condition).

### Phase 3: Repair Implementation

**Start**: Immediately after diagnosis.

**End**: The evaluator deploys a modification intended to resolve the failure.

### Phase 4: Revalidation

**Start**: Immediately after repair.

**End**: The workflow produces the correct output for the same input that previously triggered the failure. Clock stops at revalidation completion.

## Protocol Details

- Protocol defined before experimentation
- Timing recorded via automated timestamps
- Evaluator discretion limited to identifying phase transitions
- Applied identically across all three paradigms

## RC Sub-Phase Distribution at T4

| Paradigm | Localization | Diagnosis | Repair | Revalidation | Total |
|----------|-------------|-----------|--------|-------------|-------|
| Python | 6 s | 6 s | 6 s | 5 s | 23 s |
| n8n | 12 s | 48 s | 22 s | 20 s | 102 s |
| AI | 8 s | 30 s | 28 s | 22 s | 88 s |

See paper Section 4.4 and 5.4.
