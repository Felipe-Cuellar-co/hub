# Latam High-Intent Lead Engine — Project Context

**Owner:** Juan Felipe Cuellar, Sr. BA, Operations Latam  
**Status:** Active — Gen 2 delivered 2026-05-13, Gen 3 in planning  
**Last updated:** 2026-05-16  

---

## What this is

An automated/semi-automated methodology for generating high-purchase-intent infoproductor leads for the Latam New Business (NB) pipeline. Built and operated by Juanfe, delivered weekly to the LDR team under Growth.

**Stack:** Semrush Backlinks → Creators Discovery (CD) → Filter Library → LDR Delivery

**Business context:** Latam BU closed Q1 2026 at -30% on Activations OKR, compounding to -34% YTD. The LDR team lacked a reliable ToFu lead source with proven purchase intent and Latam geographic focus.

**Dual purpose:** pipeline feed + transferable playbook for Growth Brazil (André) and Gabriela.

---

## Operating cadence

- Weekly delivery of 200–250 leads per LDR
- 30-minute weekly calibration sync to adjust query parameters based on LDR feedback
- Engine targets: fuel 25–50% of LDR monthly qualified pipeline

## Targets

- **Weekly:** 200 qualified leads to LDR
- **Lead → RtC:** >32% (vs Brazil baseline +5%)
- **RtC → Contacted:** >70%
- **Pipeline model:** ~9 net Activations/month from the engine
- **Q2 end:** Playbook ready for replication without Juanfe's operational support

---

## Generation history

### Early batches (pre-Gen 1 — April 2026)
- Apr 17: 50 leads (Lote 1, anchor: "curso")
- Apr 24: 309 leads (Lote 2, anchor: "curso")
- Apr 29: 1,070 leads across 8 lots (anchors: ebook, pdf, masterclass, etc.)
- Average enrichment rate validated at ~45%

### Gen 1 — delivered 2026-05-04
- Source: buy.stripe.com
- 209 leads delivered; 92 worked (44%); 3 qualified (3.3% of worked)
- 67% disqualified for European leads (Stripe is global; Spanish-language anchors captured Spain/Portugal)
- Root cause: source wrong for Latam purity, methodology was sound
- 117 leads unworked; deferred by Laura's team; ~55 Latam leads status unclear

### Gen 2 — delivered 2026-05-13
- Sources: payco.link, pay.conekta.com, bold.co, checkout.payulatam.com, mpago.la (anchored + exclusion batches)
- 167 qualified leads delivered; total CD spend: $104.06
- As of 2026-05-15: 67% worked, 35.4% qualified rate (~40 of 113 worked)
- Parallel LDR sources: 7.4–13.2% qualified rate (engine 10.7x better on some sources)
- María Paula (LDR): "Te pasaste de crack con esa lista. Gracias." (unsolicited)
- Brugger: "Gracias Juanfe, creo que los nuevos filtros nos van a ayudar"
- Laura: no direct feedback yet — watch through mid-next-week

---

## Source performance (Gen 2)

| Source | Sent | Qualified | pe_rate | $/qual |
|---|---|---|---|---|
| pay.conekta.com | 48 | 8 | 16.7% | $0.08 |
| mpago.la (anchored) | 350 | 38 | 10.9% | $0.12 |
| payco.link | 528 | 39 | 7.4% | $0.19 |
| bold.co | 13 | 1 | 7.7% | $0.21 |
| checkout.payulatam.com | 309 | 14 | 4.5% | $0.34 |
| mpago.la (exclusion) | 6,048 | 67 | 1.1% | $1.29 |

**Key learning:** Anchored batches are 10.9x more efficient than exclusion batches. Never run exclusion at scale again.

---

## Filter library

### Hard exclusions (auto-disqualify)
1. **Hotmart status:** Client Type = PRODUCER AND (GMV last 12m > 0 OR active_in_sales_funnel = True). Keep past-funnel-no-close leads (re-engagement).
2. **Geography — 3-layer + AR exclusion:**
   - L1: Highest Traffic Country NOT in whitelist (CO, MX, CL, PE, UY, BO, EC, PY, VE, CR, DO, PA, GT, HN, SV, NI; nulls OK; AR excluded)
   - L2: TLD not in (.es, .pt, .fr, .de, .co.uk, .it, .nl, .ar, .com.ar)
   - L3: Phone not containing (+34, +351, +33, +39, +44, +49, +54)
3. **IG Category:** IN ('Internet company', 'Insurance company')
4. **Domain keywords:** donaciones, donacion, donar, noticias, noticia, pago, pagos, cita, seguros, laboral, prevencion
5. **IG audience floor:** < 5,000 followers

### Soft signals (deprioritize/flag)
- TLD .org, .edu.co, .org.co → lower conversion (~12-17% vs 34% baseline)
- IG Category = NGO → flag, don't exclude
- Linktree placeholder bio (3+ of: landing, connections, links, manage, launch, platform, page, codes, behind, create, short, detailed) → likely dormant
- Positive flag: IG Category IN ('Education', 'Educación', 'Producto/servicio') AND Has Product = True → top of batch

