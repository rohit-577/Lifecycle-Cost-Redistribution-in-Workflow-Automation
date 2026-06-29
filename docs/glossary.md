# Glossary

## Primary Metrics

| Term | Definition |
|------|------------|
| **IC** | **Implementation Cost** — Elapsed time to author, configure, and achieve a first successfully executing workflow from a zero-asset starting state. |
| **MC** | **Maintenance Cost** — Cumulative time to implement mandatory system modifications on an established workflow asset. |
| **RC** | **Recovery Cost** — Total diagnostic and correction time to restore active workflow execution after an injected failure. Decomposed into localization, diagnosis, repair, and revalidation sub-phases. |
| **VC** | **Verification Cost** — Time spent validating output correctness against a gold standard, including edge-case testing and type-invariant assertion. |
| **TWC** | **Total Workflow Cost** — Sum of IC + MC + RC + VC for a given task-paradigm combination. |

## Derived Metrics

| Term | Definition |
|------|------------|
| **LCRI** | **Lifecycle Cost Redistribution Index** — The fraction of total lifecycle cost occurring after initial implementation: (MC + RC + VC) / TWC × 100%. A descriptive summary metric for cross-paradigm comparison. |
| **RCAF** | **Recovery Cost Amplification Factor** — RC(paradigm) / RC(Code) for the same task. Measures how many times more recovery cost a non-code paradigm incurs relative to code. |
| **ICR** | **Implementation Compression Ratio** — IC(Code) / IC(paradigm). Quantifies the upfront speed advantage of higher abstraction. |
| **ACR** | **Abstraction Compression Ratio** — TWC(P1) / TWC(P2) where P1 is a lower-abstraction paradigm and P2 is higher-abstraction. Used in the Abstraction Compression Effect. |
| **COS** | **Coordination Ordering Score** — An ordinal ranking mechanism derived from coordination property counts, used solely to enforce task ordering rather than as an empirical measurement instrument. |

## Theoretical Constructs

| Term | Definition |
|------|------------|
| **CDH** | **Complexity Displacement Hypothesis** — An interpretive framework proposing that increasing abstraction does not eliminate engineering effort but displaces it across lifecycle phases. Lower-abstraction paradigms concentrate cost in implementation; higher-abstraction paradigms defer it to maintenance, recovery, and verification. |
| **ACE** | **Abstraction Compression Effect** — A secondary prediction derived from CDH: the total lifecycle cost differential between paradigms narrows as coordination demands increase, because deferred downstream costs accumulate for higher-abstraction paradigms. |

## Other

| Term | Definition |
|------|------------|
| **Saga Pattern** | A distributed transaction pattern where each step has a compensating action for rollback. Used in T4 (Multi-Agent Orchestration). |
| **Zero-Shot Prompt** | A single natural-language prompt submitted to an LLM without examples, system prompts, or multi-turn refinement. The benchmark evaluates first-pass generation efficiency. |
