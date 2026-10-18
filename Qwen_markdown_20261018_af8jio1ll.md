# GovBid Intelligence Platform (static export)

Single-file, frontend-only demonstration build of an AI-styled government tender
discovery and bid-intelligence workspace. Exported unchanged from Qwen Web Dev.

## Run locally
Open `index.html` in any modern browser. No build step, no server, no packages.
Internet is needed only for the two font stylesheets (jsDelivr CDN); the app
falls back to system fonts offline.

## Project structure
- index.html  - complete application (inline CSS + inline JS, two script blocks)
- render.yaml - Render static-site blueprint
- README.md   - this file

## Demo data vs working backend (verified from source)
DEMO / simulated (client-side only, resets on reload):
- Sign-in (local check only; any valid email + non-empty password passes)
- All 12 tender records, requirements, corrigenda, version histories
- Portal sync runs, job queues, adapter traces, duplicate report
- Eligibility / relevance scoring, gap and risk analysis (JS heuristics)
- "Ask AI" RAG answers (keyword grounding over embedded demo documents)
- Document upload pipeline, OCR/extraction steps, synthetic extracted facts
- AI company profile, conflicts, rebuilds (in-memory state)
- Pipeline board, notes, outcomes, notifications, analytics, settings, overrides
- localStorage is used ONLY for the light/dark theme preference (try/catch guarded)

REAL / working:
- Outbound links to official portals: https://etender.up.nic.in/ and
  https://mptenders.gov.in/ (new tab; INVALID-source records show a message
  instead of redirecting)
- Font loading from jsDelivr CDN

NOT PRESENT in source (do not assume they exist):
- No backend API, no database, no Supabase connection, no server authentication
- No Gemini / LLM API calls, no embeddings service, no OCR service
- No tender scraping / crawling code, no fetch/XHR/WebSocket calls at all
- No file storage; uploaded files are processed in memory only

## Deploy
See render.yaml. On Render create a Static Site, connect the repository, leave
the build command empty and publish the repository root.