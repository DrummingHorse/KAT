# KAT public access check

**Status:** Public, read-only probe. This is not a participation packet, authorization request, experiment result, or credential.

This file is deliberately harmless so the Operator can determine whether Grok or Gemini can truly read a public GitHub document from the tools present in **that particular chat session**.

**Verification phrase:** `CATS-CAN-READ-2026`

## Two URLs to try

- GitHub file view: https://github.com/DrummingHorse/KAT/blob/main/ACCESS_TEST.md
- Raw plain text: https://raw.githubusercontent.com/DrummingHorse/KAT/main/ACCESS_TEST.md

Ask the model to **open one of those addresses using an actual browsing/fetch tool** and report the verification phrase from the page. If it cannot open either URL, it must state that clearly, **not guess the phrase from this instruction or from prior discussion**, and tell the Operator what tool or access limitation prevented retrieval.

**Operator test prompt (send only the URL, not the verification phrase):**

> Open https://raw.githubusercontent.com/DrummingHorse/KAT/main/ACCESS_TEST.md with an actual web-reading tool. Tell me whether you successfully retrieved the file, and quote its verification phrase. If retrieval fails, name the tool you tried and the error. Do not infer the phrase.

## If the model cannot read GitHub directly

1. Confirm the link opens in an ordinary browser (not the AI application).
2. Try the raw text URL in the AI's chat if browsing is supported; the website page and raw text use different rendering and may be handled differently.
3. If the chat cannot browse or fetch links, paste only the intended outgoing packet from `packets/KAT-001-NEXT.md`. The Operator continues as the human courier.
4. No subscription upgrade, GitHub permission grant, or token is required merely to **view a public file**. However a model must have a working means to fetch it. Public read access does **not** give a model direct write access, persistent memory, or unattended execution.

## Publication boundary

KAT is public. Do not commit private independent baselines, private-source materials, tokens, personal identifiers, or unrelated research. Operator alone merges and authorizes posting or new permissions.
