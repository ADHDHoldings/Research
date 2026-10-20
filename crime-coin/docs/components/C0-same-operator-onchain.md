# C0 — Same-operator / entity group claim (onchain angle)

**Status:** Phase A — scoping  
**Phase B:** —  
**Triggered by:** “They’re the same operator / entities + VCs manipulating price; can wallet tracking or clustering back that up?”

This sits **under** the playbook, not as one of his day-to-day trade signals. His trade process uses visual heuristics (OI, funding, price phases, ghost socials, recurring VC names). The **same-operator** claim is the story that ties those heuristics together. Onchain clustering is a candidate way to test that story.

## 1. What he claims

From the PDF, stacked carefully:

| Claim | Strength in text | Evidence he cites |
|-------|------------------|-------------------|
| These golden names share one operator (or one group) | Belief (“very positive”) | Same setup/playbook across coins |
| Socials are fake / ghost | Gestalt observation | Looking at Twitter / Spaces |
| Recurring VCs (Bitget/Malstrom, HackVC, etc.) | Observation | Cap tables / raise announcements |
| OI is manipulated; operator controls most OI | Assumption he flags as hard to prove | Shakeout behavior; OI vs interest |
| Bitget supply moves / wash / similar lockup platforms | Indicator of “the correct group” | Onchain + venue patterns; not a trade trigger |
| Prior bubble maps found “weird things” | Anecdote | Manual cluster inspection |
| Prior BNB indexing + AI | Abandoned | Cost; friend went quiet; weak for execution |

So: **visual heuristics → belief in a coordinating group.** He already tried some onchain graph work. It confirmed weirdness; it did not prove operator identity or improve trades.

## 2. What “backing this up” would mean

We need to separate three targets. Wallet clustering does not hit them equally.

### Target A — Shared onchain controllers across golden coins

**Hypothesis:** The same wallet clusters (or tightly linked clusters) appear in supply, liquidity, unlock receivers, or wash loops across `$MYX` `$COAI` `$RAVE` `$AIA` `$LAB` `$BEAT` (and maybe fail-deads).

**If true:** Supports “same operator / same desk” more than playbook similarity alone.  
**If false:** Does not kill the thesis — operator could be the same offchain (CEX accounts, OTC, VC SPVs) with fresh onchain wallets per coin.

### Target B — VC / exchange-linked wallets participating in the path

**Hypothesis:** Addresses labeled or strongly attributed to named VCs / Bitget-related cold wallets / raise recipients show repeated, patterned involvement (receipt of unlocks, CEX deposits, timed distribution) around the playbook phases.

**If true:** Supports “these entities are in the flow,” not necessarily “they manipulate OI.”  
**If false:** VCs may only be logo/raise theater with no ongoing onchain footprint we can see.

### Target C — Onchain mechanism of the price/OI game

**Hypothesis:** Wash trading, inventory parking, and depeg-related flows are how funding/OI extremes are sustained.

**Harder.** Much of the golden playbook (perps OI, funding, CEX shakeouts) lives **offchain on exchange ledgers**. Onchain can see spot/DEX/BNB inventory and CEX deposit addresses; it usually **cannot** see who owns the OI bundle on Binance/Aster/Bitget.

## 3. What wallet tracking / clustering can actually do

Useful techniques (conceptual only — not building yet):

| Technique | What it shows | Fits which target |
|-----------|---------------|-------------------|
| Shared funder / shared deployer | Same creator of tokens or same eth/BNB funder of “team” wallets | A |
| Transfer-graph clustering (multi-hop common neighbors) | Supply and wash graph overlap across coins | A |
| Timing co-movement of clusters | Same cluster active at unlock / listing / OI-spike windows | A, weak C |
| CEX deposit-address attribution | Soft link from cluster → Bitget/Binance/Gate | A, B |
| Known-label enrichment (Arkham, Nansen, labels, VC treasuries) | Put names on clusters | B |
| Fresh-wallet rate + peel chains | MM / wash habits | C (partial) |
| Cross-coin wallet reuse (his Type B note) | Slip-ups where wallets aren’t fresh | A (strong when it hits) |

What clustering **cannot** do well on its own:

- Prove “they control OI across CEX.”
- Prove intent or illegal manipulation.
- Equate “same VC on the raise” with “same trading operator.”
- Replace his OI/funding trade read — prior work already found clusters “telling” but not executable.

## 4. What would have to be true (fundamental)

A clean fundamental we could eventually state:

> For golden-crime names, a **stable onchain entity graph** (overlapping controllers, funders, or inventory routes) recurs across tokens that also share the offchain playbook (price band, ghost socials, listing/OI pattern) — at a rate above a control set of similar-FDV alts.

That is falsifiable. Playbook similarity alone is not.

A weaker, still useful fundamental:

> Recurring venue/VC-linked deposit and supply-move patterns identify membership in “the group” even when wallets are mostly fresh per coin.

That matches his Bitget cold-wallet note more than “same EOA on every coin.”

## 5. Prior art from the PDF (do not ignore)

He and a friend already:

1. Indexed BNB txs and wallets on coins of interest; tried AI on it — expensive, stalled.  
2. Used bubble maps manually — “weird things,” no execution edge.  
3. Built cross-CEX vs Aster OI/volume monitor — **best practical tool**.

So the question is not “has anyone looked onchain?” It is: **can a narrower, cheaper clustering test on a fixed coin list do what broad indexing did not?**

## 6. Known limits

- Golden crime may be mostly a **perp/OI** game; onchain is supporting cast (inventory, wash, unlock distro).
- Fresh wallets per coin defeat naive reuse detection (he notes Type B is more reusable-wallet readable).
- Label databases are incomplete and sometimes wrong.
- “Same VC” ≠ “same manipulator.” HackVC or Bitget on a raise is a **soft** prior, not proof of trading control.
- Cost and scope creep killed the last attempt. Any work here must stay small until approved.

## 7. Minimal research design (proposal only — not started)

If we later get a go-ahead for a **small** Phase A→B probe:

1. **Fixed universe:** his golden list + a few fail-deads + a control set of similar FDV alts (not the whole chain).  
2. **Chains:** only where those tokens actually have meaningful onchain supply (likely BNB + whatever each token uses) — not “all of BNB.”  
3. **Question:** do we find cross-coin cluster overlap or shared CEX-deposit routes above the control set?  
4. **Success criteria:** overlap rate / shared-funder hits, documented false positives — not a trading bot.  
5. **Stop rule:** if first 2–3 golden names show no reusable structure vs controls, park Target A and reconsider Target B (labels + Bitget flows) only.

Tools could be as light as: existing Bubblemaps / Arkham / Nansen views on the named tickers, before any custom indexer.

**No indexer, scraper, or paid API run is approved yet.**

## 8. Phase A status

| Item | Status |
|------|--------|
| What he believes | Same group; heuristics are how he notices candidates |
| What onchain is for | Test the group story; he already found it weak for execution |
| What clustering can support | Target A (shared controllers) best; B partial; C weak for OI |
| What would falsify Target A | No cross-coin structure vs controls on a fixed list |
| Build | **Not started — needs explicit go-ahead** |

### Open questions for you

1. Are we testing **same operator across golden coins** (Target A), **VC/Bitget in the flow** (Target B), or both?
2. Is a first pass on **existing cluster UIs** (Bubblemaps etc. on `MYX`/`LAB`/…) acceptable before any custom pipeline?
3. Do you want fail-deads and a control set in scope from day one, or golden winners only for a smoke look?
