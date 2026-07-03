# Alliance Laundry Systems — Print Orders (SATV prototype)

Interactive HTML prototype of the **Print Orders** feature for the SATV app, built for Alliance Laundry Systems. Users select digital assets from the DAM, customize dynamic ones (per-machine QR pages + cover page), and send them to a third-party print provider that handles quantity, delivery and payment.

## Run it

No build, no dependencies — everything (JS, CSS, cover images, logo) is embedded in a single file.

- Open `index.html` in any browser, **or**
- Enable **GitHub Pages** (Settings → Pages → deploy from branch, root) and share the URL.

## What's inside the prototype

- **Print Orders list** — KPI cards, status filter, calendar range picker, search, orders table, empty state
- **New Print Orders** — asset grid with type tabs (All / Ready to Print / Customizable), search, single print path (cards only *add* to selection; the floating pill **Send to Print** is the only trigger)
- **Customize modal** — description accordion, per-machine QR generation with loading state (one page per machine number), cover page library (real client artwork), fixed-size page preview with prev/next
- **Third-party checkout** (mock "PrintCo") — order summary with quantities, delivery address, payment, processing → success → return flow; new order appears in the list
- **Order detail** — delivery / payment / order summary cards + the same asset-card grid as selection, with read-only preview of pages exactly as ordered

## Deliberately mocked / not wired

- QR codes are generated placeholder patterns — they encode nothing; real URL mapping is backend work
- Payment, delivery and pricing are simulated ("Calculated by provider")
- "Today" is pinned to **2026-07-02** so mock order dates and the calendar presets line up

## Open questions for the product owner

1. Which fields does the DAM actually return per asset — and which should show on the card? (`Brand` / `Segment` shown now are **assumptions**, not confirmed.)
2. Third-party print API contract: what does the success payload return (order ID, address, payment status)? This determines what Order Detail can display.
3. What does the QR encode / how does a machine number map to a URL?
4. How is static vs. customizable determined (DAM flag?)
5. Source and ownership of cover pages (preset per brand? user upload?)
6. Handling of an abandoned third-party popup (no success signal)

## Structure

```
index.html   — the whole prototype (self-contained)
README.md    — this file
```
