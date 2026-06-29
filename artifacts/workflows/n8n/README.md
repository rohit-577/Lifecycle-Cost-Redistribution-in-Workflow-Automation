# n8n Workflow Implementations

Reference implementations of the four benchmark tasks as n8n workflow JSON configurations.

## Files

| File | Task | Description |
|------|------|-------------|
| `t1_data_pipeline.json` | T1 | CSV processing pipeline (CSV → Function → JSON) |
| `t2_retry_fallback.json` | T2 | HTTP retry with error trigger and fallback routing |
| `t3_conditional_decision.json` | T3 | Switch/Merge conditional decision tree |
| `t4_saga_orchestration.json` | T4 | Merge nodes with dual error trigger branches for Saga |

## Importing

1. Open n8n (cloud or self-hosted)
2. Click "Workflows" → "Import from File"
3. Select the JSON file
4. Configure credentials and endpoints as needed

## Note

These implementations are reference examples based on the paper's task specifications. The exact original n8n configurations used in the benchmark are available at the [original repository](https://github.com/rohitr/wab-benchmark).
