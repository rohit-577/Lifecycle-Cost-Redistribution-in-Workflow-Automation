# Threats to Validity

This document summarizes the principal threats to the study's validity, organized by standard empirical software engineering categories.

## Internal Validity

| Threat | Description | Mitigation |
|--------|-------------|------------|
| Single evaluator | All measurements by one person | Automated timestamp logging; written protocol before experimentation |
| Learning/order effects | Fixed execution order (Code → Visual → AI); fixed task order (T1 → T4) | Not mitigated — arguably the largest methodological weakness |
| Confounded task dimensions | Coordination complexity not isolated from overall task size | Acknowledged design trade-off |
| Measurement reactivity | Evaluator aware of measurement objectives (Hawthorne effect) | Automated timestamp logging partially mitigates |

## Construct Validity

| Threat | Description |
|--------|-------------|
| Time-based metrics | Time captures operational effort, not software quality, defect density, or cognitive load |
| Mono-operation bias | Each metric operationalized through a single measurement procedure |
| Task artificiality | Synthetic tasks may omit real-world features (flaky services, compliance chains) |
| Derived metric validity | LCRI, RCAF, ICR inherit all threats from constituent metrics |

## External Validity

| Threat | Description |
|--------|-------------|
| Platform generalizability | One platform per paradigm (Python, n8n, GPT-4 Turbo) |
| n8n representativeness | n8n-specific limitations may not generalize to other visual builders |
| Task generalizability | Four tasks covering common patterns but not all automation domains |
| Recovery-centric design | Task suite emphasizes failure handling, conditioning RC findings |
| Setting generalizability | Controlled lab setting, not field study |

## Statistical Validity

| Threat | Description |
|--------|-------------|
| Limited sample size | n=4 tasks, 5 replications per cell — insufficient for formal hypothesis testing |
| No significance testing | Exploratory design: emphasis on effect magnitudes and trend consistency |
| Replication requirement | All patterns require independent replication before generalization |

## Ecological & Industrial Validity

| Factor | Description |
|--------|-------------|
| Real-world fidelity | Simplified relative to production workflows |
| Evaluator expertise | Balanced familiarity across paradigms; real teams show wider variance |
| Organizational factors | Team dynamics, code review, CI/CD, monitoring absent from design |

## Conclusion Validity

| Concern | Description |
|---------|-------------|
| Circularity | Tasks and metrics designed around CDH constructs |
| Mono-method bias | All conclusions from single measurement method (time logging) |
| Evaluator expectation | Same researcher formulated hypothesis and conducted measurements |

See the paper (Section 7) for the complete discussion.
