# Skills Index

This file is the single source of truth for all available skills.
Only skills listed here may be fetched and used during code generation.

---

## Frontend Skills

### High-Quality UI Generation (Non-AI-Slop)

Description:  
Enforces creation of clean, intentional, human-designed UI layouts. Prevents generic, template-looking, over-styled AI output. Focuses on hierarchy, spacing, visual rhythm, and restraint.

When to use:  
Use this skill whenever generating:
- UI components
- Pages, layouts, or dashboards
- SaaS, web apps, or landing pages
- Any visual interface where quality and originality matter

Skill URL:  
https://raw.githubusercontent.com/redmoon0x/skills/refs/heads/main/frontendui.md

---

### Design System Extractor

Description:  
Extracts comprehensive design patterns from reference pages and generates reusable DESIGN_SYSTEM.md specifications. Documents typography, colors, spacing, components, responsive patterns, assets, and code conventions to maintain consistency across projects.

When to use:  
Use this skill whenever:
- You've created a well-crafted page and want to maintain consistency
- You need to document design patterns for reuse
- You want to extract a design system from existing code
- You're standardizing styling across a project

Skill URL:  
https://raw.githubusercontent.com/redmoon0x/skills/refs/heads/main/Design%20System%20Extractor.md

---

## Backend Skills
None registered yet.

---

## Shared Skills

### Automated Changelog Generation

Description:  
Automatically creates user-facing changelogs from git commits by analyzing commit history, categorizing changes, and transforming technical commits into clear, customer-friendly release notes. Turns h[...]

When to use:  
Use this skill whenever generating:
- Release notes
- Product changelogs
- Version update summaries
- Customer-facing update announcements
- Git-based change documentation

Skill URL:  
https://raw.githubusercontent.com/redmoon0x/skills/refs/heads/main/changelog.md

---

## Rules
- Skills must be listed here before use
- Skills must be fetched from their URLs before coding
- All generated code must follow the active skills
- Each code block must reference the skill it follows