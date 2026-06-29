# Python Workflow Implementations

Reference implementations of the four benchmark tasks in Python 3.11.

## Files

| File | Task | Description |
|------|------|-------------|
| `t1_data_pipeline.py` | T1 | Data aggregation pipeline with pandas |
| `t2_retry_fallback.py` | T2 | Fault-tolerant retry with exponential backoff |
| `t3_conditional_decision.py` | T3 | Nested conditional decision tree |
| `t4_saga_orchestration.py` | T4 | Multi-agent Saga orchestration with asyncio |

## Dependencies

- requests>=2.31.0
- pandas>=2.1.0
- tenacity>=8.2.0

## Usage

```bash
python t1_data_pipeline.py --input input.csv --output output.json
python t2_retry_fallback.py --primary https://api.example.com/primary --backup https://api.example.com/backup
python t3_conditional_decision.py --input payload.json
python t4_saga_orchestration.py --input order.json
```

## Note

These implementations are reference examples based on the paper's task specifications. The exact original implementations used in the benchmark are available at the [original repository](https://github.com/rohitr/wab-benchmark).
