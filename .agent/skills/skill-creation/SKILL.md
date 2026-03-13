---
name: skill-creation
description: Generates high-quality, predictable, and efficient .agent/skills/ directories based on user requirements. Use when asked to create or build a new skill for the Antigravity agent environment.
---

# Antigravity Skill Creator

## When to use this skill
- When the user asks to create a new "skill" for the agent.
- When you need to automate or structure a specific set of repeating tasks into a reusable skill.
- When generating `.agent/skills/` directories.

## Workflow

1.  **[Plan]** Define the skill name (gerund form), purpose, and triggers.
2.  **[Validate]** Ensure the proposed structure follows the Core Structural Requirements.
3.  **[Execute]** Create the directory and files (SKILL.md, scripts/, examples/, resources/).
4.  **[Verify]** Confirm the YAML frontmatter is valid and paths use forward slashes.

## Instructions

### 1. Core Structural Requirements
Every skill generated must follow this folder hierarchy:
- `<skill-name>/`
    - `SKILL.md` (Required: Main logic and instructions)
    - `scripts/` (Optional: Helper scripts)
    - `examples/` (Optional: Reference implementations)
    - `resources/` (Optional: Templates or assets)

### 2. YAML Frontmatter Standards
The `SKILL.md` must start with YAML frontmatter:
- **name**: Gerund form (e.g., `testing-code`, `managing-databases`). Max 64 chars. Lowercase, numbers, and hyphens only. No "claude" or "anthropic".
- **description**: Written in **third person**. Include specific triggers/keywords. Max 1024 chars.

### 3. Writing Principles
- **Conciseness**: Focus on unique logic. Assume agent intelligence.
- **Progressive Disclosure**: Keep `SKILL.md` under 500 lines. Use secondary files for more detail.
- **Forward Slashes**: Always use `/` for paths.
- **Degrees of Freedom**: 
    - **Bullet Points**: High-freedom tasks (heuristics).
    - **Code Blocks**: Medium-freedom (templates).
    - **Bash Commands**: Low-freedom (fragile operations).

### 4. Workflow & Feedback Loops
- Include **Checklists** for tracking state.
- Use a **Plan-Validate-Execute** pattern.
- Instructions for scripts should be "black boxes"—suggest `--help` if unsure.

## Resources
- [.agent/skills/](file:///.agent/skills/)
