```markdown
# sig-release Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill provides guidance on contributing to the `sig-release` repository, which is primarily written in TypeScript and manages Kubernetes release notes and related artifacts. The repository emphasizes clear file organization, consistent code style, and structured workflows for drafting and refining release notes for each Kubernetes release cycle.

## Coding Conventions

- **File Naming:**  
  Use kebab-case for file names.  
  _Example:_  
  ```
  release-notes-draft.md
  pr-12345-map.yaml
  ```

- **Import Style:**  
  Use relative imports for TypeScript modules.  
  _Example:_  
  ```typescript
  import { updateDraft } from './release-notes-utils';
  ```

- **Export Style:**  
  Prefer named exports.  
  _Example:_  
  ```typescript
  export function generateReleaseNotes() { ... }
  export const RELEASE_NOTES_PATH = './release-notes/';
  ```

- **Commit Messages:**  
  Freeform style, typically concise (~48 characters on average).  
  _Example:_  
  ```
  update draft notes for beta release
  fix typo in pr-12345-map.yaml
  ```

## Workflows

### Update Release Notes Draft
**Trigger:** When preparing or refining the release notes draft for a new or ongoing Kubernetes release (e.g., alpha, beta, or final).  
**Command:** `/update-release-notes-draft`

1. Add or update multiple YAML files under `releases/release-<version>/release-notes/maps/` for each PR included in the release.
   - _Example:_  
     ```
     releases/release-1.30/release-notes/maps/pr-12345-map.yaml
     ```
2. Regenerate or update the following files to reflect the latest changes:
   - `releases/release-<version>/release-notes/release-notes-draft.json`
   - `releases/release-<version>/release-notes/release-notes-draft.md`
3. Optionally update session files under `releases/release-<version>/release-notes/sessions/` (e.g., when running automation tools).
   - _Example:_  
     ```
     releases/release-1.30/release-notes/sessions/maps-2024-06-01.json
     ```

### Refine Individual Release Note Entries
**Trigger:** When a reviewer or contributor wants to refine or correct details for specific PRs in the release notes draft.  
**Command:** `/refine-release-notes-entry`

1. Edit one or a few YAML files under `releases/release-<version>/release-notes/maps/` for targeted PRs.
   - _Example:_  
     ```
     releases/release-1.30/release-notes/maps/pr-67890-map.yaml
     ```
2. Regenerate the following files to sync changes:
   - `releases/release-<version>/release-notes/release-notes-draft.json`
   - `releases/release-<version>/release-notes/release-notes-draft.md`

## Testing Patterns

- **Test File Naming:**  
  Test files follow the `*.test.*` pattern.
  - _Example:_  
    ```
    release-notes-utils.test.ts
    ```
- **Testing Framework:**  
  Not explicitly detected; check the repository for test runner configuration or scripts.

- **Test Example:**  
  _Example:_  
  ```typescript
  // release-notes-utils.test.ts
  import { generateReleaseNotes } from './release-notes-utils';

  describe('generateReleaseNotes', () => {
    it('should create a draft with correct PR entries', () => {
      // ...test logic...
    });
  });
  ```

## Commands

| Command                        | Purpose                                                      |
|--------------------------------|--------------------------------------------------------------|
| /update-release-notes-draft    | Draft, refine, and update the release notes for a release.   |
| /refine-release-notes-entry    | Refine or correct specific PR entries in the release notes.  |
```