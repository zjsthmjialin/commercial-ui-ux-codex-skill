# Changelog

## 0.1.0-rc.1 - 2026-06-25

Status: public release candidate core package published to GitHub and released as a GitHub prerelease. This is not a final non-RC release.

### Added

- Added bilingual skill entry files: `SKILL.md` and `SKILL.zh-CN.md`.
- Added core commercial UI/UX/GUI rules, boundaries, design constitution, usage guide, quality gates, visual strategy inference, industry taxonomy, and industry template library.
- Added 18 top-level industry categories and 54 reusable UI/GUI scenario templates.
- Added two no-CDN showcase pages with screenshot and accessibility validation.
- Added independent evaluation protocol, 10 independent evaluation rounds, 20 scored runs, and report/export validation.
- Added P6 public general release roadmap and release preparation record.
- Added release package checklist for source-style RC packaging and GitHub authorization boundaries.
- Added local release record and generated local installable core package.
- Published the installable core package to `https://github.com/zjsthmjialin/commercial-ui-ux-codex-skill`.
- Added Chinese public README (`README.zh-CN.md`) to the installable core package and public GitHub repository.
- Added public author contact information to the public README files.

### Changed

- Compressed ordinary UI work read path so maintenance, governance, evals, validation, and output folders are not loaded by default.
- Clarified that this skill is not a color palette generator, pure skinning prompt, or visual styling catalog.
- Clarified existing-system repair behavior: preserve information architecture, component semantics, routes, states, density, and visual tokens unless the user asks for redesign.
- Strengthened default treatment for assumptions, unresolved gaps, workflow states, protected actions, rollback, recovery, and mobile continuity.

### Evidence

- Historical independent rounds 1-4 remained inconclusive: deltas `+1`, `0`, `+2`, and `+1`.
- P5-RC targeted evidence remained insufficient overall: RC-01 `+11`, RC-02 `+10`, RC-03 `+30`, average about `+17`.
- P6-H1 task modeling evidence: baseline `76/100`, with-skill `98/100`, delta `+22`.
- P6-H2 existing-system repair evidence: baseline `64/100`, with-skill `98/100`, delta `+34`.
- P6-H3 risk-state generalization evidence: baseline `68/100`, with-skill `98/100`, delta `+30`.
- P6-H1/H2/H3 predeclared evidence group average delta is about `+28.7`, meeting the release-preparation evidence threshold.

### Validation

- Last full gate: `scripts/validate-all.ps1`, passed on 2026-06-25 after the Chinese README/contact package rebuild and release-record updates.
- Current validated corpus: 10 eval cases, 10 independent evaluation rounds, 20 scored runs, 20 HTML pages.
- Known warnings are retained historical or reference-only evidence warnings, not new with-skill defects.

### Packaging Boundary

- Candidate installable core should include `SKILL.md`, `SKILL.zh-CN.md`, README, `README.zh-CN.md`, CHANGELOG, VERSION, and ordinary UI work references under `docs/`.
- Local package generated at `output/release/commercial-ui-ux-0.1.0-rc.1.zip`.
- SHA256 checksum recorded at `output/release/commercial-ui-ux-0.1.0-rc.1.sha256`.
- Maintenance and evidence materials may be included in a separate evidence package or repository context, but are not part of the ordinary skill read path.
- `output/`, historical handoff documents, raw validation artifacts, and reference baseline warnings should not be used as ordinary runtime instructions.

### Not Included

- Public GitHub repository was created after explicit user approval.
- Core package was pushed to GitHub after explicit user approval.
- GitHub prerelease `0.1.0-rc.1` was created after explicit user approval: `https://github.com/zjsthmjialin/commercial-ui-ux-codex-skill/releases/tag/0.1.0-rc.1`.
- No final non-RC public release tag was created.
- No complete source workspace, maintainer scripts, raw evaluation packages, generated screenshots, manifest, or plugin metadata was published in this step.
