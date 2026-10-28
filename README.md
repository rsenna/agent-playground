# Agent Playground

An experimental laboratory for **heterogeneous AI-model orchestration** in software engineering.

## Research question

Can a combination of specialised models, deterministic tools and adaptive orchestration outperform a strong single-model coding agent on **end-to-end correctness, cost and latency**?

This is a research repository, **not** a new agent platform. Findings should precede product architecture.

## Hypotheses

- **H1: Routing.** A typed task classifier and model-selection policy improves quality-adjusted cost or latency versus a strong single-model baseline.
- **H2: Composition.** Breaking work into retrieval, reasoning, coding and verification stages improves outcomes over selecting one model for the whole task.
- **H3: Decision models.** Bounded decision models (e.g. Jev), conventional rules and generative classifiers have different accuracy/cost trade-offs.
- **H4: Verification.** Deterministic tests and independent evaluation reduce false completion claims.

Null or negative results are valuable. No improvement should be claimed without controlled measurements.

## Initial scope

- TypeScript experiment runner and a **Pi SDK** harness adapter.
- Pluggable routing policies: deterministic rules, Jev, and LLM classifier.
- Typed task descriptions and execution plans, decoupled from vendor/model IDs.
- A small, versioned benchmark corpus of realistic repository tasks.
- Reproducible runs, traces, cost, latency, test outcomes and failure analysis.
- Baseline comparison using the same tools, context, permissions and budgets.

**Later, if justified:** LangGraph for stateful multi-stage/dynamic workflows, additional harness adapters, embeddings/rerankers, specialist code models and local SLMs.

**Out of scope initially:** Emacs, Zellij, agent-manager UI, OpenViking/Hindsight, distributed orchestration, monorepo consolidation, and building a new general-purpose agent framework.

## Proposed layout (not yet implemented)

```text
src/
  harnesses/        # Pi first; other adapters later
  models/           # Capability registry and typed contracts
  routing/          # Rules, Jev and LLM policies
  experiments/      # Runner and configurations
  evaluation/       # Deterministic and model-assisted assessment
benchmarks/         # Versioned tasks, fixtures and expected checks
results/            # Machine-readable run artefacts (ignore large outputs)
docs/               # Protocols, hypotheses and findings
```

## Experimental protocol

1. Freeze a representative task set and record environment/tool versions.
2. Establish a strong single-model baseline using the same Pi harness.
3. Compare routing policies while holding tools, context and budgets constant.
4. Evaluate composition separately from routing.
5. Run multiple trials where stochasticity matters; report uncertainty.
6. Track **task success**, false acceptance, total tokens/cost, wall-clock latency, retries and failures.
7. Publish reproducible commands, raw results and limitations. Avoid benchmark leakage and cherry-picking.

## Roadmap

See [GitHub Issues](https://github.com/rsenna/agent-playground/issues). Start with the benchmark protocol, Pi adapter and baseline before adding Jev routing; only add LangGraph when a multi-stage experiment requires it.

## Status

Research planning. No experimental claims yet.
