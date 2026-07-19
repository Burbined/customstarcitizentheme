# AGENT 4 — Bankroll & Risk Management
## 2026 FIFA World Cup Final: Spain vs. Argentina — MetLife, Sun Jul 19 2026, 3:00 PM ET

Built July 19, 2026 (match day). Inputs: Agent 1 model, Agent 2 (stale) prices, Agent 3 value screen.
All sizing is expressed as a percentage of a betting bankroll **B** (no dollar amount assumed). B is money you can lose entirely without changing your life — not net worth, not rent.

---

## 0. HEADLINE RECOMMENDATION (read this first)

**The default correct action is to bet NOTHING, or near-nothing, on this match.**

Agent 3's conclusion is unambiguous: there is **no clean, confident, positive-EV bet on this board.** Every sensibly priced market (Spain ML, Argentina ML, Under, both to-lift sides, BTTS) is either negative at the model's central estimate or a sub-3% edge sitting inside the model's own admitted noise, and every price is 1–4 days stale and has already moved *against* the value. The only edges that survive their full model range are three long-shot scorer props, and all three are Grade C because their "value" is most likely an artifact (a pre-injury/no-fitness-haircut model for Yamal, a probably-mislabeled +450 for Oyarzabal, and an unresolved team sheet for Lautaro).

A staking plan's job includes outputting **zero**, and here that is the honest primary output. **If you cannot get a live, re-quoted price at the counter with a confirmed team sheet and post-injury news, the plan is: stake 0% of B. Walk away. Watch the game.**

Everything below is the *conditional, maximum* plan — what you may risk **only if** you actively want recreational skin in the game AND the specific gates in §2 are met at a live book. It is a ceiling, not a target. The correct expected size of this whole exercise, honestly, rounds to zero.

---

## 1. WHY SO SMALL — THE FRAMING

Kelly sizing answers "what fraction maximizes long-run log-growth **if my probabilities are true**." We have demonstrably shaky probabilities: Agent 1 built scorer props from inferred team goals, not shot-level xG, and self-graded them Low / Low–Med; Agent 2 could not pull one live match-day quote; Agent 3 showed the surviving edges are almost certainly input errors, not market errors. When the *edge itself is suspect*, textbook Kelly on the central probability systematically **overbets**, because it treats a possibly-fictional edge as real. The entire staking structure below is therefore built to be robust to being wrong, not to maximize an edge we don't trust.

---

## 2. GATED, QUARTER-KELLY SIZING PER CANDIDATE (maximum, not target)

**Kelly:** f\* = (bp − q) / b, where b = decimal odds − 1, p = win probability, q = 1 − p.
**Quarter-Kelly:** f = f\* / 4.
**Rule applied here:** use the **LOW end** of Agent 1's probability band, not the central estimate.

**Why the low end is correct when the edge is suspect.** Kelly assumes p is the *true* probability. Our p is a point estimate wrapped in a wide, self-declared uncertainty band, and Agent 3 argues the true value is probably nearer the low end (injury haircut, lineup risk, mislabeled price). Full-probability Kelly treats the optimistic central number as certain and overbets in exact proportion to how wrong the central number is. Sizing off the **conservative low end** builds the edge-uncertainty directly into the stake: if the pessimistic read is right, we haven't overcommitted; if the optimistic read is right, we've merely left a little upside on the table — the correct asymmetry when the downside is "we bet real money on a model artifact."

### The math (low-end p, quarter fraction)

| Prop | Price | Dec | b | Low p | q | Full Kelly f\* = (bp−q)/b | Quarter f = f\*/4 | After 0.25% cap |
|---|---|---|---|---|---|---|---|---|
| **Yamal ATGS** | +650 | 7.50 | 6.5 | 0.20 | 0.80 | (1.30−0.80)/6.5 = **7.69%** | **1.92%** | **0.25%** |
| **Oyarzabal ATGS** | +450 | 5.50 | 4.5 | 0.28 | 0.72 | (1.26−0.72)/4.5 = **12.0%** | **3.00%** | **0.25%** |
| **Lautaro ATGS** | +700 | 8.00 | 7.0 | 0.15 | 0.85 | (1.05−0.85)/7.0 = **2.86%** | **0.71%** | **0.25%** |

**Even off the conservative low-end probability, quarter-Kelly still says 1.9%–3.0% of B per prop. We override that with a hard 0.25% cap.**

### The 0.25% hard cap, and why it binds

