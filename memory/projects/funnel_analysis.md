# Bottom-Up Funnel Analysis (Hotmart)

**Status:** Delivered — NB team meeting held; Growth meeting upcoming  
**Type:** One-off analytical deliverable (template origin story)  
**Last updated:** 2026-05-16

---

## What was built

Commissioned by Ricardo Ramírez. Parametric bottom-up model of the Latam Outbound Acquisition funnel.

**Artifacts:**
- `20260515_model_bottom_up_funnel_analysis.xlsx` — 6-tab parametric model, all formulas linked to Inputs sheet
- `20260515_onepager_bottom_up_funnel_analysis.docx` — 1-page senior distribution brief

---

## Funnel structure (8 stages)

RtC → C1: Contacted → C2: Connected → C3: Nurturing → C4: Qualified → C5: SQL → C6: Offer Presented → C7: Closed Won → C8: Activation

---

## Key numbers (Q1 2026, Outbound, cohorted)

| Metric | Value |
|---|---|
| Weekly RtC volume (L) | 275 leads/week (5 LDRs + 11 SDRs) |
| End-to-end conversion | 2.07% |
| Current weekly output | 5.7 activations/week |
| Forward weekly target | ~17.5 avg (peaks 22+/week Jul/Oct/Nov) |
| Gap | 3× below target |
| Total funnel SLA | 59 days |
| YTD deficit (mid-May) | ~98 activations behind plan |

---

## Biggest leaks (ranked by +5pp single-stage impact)

1. **C2: Contacted → Connected (37.2%)** — 63% of contacted leads lost here. Biggest lever.
2. **C8: Closed Won → Activation (44.6%)** — 55% post-deal drop. Onboarders' accountability.
3. **C3: Connected → Nurturing (54.4%)**
4. **C6: SQL → Offer Presented (65.1%)** — possible execution/discipline gap. An SQL should logically receive an offer.

---

## Lead quality by origin (directional — single quarter, treat as anecdotal until re-baselined)

| Stage | LDR-created | SDR self-created | Gap |
|---|---|---|---|
| C1 RtC → Contacted | 65.7% | 98.5% | –32.8pp |
| C2 Contacted → Connected | 36.6% | 36.5% | ≈ parity |
| C3 Connected → Nurturing | 36.1% | 54.1% | –18.0pp |
| C4 Nurturing → Qualified | 37.5% | 61.7% | –24.2pp |
| C5 Qualified → SQL | 58.7% | 77.7% | –19.0pp |
| C6 SQL → Offer Presented | 54.1% | 62.4% | –8.3pp |
| C7 Offer → Closed Won | 50.0% | 69.1% | –19.1pp |
| C8 | — | — | LDR cohort too recent |

⚠ **Do NOT share this table with Growth in the volume negotiation.** The LDR vs SDR quality gap can be weaponized ("more LDR leads dilutes the funnel") before the Engine conversation frames higher intent as the solution. This data is for the Engine conversation, not the volume negotiation.

---

## Three scenarios modeled

| Scenario | Parameters | Result |
|---|---|---|
| 1 — Volume only | L=650 | 17.5 act/wk ✓ but requires 2.36× volume — not realistic near-term |
| 2 — Conversion only | L=275, C2→50%, C4→70%, C6→85%, C8→55% | 13.7 act/wk ✗ insufficient |
| **3 — Blended (recommended)** | **L=405 (+47%), C2→47%, C4→66%, C6→85%, C8→54%** | **17.5 act/wk ✓** |

**Key insight:** The funnel is multiplicative — single-team fixes are mathematically insufficient. Coordinated path is not a preference; it's the only viable path. Framing removes blame and creates shared accountability.

---

## Recommended path by vertical

| Vertical | Stage | Current | Target | Lever |
|---|---|---|---|---|
| LDR (Growth) | Volume | 275 RtC/wk | 405 RtC/wk | Engine + capacity review |
| SDR (NB) | C2 | 37.2% | 47.0% (+10pp) | Cadence / copy A/B testing |
| SDR (NB) | C4 | 63.1% | 66.0% (+3pp) | Qualification criteria |
| Closer (NB) | C6 | 65.1% | 85.0% (+20pp) | Process / discipline diagnostic |
| Onboarder (NB) | C8 | 44.6% | 54.0% (+10pp) | Activation playbook |

---

## Stakeholder reactions

| Person | Reaction |
|---|---|
| Felipe Ángel (NB Director) | Booked follow-up meeting — strong positive signal |
| Ricardo Ramírez (SDR Manager) | Commissioned it; worked through model together; liked it |
| Nicolás (Closing Manager) | Thanked; his team owns C6–C7 |
| Catalina (Onboarding Manager) | Thanked; her team owns C8 |
| Eduardo (Sr. Manager Operations) | Liked format; asked if it was a template; agreed to build Ops Latam template |
| Growth (Brugger + Gabi) | Want to discuss and negotiate lead volume; in-person Bogotá meeting next week |

---

## Tone decisions (for future reference)

- **"Proposed discussion points for joint review"** (not "Asks") — audience is peer-level directors
- **C6 framed as diagnostic** — "worth investigating whether this reflects process gaps or definitional misalignment" — not "Closer team failure." Closers were in the meeting; blame-framing triggers defensiveness.

---

## Open items

- [ ] Add BR conversion rates + SLA data (new tab: BR_Benchmark) — before Tuesday Growth meeting
- [ ] Extend model with SLA differential calculation (shorter SLA = more cohorts per quarter)
- [ ] Prepare framing for Growth volume negotiation (target 405 RtC/wk; fallback if they push back)
- [ ] Re-baseline LDR cohort conversion rates at end of Q2 (separate ramp effect from systemic quality)
