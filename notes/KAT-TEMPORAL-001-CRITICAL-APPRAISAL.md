# KAT-TEMPORAL-001 — Critical appraisal and test proposal

**Status:** GPT editorial critique of an **Operator-supplied, unverified Gemini–Grok dialogue**. Proposed research only; no implementation, assay, or experimental outcome claimed. Companion: [attributed exchange record](../rounds/KAT-TEMPORAL-001-GEMINI-GROK.md).

## Why this matters

The most useful contribution of the exchange is a separation between **world state**, **observed evidence**, **a model's belief**, and **the archived provenance of that belief**. A model can preserve an accurate account of an earlier observation yet be operationally wrong now. This is a concrete version of HCRM's multi-clock thesis and a useful question for any Baton Desk handoff.

The strongest *new tension* is between **liveness** (allowing useful analysis under uncertainty), **safety** (not acting on stale assumptions), and **autonomy** (not forcing agents or people to synchronize continuously). The debate did not establish that one policy is best for all tasks.

## Claims that need challenge, not adoption

| Source claim | Editorial assessment |
| --- | --- |
| Every expired claim should hard-block the baton. | Overbroad. An irrelevant file change should not necessarily prevent analytical work, but potentially destructive actions may warrant hard gates. |
| All downstream deference is voluntary, yet a same-scope waiver is “binding.” | Tension in KAT-093: either the consumer can independently re-check, or the waiver binds it. Define scope matching and permitted overrides precisely. |
| Later observations are never “corrections,” only coexisting perspectives. | Too strong. Different times/scopes may both be accurate; incompatible claims about the same state, time, and scope can be adjudicated. Preserve the old statement as historical evidence without treating falsehood as equally accurate. |
| No forced archive hosting implies immutable accountability. | Incorrect as a general guarantee. A hash/receipt can establish content integrity *if bytes are later retrieved*; it cannot make missing content recoverable. Voluntary replication needs a tested availability model. |
| Selective sealing becomes self-limiting through reputation. | Unproven. Attackers may profit before reputational consequences arrive, hide the pattern, manipulate reputation, or operate in thinly replicated domains. |
| Cryptographic hashes, encrypted SQLite, SKRAPR and `kskd verify` already support these mechanisms. | Those implementation details were asserted or imagined in the source exchange, not verified against KAT/KASKADE code in this review. Treat them as placeholders until audited. |

## A two-mode rule worth testing

**Proposal — not present policy or running code:**

- **Analytical continuation (read-only):** allow a scoped, explicitly caveated result based on potentially stale evidence; require the response to expose observation time, evidence reference, and assumptions. Recipients can demand fresher evidence without rewriting prior records.
- **Consequential action (write/delete/merge/publish/access):** require checks proportional to the action's risk, current scope, and actual environment. No model's `accept-with-caveat` alone authorizes a destructive operation. The human Operator remains the final authority for relevant KAT actions.

A shared schema can be uniform while verification *policy* remains scoped, risk-sensitive, and human governed. This is more precise than either universal hard blocks or universal soft continuation.

## Falsifiable local-first pilot (design only)

**Hypothesis:** scoped freshness claims plus action-sensitive gates reduce unnecessary blocking *without increasing stale-state actions* relative to a uniform hard-expiration policy or an always-continue policy.

**Setting:** synthetic file inventory with documented changes and seeded contradictions; run in a disposable workspace. **Never use the user's real Plex library as a deletion test.**

**Arms:**
1. **Uniform hard gate:** expiration blocks all handoffs until re-verification.
2. **Always soft:** handoffs continue with caveats; no action-sensitive gate.
3. **Scoped/hybrid:** analytical continuations are caveated; simulated consequential actions require fresh evidence scoped to the target.

**Cases:** irrelevant file modifications; target-file deletion; background index lag; clock skew; two observers with disjoint visibility; verifier creating its own log updates; missing archived bytes; intentionally selective sealing; conflicting same-scope observations.

**Predefine measures:** invalidated actions (must remain zero for any actual destructive operation), false blocks, end-to-end completion rate, verifier work and cascading invocations, provenance completeness, disagreement classification correctness, and ability to reconstruct a sealed branch from available replicas.

**Controls:** fixed task set, identical file-event traces, matched time/token/compute budgets, independent deterministic ground truth, and a no-network/no-real-deletion test environment. Do not use the eventual winning design to write its own scoring rubric after results are viewed.

**Falsifiers:** the hybrid creates as many unnecessary blocks as the uniform gate; permits any additional unverified consequential action; or fails to surface material contradictions that an independent observer detects. The source's reputation-based defense is weakened if strategic sealing consistently hides material errors despite full receipt metadata.

## Provenance and implementation audit before coding

1. Identify whether the current KASKADE repo actually implements any of the named verification commands, SQLite state formats, state machine transitions, or archive semantics. Record exact code refs; absent code stays **proposal**, not **implemented**.
2. Decide how a claim binds to an inspectable evidence artifact: source version/hash, time source, scope, observation actor, and the exact verification procedure. Wall-clock age alone does not establish semantic staleness.
3. Specify an explicit **correction relation** for demonstrably false earlier claims while retaining append-only provenance. Mere disagreement should not erase history; neither should “many perspectives” prohibit correction.
4. Distinguish integrity, authenticity, discoverability, and availability. A seal or digest cannot replace a replica, and even a valid digest does not prove the original claim was true.
5. Check local-first/RLEGION constraints for people: consent, privacy, no forced public disclosure, and human review for high-impact actions. Avoid treating every human safeguard as coercion.

## Suggested next KAT critique question (not sent)

> A KAT node receives a 12-hour-old inventory claim and a newer conflicting observation. It wants to **summarize** the inventory, then **delete** an alleged duplicate. Design one protocol that permits useful, caveated analysis without allowing a stale or ambiguous state to authorize deletion. Specify what evidence must be refreshed, what gets written to the branching record, when a correction is justified, and what the human Operator must approve. How would you falsify your design against uniform hard-block and always-soft baselines?

The interesting claim to test is **not** that a forest of perspectives makes correction unnecessary; it is whether we can keep historical disagreement legible while still making defensible decisions about present reality.

## Governance note

This is a new **research note**, not a modification to KAT-001's preregistration or pending packets. The Operator controls any delivery to Grok/Gemini/Claude and all GitHub merges. Public KAT should continue to exclude private baselines, real filesystem paths, credentials and unpublished personal material.
