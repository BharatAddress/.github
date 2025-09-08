# Repository Guidelines

## Project Structure & Module Organization
- Multi-repo workspace: each top-level project lives in its own GitHub repo. Work inside that repo and open PRs there.
- Layout overview:
  - `api-server/` FastAPI reference API (OGC API Features-like)
  - `tools-validator/`, `tools-converters/` Python CLIs (Click)
  - `clients/python/`, `clients/js/` reference clients
  - `specs/` JSON Schema, OpenAPI, examples
  - `docs-site/` MkDocs site; `bharataddress.github.io/` Next.js org site
- Tests live in each repo under `tests/`.

## Build, Test, and Development Commands
- Common: Python 3.11+, Node 18+.
- API: `cd api-server && uvicorn main:app --reload --port 8000`
- Validator: `cd tools-validator && python validate.py --help`
- Converters: `cd tools-converters && python osm_to_register.py --help`
- JS client: `cd clients/js && npm ci && npm run build`
- Docs: `cd docs-site && pip install -r requirements.txt && mkdocs serve`

## Coding Style & Naming Conventions
- Python: 4-space indent, type hints, snake_case; classes in PascalCase.
- Format with Black; lint with Ruff. Fix before pushing.
- CLI scripts are small Click-based `*.py` files.
- JS/TS: ESM modules, types in `src/`, minimal exports.

## Testing Guidelines
- Framework: pytest. Name tests `test_*.py`; fixtures in `conftest.py`.
- Add unit tests for new endpoints, CLIs, and models; keep tests fast and isolated.
- Run per-repo: `pytest -q` from the repo root.

## Multi-Repo Workflow
- Open PRs in the matching GitHub repo against `main`.
- For coordinated changes, use the same branch name across repos (e.g., `feat/api-pagination`) and reference the same issue.

## Commit & Pull Request Guidelines
- Conventional Commits: `feat:`, `fix:`, `docs:`, `chore(repo):`, `refactor:`.
- PR checklist: description + rationale, linked issue(s), tests/docs updated, CI green. Add screenshots for docs/UI.
- Prefer scoped titles (e.g., `feat(api-server): add bbox filter`).

## Repo Map
- `api-server/` → `BharatAddress/api-server` (main)
- `tools-validator/` → `BharatAddress/tools-validator` (main)
- `tools-converters/` → `BharatAddress/tools-converters` (main)
- `clients/python/` and `clients/js/` → `BharatAddress/clients` (main)
- `specs/` → `BharatAddress/specs` (main)
- `docs-site/` → `BharatAddress/docs-site` (main)
- `bharataddress.github.io/` → `BharatAddress/bharataddress.github.io` (source)

Verify remotes/branches: `git remote -v` and `git rev-parse --abbrev-ref HEAD`.
