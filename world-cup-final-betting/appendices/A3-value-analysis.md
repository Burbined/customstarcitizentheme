# AGENT 3 — Value Identification
## 2026 FIFA World Cup Final: Spain vs. Argentina — MetLife, Sun Jul 19 2026, 3:00 PM ET

Built July 19, 2026 (match day). Inputs: Agent 1 model probabilities + Agent 2 documented (stale) market prices.
**EV% = (model_prob × decimal_odds) − 1.** American→decimal: +X → (X/100)+1; −X → (100/X)+1.
All model probs and odds are cross-checked against the two source files. **Every price here is 1–4 days stale** (see §5).

Cross-check of key numbers vs. files (CONFIRMED): Spain 44% (41–47) / Draw 28% (26–30) / Arg 28% (25–30) 90'; Spain lift 59% (56–62) / Arg lift 41% (38–44); Under 2.5 central 58% (55–62); Over 2.5 42% (38–45); BTTS Yes 47% (43–51) / No 53% (49–57). Scorer: Oyarzabal 33% (28–38), Messi 27% (22–33), Yamal 24% (20–30), Álvarez 22% (17–28), Lautaro 20% (15–27).

---

## 1. FULL EV TABLE

Decimal odds shown once; EV computed at model LOW / CENTRAL / HIGH. **Bold = positive EV.**

| Market | Best price | Dec | Model L/C/H | EV @ Low | EV @ Central | EV @ High | Survives whole range? |
|---|---|---|---|---|---|---|---|
| **Spain 90' ML** | +130 | 2.300 | 41/44/47% | −5.7% | **+1.2%** | **+8.1%** | No — flips − at low |
| **Draw 90'** | +200 | 3.000 | 26/28/30% | −22.0% | −16.0% | −10.0% | No (all −) |
| **Argentina 90' ML** | +260 (fresh) | 3.600 | 25/28/30% | −10.0% | **+0.8%** | **+8.0%** | No — flips − at low |
| Argentina 90' ML | +275 (stale open) | 3.750 | 25/28/30% | −6.3% | **+5.0%** | **+12.5%** | No — flips − at low |
| **Spain to lift** | −150 | 1.667 | 56/59/62% | −6.7% | −1.7% | **+3.3%** | No (− at central) |
| **Argentina to lift** | +136 | 2.360 | 38/41/44% | −10.3% | −3.2% | **+3.8%** | No (− at central) |
| Under 2.5 | −135 (stale open) | 1.741 | 55/58/62% | −4.3% | **+1.0%** | **+7.9%** | No — flips − at low |
| Under 2.5 | −155 (mid) | 1.645 | 55/58/62% | −9.5% | −4.6% | **+2.0%** | No (− at central) |
| Under 2.5 | −165 (current close) | 1.606 | 55/58/62% | −11.7% | −6.9% | −0.4% | No (all ≤0) |
| Over 2.5 | +125 | 2.250 | 38/42/45% | −14.5% | −5.5% | **+1.3%** | No (− at central) |
| BTTS Yes | −110 | 1.909 | 43/47/51% | −17.9% | −10.3% | −2.6% | No (all −) |
| BTTS No | −118 | 1.847 | 49/53/57% | −9.5% | −2.1% | **+5.3%** | No (− at central) |
| **Messi ATGS** | +155 | 2.550 | 22/27/33% | −43.9% | −31.2% | −15.9% | No (all strongly −) |
| **Oyarzabal ATGS** | +450 (FanDuel) | 5.500 | 28/33/38% | **+54.0%** | **+81.5%** | **+109.0%** | YES — but price suspect (§4) |
| Oyarzabal ATGS | +200 (LSB) | 3.000 | 28/33/38% | −16.0% | −1.0% | **+14.0%** | No (− at central) |
| **Yamal ATGS** | +650 (FanDuel clean) | 7.500 | 20/24/30% | **+50.0%** | **+80.0%** | **+125.0%** | YES — but price/model suspect (§4) |
| Yamal ATGS | +270 (LSB, mislabeled?) | 3.700 | 20/24/30% | −26.0% | −11.2% | **+11.0%** | No (− at central) |
| **Lautaro ATGS** | +700 | 8.000 | 15/20/27% | **+20.0%** | **+60.0%** | **+116.0%** | YES — but lineup risk (§4) |

Notes: "fresh" Argentina +260 is the honest current best (opener +275 already gone). Under 2.5 shown at three points because it steamed −135→−165 during the window; only the STALE −135 was ever +EV at central, and it no longer exists.

---

## 2. RANKED POSITIVE-EV LIST (by central-EV edge, with confidence grade)

Grade key: **A** = edge survives full model range + fresh price + solid data; **B** = survives central but marginal on one axis; **C** = fragile (dies inside range, or stale price, or soft/suspect data).

