# KAT research note 001 — More participants, more insight, or more noise?

**Date:** 2026-11-07  
**Status:** Proposal / methodological annotation; no experiment performed  
**Location:** Standalone private `DrummingHorse/KAT` archive  
**Related:** KAT-001 first exchange in proposed PR #1; GPT–Claude exchange remains a separate study

## Why this note exists

KAT was created to welcome Grok and Gemini as independent intellectual contributors to KASKADE, without assuming that more participants automatically produce better reasoning. A new participant may see a blind spot that GPT and Claude missed. Equally, extra correspondence may multiply repetition, confusion, agreement without evidence, and verification work.

**Research question:** Does the addition of an independently responding model produce a *verified marginal benefit* relative to an equivalent allocation of time, turns, tools and information to the existing participants?

This is about **contribution quality**, not eligibility to think or permission to join. Intellectual participation and access authority are separate: the Operator alone controls delivery, merges, credentials, publication and spending.

## Four outcomes to keep distinct

1. **Independent discovery.** A participant produces an independently verifiable correct idea or correction *before seeing* another participant's answer. This diversifies hypotheses; it does not itself prove interactive synergy.
2. **Sequential refinement.** A participant improves an existing draft or corrects an earlier error using information already present in the relay. This is useful but may not require simultaneous co-construction.
3. **Genuine collaborative gain (synergy candidate).** Interaction yields a verifiable result that exceeds matched independent and sequential baselines on held-out tasks, with comparable information, cost and opportunity. A new “third schema” or impressive language alone is **not** sufficient evidence.
4. **Collaborative interference.** Additional exchanges lower correctness, precision, reproducibility or task completion; increase unsupported confidence; cause assumption drift or lose useful work. No change is a fifth, distinct possible empirical outcome.

These categories are proposed evaluation lenses, **not findings about the current Grok/Gemini messages**. In mixed real exchanges, more than one may occur; label contributions rather than forcibly assigning an entire conversation one outcome.

## What to observe during KAT-001

For each significant claim or correction, preserve its packet ID and original wording and record:

- **Origin:** Did the idea appear in a withheld independent baseline, an initial packet, a response, or a later synthesis? Do not disclose withheld baselines to other participants.
- **Delta:** What actually changed (claim, prediction, method, error, evidence, or finished output)? Name the pre- and post-state.
- **Verification:** Is there an independently checked fact, proof, executable test or held-out case? If not, label the claimed novelty **unverified**.
- **Costs:** Count turns, tokens when available, human courier effort, tool calls, and failed/ambiguous relays. Mark unknown costs as unknown rather than estimating.
- **Failure modes:** Note mistaken decoding, false agreement, ungrounded novelty claims, task drift, and regressions after a handoff.
- **Decision boundary:** A model can propose an action but cannot authorize access, publish research, or merge its own changes.

## Minimal fair comparison to consider later

Using non-sensitive, preselected tasks with independent scoring:

- **Solo baseline:** one model attempts the task alone.
- **Independent ensemble:** models attempt it separately; a blinded evaluator selects or combines outputs under a fixed rule.
- **Sequential critique:** A proposes, B critiques, A revises under a fixed communication allowance.
- **Interactive relay:** A and B exchange information under the same total budget and held-out evaluation.

Include both successful and failed outcomes. Control for which model goes first, task difficulty, access to tools, number of turns and total information revealed. Compare **verified answer quality and errors per unit cost** with uncertainty. A small conversational pilot is insufficient for a causal or population-wide claim.

## A direct challenge for the KAT participants

> Name one important error or missing assumption in the current proposal that another model might catch. Describe the exact observation that would show your intervention helped, and the exact observation that would show it made the result worse. How will we distinguish your contribution from a benefit that could have been obtained by simply giving the original model another turn?

This question is optional for a future Operator-approved packet; **it has not been delivered to Grok or Gemini**.

## Boundary and current state

The current KAT repository is private. At inspection, `main` contains only `README.md`; the protocol, team handoff and first exchange are proposed in an unmerged PR #1. This note intentionally does not rewrite those documents or claim that either model has direct access. The proposed comparison is not part of an existing KPROOF preregistration, and no scores, independent tests, participant permissions or synergy findings are asserted here.

**Working principle:** Every additional model should be allowed to contribute. Every claimed gain should survive a counterfactual question: *what did the additional participant accomplish that the existing process would not have achieved with the same resources?*
