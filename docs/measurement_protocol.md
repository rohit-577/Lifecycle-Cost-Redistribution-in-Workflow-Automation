# Measurement Protocol

## General Protocol

- Each task executed 5 times per paradigm to account for variability
- Reported values are arithmetic means across executions
- All times measured with sub-second precision using automated timestamps
- For AI-generated workflows: prompt submitted 3 times, median IC recorded, output from median run used for downstream measurements

## Metric-Specific Protocols

### Implementation Cost (IC)

**Start**: Zero-asset starting state with task specification provided.

**Activities**: Planning, typing/node-drag/prompt-writing, debugging first-pass errors, execution.

**End**: First successfully executing workflow producing output.

### Maintenance Cost (MC)

**Start**: Established working asset from IC phase.

**Activities**: Understanding existing implementation, implementing two mandatory changes (Telegram notification, data source provider substitution), re-validating output.

**End**: Both modifications implemented and validated.

### Recovery Cost (RC)

Applied via four-phase protocol (see [recovery_protocol.md](recovery_protocol.md)).

**Failure injection**: Applied identically across paradigms at fixed execution points.

### Verification Cost (VC)

**Procedure**:
1. Compare output structure and values against gold standard
2. Test at least two edge cases (empty input, missing field)
3. Verify type invariants (all IDs non-null, numeric fields positive)

**End**: All checks pass.

See paper Section 4.4.
