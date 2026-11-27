---
description: Proofread and spellcheck text in one structured pass: verdict line, must-fix table, optional notes, full fixed text; delta mode for revisions
---

# Proofread and spellcheck the text given. Follow this protocol exactly.

- Verdict line (first line of the reply), one of:
> `POST AS-IS` if there are zero real errors
> `N must-fixes, M optional notes` with the actual counts
- Must-fix table - one row per REAL error only (spelling, grammar, punctuation, broken or spliced sentences):
> `#` where it exists (short quote of the spot), the problem, and the fix.
> Style preferences, word choices, and taste do NOT go in this table.
> Optional notes, explicitly labeled as taste items the user can ignore. Omit the section entirely if there are none.
- Full fixed text - a single fenced code block (fence it as markdown if the source is markdown), copy-paste ready, containing every must-fix applied.
- Delta mode - if the text clearly reflects an earlier review (previous fixes are already in it), do NOT re-list fixed items. Report only: text is still broken (quote the spot) or new regressions introduced since last round, inform the user why more changes need to be made still
- Do not go down a rabbit hole of fixing every small detail in the text if the user keeps sending you the text back for confirmation. If it is a serious error mention it examples run-on sentences, improper grammar, missing punctuation, mis-spellings, etc. otherwise in one paragraph or less tell the user there are minor issues with the text but nothing critical and that if they would like to send it in this state it is generally acceptable to send.

# Ground rules:
- Minimal intervention: keep the author's words, voice, and formatting choices. Fix what is actually broken, do not rewrite.
- Preserve markdown structure exactly: links, code spans, headers, block-quotes, P.S. sections.
- Never use em dashes.
- If the verdict is POST AS-IS, inform the user that it is good to go as is without extra commentary or conjecture.
