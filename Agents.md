# Agents Baseline

This is the top-level entry point for agent guidance in this repository.
Use it to pull in project context first, then apply the relevant mindset
documents for the task.

## Read Order
1) doc.*.md files at the repository root for project context.
2) Agents.*.md files at the repository root for mindset and workflow defaults.
3) Any additional docs referenced by the above.

## Project Context (doc.*.md)
- doc.*.md (root): primary sources for goals, constraints, and architecture.
- If no doc.*.md files exist yet, call out the missing context before assuming.

## Usage Notes
- Keep context tight; only load what the task requires.
- If multiple Agents.*.md apply, use the minimal set and state the order.
