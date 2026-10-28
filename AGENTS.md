# AGENTS.md

Instructions for coding agents contributing to Agent Playground.

## Mission

Build a small, reproducible research environment for testing heterogeneous model routing and composition in coding-agent workflows. **Do not turn this into a general agent platform.**

## Principles

1. **Evidence before architecture.** Implement the simplest experiment capable of falsifying a hypothesis. Report negative results.
2. **Controlled comparisons.** Use the same tasks, harness, tools, context access, permissions, resource limits and evaluation rules across variants. Document unavoidable differences.
3. **Separate policy from execution.** Routing policies produce typed task properties/execution plans. Harness adapters execute them. Avoid hardcoding provider/model names in task taxonomy.
4. **Deterministic checks first.** Compilers, tests, linters and explicit assertions outrank model self-assessment. Never equate a judge's opinion with verified correctness.
5. **Reproducibility.** Record model identifier/version, provider, prompts, configuration, seed if supported, code commit, dependency lockfile, environment, timestamps, tool traces, token usage, cost and latency. Redact credentials and personal data.
6. **Measure total workflow cost.** Include classification, retrieval, retries, execution and verification, not merely generation.
7. **Limit scope.** Pi is the initial harness; LangGraph and other adapters are later experimental options. No Emacs/Zellij integration, shared memory service, distributed manager or monorepo migration in phase one.
8. **Keep experiments isolated.** Use temporary worktrees/fixtures where appropriate; do not run untrusted generated code on the host without isolation and explicit controls.

## Implementation guidance

- Prefer TypeScript with strict types, small interfaces, explicit errors and testable pure functions.
- Start with a runnable baseline and documented commands before adding abstractions.
- Keep datasets, expected checks and evaluation code versioned; never let an evaluated agent read hidden answers.
- Treat all model outputs as untrusted input. Validate structured responses and bound retries, tokens, time and spend.
- Never commit API keys, private repository data, sensitive prompts or large trace artefacts.
- Provide unit tests for routing/metrics and integration tests for harness adapters where practical.
- Keep dependencies lean; justify orchestration frameworks with a specific experiment.

## Definition of done for an experiment

A task is complete only when it includes: a stated hypothesis, baseline, controlled variant, executable procedure, evaluation criteria, raw machine-readable outputs, summary statistics, failure analysis and limitations. Do not claim superiority from a single anecdotal run.

## Collaboration

Work through focused issues and reviewable pull requests. Do not self-merge. Update README/docs when scope or experimental conclusions change. Distinguish proposals, implemented behaviour and measured findings.
