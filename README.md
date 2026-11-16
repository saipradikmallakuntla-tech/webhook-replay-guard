> **Current seven-repository documentation map — 2026-11-16 UTC · CAT-v1**  
> **Primary category:** `REL-WEBHOOK` — Reliability → Webhook Freshness & Deduplication.  
> [Canonical Category Index and Directory](https://github.com/saipradikmallakuntla-tech/zion-ai-apps-hub/blob/main/CATEGORY_INDEX_AND_DIRECTORY.md) · [Seven-node registry](https://github.com/saipradikmallakuntla-tech/zion-ai-apps-hub/blob/main/NETWORK.md) · [Portfolio status](https://github.com/saipradikmallakuntla-tech/zion-ai-apps-hub/blob/main/PORTFOLIO_STATUS.md) · [Locale/review register](https://github.com/saipradikmallakuntla-tech/zion-ai-apps-hub/blob/main/TRANSLATION_PARITY_REGISTER.md).  
> This owner-approved documentation map covers seven existing owned repositories: one hub and six utilities. Earlier scope statements/counts below are retained dated batch history. Current written coverage is **79 IDs / 237 locale entries total**, not approvals or apps; 48 pre-existing Markdown files plus the new index give 49 files. Category labels classify documentation, not website filters or software. Satellite interfaces remain English-only; human language/domain, receiver and channel decisions remain pending. No code, tests, byte-hash scripts, live checks, external distribution or automatic integration is introduced.

# Webhook Replay Guard

Standalone Batch 99 **offline simulator**, not a live webhook guard. **Live:** https://saipradikmallakuntla-tech.github.io/webhook-replay-guard/

Open `index.html` directly or serve with `python3 -m http.server 8000`. Load a synthetic duplicate, retention-expiry or clock-window case. Enter an array of `{id, signedAt, receivedAt}` events using numeric integer Unix seconds. Configure maximum age, future tolerance, retention TTL and receiver clock offset. Simulate and optionally export an ID/payload-omitting JSON report. Interface: English.

## Exact model
A run begins with an empty in-memory Map, keyed only by supplied event ID. Events are sorted by receivedAt, then original row. Age is `receivedAt + offset - signedAt`. Timestamp acceptance is inclusive: `-future <= age <= window`. Freshness is tested before cache membership. An ID is duplicate while `receivedAt < firstAcceptedArrival + TTL`; at exact expiry it can be accepted again. Rejected duplicates do not extend TTL, and rejected timestamps do not insert IDs. Zero TTL provides no retention. Maximum 500 events, 100,000 text code units, 128 characters per nonblank ID. Controls accept bounded integer seconds.

## Not provided
No endpoint, receiver, signature/HMAC verification, secret handling, authenticated IDs, durable store, atomic concurrency, tenant scoping, payload hashes, malicious-event detection or exactly-once guarantee. This sequential model cannot establish security. A real system needs verified signatures and safely scoped atomic durable deduplication plus monitoring and threat review. TTL shorter than the full timestamp span can permit reacceptance. This is distinct from the historical unlaunched Webhook Signature Fixture Lab proposal and from layered client retry simulation.

No uploads, network calls, telemetry, cookies, storage, external assets or dependencies. Reports omit IDs and payloads, but timestamps remain; review before sharing. Input is rendered as text only. Never paste live secrets or production payloads.

## Tests and deployment
`timeout 15s node --check app.js`

`timeout 15s node tests/test.cjs`

Twelve built-in synthetic cases, three interactive examples, plus fixture and invalid-input checks. GitHub Pages: `main:/`, `.nojekyll`, HTTPS enforced, no custom domain.

## Seven-node network
- [Hub](https://saipradikmallakuntla-tech.github.io/zion-ai-apps-hub/)
- [Stream Inspector](https://saipradikmallakuntla-tech.github.io/llm-stream-inspector/)
- [Retry Safety Lab](https://saipradikmallakuntla-tech.github.io/agent-retry-safety-lab/)
- [CORS Doctor](https://saipradikmallakuntla-tech.github.io/cors-cookie-doctor/)
- [Token Budget Lab](https://saipradikmallakuntla-tech.github.io/prompt-token-budget-lab/)
- [Schema Drift Auditor](https://saipradikmallakuntla-tech.github.io/tool-schema-drift-auditor/)

[Discovery EN](https://saipradikmallakuntla-tech.github.io/zion-ai-apps-hub/batch-99-discovery.html) · [ES](https://saipradikmallakuntla-tech.github.io/zion-ai-apps-hub/es/batch-99-discovery.html) · [PT](https://saipradikmallakuntla-tech.github.io/zion-ai-apps-hub/pt/batch-99-discovery.html). [Network contract](NETWORK.md). Plain navigation carries no input.

## Batch-99 documentation reconciliation — 2026-11-16 UTC

Batch: `zion-batch-99-portfolio-reconciliation-2026-11-16-en-es-pt`. This repository already existed; this cycle changes only README.md and NETWORK.md. The original body above is retained as dated documentary context, including commands that are not executed here. This is not a new app launch, software localization or deployment verification.

Catalog B99-C03 and routing B99-R01: [English](https://github.com/saipradikmallakuntla-tech/zion-ai-apps-hub/blob/main/BATCH_99_CATALOG_ROUTING_GUIDE.md#en) · [Español neutro](https://github.com/saipradikmallakuntla-tech/zion-ai-apps-hub/blob/main/BATCH_99_CATALOG_ROUTING_GUIDE.md#es) · [Português](https://github.com/saipradikmallakuntla-tech/zion-ai-apps-hub/blob/main/BATCH_99_CATALOG_ROUTING_GUIDE.md#pt). This is an offline sequential timestamp/event-ID retention model, not a receiver, signature verifier, durable concurrent store or exactly-once/security guarantee. The interface remains documented as English-only.

Current reciprocal documentation is in the [dated local network appendix](NETWORK.md), with all six peer README destinations. Use the single [central portfolio/status and evidence register](https://github.com/saipradikmallakuntla-tech/zion-ai-apps-hub/blob/main/PORTFOLIO_STATUS.md) and [locale-review register](https://github.com/saipradikmallakuntla-tech/zion-ai-apps-hub/blob/main/TRANSLATION_PARITY_REGISTER.md); no competing local status file is added. Seven nodes/six utilities/42 possible directed relationships describe documentation, not verified live integration. Human language/domain, receiver and channel decisions remain pending. No sensitive inputs in links, automatic handoff, code/test/hash/browser/live-probe work, Pages/DNS change, Notion/further Mem0 call or external distribution.


## Saved handoff and free discovery — 2026-11-16 UTC

Batch: `zion-saved-handoff-discovery-2026-11-16-en-es-pt`. The complete earlier body is retained; this dated appendix is the newer editorial view, not a software change.

[Saved Handoff Playbooks and Discovery Promos — English](https://github.com/saipradikmallakuntla-tech/zion-ai-apps-hub/blob/main/SAVED_HANDOFF_PLAYBOOKS_AND_DISCOVERY_PROMOS.md#en) · [Español neutro](https://github.com/saipradikmallakuntla-tech/zion-ai-apps-hub/blob/main/SAVED_HANDOFF_PLAYBOOKS_AND_DISCOVERY_PROMOS.md#es) · [Português](https://github.com/saipradikmallakuntla-tech/zion-ai-apps-hub/blob/main/SAVED_HANDOFF_PLAYBOOKS_AND_DISCOVERY_PROMOS.md#pt). SH01–SH06 cover free self-serve discovery, seven-node routing, a manually saved private Markdown packet, actual receiver acknowledgment, optional human team/commercial scoping and reusable promotion drafts. The guide links back to this [README](README.md) and [NETWORK](NETWORK.md); existing six-peer pointers remain intact.

Webhook remains an offline sequential freshness/event-ID retention model, without a live receiver, signature verification, durable atomic protection or exactly-once/security guarantee. Record only a synthetic or explicitly permitted minimum summary with source revision, uncertainty and next owner. Saved means manual documentation, not app persistence, synchronization, automatic email or replay permission. Team/commercial discussion requires verified people and separate scope/terms; no available service, price or SLA is promised.

The package's current written inventory is 51 Markdown files and 85 logical IDs/255 pending-review EN/ES/PT entries; older counts above remain dated history. These pointers repeat SH sources and add no translated IDs. All six utility interfaces remain English-only. Human language/domain, receiver and channel decisions remain pending; external distribution stays on hold. No private receipts or diagnostic inputs in public links. No code/HTML/test/runtime/Pages/DNS edits, test/hash/browser/live-probe scripts or further Mem0 calls.
