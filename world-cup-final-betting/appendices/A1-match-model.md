# AGENT 1 — Match Model: 2026 FIFA World Cup Final

**Spain vs. Argentina — Sunday, July 19, 2026, 3:00 PM ET, MetLife Stadium, East Rutherford NJ**

Built July 19, 2026. All factual claims are sourced inline. Model outputs are labeled as model outputs, not facts. Every probability is given as a RANGE reflecting data uncertainty.

---

## 1. Verified Inputs (with sources)

### Route to the final and goal totals

**Spain** (route, per the tournament final preview):
| Round | Opponent | Result | Date |
|---|---|---|---|
| Group | Cape Verde | 0–0 | Jun 15 |
| Group | Saudi Arabia | 4–0 | Jun 21 |
| Group | Uruguay | 1–0 | Jun 26 |
| R32 | Austria | 3–0 | Jul 2 |
| R16 | Portugal | 1–0 | Jul 6 |
| QF | Belgium | 2–1 | Jul 10 |
| SF | France | 2–0 | Jul 14 |

Totals: **~13–14 goals scored, 1 conceded** in 7 games. Source: https://en.wikipedia.org/wiki/2026_FIFA_World_Cup_final (lists 14 GF / 1 GA). Opta phrases it as "outscored their opponents 13-1" — https://theanalyst.com/articles/spain-vs-argentina-prediction-world-cup-final-2026-match-preview . **DISCREPANCY (13 vs 14 GF) — minor, does not change the model.** The single goal conceded was Belgium's in the QF.

**Argentina** (route):
| Round | Opponent | Result | Date |
|---|---|---|---|
| Group | Algeria | 3–0 | Jun 16 |
| Group | Austria | 2–0 | Jun 22 |
| Group | Jordan | 3–1 | Jun 27 |
| R32 | Cape Verde | 3–2 (a.e.t.) | Jul 3 |
| R16 | Egypt | 3–2 | Jul 7 |
| QF | Switzerland | 3–1 (a.e.t.) | Jul 11 |
| SF | England | 2–1 | Jul 15 |

Totals: **19 goals scored, 6 conceded** in 7 games (two of which went to extra time, adding ~60 min). Source: https://en.wikipedia.org/wiki/2026_FIFA_World_Cup_final . SF comeback (Enzo Fernández 85', Lautaro Martínez 90+2') confirmed at https://www.espn.com/soccer/story/_/id/49369105 and https://www.nbcnews.com/sports/soccer/live-blog/england-argentina-world-cup-2026-july-15-live-updates-rcna587325 .

### Advanced/defensive stats (VERIFIED)
- Spain opponent xG per match: **0.31 (lowest of any side)**; **6 clean sheets** (most by any team in a single WC); 37 matches unbeaten in regulation. Source: https://theanalyst.com/articles/spain-vs-argentina-prediction-world-cup-final-2026-match-preview
- Per-team offensive xG figures for each side were **NOT published in any source I could fetch — UNVERIFIED.** Attack strength is therefore inferred from verified goals-for rates, not xG.

### Rest / fatigue (VERIFIED from dates)
- Spain: last played **Jul 14** → **5 days' rest**, no extra time in the tournament.
- Argentina: last played **Jul 15** → **4 days' rest**, and played **two extra-time matches** (R32, QF) — more accumulated minutes and legs. Net: **modest freshness edge to Spain.**

