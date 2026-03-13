---
name: UI/UX Pro Max
description: Advanced UI/UX design intelligence, style guide generation, and reasoning engine for building professional interfaces.
---

# UI/UX Pro Max Skill

This skill provides design intelligence, style guides, and reasoning for UI/UX tasks. It uses a local Python-based search engine to find relevant design patterns, color palettes, and implementation guidelines.

## Capabilities

1.  **Design System Generation**: Create a complete design system based on a project description.
2.  **Style Search**: Find specific UI styles (e.g., "Glassmorphism", "Neumorphism").
3.  **Component Guidelines**: Best practices for specific components (e.g., "Dashboards", "Landing Pages").
4.  **Stack-Specific Code**: Guidelines for React, Tailwind, etc.

## Usage

Run the python script located in `scripts/search.py`.

### 1. Generate a Full Design System
Use this when starting a new project or page.

```bash
python3 .agent/skills/ui-ux-pro/scripts/search.py "Project Description" --design-system -p "Project Name"
```

**Example:**
```bash
python3 .agent/skills/ui-ux-pro/scripts/search.py "AI-powered business modeling tool for startups" --design-system -p "Rocketmind"
```

### 2. Search for Specific Topics
Use this when you need help with a specific part of the UI.

**Syntax:**
```bash
python3 .agent/skills/ui-ux-pro/scripts/search.py "query" [--domain domain]
```

**Domains:** `style`, `color`, `chart`, `landing`, `product`, `ux`, `typography`, `icons`, `react`, `web`

**Examples:**
- **Colors**: `python3 .agent/skills/ui-ux-pro/scripts/search.py "fintech blue" --domain color`
- **Charts**: `python3 .agent/skills/ui-ux-pro/scripts/search.py "revenue growth" --domain chart`
- **Landing Page**: `python3 .agent/skills/ui-ux-pro/scripts/search.py "SaaS hero section" --domain landing`

### 3. Stack-Specific Guidelines

**Syntax:**
```bash
python3 .agent/skills/ui-ux-pro/scripts/search.py "query" --stack [stack_name]
```

**Stacks:** `html-tailwind`, `react`, `nextjs`, `vue`, `svelte`...

**Example:**
```bash
python3 .agent/skills/ui-ux-pro/scripts/search.py "responsive navbar" --stack nextjs
```

## When to use this skill
- When the user asks to "design" something.
- When you need to choose colors, fonts, or layouts.
- When generating a new project structure (scaffolding).
- When writing CSS or Tailwind classes.
