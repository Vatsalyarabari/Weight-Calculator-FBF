# Fab-Form Pallet Weight Estimator

Estimates the shipping weight of a pallet of Fab-Form products, using the unit and box weights from the
Contractor price list (July 2026).

- Type a quantity or press **+ Box** to add a full box (e.g. 4 FF50 rolls, 20 Zonts, 2 Fast-Tube rolls)
- Partly-filled boxes count the product inside plus the empty box
- **Custom boxes**: build your own mixed box (e.g. *FF50 kit = 1 × FF50 roll + 5 × FF50C*), with an
  empty-box weight and optional size. Use "Other item" for anything not on the list
- Pick whether Zonts ship in cardboard boxes or Zote totes, and Zuckles in boxes or Lo Zote totes
- Number of pallets and empty-pallet weight (default 45 lb) are editable
- Totals in lb and kg, box count, carton volume (ft³), **Copy summary** and **Print / PDF**
- Edits (quantities, custom boxes, weight overrides) are remembered in your browser

## Put it live with GitHub Pages

1. Create a new public repo (e.g. `pallet-weight`).
2. Upload `index.html` and the `images/` folder to the repo root.
3. **Settings → Pages** → Deploy from a branch → `main`, `/ (root)` → Save.
4. Link: `https://vatsalyarabari.github.io/pallet-weight/`

## Updating weights

Edit the `PRODUCTS` list in `index.html`: `wt` is one unit's weight (lb), `per` is units per box,
`boxWt` is a full box from the price list, `dims` is the box size in inches.
The empty-box weight is worked out as `boxWt − per × wt`.

Note: the price list shows the FT16 roll as "2.4" per box; this uses 2 (2 × 19.8 lb + box = 42 lb).
