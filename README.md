# UX/UI Design Skills Suite

A modular skill system for AI-assisted UX/UI design decisions. Built as [Claude Skills](https://docs.anthropic.com) - structured instruction files that give Claude deep domain expertise in specific design areas.

Each skill is a decision engine, not a reference dump. Ask it what to do, not just what exists.

## What This Is

12 interconnected skills covering the full spectrum of UX/UI design:

| Skill | What it decides | Creativity tiers |
|-------|----------------|-----------------|
| **web-layout-guide** | Page structure, layout types, responsive architecture | Standard / Elevated / Expressive |
| **color-system** | Palette, tokens, contrast, dark mode | Standard / Elevated / Expressive |
| **typography-system** | Type scale, pairing, hierarchy, readability | Standard / Elevated / Expressive |
| **grid-spacing-system** | Spacing scale, density, vertical rhythm | Standard / Elevated / Expressive |
| **motion-system** | Animation purpose, easing, choreography | Standard / Elevated / Expressive |
| **component-patterns** | UI patterns, states, variants, interaction models | Standard / Elevated / Expressive |
| **form-design** | Form UX, validation, multi-step flows | Standard / Elevated / Expressive |
| **accessibility** | WCAG compliance, assistive tech, inclusive design | A / AA (default) / AAA |
| **content-design** | UX writing, microcopy, voice/tone | Standard / Elevated / Expressive |
| **privacy-compliance** | Consent UX, GDPR/CCPA, trust design | By regulation context |
| **ux-audit** | Heuristic evaluation, usability scoring | Consistent rigor |
| **design-system-ops** | Token governance, naming, handoff | Operational |

## Key Features

**Three-tier creativity system.** Every visual skill rates the project as Standard, Elevated, or Expressive based on industry, brand tone, and goals - then gives different recommendations per tier. A healthcare dashboard and a fashion brand site get fundamentally different guidance from the same skill.

**Four workflows per skill.** Each skill supports Select (what should I use?), Implement (build it), Audit (review what exists), and Educate (explain the concept). One skill, four ways to use it.

**Cross-referencing.** Skills reference each other. Ask color-system for a palette and it tells you to also check typography-system for pairing harmony and accessibility for contrast compliance. The system knows what it doesn't cover.

**CSS included.** Design decisions come with illustrative CSS snippets - bridging design intent to implementation. Not full production code, but enough to show the pattern.

## Quick Start

### Claude.ai (Web)
1. Go to Skills (puzzle icon) in Claude.ai
2. Upload individual skill folders or the entire suite
3. Claude auto-activates relevant skills based on your questions

### Claude Code (CLI)
```bash
# Clone the repo
git clone https://github.com/[your-username]/ux-ui-design-skills.git

# Copy skills to Claude Code's skill directory
cp -r ux-ui-design-skills/* ~/.config/claude-code/skills/
```

### Manual (Any AI Tool)
Copy the content of any `SKILL.md` file into your system prompt or context. The reference files can be included when deeper detail is needed.

## Architecture

Every skill follows the same structure:

```
skill-name/
├── SKILL.md              # Decision engine - workflows, tier assessment, principles
└── references/
    ├── catalog.md        # Deep reference content (palettes, patterns, scales)
    ├── techniques.md     # Advanced techniques for Elevated/Expressive tiers
    └── accessibility.md  # Domain-specific accessibility guidance
```

**SKILL.md** is the brain - it routes you to the right decision based on context. **Reference files** are the knowledge - detailed catalogs, code patterns, and examples.

## Skill Dependencies

```
                    ┌─────────────────┐
                    │  frontend-design │ ← Quick aesthetic direction
                    └────────┬────────┘
                             │ aesthetic layer
    ┌────────────────────────┼────────────────────────┐
    │                        │                        │
┌───┴────────┐  ┌────────────┴──────┐  ┌──────────────┴──┐
│ color-     │  │ typography-       │  │ grid-spacing-   │
│ system     │  │ system            │  │ system          │
└───┬────────┘  └────────┬──────────┘  └──────────┬──────┘
    │                    │                        │
    └────────────────────┼────────────────────────┘
                         │ visual foundation
              ┌──────────┴──────────┐
              │  web-layout-guide   │ ← Page structure
              └──────────┬──────────┘
                         │
         ┌───────────────┼───────────────┐
         │               │               │
    ┌────┴─────┐  ┌──────┴─────┐  ┌─────┴──────┐
    │ motion-  │  │ component- │  │ form-      │
    │ system   │  │ patterns   │  │ design     │
    └──────────┘  └────────────┘  └─────┬──────┘
                                        │
                              ┌─────────┴─────────┐
                              │ content-design     │
                              └─────────┬─────────┘
                                        │
              ┌─────────────────────────┼──────────────┐
              │                         │              │
    ┌─────────┴───┐  ┌─────────────────┴┐  ┌─────────┴──────┐
    │ accessibility│  │privacy-compliance│  │ ux-audit       │
    └─────────────┘  └──────────────────┘  └────────┬───────┘
                                                    │
                                          ┌─────────┴────────┐
                                          │ design-system-ops │
                                          └──────────────────┘
```

## Build Status

| Phase | Skills | Status |
|-------|--------|--------|
| Phase 0 | web-layout-guide | Complete |
| Phase 1 | color-system, typography-system, grid-spacing-system | Complete |
| Phase 2 | motion-system, component-patterns, form-design, content-design | Planned |
| Phase 3 | accessibility, privacy-compliance, ux-audit, design-system-ops | Planned |

## Design Decisions

- **Tool-agnostic.** No Figma, Sketch, or tool-specific instructions. Design concepts apply regardless of tooling.
- **WCAG 2.2 AA as gold standard.** All accessibility guidance defaults to AA conformance.
- **GDPR + CCPA prioritized.** Privacy patterns designed for strictest-first compliance.
- **English-only with localization reference.** CJK/RTL/multilingual guidance in dedicated reference files.
- **CSS as illustration, not production.** Code snippets show the pattern - adapt to your stack.
- **Designed for UX designers, not developers.** Decisions are framed as design choices, with implementation as supporting context.

## Contributing

This is a personal skill suite. Issues and suggestions welcome. If you fork and adapt for your own workflow, that's the intended use.

## License

MIT

## Author

Kacy Yang - UX Designer & Team Lead, Web UX Design
