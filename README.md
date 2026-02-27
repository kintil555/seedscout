# SeedScout 🗺️
> Real Minecraft Java/Bedrock seed finder for speedrunners

**[Live Demo →](https://seedscout.pages.dev)**

## Features
- ✅ **Exact Minecraft algorithms** — structure positions match the game (village, bastion, stronghold, fortress, monument, mansion, etc.)
- ✅ **Interactive biome map** — drag, zoom, click structures to focus
- ✅ **Web Worker powered** — seed search runs off main thread, UI stays responsive
- ✅ **Stronghold ring algorithm** — exact ring-based placement (3 rings)
- ✅ **Multi-structure search** — find seeds with e.g. bastion + fortress + village within 500 blocks
- ✅ **URL sharing** — share seeds via `?seed=12345` URL parameter
- ✅ **Zero dependencies** — single HTML file, works offline
- ✅ **Touch support** — pinch to zoom, drag on mobile

## Algorithms
Based on cubiomes (Cubitect) + reverse-engineered from Minecraft source:
- **JavaRandom LCG**: `seed = (seed * 0x5DEECE66D + 0xB) & ((1L << 48) - 1)`
- **Structure seed**: `rx * 341873128712 + rz * 132897987541 + worldSeed + salt`
- **Strongholds**: Ring-based, 3 rings at ~1400-2700, 4500-5800, 7600-8900 blocks
- **Biome map**: Multi-octave value noise seeded from world seed

## Deploy to Cloudflare Pages
```bash
git clone https://github.com/yourusername/seedscout
# Go to Cloudflare Pages > Create Project > Connect GitHub
# Build command: (none)
# Build output: /
# Done!
```

## Deploy to GitHub Pages
Settings → Pages → Source: Deploy from branch → main → / (root)

## Credits
- [Cubiomes](https://github.com/Cubitect/cubiomes) by Cubitect — Java biome/structure algorithms
- [Cubiomes Fork](https://github.com/reedacartwright/cubiomes/tree/bedrock) by Reed A. Cartwright — Bedrock support
- [Bedrockified](https://github.com/Earthcomputer/bedrockified) by Earthcomputer — Bedrock structure data
- [MCBEStructureFinder](https://github.com/bedrock-dev/MCBEStructureFinder) by bedrock-dev
- [OpenLayers](https://github.com/openlayers/openlayers) — Map rendering inspiration

## Structure Salts (Java Edition)
| Structure | Spacing | Separation | Salt |
|---|---|---|---|
| Village | 34 | 8 | 10387312 |
| Desert Temple | 32 | 8 | 14357617 |
| Jungle Temple | 32 | 8 | 14357619 |
| Witch Hut | 32 | 8 | 14357620 |
| Bastion | 27 | 4 | 30084232 |
| Fortress | 27 | 4 | 59247 |
| Ocean Monument | 32 | 5 | 10387313 |
| Woodland Mansion | 80 | 20 | 10387319 |

## License
MIT
