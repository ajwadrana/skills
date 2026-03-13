# Claude Code Skills

Published skills and commands for Claude Code.

## Installation

Copy skills into `~/.claude/skills/` and commands into `~/.claude/commands/` to make them available globally.

```bash
# Example: install iOS design skills + commands
cp -r ios-design/skills/* ~/.claude/skills/
cp ios-design/commands/* ~/.claude/commands/
```

Or use `claude plugin add /path/to/skills/<skill-set>` if the skill set includes a plugin manifest.

## Skill Sets

### [ios-design](ios-design/)

Opinionated iOS UX design guidance for SwiftUI + iOS 26 Liquid Glass.

**Skills:**
- `ios-design` — Core design principles, component mapping, Liquid Glass API, 12-dimension audit framework
- `ios-color-palette` — Semantic colors, glass tinting, one-accent-color rule
- `ios-typography` — Open-source font recommendations, type scale, Dynamic Type
- `ios-navigation` — NavigationStack, TabView, sheets, adaptive layout, routing

**Agents:**
- `liquid-glass-ux-expert` — iOS 26 Liquid Glass design specialist for translucent materials, visual hierarchy, and accessibility

**Commands:**
- `/design-audit` — Structured UX audit: screenshot + code analysis, phased fix plan
- `/design-review` — Conversational design review: discuss information hierarchy and CTAs, then audit

### [linear-workflow](linear-workflow/)

Standardized Linear workflow for spec-driven feature development with TDD, commit conventions, and issue tracking.

**Skills:**
- `linear-workflow` — Execute Linear issues with TDD, task tracking, commit formatting (`Completes PROJ-X`), and status updates

