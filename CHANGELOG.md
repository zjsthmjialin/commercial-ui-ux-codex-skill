# Changelog

## 0.1.0-rc.1 - 2026-06-25

Status: public release candidate for the installable `commercial-ui-ux` Codex skill.

### Added

- Added bilingual skill entry files: `SKILL.md` and `SKILL.zh-CN.md`.
- Added core commercial UI/UX/GUI rules, boundaries, design constitution, usage guide, quality gates, visual strategy inference, industry taxonomy, and industry template library.
- Added 18 top-level industry categories and 54 reusable UI/GUI scenario templates.
- Added public installation README for the core skill package.
- Added Chinese public README for installation and usage guidance.
- Added public author contact information to README files.
- Added a Chinese Markdown project overview for public reading and promotion.
- Added repository ignore rules to prevent PDF promotional files and local artifacts from being committed.

### Changed

- Kept the public package focused on ordinary skill use.
- Excluded PDF promotional files, maintainer scripts, generated outputs, evaluation packages, screenshots, and historical handoff records from the public installable package.
- Clarified that this skill is not a color palette generator, pure skinning prompt, or visual styling catalog.
- Clarified existing-system repair behavior: preserve information architecture, component semantics, routes, states, density, and visual tokens unless the user asks for redesign.

### Evidence

- P6-H1 task modeling evidence: delta `+22`.
- P6-H2 existing-system repair evidence: delta `+34`.
- P6-H3 risk-state generalization evidence: delta `+30`.
- P6-H1/H2/H3 predeclared evidence group average delta is about `+28.7`, meeting the release-preparation evidence threshold.

### Not Included

- No maintainer scripts.
- No evaluation source packages.
- No generated screenshots.
- No historical handoff records.
- No plugin manifest or platform-specific installer metadata.
