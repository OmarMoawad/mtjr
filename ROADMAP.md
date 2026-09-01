# MTJR — Roadmap

*Version 0.1 — 2026-09-01. Living document. Everything here is provisional until Phase 0
decisions are locked.*

---

## 0. Orientation

### Vision
Own the answer to *"what should be made, for whom, in what combination, at what expectation"*
in a market whose supply side (small offline merchants) is still undigitized — then act on that
answer by manufacturing.

### The three stacked businesses
1. **Merchant digitization** — low tech, high field effort. The wedge and the moat.
2. **Marketplace connector** — low/medium tech, low capital. The data-collection surface.
3. **Demand intelligence → manufacturing** — very high tech, very high capital. The prize.

Do **not** build these in parallel. Phase 1 = businesses 1 + 2, kept deliberately dumb.

### Guardrails (repeat every phase review)
- Asset-light: no owned warehouses, fleet, or lending.
- Depth over breadth: density in one sliver beats a shallow map.
- Sequencing discipline: payments / logistics / credit / gov registration / multi-city /
  manufacturing each wait for the phase that calls for them.
- The deliverable of each early phase is a **demand insight**, not GMV.

---

## Phase 0 — Scoping & paper validation
**Goal:** lock the decisions that make Phase 1 startable. No code, no merchant visits yet.
**Effort:** solo, evenings, ~2–4 weeks of thinking. Compatible with the academic sprint.

### Decisions to lock (see Decision Log below)
- [ ] **City** — default: home city.
- [ ] **Zone** — one neighborhood or one merchant cluster, walkable.
- [ ] **Category set** — 1–3 categories. Selection criteria: (a) frequent repeat purchase,
      (b) interesting substitution/bundling behavior, (c) enough overlapping merchants that a
      unified view will eventually matter, (d) you personally understand the buying decision.
      Candidates: packaged groceries + household; stationery/office; auto parts; building
      materials; pharmacy-adjacent OTC.
- [ ] **Merchant value proposition** — the one non-negotiable pain Phase 1 solves for a
      merchant on day one, before any buyer volume exists. (Hypotheses: free findable online
      presence; a simple stock list they can share; incoming customer contacts.)