### Watch list (n too small for hard filter)
- tienda, hospedaje, depilacion, hotel, universidad, concurso (n<3)
- congreso: n=6, 17% qual rate
- pay.conekta.com NB-rate 63.6% (n=11 — validate at n≥50)

---

## Source taxonomy (5-tier)

### Tier A — Next gen targets
- `mpago.la` — 434 CRM mentions, Latam-wide; apply anchor filters aggressively
- `webpay3g.transbank.cl` — Chile-only, dominant
- `flow.cl` / `pay.flow.cl` — Chile, SaaS/digital ICP
- `pay.kushkipagos.com` — multi-Latam; validate subdomain

### Tier B-DONE — Already extracted
- `buy.stripe.com` (Gen 1) → needs v2 with full filter stack
- `payco.link` / `epayco.com` → re-run monthly
- `pay.conekta.com` → small volume, high NB-rate
- `checkout.payulatam.com` → deprecation candidate (4.5% pe_rate)
- `bold.co`, `wompi.com` → dismissed (retail ICP mismatch)

### Tier C — Global high-volume (deferred)
- `paypal.me` — 3,150 CRM mentions; defer until Tier A exhausted
- `secure.2checkout.com` — 17 mentions, low priority

### Tier D — Course platforms (methodology adaptation needed)
- `*.mykajabi.com` — 798 CRM mentions; **highest EV unknown; validate in Semrush first**
- `*.teachable.com` — 218 mentions
- `*.thinkific.com` — 89 mentions
- `*.wisboo.com` — 58 mentions, Latam-native
- Kartra, Systeme.io, ClickFunnels — lower priority

### Tier SKIP
- WooCommerce, WordPress/Wix/Shopify, EAD Plataforma, Domestika/Crehana/Udemy, MercadoLibre

---

## Anchor performance (validated)

| Anchor | 5k rate | Notes |
|---|---|---|
| masterclass | 75% | Best performer |
| ebook | 59% | |
| coach | 50% | |
| curso | 48% | Highest volume |
| taller | ~40% | |
| inscripción | ~35% | Mixed on retail-skewed sources |
| certificado | ~35% | |
| programa | ~30% | |
| acceso | lower | Not recommended |
| sesión | lower | Not recommended |
| pdf | 25% | Not recommended |
| mentoría | source-dependent | Bad quality on mpago.la Gen 2 |

**Queued for test:** adquirir, regístrate, matricúlate (on mpago.la next run)

---

## Key decisions (condensed)

1. **Filter geography at CD output, not Semrush** — CD's Highest Traffic Country is audience-analytics based; Semrush country detection is TLD heuristics, unreliable for .com/.ai/.io domains.
2. **Target hosted-checkout subdomains, not corporate roots** — corporate roots accumulate B2B/dev/news links. Validated: conekta.com dismissed, pay.conekta.com worked.
3. **No exclusion batches at scale** — 10.9x cost vs anchored. Tested at n=6,048. Do not repeat.
4. **Hard AR exclusion** — structural closing difficulty (capital controls). Not formally confirmed with Pablo/Edu. VE and BO may have same issue.
5. **Hotmart-status filter distinguishes active from past-funnel-no-close** — blanket PRODUCER exclusion discards re-engagement leads. Refined in Gen 2: Hotmart-active overlap from 23% → 9.7%.
6. **5k+ IG followers floor** — matches SDR qualification floor; defensible against retroactive challenge.
7. **Lead → RtC as primary KPI, $/qual secondary** — directly measures LDR-facing quality, benchmarks vs Brazil baseline.
8. **Production cycles separated from exploration runs** — keeps production KPIs clean; exploration cost doesn't contaminate efficiency tracking.
9. **Manual pre-qualification monthly only** — one-time investment to build filter library; not weekly recurring.
10. **Source deprecation rule:** after 2 cycles if Lead→RtC < 20% OR $/qual > $0.50 OR NB-target rate < 15%. Dismiss without 2nd cycle if NB-target rate < 10%.

---

## Open questions & blockers

- **Q1 (BLOCKER):** Does `lead_origin_specification` persist on Salesforce lead record after LDR action? → 5-min check with André or directly in SF.
- **Q2:** AR exclusion scope confirmed? VE/BO same issue? → Confirm with Pablo or Edu.
- **Q3 (HIGHEST EV):** Can Semrush expose `*.mykajabi.com` subdomain list with traffic data? → 15-min probe.
- **Q4:** Final Lead → RtC rate for Gen 2. 7-day SLA from 2026-05-13 → by 2026-05-20.
- **Q5:** Brugger's expectation of engine scope and timeline. → Meeting pending.
- **Q6:** Is 200/week target in any formal document beyond the playbook? → Risk if LDR capacity changes.
- **Q7:** Gen 1's 117 unworked leads — will they ever be worked? ~55 Latam leads status unclear.