| Rank | Bet | Central EV | Grade | One-line rationale |
|---|---|---|---|---|
| 1 | **Yamal ATGS +650** | +80.0% | **C** | Only outlier where edge survives the whole 20–30% band. But see §4 — most likely the model scorer estimate is too high and/or the price predates the semifinal knock. Treat as speculative, quarter-stake at most, or no-bet. |
| 2 | **Oyarzabal ATGS +450** | +81.5% | **C** | Edge survives full band, but LSB shows the same market at +200 (≈fair). The +450 is probably a mislabeled/different market. Do NOT size as if the edge is real until the +450 is confirmed a clean ATGS. |
| 3 | **Lautaro ATGS +700** | +60.0% | **C** | Big number but he is projected to START ON THE BENCH. If he starts, +700 is a gift; if he's a sub, true prob is well below the 20% central. Pure lineup gamble. |
| 4 | **Spain 90' ML +130** | +1.2% | **C** | Real, sharp-market-adjacent number, but edge is <3% (inside model noise) and FLIPS NEGATIVE at the 41% low end. No-bet by the §5 threshold. |
| 5 | **Argentina 90' ML +260** | +0.8% | **C** | Sub-1% edge, dies at the 25% low end, and price is public-inflated (drifted IN). Effectively a coin-flip on model error. No-bet. |
| — | Argentina 90' +275 | +5.0% | (dead) | Would be a real edge — but it is the STALE opener and is gone (now +255/+260). Listed only to show the opener had value. |
| — | Under 2.5 −135 | +1.0% | (dead) | Was marginally +EV at the opener; the current −155/−165 is negative at central. The value already closed. |

**Bottom line on "real" bets:** After removing stale-price mirages and the suspect-price props, **there is no clean, confident, positive-EV bet on this board.** The only edges that survive their full model range are the three long-shot scorer props, and every one of them is Grade C for a specific, nameable reason (§4). Everything at "sensible" odds (Spain ML, Arg ML, Under, to-lift both sides) is either negative at central or a sub-3% edge inside model noise.

---

## 3. REJECTED LIST (negative EV at documented best price — no sentiment exceptions)

Stated plainly, including the popular/emotional plays:

- **Draw +200 — REJECTED.** −16% at central, negative across the entire 26–30% range. Not close.
- **Messi anytime scorer +155 — REJECTED, emphatically.** −31% at central; −16% even at the generous 33% high end. The narrative bet is the single worst-priced popular play on the board. Messi's value is in creation (4 assists), not finishing — his ATGS is a trap. (Score-or-Assist at −138 is a separate market and closer to fair, but not evaluated here as no model number exists for it.)
- **Spain to lift −150 — REJECTED at central.** −1.7% central; only turns + (+3.3%) at the 62% high end. The mass-market "Spain lifts the cup" bet is a small negative-EV hold at −150 and worse (−175 elsewhere). Not a value bet even though Spain is the correct side of the match.
- **Argentina to lift +136 — REJECTED at central.** −3.2% central; the public/Messi-narrative underdog trophy bet only clears zero (+3.8%) at the 44% high end.
- **BTTS Yes −110 — REJECTED.** −10% central, negative across the whole 43–51% range. Casual "both teams score in a final" money.
- **BTTS No −118 — REJECTED at central.** −2.1% central; only + at the 57% high end. Slightly less bad than Yes, still no-bet.
- **Over 2.5 +125 — REJECTED.** −5.5% central. Casual "it's a final, goals will come" money fighting the model and the sharp Under steam.
- **Under 2.5 at the CURRENT price (−155/−165) — REJECTED.** −4.6% to −6.9% at central. The Under was the value at −135; at the steamed close the value is gone. Do not chase it.
- **Messi/Argentina/"Spain to lift" as a group — REJECTED.** Every crowd-favorite, TV-graphic bet on this match is negative-EV at documented prices. There are no sentiment exceptions here.

---

## 4. WHY-MISPRICED HYPOTHESES vs. "MY MODEL IS WRONG" (per positive candidate)

