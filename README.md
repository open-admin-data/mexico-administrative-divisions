# Mexico Administrative Divisions / México



## Overview

| Item | Details |
|------|---------|
| State | 32 |
| Municipality | 2,457 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-08-19 |
| Website | [openadmindata.org/mx](https://openadmindata.org/mx/) |
| API | [openadmindata.org/api/mx](https://openadmindata.org/api/mx/) |
| National Anthem | [🎵 Listen & Download Mexico National Anthem MP3](https://onlygames.me/national-anthems/mx/) |

## Browse by State

| # | State | Municipalitys | Link |
|---|----|----|------|
| 1 | Aguascalientes | 11 | [Browse](divisions/aguascalientes-mx01/) |
| 2 | Baja California | 5 | [Browse](divisions/baja-california-mx02/) |
| 3 | Baja California Sur | 5 | [Browse](divisions/baja-california-sur-mx03/) |
| 4 | Campeche | 11 | [Browse](divisions/campeche-mx04/) |
| 5 | Chiapas | 118 | [Browse](divisions/chiapas-mx07/) |
| 6 | Chihuahua | 67 | [Browse](divisions/chihuahua-mx08/) |
| 7 | Coahuila de Zaragoza | 38 | [Browse](divisions/coahuila-de-zaragoza-mx05/) |
| 8 | Colima | 10 | [Browse](divisions/colima-mx06/) |
| 9 | Distrito Federal | 16 | [Browse](divisions/distrito-federal-mx09/) |
| 10 | Durango | 39 | [Browse](divisions/durango-mx10/) |
| 11 | Guanajuato | 46 | [Browse](divisions/guanajuato-mx11/) |
| 12 | Guerrero | 81 | [Browse](divisions/guerrero-mx12/) |
| 13 | Hidalgo | 84 | [Browse](divisions/hidalgo-mx13/) |
| 14 | Jalisco | 125 | [Browse](divisions/jalisco-mx14/) |
| 15 | México (Mexico) | 125 | [Browse](divisions/mexico-mx15/) |
| 16 | Michoacán de Ocampo (Michoacan de Ocampo) | 113 | [Browse](divisions/michoacan-de-ocampo-mx16/) |
| 17 | Morelos | 33 | [Browse](divisions/morelos-mx17/) |
| 18 | Nayarit | 20 | [Browse](divisions/nayarit-mx18/) |
| 19 | Nuevo León (Nuevo Leon) | 51 | [Browse](divisions/nuevo-leon-mx19/) |
| 20 | Oaxaca | 570 | [Browse](divisions/oaxaca-mx20/) |
| 21 | Puebla | 217 | [Browse](divisions/puebla-mx21/) |
| 22 | Querétaro de Arteaga (Queretaro de Arteaga) | 18 | [Browse](divisions/queretaro-de-arteaga-mx22/) |
| 23 | Quintana Roo | 10 | [Browse](divisions/quintana-roo-mx23/) |
| 24 | San Luis Potosí (San Luis Potosi) | 58 | [Browse](divisions/san-luis-potosi-mx24/) |
| 25 | Sinaloa | 18 | [Browse](divisions/sinaloa-mx25/) |
| 26 | Sonora | 72 | [Browse](divisions/sonora-mx26/) |
| 27 | Tabasco | 17 | [Browse](divisions/tabasco-mx27/) |
| 28 | Tamaulipas | 43 | [Browse](divisions/tamaulipas-mx28/) |
| 29 | Tlaxcala | 60 | [Browse](divisions/tlaxcala-mx29/) |
| 30 | Veracruz de Ignacio de la Llave | 212 | [Browse](divisions/veracruz-de-ignacio-de-la-llave-mx30/) |
| 31 | Yucatán (Yucatan) | 106 | [Browse](divisions/yucatan-mx31/) |
| 32 | Zacatecas | 58 | [Browse](divisions/zacatecas-mx32/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-state.json](data/all-state.json) | JSON | All 32 state records |
| [all-municipality.json](data/all-municipality.json) | JSON | All 2,457 municipality records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-1 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-state.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['municipality']} municipalitys")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-state.json", "utf-8"));
console.log(`Total: ${data.length} states`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=state, 2=municipality |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{state-slug}/
```

Municipalitys are listed inline in each state's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-state links
- [Per-state data](docs/llms-full/) — Full data by state

## Citation

```
Mexico Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/mexico-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
