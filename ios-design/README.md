# iOS UX Design — Skills & Commands

Opinionated iOS UX design guidance for building premium SwiftUI interfaces with iOS 26 Liquid Glass.

## Skills

| Skill | Triggers On |
|---|---|
| **ios-design** | UI/UX, layout, components, screen design, Liquid Glass, SwiftUI design, UI audits |
| **ios-color-palette** | Color palette, color scheme, tinting, vibrancy, dark mode colors |
| **ios-typography** | Typography, fonts, type scale, custom fonts, Dynamic Type |
| **ios-navigation** | Navigation, tab bar, NavigationStack, sheets, modals, app structure |

## Agents

| Agent | Description |
|---|---|
| **liquid-glass-ux-expert** | iOS 26 Liquid Glass design specialist — reviews and guides translucent material usage, visual hierarchy, and accessibility |

## Commands

| Command | Description |
|---|---|
| `/design-audit` | One-shot 12-dimension UX audit from screenshot + code. Outputs a phased fix plan. |
| `/design-review` | Conversational review — discusses information hierarchy, CTAs, and content density before running the audit. |

## Installation

```bash
# Skills
cp -r skills/* ~/.claude/skills/

# Agents
cp agents/* ~/.claude/agents/

# Commands
cp commands/* ~/.claude/commands/
```

## Design Philosophy

- **Opinionated, not encyclopedic** — direct guidance, not options
- **Anti-slop focus** — identifies and avoids AI-generated UI tells
- **One accent color** — everything else uses semantic system colors
- **Dynamic Type required** — all custom fonts use `relativeTo:`
