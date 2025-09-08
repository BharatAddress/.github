# Bharat Address Open Source Project

Website: https://bharataddress.github.io — landing, docs (/docs), playground (/playground), developers (/developers)

Publish a minimal, adoptable open standard and reference tooling for India’s address data — pairing human-readable addresses with precise DIGIPIN cells, PIN compatibility, and LGD identifiers. We integrate; we do not reinvent.

## What We Build
- Specs: minimal address feature schema and guidance (DIGIPIN, PIN, LGD, optional ULPIN)
- API: reference OGC API Features service (FastAPI; PostGIS later)
- Tools: validator and converters (OSM ↔ Register, LGD↔PIN join)
- Clients: lightweight Python and JS SDKs
- Integrations: Bharat Maps adoption notes, WFS pull, demo viewer
- Pilots: ready-to-fork city templates and sample wards

## Repositories
- specs: https://github.com/BharatAddress/specs
- api-server: https://github.com/BharatAddress/api-server
- tools-validator: https://github.com/BharatAddress/tools-validator
- tools-converters: https://github.com/BharatAddress/tools-converters
- clients: https://github.com/BharatAddress/clients
- integrations-bharatmaps: https://github.com/BharatAddress/integrations-bharatmaps
- pilots: https://github.com/BharatAddress/pilots
- docs-site: https://github.com/BharatAddress/docs-site
- governance: https://github.com/BharatAddress/governance

## Quick Start
- Read the schema in `specs` and the minimal OGC API Features stub.
- Run the demo API: `uvicorn main:app --port 8000` in `api-server` (set `CORS_ALLOW_ORIGINS` to include the site when testing from the browser).
- Validate sample data: see `tools-validator` README.
- Try the viewer: open `integrations-bharatmaps/viewer.maplibre.html`.

## Principles
- No new geocode (use DIGIPIN)
- No parallel basemap (use Bharat Maps)
- No bespoke formats (use OGC API Features and GeoJSON)
- LGD as keyspace to join everything

## Security
- Report vulnerabilities privately via GitHub Security Advisories on the affected repo.

## License
- Code: MIT
- Docs/schemas: CC BY 4.0
