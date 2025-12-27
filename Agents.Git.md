# Git Plan Workflow

Guidance for using git effectively while executing a development plan. The
goal is to keep work traceable, reviewable, and aligned with plan steps.

## Principles
- Keep commits small and scoped to a single plan step or outcome.
- Favor clarity over cleverness in history; make intent obvious.
- Preserve reviewability: avoid large, mixed-purpose diffs.
- Maintain a buildable mainline; avoid committing known-broken states.

## Plan-Driven Workflow
- Translate each plan step into one or more focused commits.
- Use commit messages that reference the plan step or objective.
- If the plan changes, note the adjustment in the next commit message.
- Close out a step with a clean state: no unrelated local edits.

## Daily Practice
- Check status and diff before every commit.
- Stage deliberately (use partial staging for mixed edits).
- Run the smallest relevant tests before committing.
- Write short, descriptive commit messages with the "why".

## Commit Message Format (128 chars max)
- Example: `plan: add sim seed logging to enable reproducible runs`

## Branching and Sync
- Use short-lived branches for multi-step work.
- Rebase or merge frequently to reduce drift and conflicts.
- Avoid rewriting shared history; coordinate before force pushes.

## Hygiene and Recovery
- Keep WIP local or in clearly labeled commits.
- Use tags or notes sparingly for milestones when helpful.
- If you must revert, revert with intent and explain in the message.
