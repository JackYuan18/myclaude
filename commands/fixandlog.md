Review the current conversation to find every bug that was identified, mentioned, or discovered — including bugs reported by the user, found during code review, caught by tests, or surfaced by error output.

For each bug:

**Step 1 — Fix**
Implement a code fix using Edit or Write tools. If a fix is unclear or risky, explain the ambiguity and skip it rather than guessing.

**Step 2 — Log**
After all fixes are applied, append an entry to `BUGFIXES.md` in the current working directory (create the file if it doesn't exist). Use this format exactly:

```
## $CURRENT_DATE — {one-line summary of the fix session}

| # | Bug | File | Fix | Status |
|---|-----|------|-----|--------|
| 1 | {what was wrong} | `path/to/file:line` | {what changed} | Fixed |
| 2 | ... | ... | ... | Skipped: {reason} |

**Root causes:** {brief shared theme if any, or "N/A"}
```

Rules:
- If no bugs were identified in the session, write that explicitly and do not create a log entry.
- Do not fix bugs that weren't discussed in this session.
- If `$ARGUMENTS` is provided, treat it as a filter — only fix and log bugs matching that description or file.
- Mark a bug "Skipped" (with reason) rather than silently omitting it if you can't safely fix it.
- Keep existing `BUGFIXES.md` content intact — only append, never overwrite.
