# MTJR — Phasing & Assessment of the "Connector-First" Plan

*2026-09-01*

## Your proposed starting move (restated)

> Start with the part that needs least tech, least implementation, and gives the highest
> "boasting yield" that is leverage-able into later phases. Concretely: **inspect ALL merchants
> on the map and digitize them**, ship **the most researched, organized online shopping
> interface**, and **only connect buyers with sellers** — add further processes later.

## Verdict: right instinct, one internal contradiction to fix

**Right:** starting as a pure buyer↔seller connector, with no payments / logistics / lending /
registration, is the correct lowest-tech wedge. Almost every marketplace started this way. It
keeps you out of the capital-intensive, regulated, asset-heavy traps that killed most peers
(`LANDSCAPE.md`).

**The contradiction:** "least implementation" and "ALL merchants on the map" cannot both be
true. Inspecting and digitizing *every* merchant — visiting them, photographing stock, building
catalogs, training them, keeping data fresh — is the single most labor- and capital-intensive
activity in the entire plan. It is low-*tech* but extreme-*effort*. MaxAB-Wasoko and Cartona
each spent years and $20M–$200M+ building exactly this field muscle, and most competitors that
tried it (Wabi, Zumi, MarketForce, Joovlin, Sokowatch's early e-comm) shut down or pivoted.

As a solo founder mid-academic-sprint with constrained funding, "all merchants" is not a
startable scope.

## The fix: depth in a sliver, not breadth

"Boasting yield" does not come from a shallow map with thin coverage — that demos badly. It
comes from **density in one niche** plus **one striking insight**. The boast you want is:

> "In [neighborhood/city], for [category], we have digitized X merchants covering ~Y% of local
> supply, Z buyers transact monthly, and here is a demand pattern the merchants themselves
> missed — [specific example]."

That is leverage-able into funding and Phase 2/3 conversations. A half-populated national map
is not.

## Recommended Phase 1 (nights/weekends-scale, ~3–6 months of real calendar)

**Scope lock**
- 1 city (start with your own).
- 1 neighborhood or 1 well-defined merchant cluster.
- 1–3 product categories where substitution and bundling are interesting (e.g. groceries +
  household, or auto parts, or building materials, or stationery/office).

**Supply side (the digitization)**
- Onboard 20–50 merchants *by hand*, yourself. No field-agent team yet.
- Capture per merchant: identity/location, category, a photographed product list with prices,
  stock on/off. Nothing more. A spreadsheet or Airtable is acceptable before any app.
- The only merchant-facing promise: "free digital shopfront, more customers, zero cost, you
  keep every existing process." No fees in Phase 1.

**Demand side (the interface)**
- A clean, genuinely well-researched web catalog: search, filter, category browse, merchant
  pages, "request/contact seller." This is where your taste and rigor differentiate — it is
  cheap to build and most local competitors do it badly.
- Camera/visual search: *defer the real ML.* Phase 1 can ship text search + photos. Add
  image-based lookup only once there's a catalog worth searching. (When you do: it's an
  off-the-shelf embedding + nearest-neighbour problem, not a research project.)
- Transactions happen off-platform (call, WhatsApp, in person). You are a directory + demand
  sensor, not a checkout.

**Data (the actual point)**
- Log every search, every "no results," every merchant page view, every contact click.
- The Phase 1 deliverable is not GMV — it's the first demand report.

**Phase 1 is done when** you can show density + one real demand insight to an outsider and
have them say "huh, that's interesting."

## Phase 2 (only after Phase 1 validates, and with help/capital)

- Field-agent playbook to scale merchant count.
- On-platform ordering (still no payments — order capture only).
- Real visual search.
- Structured demand-intelligence dashboards.
- Expand categories, then city zones.

## Phase 3 (years out, needs capital + team + data depth)

- Hire data scientists against a dataset that's actually rich.
- Identify 1–2 products where demand is proven, margins are captured by nobody, and expectations
  are unmet.
- Pilot contract manufacturing (not own factories) for those SKUs first.
- Own manufacturing units only after contract-manufactured SKUs prove out.

## Sequencing guardrail

Do not touch: payments, credit/BNPL, delivery fleet, warehousing, government registration,
multi-city, or manufacturing — until the phase that calls for it. Each is a company-killer at
the wrong time. This is the lesson from every shutdown in `LANDSCAPE.md`.

## Timing note (personal)

This conflicts with the academic sprint (pre-studying Diff-Eq + Database Systems for the
extension appeal) which is the current priority. Recommended: keep MTJR as a *documented,
scoped* plan now; begin Phase 1 hand-onboarding only after the sprint clears. Flagged, your
call.
