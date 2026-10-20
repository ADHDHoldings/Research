# Project tracker

## Current focus

**Two Phase A threads:**

1. **C1a** — ghost / botted / “random” socials  
   [`components/C1a-ghost-socials.md`](components/C1a-ghost-socials.md)
2. **C0** — same-operator claim vs wallet tracking / clustering  
   [`components/C0-same-operator-onchain.md`](components/C0-same-operator-onchain.md)

Method: [`00-research-method.md`](00-research-method.md).  
No custom indexer or paid onchain pipeline until you approve a scoped probe.

## Decisions log

| Date | Decision |
|------|----------|
| 2026-10-19 | Created `crime-coin/`; Stage 1 read of the PDF complete |
| 2026-10-19 | Ask before heavy / long / rising-cost work |
| 2026-10-19 | Goal is fundamentals behind the playbook, not codifying it as-is |
| 2026-10-19 | Per component: understand first; only then add on, replace, or augment |
| 2026-10-20 | Started C1a on the social excerpt |
| 2026-10-20 | Opened C0: can wallet clustering back the same-operator / entity-group story? |

## Open questions (C0)

1. Target A (cross-coin controllers), Target B (VC/Bitget in the flow), or both?
2. First pass via existing UIs (Bubblemaps / Arkham / etc.) before any custom pipeline?
3. Include fail-deads + control alts from the start, or golden winners only for a smoke look?

## Idea inbox

- Onchain wallet tracking / clustering as a way to test the entity-group claim behind his visual heuristics (OI, VC names, price action).

## Experiments

| Name | Component | Approved? | Path | Result |
|------|-----------|-----------|------|--------|
| _(none yet)_ | | | `experiments/` | |

## Risks / constraints

- Operator and venue claims in the PDF are his conjecture.
- Prior full-chain indexing got expensive and did not help execution.
- Perp OI / funding (core of the trade) is mostly offchain — clustering won’t see it directly.
- Ask before any paid API, full-chain ingest, or long training runs.
