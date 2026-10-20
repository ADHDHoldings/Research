# Project tracker

## Current focus

**Two Phase A threads:**

1. **C1a** — ghost / botted / “random” socials  
   [`components/C1a-ghost-socials.md`](components/C1a-ghost-socials.md)
2. **C0** — same-operator claim vs wallet tracking / clustering  
   [`components/C0-same-operator-onchain.md`](components/C0-same-operator-onchain.md)  
   **Custody ceiling noted:** if the inventory/OI that matters is inside a CEX, Bubble Maps–class tools cannot see the operator; custom clustering does not fix that.

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
| 2026-10-20 | C0 custody ceiling: improving on Bubble Maps is not realistic for in-CEX inventory/OI |
| 2026-10-20 | Captured idea: CEX-funding vs existing-wallet ratio among onchain winners (mixer-edge metric) |

## Open questions (C0)

1. Park §6c funding-origin ratio as idea-only, or preferred tiny probe later?
2. Is golden-crime P&amp;L mostly onchain or CEX perps? (Decides whether “onchain winners” matter.)
3. Park C0 and continue playbook piece-by-piece (C1a → C3/C5)?

## Idea inbox

- Onchain wallet tracking / clustering as a way to test the entity-group claim behind his visual heuristics (OI, VC names, price action).
- CEX → many wallets → profit → CEX as mixer; measure CEX vs non-CEX funding origin among wallets that profited onchain.

## Experiments

| Name | Component | Approved? | Path | Result |
|------|-----------|-----------|------|--------|
| _(none yet)_ | | | `experiments/` | |

## Risks / constraints

- Operator and venue claims in the PDF are his conjecture.
- Prior full-chain indexing got expensive and did not help execution.
- Perp OI / funding (core of the trade) is mostly offchain — clustering won’t see it directly.
- CEX custody is a hard visibility ceiling for Bubble Maps–class tools; fancier clustering does not open the venue ledger.
- Ask before any paid API, full-chain ingest, or long training runs.
