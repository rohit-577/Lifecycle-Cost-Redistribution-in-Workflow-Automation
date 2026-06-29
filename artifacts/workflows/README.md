# Workflow Implementations

This directory contains the implementation artifacts for all three workflow paradigms across the four benchmark tasks.

## Structure

```
workflows/
├── python/       # Python 3.11 implementations
│   ├── t1_data_pipeline.py
│   ├── t2_retry_fallback.py
│   ├── t3_conditional_decision.py
│   └── t4_saga_orchestration.py
└── n8n/          # n8n workflow JSON
    ├── t1_data_pipeline.json
    ├── t2_retry_fallback.json
    ├── t3_conditional_decision.json
    └── t4_saga_orchestration.json
```

## Implementation Notes

- All workflows implement identical task specifications
- Inputs, expected outputs, and failure scenarios are consistent across paradigms
- Original implementations at [https://github.com/rohitr/wab-benchmark](https://github.com/rohitr/wab-benchmark) (commit a3f91e)

## Python Implementations

- **T1**: Uses pandas for CSV processing and json.dump for export
- **T2**: Uses requests and tenacity for retry with exponential backoff
- **T3**: Uses nested conditional statements for decision routing
- **T4**: Uses asyncio for parallel execution with Saga compensation

## n8n Implementations

- **T1**: Uses CSV node, Function node, and JSON node
- **T2**: Uses HTTP Request node with error trigger routing
- **T3**: Uses Switch and Merge nodes
- **T4**: Uses Merge nodes with dual error trigger branches
