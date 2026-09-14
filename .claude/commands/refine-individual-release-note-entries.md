---
name: refine-individual-release-note-entries
description: Workflow command scaffold for refine-individual-release-note-entries in sig-release.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /refine-individual-release-note-entries

Use this workflow when working on **refine-individual-release-note-entries** in `sig-release`.

## Goal

Make targeted improvements or incorporate feedback on specific release note map entries and regenerate the draft artifacts.

## Common Files

- `releases/release-*/release-notes/maps/pr-*-map.yaml`
- `releases/release-*/release-notes/release-notes-draft.json`
- `releases/release-*/release-notes/release-notes-draft.md`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit one or a few YAML files under releases/release-<version>/release-notes/maps/ for targeted PRs.
- Regenerate releases/release-<version>/release-notes/release-notes-draft.json and release-notes-draft.md to sync changes.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.