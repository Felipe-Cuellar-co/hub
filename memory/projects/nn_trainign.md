# Hotmart Lead Scoring Neural Network

**Status:** Active / Paused — Phase 1 (100% complete); blocked on upstream data  
**Last updated:** 2026-05-16  
**Scope:** Personal initiative, built outside work hours. Not yet formally presented internally.

---

## What this is

Deep learning binary classification system to automate B2B lead qualification for Hotmart's Nuevos Negocios (NB) team. Redirects manual hunter/SDR verification time toward high-value targets.

**Output:** Probability score 0.0–1.0 for each inbound lead.

**Connection to Lead Engine:** These are two layers of the same product.
- Engine = generation layer (finds leads)
- NN = scoring layer (prioritizes them)
- Future convergence: Engine web signals become NN input features → single probability output
- This convergence has NOT been formally articulated to any stakeholder yet — making it explicit to Felipe Ángel is a high-leverage move.

---

## Target definition

"Ready to Contact" (RtC) — a creator with:
- Established audience
- Existing digital asset
- Active ad spend
- Niche alignment
- Estimated earnings > $5,000 USD

---

## Architecture

- **Model type:** Feed-Forward MLP binary classifier
- **Framework:** TensorFlow / Keras
- **Input:** Creators Discovery enriched profiles only (no CRM data — anti-leakage)
- **Training labels:** Binary — 1 = reached RtC, 0 = disqualified

### Planned architecture
- Input layer: dynamic shape (final one-hot matrix minus Input ID)
- Hidden layers: Dense, ReLU — starting recommendation 64 → 32
- Output layer: 1 neuron, Sigmoid
- Loss: binary_crossentropy
- Optimizer: Adam (lr=0.001)
- Regularization: Dropout 0.3 between layers
- Batch size: 32
- Early stopping on validation loss

---

## Feature engineering (Phase 1 — complete)

**Numerical (MinMaxScaler):**
IG Followers, IG Following, IG Avg Engagement Rate, IG Posts Count, IG Highlight Reels, YT Subscribers, YT Videos Count, YT Views, Lead Score V1, Lead Score, Domain Score, Total Traffic, Organic Traffic, Paid Traffic, active_ads_count, max_product_price, yt_channel_age_days

**Categorical (one-hot):**
Input Type, IG Category, Detected Language, Highest Traffic Country, IG Verified, IG Joined Recently, IG Private, IG Is Business Account, YT Verified

**Binary flags (manually engineered):**
has_username, has_external_url, has_phone_number, has_whatsapp, has_email, has_meta_ads

**NLP keyword features (IG Bio + YT Description, lowercased):**
contains_alumno, contains_capacito, contains_taller, contains_enseño, contains_aprende, contains_estudiantes, contains_academia, contains_ayudo, contains_curso, contains_usd, contains_mentor, contains_coach, contains_formación, contains_masterclass, contains_escuela, contains_link, contains_hotmart, contains_programa, contains_clase

**Protected (excluded from training):** Input ID (kept for CRM mapping)

---

## Key technical decisions

| Decision | Rationale |
|---|---|
| **Creators Discovery only (no CRM)** | Data leakage prevention. New leads won't have SDR notes or GMV history on Day 1. |
| **Balanced cohort from Salesforce (not fuzzy matching)** | Fuzzy matching by email/name fails too often. Pre-labeled cohorts from SF guarantee clean Y labels. |
| **Retain `has_hotmart` flag** | Share-of-Wallet (upselling) is a valid NB strategy. Existing client = signal, not disqualifier. |
| **Build XGBoost baseline FIRST** | Tabular data, ~10k samples — gradient boosting almost always outperforms NNs here. Need a benchmark to know if NN adds value. ⚠ Not yet done. |
| **Class weights over SMOTE** | High-density one-hot dimensions → SMOTE produces corrupt non-binary floats. Native Keras class_weight is correct. |
| **Time-based validation split** | More honestly simulates production (train on older, validate on newer) vs. random 80/20 which overestimates real-world performance. |

---

## Current state

| Phase | Status |
|---|---|
| Phase 1: Feature Engineering & Preprocessing | ✅ 100% complete |
| Phase 1b: XGBoost baseline | ⚠ Not yet built — do this before Phase 2 |
| Phase 2: Model Training | ⛔ Blocked on Salesforce data |
| Phase 3: Evaluation & Deployment | Not started |

**Output artifact so far:** `matriz_entrenamiento_X_con_ID.csv`
⚠ Note: the 0–1 values in this matrix are preprocessed features (MinMaxScaler + one-hot), NOT model predictions.

---

## Blockers

1. **Salesforce balanced cohort extraction** — 5k Class 1 (RtC) + 5k Class 0 (disqualified), last 12 months, re-run through Creators Discovery. Who owns this export?
2. **No historical CD snapshots** — would cleanly solve temporal leakage (current state of leads ≠ their state at qualification time)
3. **XGBoost baseline not built** — needed before NN training to establish whether NN adds meaningful value

---

## Open risks

1. **Temporal leakage:** Re-running qualified leads through CD now reflects current state, not qualification-time state. Mitigation: restrict cohort to last 30–60 days.
2. **Model stacking:** Lead Score V1, Lead Score, Domain Score are existing scoring outputs. NN may just mirror them. Compare against baseline using only these three.
3. **Class imbalance vs. production reality:** 50/50 training split ≠ production (most leads won't qualify). Use class weights + tune decision threshold for precision vs. recall.
4. **NN vs. XGBoost:** If XGBoost hits 75–80% F1, NN becomes a learning exercise, not a business necessity. Important distinction for internal positioning.

---

## Learning stack

- Probability fundamentals: Brilliant (directly relevant to loss functions, model evaluation)
- Anthropic AI courses (in progress)
- Content style: 3Blue1Brown, Veritasium, Branch Education
- Prior technical work: Gemini handover document extracted and available

---

## Career signal

Directly demonstrates the AI Specialist for NB path. Felipe Ángel is looking for this profile. Phase 1 pipeline complete = concrete artifact, not a pitch. The Engine + NN convergence story is the high-leverage frame: not two separate experiments, but a two-layer lead intelligence system.

---

## Open commitments

- [ ] Build XGBoost baseline before NN training
- [ ] Identify who can run the Salesforce cohort extraction
- [ ] Define success metrics with business stakeholders (what precision/recall changes their workflow?)
- [ ] Set up dedicated Claude project for NN (learning-mode instructions, separate from Engine)
- [ ] Formally articulate Engine + NN convergence story for Felipe Ángel meeting
