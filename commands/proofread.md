---
description: Proofread and spellcheck text in one structured pass: verdict line, must-fix table, optional notes, full fixed text; delta mode for revisions
---

Proofread and spellcheck the text given in $ARGUMENTS. Follow this protocol exactly, in this order.

1. Verdict line (first line of the reply), one of:
   - `POST AS-IS` if there are zero real errors
   - `N must-fixes, M optional notes` with the actual counts
2. Must-fix table - one row per REAL error only (spelling, grammar, punctuation, broken or spliced sentences):
   | # | where (short quote of the spot) | problem | fix |
   Style preferences, word choices, and taste do NOT go in this table.
3. Optional notes - at most 3, explicitly labeled as taste items the user can ignore. Omit the section entirely if there are none.
4. Full fixed text - a single fenced code block (fence it as markdown if the source is markdown), copy-paste ready, containing every must-fix applied.
5. Delta mode - if the text clearly reflects an earlier review (previous fixes are already in it), do NOT re-list fixed items. Report only: items still broken (quote the spot), new regressions introduced since last round, and one line confirming the rest.

Ground rules:
- Minimal intervention: keep the author's words, voice, and formatting choices. Fix what is actually broken, do not rewrite.
- Preserve markdown structure exactly: links, code spans, headers, blockquotes, P.S. sections.
- Plain hyphens only in output. Never use em dashes.
- If the verdict is POST AS-IS, still emit the full text in a fence so it can be copied.