**Yamal ATGS +650 (implied 13.3%) vs model 24% — the headline outlier. Interrogated hard:**
- *Mispriced hypothesis:* Casual money floods the two big narrative scorers (Messi, and the lone striker Oyarzabal), leaving the winger's number lazily set; wingers are chronically under-bet for ATGS. A clean +650 could be a soft, un-sharpened price.
- *Model-is-wrong hypothesis (STRONGER here):* (1) **The price is very likely post-injury-aware and the model is not.** Yamal took a semifinal knock; Agent 1 only has him "expected fit" and applies NO minutes/fitness haircut to his 24%. A book that thinks he starts hobbled, plays 60 mins, or is a game-time decision would rationally price ~13%. (2) **The scorer model is soft by construction** — Agent 1 built ATGS from inferred team goals, not shot-level xG, and flags Yamal himself "Low–Med." (3) In a cagey, low-total final (model total 2.35, Under favored), a wide forward's individual scoring rate should compress. (4) Sources disagree on the price by 380 cents (+270 vs +650), so the +650 itself is low-confidence. **Verdict: the 24% is more likely too high than the market being 80% wrong.** A hobbled or 24%→~16% "true" Yamal makes +650 roughly fair, not a windfall. If he is confirmed fully fit and starting, a small stake has genuine value; if there is ANY start/fitness doubt at the counter, pass.

**Oyarzabal ATGS +450 vs model 33%:**
- *Mispriced hypothesis:* he is the lone number-9 and Spain's focal finisher (5 tourn. goals); a +450 lone-striker ATGS would be a real overlay.
- *Model-is-wrong / price-is-wrong hypothesis (STRONGER):* Agent 2 documents the SAME market at **+200 (LSB)**, which is ≈fair-to-slightly-negative vs 33%. A 250-cent gap between two sources on the same player, same week, is the signature of a **mislabeled or different market** (e.g., "first/last" or a shots-based line dressed as ATGS), not a live overlay. **Verdict: do not trust the +450 as a clean ATGS.** At the credible +200 the bet is −1% central — a pass. The apparent edge is a data artifact, not value.

**Lautaro ATGS +700 vs model 20%:**
- *Mispriced hypothesis:* the market may still be pricing him as a bench player after the projection had him benched despite his SF winner; if Scaloni starts his in-form finisher, +700 is stale-cheap.
- *Model-is-wrong hypothesis:* Agent 1's 20% already carries heavy lineup risk and is "Low confidence." If he is genuinely a substitute (30–60 mins), true ATGS is closer to 10–12% and +700 is fair. **Verdict: this is a lineup bet, not a model bet.** Its EV is entirely a function of the team sheet, which is unknown. Decide only after confirmed XI.

**Spain 90' ML +130 (central +1.2%) and Argentina 90' ML +260 (+0.8%):**
- *Mispriced hypothesis:* books shade the mass-market favorite and the public over-backed Argentina (58–59% of bets/money on the underdog), which could leave thin value on BOTH regulation sides simultaneously across different books.
- *Model-is-wrong hypothesis:* both edges are <3% and vanish at their low endpoints — well inside the model's own admitted uncertainty (no per-team xG, judgment-based ET deflation). **Verdict: indistinguishable from model noise.** More likely "no edge" than "real edge." Neither is a bet.

---

## 5. BRUTAL HONESTY

- **Every price in this analysis is 1–4 days stale.** Agent 2 could not pull a single live match-day quote (books JS-rendered/geo-blocked). Any edge computed above is against a **paper price that may not exist at the 3 PM ET counter.**
- **Lines have already moved, and against the value:** Under 2.5 steamed **−135 → −155/−165** (the one +EV central number, −135, is dead); Argentina shortened **+275 → +255/+260** (the +5% opener edge is gone); Draw drifted +195→+200; Spain to-lift got *cheaper* −164→−150 (good for late Spain backers, bad CLV for early ones). **Assume any listed edge computed against a stale price is already gone or shrunk at the real counter.**
- **The ~3% noise floor:** the model itself carries wide, self-declared uncertainty (no shot-level xG, inferred λ, provisional lineups, heuristic ET coin-flip). **Any edge under ~3% EV is inside that noise and must be treated as NO-BET.** That kills Spain +130 (+1.2%), Argentina +260 (+0.8%), and the dead Under −135 (+1.0%). It leaves only the three long-shot scorer props as nominally >3% — and all three are Grade C for reasons unrelated to the size of the number (injury, mislabeled price, lineup risk).
- **The outlier discipline:** a "+80% EV" on Yamal or Oyarzabal is not a green light — it is a red flag that a model input or a price label is wrong. In real markets, an 80% edge on a mainstream final almost never survives contact; the base rate says the error is on our side, not the book's.

### SINGLE MOST IMPORTANT CAVEAT
**There is no clean, confident, positive-EV bet on this board.** The only edges that survive their full uncertainty range are three long-shot scorer props whose "value" is almost certainly an artifact — a pre-injury/no-fitness-haircut model (Yamal), a mislabeled price (Oyarzabal +450 vs a fair +200 elsewhere), or an unresolved team sheet (Lautaro). Every sensibly priced market is either negative at the model's central estimate or a sub-3% edge inside model noise, and computed against prices that are 1–4 days stale and have already moved away from the value. **Do not bet off these numbers without a live, confirmed-lineup, post-injury-news re-quote at the actual counter.**