For a Grade-C long-shot prop, **model risk dominates estimation risk dominates everything.** The scorer probabilities are the softest numbers Agent 1 produced (no shot-level xG, provisional lineups, an unhaircut injury on Yamal, a bench question on Lautaro, a price two sources disagree on by 380 cents for Oyarzabal). Quarter-Kelly protects against *variance around a trusted edge*; it does nothing to protect against the edge being **fiction**, which is the live risk here. The 0.25% cap is a flat statement that the model is not trustworthy enough to earn more than a rounding-error stake, no matter how large Kelly computes the "edge." That the cap binds hard on all three (each Kelly number is 3×–12× the cap) is the tell: the numbers are too good to be true, so we refuse to size to them.

### Gating conditions (ALL must hold at a LIVE book, or stake = 0)

| Prop | Max stake | Gate — every condition required |
|---|---|---|
| Yamal ATGS | 0.25% B | Confirmed in starting XI **and** confirmed fully fit (no game-time-decision / limp / minutes-managed tag) **and** live price still ≥ **+600** at a real book. Any fitness doubt at the counter → 0. |
| Oyarzabal ATGS | 0.25% B | Confirmed starting as the lone 9 **and** the **+450 confirmed a clean anytime-goalscorer market** (not first/last/shots dressed up). If any book shows the same clean ATGS near +200, the +450 is a mislabel → 0. |
| Lautaro ATGS | 0.25% B | Confirmed in the **starting XI** (not bench). If he is a substitute, true prob collapses to ~10–12% and +700 is fair → 0. This is a team-sheet bet, decided only after the XI drops. |

Any gate not verifiable at kickoff → that stake is **0%**. "Expected to be fit" is not "confirmed fit." Missing information resolves to no-bet, not to hope.

---

## 3. TOTAL SINGLE-MATCH EXPOSURE CAP: ≤ 1% of B

**Across ALL bets on this one match, cap total staked at 1% of B.** Given the Grade-C confidence on everything that survived, the *practical* recommended ceiling after §4's correlation haircut is lower still (~0.5% B).

**Why a single-event cap exists even when Kelly sums higher.** Kelly is a *long-run, many-independent-bets* growth-optimizer. A World Cup final is a **single, non-repeating event** — you get one settlement, not a law-of-large-numbers average. Kelly's log-growth guarantee simply does not apply to a one-shot outcome; the realized result is all-or-nothing, and there is no "next hand" to regress toward the edge. On top of that, every input is correlated model error from *one* model built by *one* analyst off *stale* prices — so the "diversification" across the three props is far weaker than it looks (see §4). A single-event cap says: no lone match, however tempting the screen, gets to move the bankroll. 1% is already generous for a board this weak; it is a ceiling, not an allocation to fill.

---

## 4. CORRELATION — THE PORTFOLIO IS FEWER, BIGGER BETS THAN IT LOOKS

The three props are **not independent**, so summing their stakes as if diversified overstates the real diversification and *understates* the true risk per unit staked.

