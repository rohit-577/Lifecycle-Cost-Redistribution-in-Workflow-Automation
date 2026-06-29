# Frequently Asked Questions

## General

**Q: What is this benchmark measuring?**

A: This benchmark measures four time-based lifecycle costs (Implementation, Maintenance, Recovery, Verification) across three workflow paradigms (Python code, n8n visual, GPT-4 Turbo AI) on four coordination-demanding tasks.

**Q: Why time-based metrics?**

A: Time is directly comparable across paradigms, measurable with sub-second precision via automated timestamps, and is the primary resource constraint in industrial automation practice.

## Methodology

**Q: Why only one evaluator?**

A: The single-evaluator design holds evaluator effects constant across all three paradigms. However, this means results should be interpreted as evaluator-conditioned observations rather than population-level paradigm timings. Replication by independent operators is essential.

**Q: Why was the execution order fixed (Code → Visual → AI)?**

A: The fixed order was chosen for logistical consistency (code implementation served as reference baseline). This is arguably the single largest methodological weakness — learning effects may inflate AI's apparent advantage.

**Q: Why GPT-4 Turbo specifically?**

A: GPT-4 Turbo (gpt-4-turbo-2024-04-09) was the most capable publicly available instruction-tuned model at data collection (March 2025). The frozen snapshot prioritizes reproducibility over generalization.

## Results

**Q: Does the benchmark show that AI is worse than code?**

A: No. AI achieved the lowest total lifecycle cost at every task level including T4 (191 s vs. Python 366 s). The finding is that the *composition* of cost changes — AI shifts effort from implementation toward downstream phases.

**Q: What is the most important finding?**

A: Recovery cost is the primary differentiator. Visual builders exhibit 20.4× escalation and AI shows 4.9× escalation under orchestration, while code-based recovery remains flat (19–23 s).

**Q: Can these results be generalized?**

A: The results are conditioned on specific platforms (Python 3.11, n8n, GPT-4 Turbo), tasks (4 synthetic coordination tasks), and evaluator profile. Generalization requires independent replication across more platforms, tasks, and operators.

## Replication

**Q: How can I replicate the benchmark?**

A: See [replication/quickstart.md](../replication/quickstart.md) for step-by-step instructions. The original benchmark artifacts are at [https://github.com/rohitr/wab-benchmark](https://github.com/rohitr/wab-benchmark) (commit a3f91e).

**Q: What tools do I need?**

A: Python 3.11, n8n account (cloud or self-hosted), OpenAI API access (GPT-4 Turbo), and the task specifications provided in this repository.

## Theoretical

**Q: Is CDH a validated theory?**

A: No. CDH is an interpretive framework applied to the benchmark observations, not a validated predictive theory. The benchmark data can inform CDH but cannot confirm it as uniquely correct.

**Q: What would falsify CDH?**

A: Observing a higher-abstraction paradigm that reduces IC without increasing any downstream component across a range of coordination complexities — e.g., an AI generator whose outputs require no debugging or maintenance.
