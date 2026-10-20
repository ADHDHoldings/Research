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

## 6c. Idea — CEX-as-mixer and funding-origin ratio of winners

**User idea (2026-10-20):** Workflow = CEX → many wallets → profit onchain → back to CEX (exchange as mixer). Could we compute, among wallets that **profited** on the coin, the ratio of funding origin **CEX vs existing wallets** — and would that help?

### What the metric would be

Roughly:

1. Define a set of wallets that **realized profit** on the token onchain (sold/sent more value out than they put in, under some rules).
2. For each, walk **funding origin**: first meaningful inbound capital — labeled CEX withdrawal/hot wallet vs another EOA / bridge / DeFi / “already existed in the wild.”
3. Aggregate: share of winner capital (or winner wallets) that is **CEX-sourced** vs **non-CEX-sourced**.

Optional refinements (still conceptual): wallet age, fan-out from the same withdrawal batch, time from withdraw → trade → deposit-back, peel-chain shape.

### What it would actually test

| It can support | It cannot do |
|----------------|--------------|
| “Onchain winners look **industrially CEX-cycled** (fresh, exchange-funded) vs organic holders who were already funded elsewhere” | Name the operator inside the CEX mixer |
| Compare that ratio on golden coins vs a control set | Link coin A’s deposit-back to coin B’s next withdrawal (ledger is opaque) |
| Fit a **wash / inventory / onchain-leg** story | Prove the **perp OI** desk is the same entity |

So this is a **deposit-edge / participant-structure** metric — Target A/B-adjacent — not a custody pierce.

### Would it help?

**Somewhat, with a narrow claim — not as proof of the full playbook.**

- **Helps if** the money-making (or wash) leg you care about is **onchain**, and you want evidence that winners are mostly “exchange-spawned” participants rather than a real community of pre-existing wallets. That aligns with ghost-social + industrial flow.
- **Weak for golden crime’s main P&amp;L** if profits sit on **CEX perps** the whole time. Those winners **never appear** in “wallets who profited onchain.” You would be measuring a side cast (DEX traders, wash loops, exit liquidity), not the OI bundle.
- **CEX→wallet is also normal retail.** High CEX-funding among traders is common. The metric needs a **control set** and probably shape features (freshness, batch fan-out, fast round-trip) — ratio alone is not a smoking gun.
- **Mixer works:** once they deposit back, the next coin’s fresh wallets look unrelated onchain. The ratio can say “this coin’s winners look CEX-cycled”; it still won’t stitch cycles across coins into one identity.
- **Definition risk:** “profited” is ambiguous (unrealized, MEV/arb, partial exits, transfer ≠ trade). Bad definitions make the ratio meaningless.

### Fit to custody ceiling

This idea lives exactly on the **edge** we said was still visible: withdraw → activity → deposit. It does **not** contradict the ceiling; it accepts it and asks a weaker question: *what kind of onchain winners does this coin produce?*

Falsifiable fundamental (if we ever tested it):

> On golden-crime names, onchain realized-profit wallets are more often freshly CEX-funded (and/or fast round-trip) than on a control set of similar-FDV tokens — consistent with industrial CEX-cycled flow, not organic holder distribution.

### Phase A verdict on the idea

| Question | Answer |
|----------|--------|
| Is the workflow plausible? | Yes — standard CEX-as-hub behavior |
| Is the ratio computable in principle? | Yes, with labels + a profit definition + cost |
| Does it beat Bubble Maps on operator ID? | **No** — still can’t see through the mixer |
| Does it help at all? | **Yes, narrowly** — as a *structure of onchain winners* / industrial-flow check, especially vs controls; better as add-on evidence than as the main validation of same-operator OI control |
| Build now? | **No** — idea captured only |

## 7. Minimal research design (proposal only — not started)

Given §6b, a custom indexer to “see past Bubble Maps into custody” is **not** a proposed design.

Onchain probes still worth considering later (only with explicit go-ahead), in increasing cost:

1. **Existing UIs** on a few golden names — is the picture just big CEX bubbles?  
2. **Deposit-edge overlap** across coins vs controls.  
3. **Funding-origin ratio of onchain winners** (CEX-sourced vs existing wallets) vs controls — §6c; needs a profit definition; still does not pierce the mixer.  

Stop if (1) already shows only custody walls and no distinctive edge structure.

**No indexer, scraper, or paid API run is approved yet.**

## 8. Phase A status

| Item | Status |
|------|--------|
| What he believes | Same group; heuristics are how he notices candidates |
| What onchain is for | Test the group story; he already found it weak for execution |
| Custody ceiling | **If inventory/OI is inside CEX, Bubble Maps–class tools cannot see the operator** |
| What clustering can support | At best deposit-edge / pre-custody overlap; not OI control |
| CEX-funding ratio of winners | Narrow help for “industrial onchain winners”; does not ID operator through mixer |
| Build | **Not started — needs explicit go-ahead** |

### Open questions for you

1. Keep §6c as a **parked metric idea** only, or treat it as the preferred tiny onchain probe if we ever do one?
2. For golden crime specifically: do you believe a meaningful P&amp;L leg is **onchain**, or mostly **CEX perps**? (If mostly perps, this ratio measures the wrong winners.)
3. Park C0 and continue piece-by-piece on the playbook (C1a → C3/C5), with venue data as the later path for the entity-group footprint?
