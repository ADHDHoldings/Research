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

## 6b. Custody ceiling — can we beat Bubble Maps?

**User question (2026-10-20):** If the relevant inventory is in CEX custody, is it realistic to improve on what the author already could not see with Bubble Maps?

### What custody does to visibility

Once tokens (or the trading inventory that matters) sit on a centralized exchange:

1. Onchain you usually see a transfer into a **deposit address**, then aggregation into exchange hot/cold wallets.
2. After that, balances, who owns what, transfers between traders, and **perp OI** are on the exchange’s **internal ledger**.
3. Clustering UIs (Bubble Maps and anything like them) still draw bubbles for “Binance” / “Bitget” / “Gate” as big opaque nodes. That is not an improvement on custody — it is a picture of the wall.

So for the author’s core claim — **one group controls most OI and runs shakeouts on CEX perps** — Bubble Maps-class tools are the wrong instrument. Building a fancier clusterer does not open the CEX ledger.

### Where a marginal improvement is still possible

Only on the **edges of custody**, not inside it:

| Still visible onchain | What it might show | Beats Bubble Maps? |
|-----------------------|--------------------|--------------------|
| Who deposited *into* which CEX, when | Shared deposit routes across golden coins | Maybe slightly, if we compare coins systematically |
| Unlock / raise recipients before they deposit | Soft link from “VC/team” → exchange | Maybe, with better labels |
| DEX wash / residual free-float clusters | Pre-custody or parallel onchain theater | Small; he already saw “weird things” |
| Exchange cold-wallet *supply moves* between known exchange addresses | His Bitget note — group confirmation, not trade | He already treats this as weak for trading |

None of that shows who holds the OI bundle or who is liquidating whom inside Binance/Aster/Bitget.

### Verdict for this project

| Goal | Realistic with Bubble Maps–class / custom clustering? |
|------|--------------------------------------------------------|
| Prove or improve on **CEX OI control / same desk trading inside the venue** | **No.** Custody (and perp ledgers) block it. |
| Slightly better **pre-deposit / cross-coin deposit-route** overlap than manual Bubble Maps | **Maybe**, narrow and cheap only. |
| Replace or improve his **trade** read | **No.** His own best tool was cross-CEX OI vs Aster — venue data. |

**Implication:** If the thesis we care about is “entities manipulating price via custody + perps,” onchain clustering is the wrong primary path. Venue-side data (OI, funding, open interest by exchange, basis) is closer to what he actually trades — and still won’t name the operator, only the footprint.

Park or heavily demote Target A/C as *proof of manipulator identity*. Keep any onchain work, if at all, as a small optional check on deposit-edge overlap — not as the way to beat what Bubble Maps missed inside the CEX.

## 7. Minimal research design (proposal only — not started)

Given §6b, a custom indexer to “see past Bubble Maps into custody” is **not** a proposed design.

The only onchain probe still worth considering later (and only with explicit go-ahead):

1. **Fixed universe:** a few golden names (+ optional fail-deads / controls).  
2. **Question limited to deposit-edge:** do the same pre-CEX clusters or deposit routes recur across coins more than controls?  
3. **Method:** existing UIs first; no full-chain ingest.  
4. **Stop rule:** if the picture is just “big CEX bubbles,” stop — that is the custody ceiling, not a data gap we can fill.

**No indexer, scraper, or paid API run is approved yet.**

## 8. Phase A status

| Item | Status |
|------|--------|
| What he believes | Same group; heuristics are how he notices candidates |
| What onchain is for | Test the group story; he already found it weak for execution |
| Custody ceiling | **If inventory/OI is inside CEX, Bubble Maps–class tools cannot see the operator** |
| What clustering can support | At best deposit-edge / pre-custody overlap; not OI control |
| Build | **Not started — needs explicit go-ahead** |

### Open questions for you

1. Given the custody ceiling: **park onchain clustering** as a primary path, or keep only a tiny deposit-edge smoke look?
2. Prefer to shift the “back the entity-group story” effort toward **venue data** (OI / funding / basis — closer to what he trades) instead?
3. Or continue piece-by-piece on the playbook (C1a socials, then C3/C5) and leave C0 parked?
