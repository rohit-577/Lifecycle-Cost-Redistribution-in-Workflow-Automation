# Quick Start Guide

## Prerequisites

- Python 3.11+
- n8n account (cloud or self-hosted)
- OpenAI API access (GPT-4 Turbo: gpt-4-turbo-2024-04-09)
- Git

## Step 1: Clone the Repository

```bash
git clone https://github.com/rohit-577/Lifecycle-Cost-Redistribution-in-Workflow-Automation.git
cd Lifecycle-Cost-Redistribution-in-Workflow-Automation
```

## Step 2: Set Up Python Environment

```bash
python -m venv .venv
source .venv/bin/activate  # Linux/Mac
# or .venv\Scripts\activate  # Windows
pip install -r requirements.txt
```

## Step 3: Review Task Specifications

Read task definitions in `benchmark/task_definitions/`. Each task has input specifications, expected outputs, and success criteria.

## Step 4: Obtain Original Artifacts

The original implementation artifacts are at:
[https://github.com/rohitr/wab-benchmark](https://github.com/rohitr/wab-benchmark) (commit a3f91e)

Clone this repository to obtain:
- Python workflow scripts
- n8n workflow JSON configurations
- LLM prompts
- Gold-standard outputs
- Failure-injection scripts

## Step 5: Run Measurements

Follow the measurement protocol in `docs/measurement_protocol.md` and recovery protocol in `docs/recovery_protocol.md`.

## Step 6: Compare Results

Compare your measurements against the published data in `data/published/table6_measurements.csv`.

## Expected Timeline

- Environment setup: 30 minutes
- Per-task implementation and measurement: 1–2 hours per paradigm
- Full replication: 8–16 hours (depending on familiarity with paradigms)
