# Baseline data — Strava export, 6 Jul – 5 Aug 2026

Derived from the Strava bulk export (`export_115645287.zip`). Runs only; everything before
6 Jul 2026 excluded per instruction. Timestamps converted from UTC to SGT (+8).

## Run log

| Date (SGT) | Session | Dist | Moving | Pace | Elev +/- | HR avg/max |
|---|---|---|---|---|---|---|
| Mon 06 Jul | Night Run | 2.17 km | 14:21 | 6:36/km | +15 / -15 m | — / — |
| Fri 17 Jul | Evening Run | 1.68 km | 12:14 | 7:18/km | +2 / -2 m | — / — |
| Sat 18 Jul | 30 mins | 4.17 km | 30:19 | 7:17/km | +22 / -41 m | — / — |
| Mon 20 Jul | opened stride at end | 2.42 km | 16:40 | 6:54/km | +4 / -16 m | — / — |
| Wed 22 Jul | idk | 2.19 km | 13:48 | 6:18/km | +2 / -20 m | — / — |
| Sat 25 Jul | Evening Run | 3.04 km | 20:19 | 6:41/km | +3 / -19 m | 126 / 193 |
| Wed 29 Jul | intervals | 2.97 km | 17:38 | 5:56/km | +6 / -21 m | 178 / 197 |
| Fri 31 Jul | **2.4 trial** | 2.41 km | **12:37** | 5:14/km | +3 / -18 m | 189 / **200** |
| Tue 04 Aug | intervals 2 | 2.81 km | 15:51 | 5:38/km | +3 / -19 m | 181 / 193 |
| Wed 05 Aug | 5k | 5.01 km | 37:23 | 7:28/km | +20 / -23 m | 170 / 190 |

Heart rate data begins 25 Jul. Cadence, power, and weather fields are empty across all
activities. **`Grade Adjusted Distance` in this export is a verbatim copy of raw distance on
every row — it performs no adjustment and must not be used.**

## Weekly volume

| Week beginning | Distance | Runs |
|---|---|---|
| Mon 06 Jul | 2.2 km | 1 |
| Mon 13 Jul | 5.8 km | 2 |
| Mon 20 Jul | 7.6 km | 3 |
| Mon 27 Jul | 5.4 km | 2 |
| Mon 03 Aug | 7.8 km | 2 (through Wed) |

## Reference values

- **Observed HRmax: 200** (31 Jul TT, final 200 m). All zones derive from this.
- **Baseline 2.4 km, gradient-corrected: ~12:50.** Recorded 12:37 on a course with a
  −12.2 m net drop over 2.4 km (≈0.5% net downhill), worth ~10–13 s.
- Longest run on record: 5.01 km (5 Aug 2026).

## Session breakdowns

### 31 Jul — 2.4 km time trial (200 m splits)

| Dist | Split | Pace | Δ elev | HR avg | HR max |
|---|---|---|---|---|---|
| 200 | 0:54 | 4:30 | +1.1 | 161 | 170 |
| 400 | 1:03 | 5:15 | 0.0 | 173 | 178 |
| 600 | 1:03 | 5:15 | +1.3 | 182 | 185 |
| 800 | 0:59 | 4:55 | −1.2 | 187 | 189 |
| 1000 | 1:00 | 5:00 | −3.1 | 190 | 192 |
| 1200 | 0:57 | 4:45 | +0.3 | 192 | 193 |
| 1400 | 1:01 | 5:05 | +2.4 | 194 | 195 |
| 1600 | 1:03 | 5:15 | −4.1 | 194 | 195 |
| 1800 | 1:05 | 5:25 | −1.4 | 196 | 197 |
| 2000 | 1:02 | 5:10 | −6.7 | 195 | 196 |
| 2200 | 1:06 | 5:30 | −1.2 | 196 | 198 |
| 2400 | 1:06 | 5:30 | +0.4 | 198 | 200 |

First 1200 m: 4:57/km. Second 1200 m: 5:19/km. **22 s/km positive split.** Opening 200 m
was 44 s/km faster than average pace. HR reached 190 at the 1000 m mark.

### 4 Aug — "intervals 2" (30 s buckets, abridged)

| t (min) | Pace | HR |
|---|---|---|
| 0.0–2.0 | 10:04 → 5:32 | 135 → 158 |
| 2.5–3.5 | 4:17 → 4:02 | 167 → 181 |
| 4.0–5.0 | 5:48 → 7:01 | 183 → 179 |
| 6.0–7.0 | 4:26 → 5:20 | 181 → 188 |
| 9.0–10.0 | 4:26 → 5:13 | 188 → 192 |
| 10.5–11.5 | 6:54 → 6:05 | 190 → 186 |
| 13.5–14.5 | 7:49 → 6:55 | 192 → 188 |
| 15.0–16.5 | 4:49 → 5:41 | 188 → 193 |

**HR never fell below 179 after minute 4.** Recovery floor rose 179 → 186 → 190 → 192.
Warmup was ~2.5 min from standing to 4:17/km. Fastest 30 s bucket: 4:02/km.

### 5 Aug — "5k" (200 m splits, abridged)

| Dist | Pace | HR avg |
|---|---|---|
| 200–800 | 7:50 – 8:05 | 124 → 150 |
| 1000–1600 | 6:55 – 6:40 | 155 → 166 |
| 1800–2800 | 7:15 – 6:40 | 165 → 173 |
| 3000–3400 | 6:25 – 6:00 | 179 → 186 |
| 3600–4000 | 7:10 – 7:50 | 187 → 190 |
| 4200–5000 | 8:00 – 8:20 | 183 → 177 |

Only the first ~800 m sat inside the easy cap. A 5:35/km surge at 3.2 km drove HR to 189,
after which pace collapsed to 8:00+/km while HR stayed above 180. Textbook cardiac drift on
top of an unintended hard effort.
