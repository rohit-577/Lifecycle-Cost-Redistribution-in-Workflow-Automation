# Repository Overview

## Purpose

This repository is the official reproducibility package for the paper **"Lifecycle Cost Redistribution in Workflow Automation: An Exploratory Benchmark of Code, Visual, and AI Paradigms"**.

## Structure

```
/
├── README.md              # Repository overview and quick links
├── LICENSE                # MIT License
├── CITATION.cff           # Citation metadata
├── CONTRIBUTING.md        # Contribution guidelines
├── CODE_OF_CONDUCT.md     # Community guidelines
├── CHANGELOG.md           # Version history
├── ROADMAP.md             # Development plans
├── SECURITY.md            # Security policy
├── .gitignore             # Git ignore rules
│
├── paper/                 # Published paper and related files
│   ├── pdf/               # Published PDF
│   ├── source/            # LaTeX source
│   ├── figures/           # Figure files
│   ├── tables/            # CSV table exports
│   └── supplementary/     # Supplementary materials
│
├── data/                  # Benchmark dataset
│   ├── published/         # Published tables as CSV
│   ├── processed/         # Cleaned analysis-ready data
│   └── schemas/           # Data schema definitions
│
├── benchmark/             # Benchmark definitions
│   ├── task_definitions/  # T1–T4 specifications
│   ├── metrics/           # Metric definitions
│   └── protocols/         # Measurement protocols
│
├── replication/           # Replication guides
│   ├── quickstart.md      # Quick start guide
│   ├── full_replication_guide.md  # Full replication instructions
│   ├── environment.md     # Environment setup
│   └── limitations.md     # Replication limitations
│
├── artifacts/             # Implementation artifacts
│   ├── workflows/         # Python and n8n implementations
│   │   ├── python/        # Python workflow scripts
│   │   └── n8n/           # n8n workflow JSON
│   └── prompts/           # LLM prompts
│
├── docs/                  # Documentation
│   ├── methodology.md     # Experimental methodology
│   ├── benchmark_design.md # Benchmark design details
│   ├── recovery_protocol.md # Recovery timing protocol
│   ├── measurement_protocol.md # Measurement protocol
│   ├── glossary.md        # Terminology definitions
│   ├── faq.md             # Frequently asked questions
│   ├── threats_to_validity.md # Validity threats
│   └── repository_overview.md # This file
│
├── assets/                # Visual assets
│   ├── diagrams/          # Architecture and concept diagrams
│   ├── figures/           # Paper figures
│   └── branding/          # Branding assets
│
└── .github/               # GitHub templates
    ├── ISSUE_TEMPLATE/    # Issue templates
    ├── PULL_REQUEST_TEMPLATE.md  # PR template
    └── workflows/         # CI workflows
```

## Key Links

- **Published paper**: `paper/pdf/`
- **Raw measurement data**: `data/published/table10_raw_trials.csv`
- **Task specifications**: `benchmark/task_definitions/`
- **Replication guide**: `replication/quickstart.md`
- **Original benchmark**: [https://github.com/rohitr/wab-benchmark](https://github.com/rohitr/wab-benchmark)

## Data Integrity

All CSV files in `data/published/` are transcribed directly from the published paper tables. No fabricated or synthetic data has been introduced.

## License

All contents are MIT licensed unless otherwise noted.
