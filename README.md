# Commercial UI/UX Codex Skill

Chinese documentation: [README.zh-CN.md](README.zh-CN.md)

`commercial-ui-ux` is a Codex skill for designing, reviewing, repairing, and implementing commercial UI/UX/GUI surfaces.

It helps Codex prioritize business tasks, user journeys, workflow states, interaction risk, existing design systems, accessibility, and verification before visual polish. It is not a color-palette generator, a skinning prompt, or a component-library template.

Project overview in Chinese: [docs/08-project-overview.zh-CN.md](docs/08-project-overview.zh-CN.md)

## Contact

- Author: `zjsthm`
- Email: `zjsthm@gmail.com`
- WeChat: `63656299`

## Install

Clone this repository into your Codex skills directory as `commercial-ui-ux`.

Windows PowerShell:

```powershell
git clone https://github.com/zjsthmjialin/commercial-ui-ux-codex-skill "$env:USERPROFILE\.codex\skills\commercial-ui-ux"
```

macOS/Linux:

```bash
git clone https://github.com/zjsthmjialin/commercial-ui-ux-codex-skill ~/.codex/skills/commercial-ui-ux
```

After installation, ask Codex to use `commercial-ui-ux` for commercial UI/UX/GUI design, review, repair, or implementation work.

## When To Use

Use this skill for:

- SaaS dashboards, admin panels, workflow tools, mobile app screens, forms, tables, and data-heavy product surfaces.
- UI/UX review where findings should focus on task success, state coverage, hierarchy, accessibility, and risk.
- Existing product screen repair where the design system, routes, component semantics, density, and visual tokens should be preserved.
- No-brand visual strategy when the user has not provided a brand guide, reference image, or design system.
- Industry-specific UI/GUI planning where vertical context affects states, risks, controls, and information density.

Do not use it as the primary tool for pure logo design, standalone illustration, poster art, decorative styling, legal/medical/financial/compliance judgment, or deceptive interface work.

## Included Files

Core skill files:

- `SKILL.md`
- `SKILL.zh-CN.md`
- `README.zh-CN.md`

User-facing documentation:

- `docs/05-usage-guide.md`
- `docs/01-commercial-ui-ux-rules.md`
- `docs/02-skill-boundaries.md`
- `docs/03-design-constitution.md`
- `docs/06-quality-gates.md`
- `docs/07-visual-strategy-inference.md`
- `docs/08-project-overview.zh-CN.md`
- `docs/09-industry-taxonomy.md`
- `docs/10-industry-template-library.md`

Release metadata:

- `VERSION`
- `CHANGELOG.md`

This public package intentionally excludes PDF promotional files, maintainer scripts, evaluation rounds, generated screenshots, local release artifacts, and historical handoff records.

## Typical Prompt

```markdown
Use commercial-ui-ux to design a B2B SaaS customer health dashboard.

Task type: new product screen
Target users: customer success managers and sales leads
Platform: responsive web, desktop first
Core task: find risky accounts, understand why they are risky, and assign follow-up work
Existing design system: light theme, 8px radius, compact table density
Visual source: infer from product context
Must include: account list, health score, filters, empty/loading/error states, protected bulk action
Avoid: marketing hero layout, decorative gradients, unrelated redesign
```

## How Codex Should Work

1. Start from `SKILL.md`.
2. Read only the references needed for the current task.
3. Keep UX before UI, and UI before GUI details.
4. Preserve existing product systems unless the user asks for redesign.
5. Cover loading, empty, error, disabled, permission, success, and destructive-action states when applicable.
6. Verify with the project’s available checks, and state any unverified gaps.

## Evidence

The release candidate is supported by three public-release preparation evaluation rounds:

| Hypothesis | Result |
| --- | ---: |
| P6-H1 task modeling | `+22` |
| P6-H2 existing-system repair | `+34` |
| P6-H3 risk-state generalization | `+30` |

Average delta: about `+28.7`, above the `+25` release-preparation threshold used for this package.

## Version

Current version: `0.1.0-rc.1`

This is a release candidate. It improves Codex behavior for commercial UI/UX/GUI work, but it does not replace human product, design, accessibility, security, domain, or compliance review.
