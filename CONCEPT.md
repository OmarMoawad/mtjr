# MTJR — Concept

*Captured 2026-09-01. Early-stage thinking. Not a commitment.*

## One-line

A merchant-first commerce platform: digitize real-world merchants at ground level, put a
well-designed marketplace on top that only connects buyers and sellers, and use the resulting
demand data to eventually decide what to manufacture.

Name: **MTJR** — reads as متجر (matjar, "store") and تاجر (tajir, "merchant").

## The real thesis

The marketplace is not the asset. The asset is a proprietary, ground-truth dataset of **what
people need, why they need it, how they bundle it, and what they expect from it** — collected
by owning both sides of the transaction (digitized merchants + a search/scan interface buyers
actually use). That dataset is what later justifies vertical integration into manufacturing.

This is the Shein/Temu **C2M** (consumer-to-manufacturer) logic — demand-sensing drives
small-batch production — applied to a market where the supply side (merchants) is still
undigitized.

## Three stacked businesses (do NOT build simultaneously)

| # | Business | Tech sophistication | Capital need | Role |
|---|----------|--------------------|--------------|------|
| 1 | Merchant digitization (catalog, inventory, basic ops) | Low | **High (field ops)** | The wedge / moat |
| 2 | Marketplace — pure buyer↔seller connector | Low–medium | Low–medium | Data-collection surface |
| 3 | Demand-intelligence engine → own manufacturing | Very high | Very high | The prize (years out) |

Phase 1 = businesses 1 + 2, deliberately kept dumb (no payments, no logistics, no lending,
no registration-as-a-service). See `PHASING.md`.

## What is genuinely defensible

- A field operation that has **physically digitized N merchants and owns their transaction
  data** is not copyable by a software team. Shoe-leather moat.
- **Camera/visual product search over a live local inventory** is a real unlock where catalogs
  are messy, bilingual, and barcode-free. Big players do this badly regionally.
- Owning the "what to make" decision with real demand data beats guessing — *if* you get to
  Phase 3 with a rich enough dataset.

## What is NOT defensible / hard

- The marketplace UI itself — table stakes, copyable.
- "Digitize ALL merchants" — that is the *most* operationally expensive part of the whole plan,
  not the cheapest. Well-funded players (MaxAB-Wasoko, Cartona) have spent years and tens of
  millions on exactly this and most rivals have shut down. See `LANDSCAPE.md`.
- Manufacturing — different competency, brutal capex.
- "Automate merchant registration" with government/tax authorities — regulated, jurisdiction-
  specific, a legaltech/fintech company on its own. Defer entirely.

## Open questions to resolve before committing

1. **Geography + category**: one city, which one, which 1–3 product categories?
2. **Who does the field digitization?** Solo founder can onboard ~dozens by hand for a pilot.
   Beyond that needs agents + capital. What's the realistic pilot ceiling?
3. **Why do merchants say yes?** What non-negotiable pain does Phase 1 solve for them on day
   one (before any buyer volume exists)?
4. **Why do buyers come** to a new marketplace with thin catalog vs. Amazon.eg / Noon?
5. **What is the smallest demonstration** of the demand-intelligence insight that would be
   "boastable" to a sponsor/partner/investor?
