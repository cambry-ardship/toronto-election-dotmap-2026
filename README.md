# Toronto's 2026 mayoral vote

An animated dot map of every vote cast in Toronto's 2026 mayoral election, placed in the poll it came from.

**Live map:** https://cambry-ardship.github.io/toronto-election-dotmap-2026/

Each poll's dots match its official totals (rounded to the dot size). Which household voted which way is unknown, so dots keep swapping colours with others in their poll. Zoomed out, the map switches from 1 dot = 1 voter through coarser levels to hexagons.

## How it's built

- **Results:** City of Toronto 2026 poll-by-poll results. Advance and mail votes are only reported by ward, so they're spread over each ward's polls in proportion to election-day votes.
- **Placement:** buildings are assigned to polls with the City's 2026 street index. Each poll's voters are placed at its residential buildings (Statistics Canada National Address Register, June 2026) in proportion to estimated citizens 18+ (2021 Census, adjusted for buildings occupied since 2021).
- **Front end:** MapLibre GL JS, deck.gl (colour fades computed on the GPU in OKLab), and a Protomaps basemap.

## Running locally

The basemap needs HTTP range requests, which Python's built-in server doesn't support. Use the included server:

```
python3 serve.py 8000
```

then open http://localhost:8000/.

## Sources and licences

- Contains information licensed under the [Open Government Licence – Toronto](https://open.toronto.ca/open-data-license/) (election results, street index, address points, ward boundaries).
- Adapted from Statistics Canada, 2021 Census of Population and National Address Register. This does not constitute an endorsement by Statistics Canada of this product ([Statistics Canada Open Licence](https://www.statcan.gc.ca/en/reference/licence)).
- Basemap © [OpenStreetMap](https://openstreetmap.org/copyright) contributors, via [Protomaps](https://protomaps.com).
