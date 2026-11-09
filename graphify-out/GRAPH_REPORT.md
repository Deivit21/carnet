# Graph Report - carnet  (2026-11-09)

## Corpus Check
- Corpus is ~2,554 words - fits in a single context window. You may not need a graph.

## Summary
- 46 nodes · 74 edges · 8 communities (7 shown, 1 thin omitted)
- Extraction: 85% EXTRACTED · 15% INFERRED · 0% AMBIGUOUS · INFERRED: 11 edges (avg confidence: 0.9)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- Editor imagen carnet
- Carrusel de servicios UPV
- Navegación por pestañas
- Render y códigos QR/barras
- PWA y service worker
- Persistencia localStorage
- Hoja de edición
- Vista calendario

## God Nodes (most connected - your core abstractions)
1. `MiUPV Prototipo (index.html)` - 11 edges
2. `SVC service registry` - 9 edges
3. `Servicios UPV carousel` - 7 edges
4. `render()` - 7 edges
5. `Card image button (#card)` - 6 edges
6. `openEditor()` - 6 edges
7. `image state` - 5 edges
8. `showView()` - 5 edges
9. `fPhoto change handler (crop to 1.6:1)` - 5 edges
10. `commit()` - 5 edges

## Surprising Connections (you probably didn't know these)
- `MiUPV Prototipo (index.html)` --implements--> `MiUPV Carnet PWA prototype`  [INFERRED]
  index.html → index.html  _Bridges community 2 → community 0_
- `showView()` --references--> `Calendario view`  [INFERRED]
  index.html → index.html  _Bridges community 7 → community 2_
- `MiUPV Prototipo (index.html)` --references--> `Card image edit sheet`  [EXTRACTED]
  index.html → index.html  _Bridges community 2 → community 6_
- `MiUPV Prototipo (index.html)` --references--> `manifest.webmanifest`  [EXTRACTED]
  index.html → index.html  _Bridges community 2 → community 4_
- `MiUPV Prototipo (index.html)` --references--> `Service modal`  [EXTRACTED]
  index.html → index.html  _Bridges community 2 → community 1_

## Import Cycles
- None detected.

## Hyperedges (group relationships)
- **Card image edit and persist flow** — index_openeditor, index_photo_change, index_renderdraft, index_commit, index_save, index_render [EXTRACTED 1.00]
- **Service tile to modal flow** — index_services_carousel, index_svc, index_svc_modal, index_barcodesvg, index_qrsvg, index_parkings [EXTRACTED 1.00]
- **Tab-based view navigation** — index_tab_bar, index_showview, index_view_carnet, index_view_avisos, index_view_calendario, index_view_menu [INFERRED 0.95]

## Communities (8 total, 1 thin omitted)

### Community 0 - "Editor imagen carnet"
Cohesion: 0.33
Nodes (10): Card aspect ratio 1.6:1, Card image button (#card), commit(), draft state, image state, MiUPV Carnet PWA prototype, openEditor(), fPhoto change handler (crop to 1.6:1) (+2 more)

### Community 1 - "Carrusel de servicios UPV"
Cohesion: 0.29
Nodes (10): Carousel dots indicator, Carousel scroll handler, PARKINGS data, Servicios UPV carousel, SVC service registry, Barcode service tile, Door opening service tile, Service modal (+2 more)

### Community 2 - "Navegación por pestañas"
Cohesion: 0.43
Nodes (7): MiUPV Prototipo (index.html), App icons (icon-192, icon-180), showView(), Bottom tab bar navigation, Avisos (notices) view, Carnet view, Menu view

### Community 3 - "Render y códigos QR/barras"
Cohesion: 0.50
Nodes (5): barcodeSVG(), $ (getElementById helper), DOOR_SVG, qrSVG(), render()

### Community 4 - "PWA y service worker"
Cohesion: 0.40
Nodes (4): manifest.webmanifest, Offline-capable PWA, Service worker registration, FILES

### Community 5 - "Persistencia localStorage"
Cohesion: 0.67
Nodes (4): load(), localStorage, save(), STORE_KEY 'miupv-prototipo-img'

### Community 6 - "Hoja de edición"
Cohesion: 1.00
Nodes (3): closeEditor(), editForm submit handler, Card image edit sheet

## Knowledge Gaps
- **4 isolated node(s):** `$ (getElementById helper)`, `Sample calendar items`, `PARKINGS data`, `App icons (icon-192, icon-180)`
  These have ≤1 connection - possible missing edges or undocumented components. (Counts symbols only; 5 node(s) total have ≤1 connection when file, concept and rationale nodes are included.)
- **1 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `MiUPV Prototipo (index.html)` connect `Navegación por pestañas` to `Editor imagen carnet`, `Carrusel de servicios UPV`, `PWA y service worker`, `Hoja de edición`, `Vista calendario`?**
  _High betweenness centrality (0.430) - this node is a cross-community bridge._
- **Are the 2 inferred relationships involving `Card image button (#card)` (e.g. with `fPhoto change handler (crop to 1.6:1)` and `UPV student card (carnet)`) actually correct?**
  _`Card image button (#card)` has 2 INFERRED edges - model-reasoned connections that need verification._
- **What connects `$ (getElementById helper)`, `Sample calendar items`, `PARKINGS data` to the rest of the system?**
  _4 weakly-connected nodes found - possible documentation gaps or missing edges._
- **Why does `Carnet view` connect `Navegación por pestañas` to `Editor imagen carnet`, `Carrusel de servicios UPV`?**
  _High betweenness centrality (0.234) - this node is a cross-community bridge._
- **Why does `Card image button (#card)` connect `Editor imagen carnet` to `Navegación por pestañas`, `Render y códigos QR/barras`?**
  _High betweenness centrality (0.193) - this node is a cross-community bridge._