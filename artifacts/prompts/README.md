# LLM Prompts

This directory contains the zero-shot prompts used for AI-generated workflows in the benchmark.

## Prompts

| File | Task | Description |
|------|------|-------------|
| `t1_prompt.txt` | T1 | Data aggregation pipeline |
| `t2_prompt.txt` | T2 | Fault-tolerant retry and fallback |
| `t3_prompt.txt` | T3 | Conditional decision workflow |
| `t4_prompt.txt` | T4 | Multi-agent Saga orchestration |

## Generation Parameters

- **Model**: GPT-4 Turbo (gpt-4-turbo-2024-04-09)
- **Temperature**: 0.2
- **Max tokens**: 4096
- **System prompt**: None (zero-shot)
- **Generation mode**: Single prompt, no iteration

## Protocol

Each prompt was submitted three times. The median IC run was selected, and the generated output from that run was used for all downstream measurements (MC, RC, VC).

## Prompts from the Paper

### T1 Prompt

```
You are a workflow automation expert. Create a Python script
that reads a CSV file with columns id, name, value, category,
timestamp. Remove any rows where value is empty or
non-numeric. Cast value to float. Group records by category.
Export the result as a JSON file. The input file path is
'input.csv' and the output file path is 'output.json'. Handle
errors gracefully.
```

### T2 Prompt

```
You are a workflow automation expert. Create a Python script
that calls an HTTP GET endpoint at
'https://api.example.com/primary'. If the response is 503 or
the request times out after 5 seconds, retry up to 3 times
with exponential backoff (base 2). If all retries fail, call
a backup endpoint at 'https://api.example.com/backup'. Log
the response status, source (primary or backup), and retry
count to a file called 'execution.log'. Use the requests
library. Handle missing credentials by checking the API key
environment variable before invoking.
```

### T3 Prompt

See the paper (Appendix E) for the full T3 prompt with routing logic.

### T4 Prompt

```
You are a workflow automation expert. Implement a Saga
pattern for order processing with two parallel sub-services:
Inventory Reservation (POST /inventory/reserve) and Payment
Authorization (POST /payment/authorize). The input is an
order event with fields order_id, items (array),
total_amount, and customer_id. Execute both sub-services
concurrently using asyncio.gather. If both succeed, POST
/order/confirm and return state 'confirmed'. If either fails,
trigger compensating actions: POST /inventory/release for
the inventory reservation and POST /payment/void for the
payment authorization. Log all actions to 'saga.log'. Return
the final state ('confirmed' or 'cancelled') and the
compensation log. Handle exceptions at each step
individually so that one failure does not prevent the other
compensation from executing.
```

## Note

These prompts are reproduced verbatim from Appendix E of the paper. Minor formatting differences may exist between this file and the original publication.
