# sciqnt

**Standardizing brokers for the age of AI — from the connector side.**

sciqnt is an open, **local-first, agent-native** cross-asset financial-data layer: one
canonical, point-in-time-correct schema, fed by an open ecosystem of connectors for each
broker / exchange / data source, exposed to *any* AI agent. Deterministic code computes
the numbers; LLMs reason and explain. **You own your data and keys** — *fire us and keep
everything.*

This org is a **component world** — a toolkit of independently-valuable open-source
building blocks, each its own repo, all MIT, all governed by one constitution.

## The map

- **[`sq-constitution`](https://github.com/sciqnt/sq-constitution)** — the principles +
  the reusable governance every repo inherits
- **`sq-contract`** — the canonical point-in-time schema + the conformance harness (the
  hub everything pins) + the connector SDK
- **Libraries** — `sq-math`, `sq-performance` (XIRR/TWR/drawdown), `sq-compute`, `sq-fx`,
  `sq-price-store`, `sq-secrets`, `sq-fmt`
- **`sq-portfolio`** — composes conformant connectors into unified portfolio state
- **`sq-tui`** — the interactive terminal app
- **Connectors** (`sq-degiro`, `sq-kalshi`, `sq-yahoo`, …) — one repo each; map a
  source into the canonical schema. Build one from **`sq-connector-template`**.

> The `sciqnt/sciqnt` monorepo is the transitional source-of-truth for the code while
> components graduate into their own repos.

## Use it

A connector reads **your own account with your own credentials, locally**, and
standardizes it into the canonical schema. Install the contract + a connector, or run
the app. Every surface also emits versioned structured data (`--json`) — agents
consume it directly.

## Contribute

Each repo inherits the same gated flow: CI + conformance, an advisory principle-review
agent, and `@claude` fix-mode. DCO, not CLA. See `CONTRIBUTING.md`. The most valuable
contribution is a **connector** — start from `sq-connector-template`.
