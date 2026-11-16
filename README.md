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
