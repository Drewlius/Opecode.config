---
name: automations
description: Useful tips when creating OpenCode automations, including triggers, expiry, missed runs, and conditional prompts.
---

# RULES

- if i learn useful information about automations come back and append that information to this skill file following the format that this file already adheres to
- keep only reusable rules here, never task-specific details. General automation tips and tricks only.

## TIPS

- For a daily check over N days, set `expires` just before slot N+1 so exactly N checks run.
- Use a prompt action when the automation should act only on failure; tell it to stay silent when healthy.
- If the PC or OpenCode service is off at the due time, the check runs once when it returns; missed slots are skipped, not replayed in a burst.
- If it returns after `expires`, the missed check is marked expired and does not run.
