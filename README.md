# Fab-Form Calculators

One page, two tabs, sharing the same header and light/dark toggle:

- **Rental Quote** (`#rental`): used-equipment rental quote (from `Rental-Calculator`)
- **Pallet Weight** (`#weight`): shipping weight, box sizes, pallet L × W × H and product value (from `Weight-Calculator-FBF`)

Link straight to a tab with `.../index.html#rental` or `.../index.html#weight`. The page remembers the last tab,
and each tab keeps its own quantities and settings in the browser (old saved data from both original pages still loads).

## Pallet Weight: what's new

- **Contractor prices (July 2026)** on every product, with a *Product value* total (before shipping and tax, FOB Delta)
- Products added from the price list: **Level-R**, **MPHD**, **MID ZOTE**
- **Box size (L × W × H)** shown on every card, summary line and copied summary
- **Pallet size:** Small 44 × 30 or Big 48 × 44. Enter the height **H**, or leave it blank to have it estimated
  (5" pallet deck + box volume spread over the footprint at 85% fill, never shorter than the tallest box lying flat).
  Shows pallet L × W × H and density (lb/ft³)
- **Fast-Tube packing** (H = height of that size's 10' Fast-Tube box: 13, 16, 20, 23, 26, 30):
  - 100' rolls: **Half box H × 21 × 6** (1 roll, default), **Full box** 11 × 21 × H (2 rolls), or **Full + half** (pairs in full boxes, odd roll in a half box)
  - 10' pieces: full boxes of 20, with leftovers going in a **sample box H × 10 × 6** (capacity editable, default 5)
  - Half and sample box empty weights are estimated from cardboard area (0.001 lb/in²)

## Put it live with GitHub Pages

Upload `index.html` and the `images/` folder to the repo root, then **Settings → Pages → Deploy from a branch → `main`, `/ (root)`**.

## Editing data

- Rental prices: `PRODUCTS` in the *RENTAL QUOTE* script block
- Weights, prices, box sizes: `PRODUCTS` in the *PALLET WEIGHT* script block (`price`, `wt`, `per`, `dims`, `boxWt`; Fast-Tube rows also have `ft` and `ftH`)
- Pallet footprints, deck height, fill factor, cardboard weight: `PALLETS`, `PALLET_DECK`, `PALLET_FILL`, `CARDBOARD`

Note: the price list shows the FT16 roll as "2.4" per box and FT18 roll as "20" per box. Both are treated as 2.
