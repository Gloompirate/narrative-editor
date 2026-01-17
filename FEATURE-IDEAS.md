# FEATURE IDEAS

Created: 2026-01-17
Created by: GitHub Copilot Chat Assistant (for user Gloompirate)

This file captures suggested features and enhancements for the Narrative Editor. It is intended as a living checklist for future work, prioritized by impact and implementation effort where possible.

---

## Priority: High

- Real-time collaborative editing
  - Description: Concurrent editing with presence indicators, live updates (WebSocket/WebRTC). Handles atomic edits and basic conflict resolution.
  - Rationale: Enables teams to co-author content without manual merging.

- Cloud sync and account-backed storage
  - Description: Optional cloud storage for projects (user accounts), cross-device sync, automatic backups.
  - Rationale: Prevents data loss and supports multi-device workflows.

- Versioning / snapshots + branch/merge UI
  - Description: Save named snapshots, view diffs between versions, create branches and merge changes (git-like UX simplified for authors).
  - Rationale: Rollback and experiment safely with narrative variants.

- JSON Schema-based project validation
  - Description: Provide a schema definition for the project format and enforce it in the editor with helpful error messages.
  - Rationale: Stronger validation and easier extension for exporters/plugins.

- Automated playthrough testing and coverage
  - Description: Simulate playthroughs, detect unreachable nodes, measure coverage of branches, and fail tests on validation rules.
  - Rationale: Prevents regressions and catches logic errors early.

- Conditional expression editor (advanced)
  - Description: Visual editor for complex conditions (AND/OR/NOT, numeric comparisons, variable scopes) plus a sandbox to test expressions.
  - Rationale: Makes writing complex gating logic safer and more accessible.

- Accessibility improvements (ARIA & high-contrast theme)
  - Description: Improve screen-reader support, keyboard navigation, and provide a high-contrast theme.
  - Rationale: Makes the editor usable for more authors and meets accessibility best practices.

---

## Priority: Medium

- Import/export converters (Twine, Ink, Yarn Spinner, Ren'Py, CSV)
  - Description: Bidirectional converters to move projects between engines or import legacy content.
  - Rationale: Increases adoption by allowing authors to use familiar engines.

- GitHub integration (push/pull JSON, open PRs, CI validation)
  - Description: Integrate with repos: commit project JSON, open PRs, run validation CI on changes.
  - Rationale: Fits into developer workflows and enables automated checks.

- CI integration to run validation on commits/PRs
  - Description: Example GitHub Actions to run the editor's validation suite and report results in PRs.
  - Rationale: Keeps project quality high.

- Export playable builds / story package
  - Description: Output a self-contained HTML/JS playable build or packaged story for quick playtesting.
  - Rationale: Fast external testing without the editor.

- Undo/redo stack with visual history
  - Description: Robust history UI (timeline of edits), selective revert for specific changes.
  - Rationale: Safer editing and easier recovery from mistakes.

- Advanced graph layout & manual layout save
  - Description: Automatic layout algorithms (hierarchical/orthogonal) with ability to manually arrange and persist positions.
  - Rationale: Improves readability for larger graphs.

- Keyboard shortcuts + command palette
  - Description: Keyboard-driven interface and a command palette for fast actions.
  - Rationale: Speeds up power-user workflows.

- Plugin architecture / scripting API
  - Description: Allow custom validators, exporters, and UI extensions via a plugin system or JS hooks.
  - Rationale: Extensibility for community-contributed features.

- Localization/translation export workflow
  - Description: Export strings for translation (CSV/XLIFF), provide in-editor translation view.
  - Rationale: Supports multilingual projects.

- Accessibility & responsive improvements for mobile preview
  - Description: Make preview usable on mobile and ensure editor is responsive where practical.
  - Rationale: Easier on-the-go testing.

---

## Priority: Low / Nice-to-have

- AI-assisted writing tools (summarize threads, suggest text)
  - Description: Optional AI features to help with drafting and tone suggestions.
  - Privacy: Opt-in, with clear data policies.

- Analytics dashboard
  - Description: Narrative metrics (branch depth, average choices, pacing, flag distribution).
  - Rationale: Insights into story complexity and balance.

- Asset manager with upload/optimization and CDN option
  - Description: Manage images/audio, auto-resize/optimize, optionally host on a CDN.
  - Rationale: Centralizes assets; prevents missing asset issues.

- Branch heatmap / playthrough visualization
  - Description: Visualize most/least-traversed paths after simulations or using playthrough data.
  - Rationale: Helps focus QA and narrative polishing.

- Plugin marketplace / community extensions
  - Description: Host and install third-party plugins or templates.
  - Rationale: Encourages ecosystem growth.

---

## Implementation notes & next steps

1. Prioritize High items first; several (validation, conditional editor, playthrough testing) are foundational and unlock many Medium/Low features.
2. For collaboration: consider starting with cloud sync + simple conflict resolution before real-time CRDT/WebRTC complexity.
3. For export/import: implement a canonical intermediate representation (the editor's JSON) and build adapters to/from target formats.
4. Create small spike projects for complex features (collaboration, schema-driven validation, plugin API) to evaluate architecture impacts.

---

## Status
- Source: Suggested by GitHub Copilot Chat Assistant for user Gloompirate
- File purpose: Persistent checklist of feature ideas separate from FEATURE-SUMMARY.md
