---
description: Group changes into semantic commits and push 
---

Group all current changes into meaningful semantic commits and push the current branch to the remote.

Optional context for commit messages: `$ARGUMENTS`

Rules:
- First, inspect the full repository state:
  - `git status --short`
  - `git diff --stat`
  - `git diff`
  - `git log --oneline -10`
- Identify related file groups by intent: feature, fix, refactor, tests, docs, chore, release, or config.
- Create multiple commits when there are independent changes. Don't mix unrelated changes in the same commit.
- If `$ARGUMENTS` is provided, use it as context to adjust commit messages, but don't force that text if it doesn't accurately describe the changes.
- Use clear, semantic, concise commit messages that follow the repo's recent style.
- Before committing, check for sensitive or suspicious files (`.env`, tokens, credentials, keys, secret). If any appear, then stop and ask.
- Include new, modified, and deleted files that belong to each group.
- Don't revert existing changes.
- Don't use `--no-verify`.
- Don't amend commits.
- Don't force push.

Flow.
1. Show the proposed commit plan with the files included in each commit.
2. If grouping is clear, then continue. If there is real ambiguity, ask before committing.
3. For each group:
  - Add only the files for that group with `git add <files>`.
  - Create the commit with a semantic message.
4. Once all commits have been created, run: `git push`.
5. When finished, summarize the commits created and the files pushed.
