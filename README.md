# AI-to-EV Workbook v43 — README

**File:** `AI_to_EV_Workbook_lv_v43.xlsx`
**Case:** Contoso (vertical SaaS)
**Tabs:** 11 · **Formulas:** 1,145 · **Errors:** 0 (verified by recalc)

Every figure below is read from the file as it currently stands, not from prior notes.

---

## What this model does

It answers one question: if you close the capability gap, what is the business worth afterward?

It does not size an AI opportunity in the abstract. It starts from an enterprise value you already have, moves ARR and the multiple, and nets off what the program costs.

---

## The chain

One chain, end to end. There are no side calculations that get added in.

1. Score 36 capabilities against a frontier rubric.
2. Distance from the frontier sets how much of each value pool is reachable.
3. Reachable pool is cut by feasibility, then by timing.
4. What survives splits into a revenue half and a cost half.
5. The revenue half lifts ARR. The whole pool lifts growth. Growth lifts the multiple.
6. New ARR × new multiple = new enterprise value. Subtract the NPV of program cost.

**The pool is never capitalized separately.** It moves the multiple and it moves ARR, and those two things produce the answer. Adding the pool on top would double-count it.

**There is no re-rating term.** It was removed as unsupported. In an earlier version it was carrying 92% of a $22B answer.

---

## Headline numbers

| | |
|---|---|
| ARR | $1.2B |
| Total revenue | $1.5B |
| EBITDA margin | 42% |
| Enterprise value today | $11.0B at 9.17x |
| Capability score | 5.56 against a 9.25 ceiling |
| Gross pool | $484.9M |
| Capturable at current capability | $49.6M (10.2% retained) |
| After feasibility | $45.3M |
| After timing | $43.5M (9.0% retained) |
| — of which new revenue | $26.0M |
| — of which cost out | $17.5M |
| Build cost, one-time | $7.5M |
| Run cost, annual | $2.5M |
| NPV of program cost | $16.3M |
| **EV created, net** | **$501.6M** |
| **New enterprise value** | **$11.50B** |
| Value density | 30.8x |
| Break-even | month 24 |

The bridge: $11.0B + $221.3M ARR uplift + $296.6M multiple uplift − $16.3M cost = $11.50B.

---

## Tab guide

| Tab | What it holds |
|---|---|
| `0_AI_to_EV_Bridge` | Inputs and the waterfall. Start here. Ties to tab 8. |
| `1_Industry_Rubric` | Six frontier dimensions (BD, OA, AUT, DC, VEL, DE), the comparator cohort, and 72 sets of five level anchors. |
| `2_Capability_Assessment` | The 36 dropdowns. Everything downstream moves from here. |
| `3_Distance_to_Frontier` | Gap by lever, and the pool at stake against the pool adjusted. |
| `4b_Value_Pools_by_Capability` | Pool construction. Firm scale factor, enabler gate, per-capability split. |
| `4d_Metric_Impact` | Nine operating metrics, baseline to target. Allocation grid — each row sums to 100%. |
| `4m_Exit_Multiple` | Growth cohorts and the multiple. See the warning below. |
| `5_Implementation_Feasibility` | Vendor risk, competitive response, regulatory exposure. Plus the two timing factors. |
| `6_Implementation_Cost` | Three workstreams, built bottom-up from headcount and duration. |
| `7_Value_Timing` | Ramp curve across a 60-month window. |
| `8_Enterprise_Value` | The chain step by step, four valuation methods, DCF, LBO floor. |

---

## Where to type

Cells marked `ENTER:` are inputs. Everything else is formula-driven and should be left alone.

- **Tab 0** — enterprise value, ARR, EBITDA margin, basis at entry
- **Tab 2** — the 36 capability dropdowns
- **Tab 4b** — industry vertical, share of accounts on an AI tier, pricing headroom
- **Tab 5** — five factor scores, 1 to 5
- **Tab 6** — headcount, durations, loaded cost, change cost per user
- **Tab 8** — target MOIC, hold period, entry leverage

**Always seed all 36 dropdowns on tab 2 before reading any output.** A partial seeding produces a number that looks finished and isn't.

