---
name: update-release-notes-draft
description: Workflow command scaffold for update-release-notes-draft in sig-release.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /update-release-notes-draft

Use this workflow when working on **update-release-notes-draft** in `sig-release`.

## Goal

Draft, refine, and update the release notes for a specific Kubernetes release version. This includes adding or updating multiple PR map YAML files, regenerating the draft JSON and Markdown, and sometimes updating session files.

## Common Files

- `releases/release-*/release-notes/maps/pr-*-map.yaml`
- `releases/release-*/release-notes/release-notes-draft.json`
- `releases/release-*/release-notes/release-notes-draft.md`
- `releases/release-*/release-notes/sessions/maps-*.json`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Add or update multiple YAML files under releases/release-<version>/release-notes/maps/ for each PR included in the release.
- Regenerate or update releases/release-<version>/release-notes/release-notes-draft.json and release-notes-draft.md to reflect the latest changes.
- Optionally update session files under releases/release-<version>/release-notes/sessions/ (e.g., when running automation tools).

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.