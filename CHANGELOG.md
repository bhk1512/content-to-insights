# Changelog
All notable changes to this project are documented here.  
Format loosely follows [Keep a Changelog] and semantic versioning.

## [1.1.0] - 2025-09-01 — Public skeleton
### Added
- Minimal **showcase** repo with four modular n8n workflows:
  - `collect-videos.skeleton.json`
  - `de-duplication.skeleton.json`
  - `fetch-transcript-and-analyze.skeleton.json`
  - `create-files.skeleton.json` (Markdown → optional PDF)
- `assets/` screenshots for quick overview.
- README-lite explaining Problem → Action → Result → Learnings and 5-step run guide.

### Changed
- **Sanitized secrets & IDs**:
  - Replaced Google Sheets ID with env var **`CTI_SHEETS_DOC_ID`**.
  - Removed fixed sub-workflow IDs in “Execute Workflow” nodes (relink by name after import).
  - File paths now use **`CTI_BASE_DIR`**; MD→PDF script path uses **`CTI_MD2PDF`**.
- Prompts/notes clarified for transcript → summary → Markdown flow.

### Removed
- Hard-coded Windows/local file paths.
- Inline Sheet IDs and any credentials.

### Notes
- Functionally equivalent to the private build once credentials are linked and env vars are set.
- Intended for **reading, cloning, and local re-wiring**; not a turnkey deploy.

## [1.0.0] - 2025-08-xx — Private build (internal)
### Added
- End-to-end pipeline:
  - Collect new YouTube videos (video/playlist/channel), paginate playlists.
  - De-dup against a `Videos` Google Sheet tab.
  - Fetch transcript (Supadata) → summarise with Gemini (narrative + 5–7 bullets).
  - Write Markdown notes; optional MD→PDF conversion.
- ~4 hours → ~5 minutes per talk (≈30× faster capture).