---

## What is evidenced and what is not

Sourced: the capability assessment, the cost-side uplifts, feasibility, timing, and implementation cost.

Not sourced:

- **The chain from capability level to growth rate.** The 0.46 and 0.93 scale factors on `4m` are internal arithmetic, not observed.
- **The 25% AI-tier premium.** Management estimate. It is 83% of the revenue pool — the largest single-point dependency in the model.
- **Ecosystem strategy at 2%.** No published SaaS uplift figure.
- **Revenue operations at 30%.** One case study, not a median.
- **The 40% revenue share on Sales effectiveness.** Set by hand.

---

## Open issues

### 1. The $11.0B has never been tested against comparables

Contoso's 9.17x is roughly three times its own growth cohort's median. It is priced as though it grows at 30%. It grows at 13%. No capability position anywhere in the model reaches 30% growth.

This is a larger exposure than anything the program adds — and because the mechanic runs new ARR × new multiple, the base multiple scales the $501.6M as well. The input risk and the program risk are the same risk.

The cohort data is already in the file. `4m` row 8: 10–20% growth, EV/ARR median **3.1x**, n=23, SaaS Capital Index, 30 June 2026. At 3.1x, $1.2B ARR is **$3.72B**. It is not wired into the method range on tab 8.

### 2. Trading comps and DCF are not independent

Tab 8 presents four methods. Two of them share an anchor.

The exit multiple on `4m` is `=$E$22*$D24/$D$22+($C24-$C$22)*10*$C$13`. `$E$22` reads tab 0 C12 — the 9.17x derived from the $11.0B. The cohort ratio `$D24/$D$22` is 3.1/3.1 = 1, because growth moves 13% → 14.9% and never leaves the band, so the cohort term cancels out entirely. What remains is 9.17x plus a within-band adjustment.

So "trading comps" is ARR at exit × a multiple inherited from the mark. And "DCF" is the mark plus the program's own cash. Both start from $11.0B. They agree because they share an anchor, not because two methods independently converged.

| Method | Value | Anchored on $11.0B? |
|---|---|---|
| Trading comps, two levels | $11.52B | Yes |
| DCF | $11.34B | Yes |
| Precedent (Anaplan, 18.1x, Mar 2022) | $21.72B | No |
| LBO floor (2.5x MOIC) | $4.61B | Partly |
| Cohort median (3.1x, not yet on tab 8) | $3.72B | No |

The two methods that don't inherit the mark both land near a third of it.

---

## Three priorities

| Capability | Adjusted pool | Level today |
|---|---|---|
| Workflow depth and embeddedness | $7.73M | L3 |
| Pricing — value metric and packaging design | $3.54M | L3 |
| Pricing — outcome measurement and price realization | $3.54M | L3 |

Plus: **organizational change capacity** scores 3 of 5. It doesn't change the size of the pool, it changes when the pool arrives — pushing the ramp midpoint from 18 to 24 months. Improving it pulls break-even forward by roughly six months.

---

## Working notes

- **Sheet names starting with a digit then `e` break formula references.** `4e` parses as scientific notation. That's why the tab is `4m_Exit_Multiple`.
- **Never run sequential find-and-replace on cell references.** It cascades — each replacement becomes the input to the next.
- **Recalculate with** `/mnt/skills/public/xlsx/scripts/recalc.py`. openpyxl writes formulas with no cached values, so anything reading the file sees blanks until this runs.
- **A clean recalc proves the formulas evaluate, not that they're right.** An off-by-one range gives you zero errors and the wrong answer.

---

## Reading the output without tripping up

Two traps, both on tab 8.

**$484.9M is not enterprise value.** It's the top of the funnel — the whole theoretical prize before any haircut. It sits in bold at the top of section A and it's the first number anyone's eye lands on. What actually survives is $43.5M, 9.0% of it.

**$43.5M and $501.6M are different kinds of number.** $43.5M is annual — a flow. $501.6M is enterprise value — a stock. You get from one to the other by lifting ARR and letting the multiple work, not by adding them together.

