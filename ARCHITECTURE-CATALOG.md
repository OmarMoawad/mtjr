# MTJR — Catalog Architecture: Unified Shop vs. Per-Merchant Storefronts

*2026-09-01. Answers the question: should MTJR be one big Amazon-like shop with pooled stock
from all merchants, or the Talabat/InstaShop model where each store is its own virtual shop
inside the app?*

## The two models

### Model A — Per-merchant storefronts (Talabat / InstaShop / Uber Eats)
Buyer picks a store first, then browses *that store's* catalog. Each merchant's listings are
independent. No notion of "the same product across stores."

- **Pro:** trivial to build. A listing is just text + photo + price under a merchant. No
  normalization. Matches how you actually acquire supply — one merchant at a time.
- **Pro:** preserves merchant identity and relationship. The merchant feels ownership, is not
  commoditized. Easier to get their buy-in — important for your shoe-leather moat.
- **Con:** fragmented data. "What does the market need for rice?" requires stitching together
  dozens of differently-named listings by hand. Weak demand intelligence.
- **Con:** bad buyer experience for comparison shopping ("who near me has this, cheapest?").

### Model B — Unified catalog (Amazon)
One canonical product ("Indomie Chicken 70g"). Multiple merchants attach *offers* (price,
stock, distance) to it. Buyer searches the product, sees all offers.

- **Pro:** this is what makes the demand-intelligence thesis work. Clean, cross-market signal:
  demand per canonical SKU, substitution, bundling, price elasticity, unmet demand.
- **Pro:** best buyer experience for "find/compare what's near me."
- **Pro:** precondition for visual/camera search (you search an image → a canonical product →
  offers).
- **Con:** the **catalog normalization problem** is the single hardest data problem in the
  whole marketplace. Deciding that merchant X's "اندومي فراخ" and merchant Y's "Indomie
  chicken flavour" are the same SKU, at scale, across categories, in two languages, with
  variants and unit differences — Amazon has worked on this for 25 years (ASINs, brand
  registry, catalog teams). Instacart/Talabat mostly *avoid* it by staying per-store.
- **Con:** commoditizes merchants (they become interchangeable price lines) — some will resist.

## Verdict on your instinct

Your bias — **do both, with the unified shop as the primary interface** — is **directionally
correct for the end state** and wrong as a *starting* build order.

- Unified-as-primary is the right Phase 2+ target. It is where the demand data, the buyer
  experience, and visual search all point.
- Building it upfront is not feasible solo: you'd spend all your time on catalog normalization
  instead of acquiring supply and learning demand, and you'd have nothing to normalize until
  you have overlapping merchants anyway.

The unified catalog is **earned, category by category, as merchant density justifies it** —
not built on day one.

## Recommended sequencing

| Phase | Model | Why |
|-------|-------|-----|
| **P1** | Per-merchant storefronts only | Ship fast, acquire supply one merchant at a time, start logging demand events. No normalization. |
| **P1.5** | Add a canonical layer for the **one densest category** | Only once ~8–10 merchants have overlapping inventory. Start with barcoded / known-SKU packaged goods — easiest to canonicalize. Keep storefronts for everything else. |
| **P2** | Unified shop becomes **primary** for dense categories; storefronts remain for the long tail and unique-inventory merchants | Both models coexist — exactly your instinct, just phased. Visual search rides on the canonical layer here. |

## The hybrid that resolves the merchant-commoditization tension

Do not make it pure Model B. Use the **Amazon-marketplace hybrid**:

- Unified discovery (search a product, see offers) **and** every offer clearly shows *which
  merchant*, their distance, and links to their storefront page.
- Merchants keep a real storefront identity, ratings, and their unique/long-tail items that
  never get canonicalized.
- No algorithmic "buy box" that hides merchants — show all nearby offers, let the buyer choose.

This keeps the demand-intelligence benefit of unification while protecting the merchant
relationship that is your actual moat.

## Practical notes on building the canonical layer (Phase 1.5)

- **Seed from barcodes.** Packaged FMCG in Egypt largely carries EAN barcodes; a barcode scan
  on onboarding resolves most packaged goods to a shared identity for free.
- **Category by category.** Never try to canonicalize the whole catalog. Groceries first,
  fresh produce and hardware much later (or never).
- **Human-in-the-loop matching.** String similarity + text embeddings surface candidate
  matches; you (or an ops person) approve. Fully automatic matching will corrupt the dataset.
- **Unmatched is fine.** A listing that isn't matched to a canonical product still lives on its
  merchant's storefront and still logs demand events. Coverage grows over time.
- **Units and variants** are where it gets nasty — define a small schema early (base unit, pack
  size, variant axis) so you don't rework it.
