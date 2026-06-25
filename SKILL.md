---
name: commercial-ui-ux
description: Use when designing, reviewing, repairing, or implementing commercial UI/UX/GUI for product screens, dashboards, admin panels, SaaS tools, mobile apps, forms, tables, workflow states, design systems, or no-brand visual strategy.
---

# Commercial UI/UX

## Core Principle

Commercial interface work starts with user task clarity, then interaction safety, then visual expression. A polished screen that does not help the user complete the right task is not good design. Visual style supports the business flow; it is not the main deliverable unless the user explicitly asks for visual exploration.

## Read Order

Load only the references needed for the current task:

| Situation | Required Reference |
| --- | --- |
| Designing or implementing UI | `docs/01-commercial-ui-ux-rules.md` |
| Deciding whether the skill should act, refuse, or ask for scope | `docs/02-skill-boundaries.md` |
| Resolving trade-offs between aesthetics, usability, business goals, and accessibility | `docs/03-design-constitution.md` |
| Helping a user invoke the skill effectively | `docs/05-usage-guide.md` |
| Before claiming the UI work is complete | `docs/06-quality-gates.md` |
| User provides no brand guide, reference image, or explicit style | `docs/07-visual-strategy-inference.md` |
| User provides an industry, vertical, or broad product domain | `docs/09-industry-taxonomy.md` |
| Selecting a reusable industry UI/GUI template or scenario pattern | `docs/10-industry-template-library.md` |

## Required Workflow

1. Identify the task mode and input contract: domain, audience, platform, core journey, brand identity, stack, existing design system, and constraints; record assumptions and unresolved gaps when the brief is incomplete.
2. Determine the visual source mode: user-specified assets, reference image, existing design system, or project-inferred strategy when no style source is provided.
3. Inspect existing project context before changing files. Preserve framework, component library, routing, state, naming, and visual conventions unless the user asks for a redesign.
4. Work in UX -> UI -> GUI order: task flow and states first, hierarchy and responsive layout second, interaction affordances and control states third.
5. Implement only within the requested surface area. Avoid unrelated refactors, new frameworks, and decorative complexity that does not support the task.
6. Verify with the project’s available checks. For visual work, prefer browser or screenshot review in desktop and mobile viewports.

## Output Contract

For design-only work, provide UX structure, role and journey model when relevant, visual source/rationale, UI specs, risks, assumptions or unresolved gaps, and acceptance checks.

For implementation work, provide edited files, verification performed, and any gaps that could not be verified locally.

For review work, lead with findings: severity, file/line reference when available, user impact, and suggested fix.

## Default Commercial Rules

- Follow the existing design system first.
- When repairing an existing product screen, preserve information architecture, component semantics, and visual tokens; fix failed states or flows without restyling unrelated surfaces.
- Use an 8px spacing rhythm and card radius of 8px or less unless the existing system differs.
- Ensure text contrast meets WCAG AA and prefer familiar controls over custom novelty.
- Every interactive element needs default, hover, active, focus, disabled, loading, and error treatment when applicable.
- Protected or destructive actions need hard gates: disabled or aria-disabled states, confirmation input, permission checks, approval waits, or undo paths.
- Build actual usable screens, not marketing-first landing pages, unless the user asks for a landing page.
- Do not hide critical product information behind vague decorative imagery.
- For dense or high-risk workflows, keep audit context, field validation, mobile task length, and measurable quality gains visible.

## Red Flags

Stop and re-scope when you notice:

- The request asks for “make it beautiful” without a user task, audience, or product context.
- The UI uses color or animation as a substitute for information hierarchy.
- The screen has no loading, error, empty, disabled, or destructive-action handling.
- A generated page introduces a new design language into an existing product without justification.
- A dense workflow looks complete only because the prompt listed every required state, while mobile flow, audit context, or field validation remains weak.
- The interface relies on dark patterns, fake urgency, deceptive defaults, or inaccessible interactions.