- [ ] **Buyer value proposition** — why a buyer uses MTJR instead of walking to the shop or
      opening Amazon.eg / Noon. (Hypotheses: see what nearby shops actually have in stock right
      now; compare prices across shops you'd otherwise have to visit; find niche items.)
- [ ] **Catalog architecture for Phase 1** — per `ARCHITECTURE-CATALOG.md`: **segregated
      storefronts first**, canonical layer deferred to Phase 1.5.
- [ ] **Legal posture** — operate as informal pilot / sole proprietor; no company formation,
      no merchant fees, no payment handling in Phase 1.

### Phase 0 exit criteria
- A one-page written answer to each decision above.
- A list of 30–50 named target merchants in the chosen zone (walk it, note them).
- A hypothesis for the first demand insight you expect to find.

---

## Phase 1 — Hand-built connector pilot
**Goal:** prove that (a) merchants will be digitized for free, (b) buyers will use a directory,
(c) the data reveals at least one non-obvious demand pattern.
**Effort:** solo + maybe one helper. ~3–6 months calendar at nights/weekends scale.
**Start:** after the academic sprint clears (recommended) or in parallel if capacity allows.

### Workstream A — Field ops (the hard part)
- [ ] Onboard 20–50 merchants **by hand, yourself**. No field-agent team.
- [ ] Per merchant capture: name, location/pin, category, contact, photographed product list
      with prices, open/closed hours, "in stock / out" toggle per item.
- [ ] Tooling: Airtable or a spreadsheet + a phone camera. **No custom app yet.**
- [ ] Refresh cadence: visit or message each merchant weekly to update stock/prices. Track how
      much time this costs — it's the core scaling constraint.
- [ ] Merchant agreement: one-page plain-language note. Free. No exclusivity. They keep every
      existing process. They can leave anytime.

### Workstream B — Buyer interface
- [ ] A clean web catalog (mobile-first). No native app.
- [ ] Features: text search, category browse, filters, per-merchant storefront pages, item
      pages with photo/price/stock/merchant, "contact seller" (WhatsApp deep link / call).
- [ ] **No** checkout, cart, payment, or delivery. Transactions happen off-platform.
- [ ] Design quality is the differentiator — invest here. Research local shopping UX, Arabic/
      RTL + bilingual handling, low-bandwidth performance.
- [ ] Stack: whatever ships fastest and you can maintain solo (e.g. Next.js + a hosted DB, or
      even a static site generated from the Airtable). Decide at Phase 1 kickoff.

### Workstream C — Data capture (the actual point)
- [ ] Log every: search query, zero-result search, category view, item view, storefront view,
      contact-seller click. Timestamped, session-keyed.
- [ ] Weekly review of the logs.
- [ ] Month 3+: produce **Demand Report v1** — top unmet searches, substitution signals,
      co-view/co-contact bundles, price sensitivity observations.

### Workstream D — Distribution
- [ ] Get the first 100–500 buyers into the zone: local Facebook groups, WhatsApp community
      groups, physical flyers at the merchants themselves, word of mouth.
- [ ] Track where buyers come from and what they do.

### Phase 1 exit criteria
- ≥ 30 merchants live, covering a meaningful share of the chosen category in the zone.
- ≥ 200 monthly active buyers doing ≥ 500 searches/month.
- Demand Report v1 contains ≥ 1 insight an outsider finds genuinely interesting.
- You know the per-merchant weekly maintenance cost in hours → can model what scaling needs.
- A go / no-go / re-scope decision, written down.

---

## Phase 1.5 — Canonical product layer (one category)
**Goal:** turn segregated storefronts into a unified, searchable product graph for the *densest*
category — the precondition for both the "big unified shop" interface and visual search.
**Trigger:** only when one category has ≥ 8–10 merchants with overlapping inventory.

- [ ] Build a master product table for that one category. Start with items that have barcodes
      or well-known SKUs (packaged goods) — easiest to canonicalize.
- [ ] Matching pipeline: merchant listing → canonical product. Semi-manual first (you approve
      matches), then assisted (string + embedding similarity surfaces candidates).
- [ ] Unified product page: one canonical item, multiple merchant offers (price, stock,
      distance) underneath — the "buy box" pattern, but discovery only, no purchase.
- [ ] Keep per-merchant storefronts for everything not yet canonicalized and for
      unique-inventory merchants.
- [ ] Measure: does unified discovery increase searches / contacts / repeat use vs. segregated?

### Exit criteria
- One category fully unified, merchants still consenting, buyer engagement up, matching cost
  per new listing understood.

---

## Phase 2 — Scale supply + unified discovery + real demand product
**Goal:** move from pilot to a real regional platform. Needs a small team and/or capital.
**Trigger:** Phase 1.5 shows unified discovery lifts engagement and the model has a funding or
revenue path.

### Supply
- [ ] Field-agent playbook: hire/train 2–5 agents, define quota, quality checks, pay structure.
- [ ] Merchant self-service: let merchants update their own stock/prices (app or web form).
- [ ] Expand: more categories, then adjacent zones, then the rest of the city.

### Product
- [ ] On-platform **order capture** (still no payment) — buyer places order, merchant confirms,
      they arrange fulfilment. This is the first step that keeps activity on-platform.
- [ ] **Visual / camera search** — image embeddings + vector search over the canonical catalog.
      Off-the-shelf models; not research.
- [ ] Unified shop becomes the **primary** interface for dense categories; storefronts remain
      for the long tail.
- [ ] Demand-intelligence dashboards as a real internal product.

### Business
- [ ] First monetization test — likely merchant subscription for premium placement /
      analytics, or a lead fee. Not transaction fees yet.
- [ ] Company formation, proper contracts, basic compliance.
- [ ] Decide: raise, or stay bootstrapped and slow.

### Exit criteria
- Multi-zone coverage, thousands of merchants, tens of thousands of buyers, a defensible
  demand dataset, and a validated revenue line covering field-ops cost.

---

## Phase 3 — Demand intelligence → manufacturing
**Goal:** act on the data. This is the original point of the whole exercise.
**Trigger:** the demand dataset is deep enough that a data team can find real signal, and
there's capital.

- [ ] Hire data scientists against the accumulated dataset.
- [ ] Identify 1–2 SKUs where: demand is proven and stable, no incumbent captures the margin,
      and buyer expectations are visibly unmet (quality, price, format, bundling).
- [ ] **Contract-manufacture** those SKUs first — do not build factories. Sell them through
      MTJR's own unified shop as a private label.
- [ ] Measure sell-through, margin, returns, repeat rate against the demand prediction.
- [ ] Own manufacturing units **only after** several contract-manufactured SKUs beat their
      predictions and volume justifies capex.

### Exit criteria
- A private-label line whose performance was predicted by the demand engine before launch —
  the proof that the thesis works.

---

## Cross-cutting workstreams (all phases)

| Workstream | Phase 1 | Phase 2 | Phase 3 |
|-----------|---------|---------|---------|
| **Field ops** | Founder hand-onboards | Agent team + playbook | Regional ops org |
| **Product/eng** | Solo, no-app catalog | Small team, apps, visual search | Data platform + private-label ops |
| **Data** | Event logs → manual report | Dashboards, canonical catalog | ML demand models |
| **Legal/business** | Informal pilot | Company, contracts, monetization | Manufacturing/import, IP |
| **Capital** | Self-funded, ~minimal | Revenue and/or seed raise | Significant raise or partner |

---

## Metrics ladder

| Phase | Primary metric | Guard metric |
|-------|---------------|--------------|
| 0 | Decisions locked; 30–50 merchants scouted | — |
| 1 | Demand Report v1 with a real insight | Merchant retention; founder hours/merchant/week |
| 1.5 | Unified-discovery engagement lift | Merchant consent retained; match cost/listing |
| 2 | Multi-zone GMV-equivalent (order capture volume) | Field-ops cost vs. revenue |
| 3 | Private-label sell-through vs. predicted | Margin, return rate, cannibalization |

---

## Decision Log

| # | Decision | Status | Notes |
|---|----------|--------|-------|
| D1 | Connector-first, transactions off-platform in Phase 1 | **Decided** | Survivor's path; see `PHASING.md` |
| D2 | Asset-light forever (no warehouse/fleet/lending) | **Decided** | Every asset-heavy peer folded |
| D3 | Catalog: segregated storefronts in P1, canonical layer from P1.5, unified primary in P2 | **Decided** | See `ARCHITECTURE-CATALOG.md` |
| D4 | Depth in one zone + category over a wide shallow map | **Decided** | "Boast yield" comes from density |
| D5 | City | Open | Default: home city |
| D6 | Zone / neighborhood | Open | Must be walkable, dense with target merchants |
| D7 | Category set (1–3) | Open | Apply the four selection criteria in Phase 0 |
| D8 | Merchant value proposition (day-one pain solved) | Open | Test 2–3 hypotheses in first merchant visits |
| D9 | Buyer value proposition | Open | Test via distribution experiments |
| D10 | Phase 1 tech stack | Open | Decide at Phase 1 kickoff; optimize for solo maintainability |
| D11 | First monetization model | Open (Phase 2) | Likely merchant subscription / lead fee, not txn fees |
| D12 | Raise vs. bootstrap | Open (Phase 2) | — |

---

## Personal / timing constraints

- The **academic sprint** (pre-studying Diff-Eq + Database Systems for the extension appeal) is
  the current priority. Recommendation: complete Phase 0 on paper now (low load), begin Phase 1
  field work only after the sprint clears.
- Job search is active in parallel — MTJR is not a substitute for income in the near term.
- MTJR is a **venture**, not a bounded software project. It does not have a "done." It competes
  for attention with `receiptless` and `IDent`, which are near-term-completable and have
  momentum. Deliberate choice required — don't drift into it by default.

## Relationship to other projects

- **Not** an easier alternative to `receiptless` or `IDent` — see the answer written up with
  this roadmap. Those are keyboard-only, single-player, finishable. MTJR's software is smaller
  than either, but its field-ops / two-sided-market / capital / regulatory surface makes it a
  categorically harder undertaking.
