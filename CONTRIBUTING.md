# Contributing

Open an issue before starting work on anything non-trivial. It's better to align on scope before writing 400 lines of skill content.

## Skill Structure

Each skill is a directory under `skills/`:

```
skills/my-skill/
├── SKILL.md              # Required — loaded when Claude activates the skill
└── references/           # Optional — detailed reference Claude reads on demand
    └── patterns.md
```

`SKILL.md` needs YAML frontmatter:

```yaml
---
name: my-skill
description: "When Claude should activate this skill. Be specific about trigger conditions."
---
```

The `description` determines when Claude loads the skill — vague descriptions waste context window on irrelevant activations.

## Principles

### Accuracy over coverage

Skills directly influence what Claude generates. Wrong information (incorrect filter syntax, outdated object properties, broken code examples) is worse than missing information. Verify patterns against [Shopify's Liquid docs](https://shopify.dev/docs/api/liquid) before contributing.

### Code over prose

Show Do/Don't examples. A three-line code block teaches Claude more than a paragraph of explanation.

### Sensible defaults

When showing patterns, pick the option most developers would reach for. A skill that covers every edge case but buries the common path is less useful than one that leads with the 80% case and links to references for the rest.

## What Makes a Good Skill

| Principle | Do | Don't |
|-----------|-----|-------|
| Scope | One concern per skill | Combine unrelated topics |
| Content | Code examples with Do/Don't | Paragraphs of explanation |
| Gotchas | In `SKILL.md`, up front | Buried in `references/` |
| Depth | Exhaustive lists in `references/` | Everything in one file |
| Naming | Descriptive: `liquid-theme-performance` | Versioned: `liquid-theme-standards-v2` |

## Adding a Skill

Fork, branch from `main`, follow the structure above.

New skills should complement rather than replace existing ones. If a skill targets a specific stack or tooling choice, name it to reflect that scope rather than versioning an existing skill.

## Updating Reference Files

Shopify adds new filters, objects, setting types, and tags over time. Reference files in `references/` are the most common update target. Update the relevant reference file and add to the quick-reference table in `SKILL.md` if applicable.

## Testing Locally

```bash
claude --plugin-dir /path/to/liquid-skills
```

Work on a `.liquid` file and verify Claude references your skill content.

## Pull Requests

- One skill or concern per PR
- Include before/after examples if changing existing patterns
- Squash merge