- **Yamal ↔ Oyarzabal: strongly POSITIVELY correlated.** Both are Spain attackers; both cash disproportionately in the same world — the one where **Spain scores 2+**. In a 1–0 or 0–0 Spain-defensive grind (the model's most likely scoreline, and Under 2.5 is favored), *both* tend to lose *together*. This is not two shots at goal; it is closer to **one leveraged bet on "Spain's attack fires."**
- **Lautaro ↔ the Spain pair: partially NEGATIVELY correlated.** Lautaro scores in an Argentina-scores / higher-total world, which is the *opposite* of the Spain-clean-sheet world the other two need. The negative leg dampens combined variance slightly — but it also means at least one prop is structurally likely to lose in any given outcome, so their EVs cannot simply be added as independent wins.
- **Scorer props ↔ team moneylines: correlated.** A Spain scorer prop is a *conditional* Spain-does-well bet. Stacking **Spain ML + a Spain scorer prop** is **not** two independent positions — it is one directional Spain bet with the scorer leg as leverage on top. **Do NOT stack Spain ML alongside Yamal/Oyarzabal and treat the total as diversified: you are doubling down on a single correlated view of the game, and your true exposure to "Spain underperforms" is roughly the sum of the stakes, not the offsetting mix a naive read implies.**

**Sizing consequence.** Because the two Spain props behave like ~1.5 effective bets rather than 2, the naive capped sum (0.25% × 3 = **0.75% B**) overstates diversification. Apply a correlation haircut to the positively-correlated Spain pair. Recommended correlation-adjusted ceiling:

| Prop | Per-prop cap | Correlation-adjusted recommended |
|---|---|---|
| Yamal ATGS | 0.25% B | **0.25% B** (keep the least-suspect single leg full) |
| Oyarzabal ATGS | 0.25% B | **0.15% B** (haircut: correlated with Yamal + mislabel risk) |
| Lautaro ATGS | 0.25% B | **0.10% B** (haircut: lineup risk; small independent/offsetting leg) |
| **Total staked** | 0.75% B | **≈ 0.50% B** |

0.50% B sits comfortably under the 1% single-match cap, with the gap deliberately reserved as the buffer the correlation demands. **Never bet the Spain ML on top of these as if it were a separate, uncorrelated position.**

---

## 5. HEDGING / IN-PLAY DECISION TREE

Governing principle: **hedging is only rational to cut variance on a LARGE position. This portfolio is deliberately tiny (≤0.5% B) and specifically built so it never needs hedging.** Every in-play "rescue" pays fresh vig; on a sub-1% book that vig is guaranteed to exceed any variance you'd smooth. So the tree is mostly "do nothing."

```
KICKOFF: only the §2-gated props are on, ≤0.5% B total. No in-play plan needed. Watch.

├─ Spain leads early (1–0, 2–0)
│     → HOLD. Do nothing. The Spain-scorer props are live and in their good world.
│       Do NOT "lock in" by laying — you'd pay vig to shrink a 0.25% ticket. Let it ride.
│
├─ 0–0 at ~70'  (the Under-ish, low-total world)
│     → Yamal/Oyarzabal/Lautaro are all quietly dying; that is the expected failure mode
│       of long-shot scorer props and it was PRICED IN when you staked 0.25%.
│       → NO rescue bet. Do NOT buy Under now (value long gone, §Agent 3), do NOT chase a
│         late-goal Over, do NOT parlay out. Chasing a 0.25% loss with a fresh -EV bet is
│         how a rounding-error becomes a real loss. Accept the likely small loss. HOLD.
│
├─ Argentina leads (0–1, 0–2)
│     → Do NOT hedge the Grade-C Spain props. They are 0.15–0.25% tickets; laying them off
│       in-play burns the spread/vig for essentially nothing saved. The maximum you can lose
│       is already the tiny stake you chose precisely so you'd never need to hedge.
│     → Lautaro leg may still be live (Argentina-scores world) — that is the intended internal
│       offset. Let the portfolio settle as designed. HOLD.
│
└─ Any scoreline, any minute
      → No in-play top-ups. No "doubling to get even." No live parlays. No new markets.
        The pre-match ticket is the entire position. HOLD to settlement.
```

**The rule, stated once:** hedging trades EV (via vig) for reduced variance, and is only worth it when the position is large enough that the variance genuinely threatens the bankroll. A ≤0.5% B portfolio threatens nothing. Therefore **we never hedge it** — that outcome was designed in at staking time, which is the *only* rational time to manage this risk.

---

## 6. STOP-LOSS

**This is a single event, so the stop-loss IS the exposure cap itself — set once, before kickoff, and never revisited.** The most you can lose is the ≤1% B (recommended ≤0.5% B) you staked pre-match. There is nothing to "stop" mid-game because there are no additional entries.

Explicit prohibitions (each is a way people turn a capped small loss into an uncapped large one):
- **No in-play top-ups** — the cap is the cap; a losing scoreline is not a buy signal.
- **No "recovering" losses live** — a down 0.25% ticket does not get chased with a new bet; that converts a rounding error into real money at fresh vig.
- **No parlays / same-game parlays** — they multiply the correlated model error and the hold; a soft edge parlayed is a guaranteed negative.
- **No re-staking after settlement** — one match, one settlement, done.

---

## 7. SCENARIO TABLE — recommended max portfolio (all §2 gates pass)

Stakes: **Yamal 0.25% B, Oyarzabal 0.15% B, Lautaro 0.10% B — total 0.50% B staked.** Net profit = (dec − 1) × stake per winning leg.

| Scenario | What happens | Bankroll impact |
|---|---|---|
| **Best case** | All three named players score | Y +6.5×0.25% = +1.625% ; O +4.5×0.15% = +0.675% ; L +7.0×0.10% = +0.70% → **≈ +3.0% B** (low joint prob; the Spain pair is positively correlated so "all three" is rarer than independence implies) |
| **Typical winning leg** | Exactly one prop hits | roughly **+0.2% to +1.3% B** net depending which leg, with the other two lost |
| **Expected case** (see discount below) | Probability-weighted | **≈ −0.05% to +0.08% B → round to ~0% B** |
| **Worst case** | None of the three score (the most-likely single outcome — a low-total or Spain-defensive final) | lose **every stake = −0.50% B** |
| **Exposure-cap floor** | Absolute bound by construction | can never exceed **−1% B**, the single-match cap |

**Worst case = total loss of all stakes.** On the recommended portfolio that is **−0.50% B**; had you sized every prop to the full 0.25% cap without the §4 correlation haircut it would be **−0.75% B**; and the §3 hard exposure cap guarantees the worst case can **never be worse than −1% B** no matter what. Long-shot scorer props lose most of the time — expect the worst case to be the *most common* single result, not a tail.

**Expected-case discount (stated explicitly).** Agent 3's central EVs (Yamal +80%, Oyarzabal +81.5%, Lautaro +60%) are almost certainly **artifacts** — an unhaircut injury model, a probably-mislabeled price, an unresolved team sheet. Taking them at face value is the exact error §1 warns against. I apply an **~80% haircut** to the stated central edge (i.e., assume at most ~20% of the printed EV is real, and quite possibly none of it is):
- Yamal 0.25% × (0.80×0.20) = +0.040% ; Oyarzabal 0.15% × (0.815×0.20) = +0.024% ; Lautaro 0.10% × (0.60×0.20) = +0.012% → **≈ +0.08% B** if you believe a fifth of the edge survives.
- If you take Agent 3's honest lean that the edge is **fully** an artifact, true EV reverts to a longshot book's hold (materially negative), and the expected case is **mildly negative, ~−0.03% to −0.07% B** — you are simply paying vig for entertainment.

Either way the expected value **rounds to zero**, which is the whole point: this is, at best, a break-even recreational flutter, not an investment. That is precisely why §0 says the default is to bet nothing.

---

## 8. WHY QUARTER-KELLY (NOT HALF, NOT FULL)

- **Full Kelly assumes your probability is the true probability.** We have shown, at length, that ours is not — no shot-level xG, inferred λ, provisional lineups, stale prices, and a value screen concluding the surviving edges are likely input errors. Full Kelly on a wrong p doesn't just underperform; near the optimum it **risks a large fraction of bankroll on a fictional edge**, and its drawdowns are brutal even when the edge is real.
- **Estimation error compounds multiplicatively.** Kelly is nonlinear in p; a modest overestimate of p produces a *disproportionate* overbet, and errors across correlated legs stack rather than cancel (§4). Fractional Kelly is the standard defense: **half-Kelly** already cuts growth-rate cost to ~25% of full while sharply reducing variance and ruin risk. **Quarter-Kelly** cuts it further — the right choice when the edge is not merely uncertain but *suspected fictional*. Here the fraction is doing real work: it is the mathematical expression of "we don't trust these numbers."
- **And even quarter-Kelly was still too big** — it printed 1.9%–3.0% per prop off the conservative low-end p, which is why the flat 0.25% cap (§2) overrides it. When your sizing method and your hard cap disagree by 8×–12×, the honest reading is not "the cap is too tight" — it is **"the edge is not real,"** and the plan sizes accordingly: at the floor, or at zero.

---

## APPENDIX — ONE-SCREEN SUMMARY

- **Default: bet 0% of B.** No confirmed live re-quote + confirmed XI + post-injury news → stake nothing.
- **Absolute per-prop cap:** 0.25% B (Kelly says more; model risk overrides).
- **Correlation-adjusted recommended (if all gates pass):** Yamal 0.25% / Oyarzabal 0.15% / Lautaro 0.10% = **0.50% B total.**
- **Single-match exposure cap:** ≤ **1% B**, hard.
- **Never** stack Spain ML with Spain scorer props as independent — they are one correlated view.
- **No hedging, no in-play top-ups, no chasing, no parlays.** The stop-loss is the pre-set cap.
- **Scenario (recommended portfolio):** best ≈ **+3.0% B** / expected ≈ **~0% B** (after 80% model-risk haircut) / worst = loss of all stakes = **−0.50% B**, bounded at **−1% B** by the cap.
