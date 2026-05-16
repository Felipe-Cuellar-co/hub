# Finances 2.0 (Hub Financiero)

**Status:** Active — Phases 1 & 2 complete; Phase 3 initiated  
**Last updated:** 2026-05-16

---

## What this is

Personal finance data warehouse and automated CFO Dashboard. Goal: track net worth, P&L, net cash flow, and savings rate to the penny — eliminating manual tracking friction and monthly statement latency.

**Stack:** Monai (mobile entry) + DAVIbank transaction data → Google Drive → Python pipeline → Google BigQuery (Star Schema) → Looker Studio

**Current test agent:** `Test_Agente_Registro_Transacciones` running with real Visa Platinum transactions (Mar–May 2026)

---

## Phases

- **Phase 1:** ✅ Complete
- **Phase 2:** ✅ Complete
- **Phase 3:** 🔄 In progress — Looker Studio dashboard builds; Net Worth tracking modules

---

## Database design

- **Star Schema** with `f_transactions` as the central fact table
- Dynamic string IDs for dimensional normalization
- Rationale: eliminates tracking redundancy; high structural complexity upfront, clean maintenance interface downstream

---

## Data entry

- Mobile: `Monai` app → syncs to Google Drive
- Pipeline: Python scripts processing Drive exports into BigQuery

---

## Open commitments

- [ ] Move from test environment to production
- [ ] Define BigQuery schema (production)
- [ ] Clarify Looker Studio pull mechanism
- [ ] Initialize Phase 3 — build Looker Studio dashboard
- [ ] Build Net Worth tracking module
- [ ] Build P&L and cash flow tracking modules