### Ratings / market (VERIFIED)
- **Opta Supercomputer (25,000 sims):** Spain win in 90' **45.0%**, draw **29.0%**, Argentina win in 90' **26.0%**; **to lift trophy: Spain 59.6%, Argentina 40.4%.** https://theanalyst.com/articles/spain-vs-argentina-prediction-world-cup-final-2026-match-preview
- **Elo (eloratings.net, as of ~Jul 17):** Spain **~2232 (#1)**, Argentina **~2200 (#2)** — a ~32-point gap ≈ a small favorite edge to Spain. Sourced via search of https://eloratings.net/2026_World_Cup (the live page renders via JS; numbers are from the search index snapshot — treat as **approximate**).
- **Squawka Signal:** Spain 59.3% to win the final. https://www.squawka.com/us/outright-markets/world-cup-2026-outright-odds/
- These independent sources cluster tightly (~59–60% Spain trophy), which raises confidence in the central tendency.

### Lineups / injuries (VERIFIED, but "expected" = provisional)
- **Spain (4-3-3, de la Fuente):** Oyarzabal up top; Yamal & Baena wide; Rodri, Fabián Ruiz, Dani Olmo midfield. **Pedri NOT in projected XI.** Yamal expected fit despite a semifinal limp; Pedro Porro a minor doubt but expected to play; only confirmed absentee **Yeremy Pino** (shoulder). No suspensions. Source: https://www.sportsmole.co.uk/football/spain/world-cup-2026/predicted-lineups/yamal-status-and-pedri-decision-predicted-spain-xi-vs-argentina_601303.html and https://www.rotowire.com/soccer/article/spain-vs-argentina-preview-predicted-lineups-team-news-tactical-analysis-2026-world-cup-final-123191
- **Argentina (4-3-3, Scaloni):** Messi central alongside **Julián Álvarez** and **Giuliano Simeone**; Paredes, Enzo Fernández, Mac Allister midfield. **Fully fit 26-man squad.** Note: this projection has **Lautaro Martínez on the bench** despite his SF winner — a lineup uncertainty. Same sources.

### Referee (VERIFIED)
- **Slavko Vinčić (Slovenia).** Card tendencies: 2026 WC avg **2.33 yellows/game**; 2025/26 season **2.91 yellow / 0.22 red per game**; career **4.19 yellow / 0.23 red**. Sources: https://bolavip.com/en/world-cup/2026-world-cup-what-is-slavko-vincics-average-cards-per-match and https://www.statshub.com/referee/slavko-vincic/68557

### Weather (VERIFIED, approximate)
- East Rutherford, afternoon of Jul 19: **high ~87–92°F**, some sources note possible **haze/smoke**, WNW winds 10–20 mph. Hot afternoon kickoff → slower pace, less sustained high pressing, mild suppression of total goals; modestly favors the more possession-based, energy-conserving side (Spain) and compounds Argentina's fatigue. Source: https://www.accuweather.com/en/us/east-rutherford/07073/july-weather/344423 (monthly forecast — a single-day figure this far out is **inherently uncertain**).

---

## 2. Model Framework

**Bivariate/independent-Poisson with a Dixon-Coles low-score adjustment.** I estimate each team's expected goals (λ) for THIS match, build the score grid, and derive all markets. ET/penalties for the "lift trophy" market are modeled as a strength-tilted coin flip.

### Deriving expected goals (λ) — MODEL INPUTS, not facts
Verified rate priors:
- Spain: ~1.9 goals/90 scored; ~0.14 conceded/90 (elite; opp xG 0.31/game).
- Argentina: ~2.5 goals/90 scored and ~0.78 conceded/90 **after** deflating the two extra-time games to a per-90 basis (raw 19/6 over 7 games overstates both).

Adjustments applied (each labeled, directional):
1. **Opposition quality.** Argentina's attack meets the tournament's best defense (opp xG 0.31) → strong suppression of Argentina's λ. Spain's attack meets a good-but-leaky Argentina back line (conceded in 4 of 7, needed two comebacks) → mild suppression only.
2. **Final-stage effect.** WC finals trend cagey/lower-scoring → small downward nudge to both.
3. **Heat + fatigue.** Slower game, Argentina 4 days rest + 2 ET matches → small downward nudge to Argentina, small relative lift to Spain's control.

**Central λ (model):** Spain **1.35**, Argentina **1.00** (match total ≈ 2.35 goals).
**Plausible λ ranges:** Spain **1.20–1.55**, Argentina **0.85–1.20**.

**Validation:** independent Poisson on λ(1.35, 1.00) yields Spain 44.8% / draw 27.5% / Arg 27.7% in 90'; a mild Dixon-Coles boost to the draw gives ~44 / 28 / 28. The trophy calc below reproduces Opta's 59.6/40.4 almost exactly — a good external check.

---

## 3. Outputs (all ranges are honest uncertainty bands)

### 3.1 — 1X2 (90 minutes)
| Outcome | Model central | Range | Opta (external) |
|---|---|---|---|
| **Spain win** | ~44% | **41–47%** | 45.0% |
| **Draw** | ~28% | **26–30%** | 29.0% |
| **Argentina win** | ~28% | **25–30%** | 26.0% |

My model is fractionally kinder to Argentina than Opta; I therefore give ranges that contain both.

### 3.2 — Asian handicap fair lines (fair decimal odds; implied % of stake-at-risk)
| Line | Fair odds (central) | Implied win-equiv | Range on implied |
|---|---|---|---|
| Spain **−0.5** (= Spain to win) | ~2.23 | 44.8% | 41–47% |
| Spain **−0.25** | ~1.93 | ~52% | 48–56% |
| Spain **0** (draw-no-bet) | ~1.62 | ~61.8% | 58–65% |
| Spain **+0.25** | ~1.47 | ~68% | 64–72% |
| Argentina **+0.5** (draw or Arg win) | ~1.40 | 55.2% | 53–59% |
| Argentina **+0.25** | ~2.08 | ~48% | 44–52% |
| Argentina **0** (DNB) | ~2.62 | ~38.2% | 35–42% |
| Argentina **−0.5** (= Arg to win) | ~3.61 | 27.7% | 25–30% |

### 3.3 — Over/Under (total goals)
| Line | Over | Under |
|---|---|---|
| **1.5** | **65–71%** (central 68%) | 29–35% (32%) |
| **2.5** | **38–45%** (central 42%) | 55–62% (58%) |
| **3.5** | **18–24%** (central 21%) | 76–82% (79%) |

Low-total lean is deliberate: elite Spain defense + heat + final-stage caution.

### 3.4 — Both Teams To Score
| | Central | Range |
|---|---|---|
| **BTTS Yes** | ~47% | **43–51%** |
| **BTTS No** | ~53% | **49–57%** |

BTTS is held down mainly by the strong chance Spain keeps a clean sheet (they have 6 this tournament).

### 3.5 — Top 6 correct scores (model; Dixon-Coles-adjusted ordering)
| Score | Central prob | Range |
|---|---|---|
| **1–0 Spain** | ~13% | 11–15% |
| **1–1** | ~13% | 11–15% |
| **0–0** | ~9.5% | 8–11% |
| **0–1 Argentina** | ~9.5% | 8–11% |
| **2–1 Spain** | ~8.7% | 7–10% |
| **2–0 Spain** | ~8.7% | 7–10% |

(2–1 Argentina ~6.4% and 0–2 Argentina ~4.8% are the next most likely.)

### 3.6 — To LIFT THE TROPHY (incl. extra time / penalties)
Model: `P(win 90') + P(draw 90') × P(win the ET/shootout phase)`. ET/pens treated as a coin flip tilted to Spain (~55%) for superior squad strength, freshness edge, and Argentina's heavier legs.
| Team | Central | Range | Opta |
|---|---|---|---|
| **Spain** | ~59% | **56–62%** | 59.6% |
| **Argentina** | ~41% | **38–44%** | 40.4% |

### 3.7 — Player & discipline props (LOW–MEDIUM confidence)
Anytime scorer via `1 − e^(−player match-xG)`, player xG inferred from verified tournament goals and role (not from published shot-level xG — **UNVERIFIED at that granularity**).
| Player | Anytime scorer (central) | Range | Confidence |
|---|---|---|---|
| Mikel Oyarzabal (ESP, 5 tourn. goals, lone 9) | ~33% | 28–38% | Medium |
| Lionel Messi (ARG, 8 goals — co-Golden Boot) | ~27% | 22–33% | Medium |
| Lamine Yamal (ESP, winger) | ~24% | 20–30% | Low–Med |
| Julián Álvarez (ARG, projected starter) | ~22% | 17–28% | Low |
| Lautaro Martínez (ARG, SF winner, may start on bench) | ~20% | 15–27% | Low (lineup risk) |

Messi's number understates his impact — he is Argentina's chief creator (4 assists), so his *involvement* in a goal is much higher than his scoring odds. Golden Boot standings source: https://www.goal.com/en/lists/world-cup-2026-golden-boot-standings-fifa-award/blt29fdba0896b8fd09 and https://www.espn.com/soccer/story/_/id/49117037 ; Oyarzabal 5 per same.

**Cards (LOW confidence):** Vinčić lets play flow (2.33 yellows/game this WC) but a high-stakes final and Argentina's tactical fouling push it up. Model total booking points ~4–5.5. **Over 3.5 total cards ~55–65%**; a red card is unlikely (~12–18%). Data is thin — treat as indicative only.

---

## 4. Assumptions (stated explicitly)
1. λ(Spain)=1.35, λ(Argentina)=1.00 are **model estimates** derived from verified goal rates plus the labeled adjustments in §2 — not published facts.
2. Per-team offensive **xG was not available**; attack strength is inferred from goals-for, which is noisier than xG.
3. Argentina's raw 19/6 is deflated for two extra-time games; the exact deflation is judgment.
4. Independence of the two scores is assumed, softened by a mild Dixon-Coles correction (low scores/draws nudged up). Rho not fitted to data — assumed (~−0.05 to −0.10).
5. Expected lineups are **provisional**; a late change (e.g., Yamal or Porro not fit, Lautaro starting) would move the props and slightly the team λ.
6. ET/shootout modeled as a strength-tilted coin flip (~55% Spain) — a simplification.
7. Weather is a **monthly-outlook** figure; a cooler or wetter day would reduce the heat adjustment.
8. Elo point values come from a search snapshot, not a rendered page — treat as approximate.
9. No home advantage applied (neutral venue in the U.S.; both traveling), though Argentina likely enjoys a louder crowd — not quantified.

---

## 5. Summary & Three Biggest Uncertainties

**Central estimate.** This is a match Spain should be a clear but not overwhelming favorite to control. My model lands at **Spain ~44% / Draw ~28% / Argentina ~28%** over 90 minutes, and **Spain ~59% / Argentina ~41% to lift the trophy** — essentially identical to the Opta supercomputer (45/29/26 and 59.6/40.4) and to the Elo/Squawka signals, which strengthens confidence in the central tendency. I expect a **low-scoring, cagey final** (total goals ≈ 2.3–2.4; Under 2.5 favored ~58%, BTTS No slightly favored ~53%), driven by the tournament's best defense (Spain, opp xG 0.31, six clean sheets), the final-stage caution effect, and a hot afternoon kickoff that compounds Argentina's thinner rest (4 days plus two extra-time games). Most likely scores are 1–0 Spain and 1–1, then 0–0. Oyarzabal (~33%) and Messi (~27%) are the leading anytime-scorer picks, with Messi's true danger sitting in his creation rather than his finishing.

**Three biggest uncertainties.** (1) **Argentina's true attacking level against elite defense** — I had no per-team xG, so I inferred their λ from goals-for and a judgment-based deflation of two extra-time games; if Argentina's finishers (Messi, Álvarez, Lautaro) click, the single-goal margin flips easily. (2) **Lineups and fitness** — Yamal's semifinal limp, Porro's muscle doubt, and whether Lautaro Martínez starts are all unresolved and materially move the props and, at the margin, the team λ. (3) **The extra-time/shootout coin flip** — with ~28% of outcomes going to a draw, a large share of the trophy question rides on a phase I could only model heuristically at ~55% Spain; a small mis-estimate there swings the trophy probabilities by several points.