---

## Risks

1. **Single Juanfe dependency** — playbook + Gabriela shadowing in progress but incomplete.
2. **LDR Gen 1 perception** — negative impression from EU contamination. Gen 2 results are the defense.
3. **CD cost scaling** — not a problem now at $0.12–$0.34/qual; monitor if source quality degrades.
4. **OKR pressure (-34% YTD)** — may shorten methodology's development window.
5. **PayU in rotation without decision** — 4.5% pe_rate, $0.34/qual; one cycle gate agreed.
6. **Kajabi methodology may not work** — if Semrush can't expose subdomain structure usefully.
7. **AR exclusion scope** — may be too broad (excludes AR creators targeting MX/CO) or too narrow (VE/BO not yet assessed).

---

## Next steps

### This week
- [ ] Receive Gen 2 Lead → RtC final numbers (SLA: 2026-05-20)
- [ ] Hold Brugger meeting — goal: understand his expectations beyond current delivery
- [ ] Send Brugger follow-up note within 24h of meeting

### Next week (Gabriela in Bogotá)
- [ ] Run Gabriela shadowing — 2 sessions, ~2h total
- [ ] Collect Gabriela's input on Growth lead gen pain points

### Gen 3 source work (queued)
- [ ] Kajabi subdomain probe in Semrush — **highest EV, 15 min, go/no-go on Tier D**
- [ ] Webpay (`webpay3g.transbank.cl`) extraction
- [ ] Stripe v2 with full filter stack (~1,000 leads available)
- [ ] Test anchors: adquirir, regístrate, matricúlate on mpago.la

### Structural
- [ ] Add BR conversion rates + SLA to model (new tab: BR_Benchmark) — for Growth volume negotiation
- [ ] Build meeting framing for Growth volume negotiation (target: 405 RtC/wk; fallback framing ready)
- [ ] Do NOT share lead-quality table (LDR vs SDR) with Growth in volume negotiation — it can be weaponized before the Engine conversation frames higher intent as the solution
- [ ] Missing from playbook: Argumentos de Migración (sales scripts per competitor tool — e.g. Stripe vs Kajabi framing)
- [ ] Scalability transfer to other regional teams (Spain/US) — targeted end of Q2
- [ ] Verify Salesforce tagging (lead_origin_specification persistence)
- [ ] Confirm AR exclusion scope with Pablo or Edu
- [ ] PayU one more cycle → apply deprecation rule
- [ ] Mine `Checkout Platforms` field from Gen 2 qualified leads for Gen 3 source candidates

---

## Stakeholders

| Name | Role | Relevance |
|---|---|---|
| Juanfe | Sr. BA, Operations Latam | Owner/operator |
| Edu (Eduardo) | Sr. Manager Operations | Direct boss; focused on team upskilling; critical of AI usage |
| Pablo | VP Latam | Senior Latam BU context; prior direct leader |
| Laura Bejarano | Growth Manager | Direct Growth counterpart; LDR team boss; day-to-day |
| Guilherme Brugger | Growth Sr. Manager | Laura's boss; meeting booked; career-relevant for LDR Coordinator path |
| André | BA Coordinator, Growth Brazil | Eventual playbook recipient; not yet engaged |
| Gabriela | BA, Growth | New; shadowing planned next week in Bogotá |
| Ana María | LDR | Lead recipient Gen 1 + Gen 2 |
| María Paula | LDR | Lead recipient; gave unsolicited positive Gen 2 feedback |
| Ricardo | SDR Manager | Juanfe's mentor for leadership track |
| Felipe Ángel | NB Director | Looking for AI Specialist; career-relevant for AI track |

---

## Tools & references

- **Semrush Backlinks:** https://www.semrush.com/analytics/backlinks/overview/
- **Creators Discovery:** https://creators-discovery.hotmart.com/ (contact: leadintelligence@hotmart.com; max 5k rows/batch; ~$0.014/lead)
- **Astrobox:** https://astrobox.hotmart.com/ (where CD results are queried)
- **Salesforce:** CRM; lead_origin_specification field for source tagging

### Internal docs (as of 2026-05-16)
- `202604_HighIntent_Generation_Log.xlsx` — per-batch quantitative tracking
- `202605_Competitor_Research_Log.xlsx` — 26 competitors across 5 tiers
- `202605_LeadEngine_Playbook_v3_shareable.docx` — current shareable playbook
- `202605_LeadEngine_Methodology_Framework_v2.docx` — internal framework with decision rationale
- `202604_Latam_High-Intent_Lead_Engine.docx` — original project brief

### CD cost model
- ~$0.014 per lead enriched
- Anchored batches: $0.08–$0.34/qual
- Exclusion batches: $0.82–$1.47/qual (validated inefficient)

### Self-feeding source discovery
After each cycle: aggregate `Checkout Platforms` field from qualified leads. Gateways appearing >5 times → next cycle extraction candidates.
