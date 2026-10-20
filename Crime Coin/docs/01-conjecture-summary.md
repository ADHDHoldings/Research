# Stage 1 — Conjecture summary

Read of `references/Crime_Coin.pdf` (author’s informal overview). This is a
**paraphrase for research**, not endorsement of the claims.

## Core claim

A recurring operator (or small set of operators) runs a recognizable playbook on
certain mid-FDV “ghost” tokens. The profitable edge is not fundamental research —
it is **early recognition of the setup**, then riding the squeeze while reading
**open interest (OI), funding, and depegs** as the main risk/exit gauges.

The author says they have traded this for years and monitors listings + CMC top
500 for candidates.

---

## Type A — “Golden crime” (main thesis)

**Example winners (author’s list):** `$MYX` `$COAI` `$RAVE` `$AIA` `$LAB` `$BEAT`  
**Failed / incomplete (still sometimes tradeable early):** `$CYS` `$PIEVERSE` `$VELVET` `$POWER` `$BSB`  
**Also flagged by a third party:** `$CT` (different surface look than `$REZ`)

### Typical profile (pre-pump)

| Signal | Rough description |
|--------|-------------------|
| Price base | ~$0.30–0.40 for weeks–months |
| FDV | Often ~$300M |
| Socials | “Ghost” project: botted Twitter, random Spaces hosts, no real community interest |
| Fundraising | VC raises; recurring names mentioned: Bitget / Malstrom, HackVC |
| Listings | Perps on Binance first, then other CEXes; spot often delayed |
| OI vs interest | OI looks manipulated relative to volume / social interest |
| Shakeouts | Several shakeouts before the “real” pump; author believes the operator controls most OI across venues |

**Claimed outcome when it “works”:** run from ~$0.3–0.4 toward **$10–20** in ~1–2 weeks.  
**Author’s practical exit habit:** often jumps ship around **~$8** (up a lot; less confident farming funding further).

### Watchlist → entry confluence (author’s checklist)

1. Move **above ~$1**
2. **Violent OI increase that holds >12h** (often 2–3× in 1–6h after weeks/months of flat OI)
3. Shift into **positive funding**
4. Large OI increase on **Aster or Bitget** vs comparable markets (early tell; e.g. LAB OI comparable to ENA/TAO/ZEC on Aster before the move)
5. **Presale / lockup** with a movable date (Echo / Legion often) — not required; theorized as public attention + distribution / short-bait mechanics
6. **Onchain wash trading**, similar lockup/distro platforms, frequent supply moves via Bitget cold wallet (confirmation of “the group,” not a trade trigger)
7. After >$1 + positive funding: within **~48h**, want a strong move **above ~$2.30** and funding to go **deeply negative** (~1–2%/hour). Thereafter: funding should cycle **very negative ↔ ~0**; any sustained **positive** funding is a bad tell (late longs / shorts exiting)
8. **Obvious depegs**: perp vs perp across CEX, and onchain vs CEX spot — theorized as how extreme funding is sustained given operator control of OI / onchain bundle

### Failure mode

Some names set up the same way but never hit whatever short-threshold / metrics the operator needs, then get **dropped dead**. Early small size + trim on the run can still work (`$BSB`, `$POWER`).

---

## Type B — “Alt crime” (memecoins / DWF-linked)

**Examples:** `$SIREN` `$PIPPIN` `$JELLYJELLY` `$BANANAS31`  
**Failed:** `$SWARMS`

- Often old memecoins that used to be “real” projects.
- Supply accumulated cheap over months (or bought from original team — Siren).
- **DWF** called as operator for Siren; suspected for others.
- More random; associated with **Gate.io** and large supply ending there.
- More readable with strong onchain tooling (wallet reuse, DCA-in vs wash-out).
- Author suspects laundering angle once size is huge; fewer clean “setup” tells than golden crime.

---

## Type C — Old thin coins (hardest)

**Good examples:** `$STO` `$AKE`  
**Failed:** `$JUNCTION`  
**Suspected:** `$REZ`

- Coins older than ~1 year, often **$20–50M** MC, accumulated then squeezed hard.
- Hard to size; frequent losses for the author.
- Highest multiples when right; more frequent lately while author was less engaged.
- Suspected similar mechanic to golden crime (bait + liquidate shorts with a bundle) but needs more research.

**Operator taxonomy guess (from Token2049 conversation):** golden-crime operators may also run related short-liquidation games (`$CT` vs `$REZ` look different); DWF-style old onchain coins may mix **laundering + profit**.

---

## What they already tried building (prior art)

| Effort | Outcome |
|--------|---------|
| Full BNB-chain tx indexing + wallet history on coins of interest + AI analysis | Expensive; friend went quiet; abandoned |
| Bubble maps / cluster inspection | Interesting anomalies; **did not help execution** |
| **OI + volume monitor across CEX vs Aster** | Best practical tool — some setups “stand out obviously”; not a catch-all (not everything uses Aster) |

**Open research hope:** patterns in wallet transfers / wash trading / MM or algo habits — author believes the data exists but they never got deep enough.

---

## Implied research stack (for later stages)

Roughly, the conjecture decomposes into:

1. **Candidate discovery** — listings, CMC top 500, tokenomics, social “ghost” score, price/FDV band  
2. **OI / funding / venue anomalies** — cross-CEX + Aster/Bitget emphasis  
3. **Structure tells** — lockups, Echo/Legion, Bitget supply moves  
4. **Phase detection** — $1 → OI spike → +funding → $2.30 + deep −funding → depegs  
5. **Exit / risk rules** — funding regime, ~$8 habit, fail-dead recognition  
6. **Onchain graph** — wash, clusters, wallet reuse (secondary; costly; weak for execution so far)

Nothing in this folder implements those yet.
