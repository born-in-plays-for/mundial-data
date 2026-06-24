# mundial-data

Shared data files for the [Born In, Plays For](https://github.com/born-in-plays-for) project.

This repo is included as a git submodule at `data/` in both [mundial](https://github.com/born-in-plays-for/mundial) (frontend) and [mundial-build](https://github.com/born-in-plays-for/mundial-build) (pipeline).

## Files

| File | Description |
|---|---|
| `wc2026_map_data.json` | Player exports + natives by birth country, population, `wiki_langs` |
| `wc2026_elo_rank.json` | Current World Football Elo ratings (source: eloratings.net) |
| `wc2026_elo_history.json` | Monthly Elo rating history (bar chart race) |
| `countries.json` | Population + multilingual capital names by ISO numeric id |
| `uk-nations.geojson` | Polygons for England, Scotland, Wales, Northern Ireland |
| `wc2026_gdp.json` | GDP total by country (World Bank) |
| `wc2026_gdp_pc_ppp.json` | GDP per capita PPP by country (World Bank) |
| `wc2026_hdi.json` | Human Development Index by country (UNDP) |

## Workflow

The pipeline in `mundial-build` generates these files:

```bash
# In mundial-build — after running the pipeline:
cd data
git add -A && git commit -m "update data" && git push

# In mundial — pull the latest:
cd data
git pull origin main
cd ..
git add data && git commit -m "update data submodule" && git push
```

## See also

- [born-in-plays-for](https://github.com/born-in-plays-for) — org overview + architecture diagram
- [mundial](https://github.com/born-in-plays-for/mundial) — frontend
- [mundial-build](https://github.com/born-in-plays-for/mundial-build) — data pipeline
