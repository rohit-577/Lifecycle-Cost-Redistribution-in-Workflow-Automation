# Task Definitions

This directory contains the full specifications for all four benchmark tasks.

## Tasks

### T1: Data Aggregation Pipeline

- **Category**: API / Data Chaining
- **Steps**: 5
- **Coordination Pattern**: Sequential linear
- **Failure Model**: Malformed input (10% of records)

**Input**: CSV file with 100 records (id, name, value, category, timestamp). ~10% null values.

**Expected Output**: JSON array of cleaned records grouped by category (90 records).

**Success Criteria**: Output must match gold-standard JSON structure exactly.

**Implementation Constraints**:
- Python: pandas.read_csv, json.dump
- n8n: CSV node, Function node, JSON node
- AI: Single prompt specifying format, rules, and output path

---

### T2: Fault-Tolerant Retry & Fallback

- **Category**: Error Recovery
- **Steps**: 10
- **Coordination Pattern**: Linear with retry branches
- **Failure Model**: API timeout (30%), missing credential (10%)

**Input**: Trigger signal with configuration credentials.

**Expected Output**: JSON payload with response body and execution metadata.

**Success Criteria**: After up to 3 retries with exponential backoff, must return successful response or log terminal failure.

**Implementation Constraints**:
- Python: requests, tenacity
- n8n: HTTP Request node with error trigger routing
- AI: Single prompt specifying endpoints and retry policies

---

### T3: Conditional Decision Workflow

- **Category**: Branching Logic
- **Steps**: 12
- **Coordination Pattern**: Nested decision tree (4 leaves)
- **Failure Model**: Schema mismatch at decision node (15% of runs)

**Input**: JSON payload representing transaction event.

**Expected Output**: Transformed JSON payload with routing metadata and applied discounts.

**Success Criteria**: Route field must indicate correct path; at least 4/5 test payloads route correctly.

**Implementation Constraints**:
- Python: Nested conditional statements
- n8n: Switch and Merge nodes
- AI: Single prompt specifying routing criteria

---

### T4: Multi-Agent Asynchronous Orchestration

- **Category**: Distributed Orchestration
- **Steps**: 18
- **Coordination Pattern**: Parallel join, conditional compensation (Saga)
- **Failure Model**: Partial failure (20% of runs)

**Input**: JSON payload representing transaction event.

**Expected Output**: Confirm/cancel confirmation signal and compensation history log.

**Success Criteria**: Both sub-services succeed → confirmed with no compensation entries. Either fails → cancelled with compensating actions logged.

**Implementation Constraints**:
- Python: asyncio library
- n8n: Merge nodes with dual error trigger branches
- AI: Single prompt specifying parallel execution and compensation logic
