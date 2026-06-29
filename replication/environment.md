# Environment Setup

## Python Environment

### Required Software

- Python 3.11 or later
- pip package manager

### Required Packages

```
requests>=2.31.0
pandas>=2.1.0
tenacity>=8.2.0
openai>=1.0.0
numpy>=1.24.0
```

### Virtual Environment Setup

```bash
python -m venv .venv
source .venv/bin/activate  # Linux/Mac
# .venv\Scripts\activate    # Windows
pip install -r requirements.txt
```

## n8n Environment

### Option 1: n8n Cloud

Sign up at [https://app.n8n.cloud](https://app.n8n.cloud)

### Option 2: Self-Hosted

```bash
# Using npx
npx n8n start

# Using Docker
docker run -it --rm --name n8n -p 5678:5678 n8nio/n8n
```

## OpenAI API

### Requirements

- OpenAI API account with GPT-4 Turbo access
- API key set as environment variable: `OPENAI_API_KEY`

### Model Configuration

- Model: `gpt-4-turbo-2024-04-09`
- Temperature: 0.2
- Max tokens: 4096
- No system prompt

## Network Requirements

- Stable internet connection (latency < 50 ms recommended)
- API access to OpenAI endpoints
- n8n cloud or local instance connectivity

## Hardware

### Minimum Requirements

- 8 GB RAM
- 4 CPU cores
- 10 GB free disk space

### Recommended

- 16 GB RAM
- 8 CPU cores
- 20 GB free disk space

## Verification

After setup, verify your environment:

```bash
python --version  # Should be 3.11+
python -c "import requests; import pandas; import tenacity; print('All imports OK')"
```
