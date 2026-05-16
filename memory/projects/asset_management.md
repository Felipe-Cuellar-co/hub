# Asset Management (Fondo de Gestión Patrimonial Unificado)

**Status:** Active — accounting framework built; Phase C-to-A deployment ongoing  
**Last updated:** 2026-05-16

---

## What this is

Private, multi-class unitized family investment fund. All physical capital consolidated in a single master broker account to unlock premium tier advantages. Ownership separation handled entirely in the logical accounting layer (ledger).

---

## Capital infrastructure

| Platform | Use |
|---|---|
| **eToro** | International equities (master broker account) |
| **Nu** | Local liquidity |

---

## Portfolio framework: Core-Satellite 2026

| Allocation | Asset | Ticker | Weight |
|---|---|---|---|
| Core | MSCI ACWI | IUSQ.DE | 35% |
| Core | Berkshire Hathaway | BRK.B | 20% |
| Core | Gold | GLD | 15% |
| Satellite | Nubank | NU | 15% |
| Satellite | HubSpot | HUBS | 5% |
| Satellite | Crypto | — | 10% |

- **Core:** 70% — low-volatility diversified
- **Satellites:** 30% — high-conviction growth

---

## Asset classes (risk tiering)

| Class | Allocation | Instruments |
|---|---|---|
| **Clase A** | 40% Variable / 60% Fixed | eToro + Nu + Private loans |
| **Clase B** | 100% Variable Growth | eToro + Crypto |
| **Clase C** | 100% Liquid cash buffer | — |

---

## Unitization methodology (Valor Cuota)

- Abandoned pro-rata accounting to prevent historical performance distortion
- Entry moment of cleared capital → acquires shares at daily NAV price
- **Strict rule:** Capital cannot be credited to variable assets until funds are physically cleared and transferred to broker
- Rebalancing: passive only — new monthly inflows directed to underweight assets; no liquidations

---

## Currency strategy

- COP/USD exchange rate (TRM) treated as an intrinsic hedge asset within local ledger
- Global revenue captured in USD and MXN; operations run on COP baseline (~$3M COP living expenses, Pasadena)

---

## Performance

- **Q1 YTD:** -6.49% (reported transparently to clients, no cosmetic masking)
- **Monthly inflow:** $650.11 USD (April)
- **eToro Risk Score target:** 4–5 (stable public range)

---

## Stakeholders

| Name | Role |
|---|---|
| Juan Jaramillo | Key premium investor; benchmark user for automated reporting |
| Core family members | Capital investors; drive Clase C → Clase A migration |

---

## Open commitments

- [ ] Execute non-dilutive Clase C → Clase A migration for family funds
- [ ] Build client-facing automated performance reporting in Looker Studio (for Juan Jaramillo and family)
- [ ] Package and distribute March/April performance ledger summaries to Juan Jaramillo and family
