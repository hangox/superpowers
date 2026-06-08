---
name: using-superpowers
description: "Index of available Superpowers skills and how to invoke them manually."
---

<SUBAGENT-STOP>
If you were dispatched as a subagent to execute a specific task, skip this skill.
</SUBAGENT-STOP>

> **This fork disables automatic skill triggering.**
> Skills are **opt-in**. Invoke one only when the user explicitly asks for it, or when you
> have deliberately decided it is the right tool for the current step. There is **no**
> "if there's even a 1% chance a skill applies you must invoke it" rule here, and there is
> no requirement to check for skills before every task, question, or action.

## Instruction Priority

1. **User's explicit instructions** (CLAUDE.md, GEMINI.md, AGENTS.md, direct requests) — highest priority
2. **Superpowers skills** — apply only when explicitly invoked; they guide HOW to do the work
3. **Default system prompt** — lowest priority

The user is always in control. If an instruction conflicts with a skill, follow the user.

## How to Access Skills

**In Claude Code:** Use the `Skill` tool. When you invoke a skill, its content is loaded and presented to you—follow it directly. Never use the Read tool on skill files.

**In Copilot CLI:** Use the `skill` tool. Skills are auto-discovered from installed plugins. The `skill` tool works the same as Claude Code's `Skill` tool.

**In Gemini CLI:** Skills activate via the `activate_skill` tool.

**In other environments:** Check your platform's documentation for how skills are loaded.

## Platform Adaptation

Skills use Claude Code tool names. Non-CC platforms: see `references/copilot-tools.md` (Copilot CLI), `references/codex-tools.md` (Codex) for tool equivalents.

## Available Skills

Invoke any of these **by name** with the `Skill` tool when you (or the user) want them:

| Skill | Purpose |
|-------|---------|
| `brainstorming` | Explore intent, requirements, and design before implementation |
| `writing-plans` | Turn a spec/requirements into a written multi-step plan |
| `executing-plans` | Execute a written plan with review checkpoints |
| `test-driven-development` | RED-GREEN-REFACTOR TDD workflow |
| `systematic-debugging` | Root-cause workflow for bugs and test failures |
| `subagent-driven-development` | Execute plan tasks via subagents in the current session |
| `dispatching-parallel-agents` | Coordinate 2+ independent tasks across parallel agents |
| `using-git-worktrees` | Set up an isolated workspace via git worktrees |
| `requesting-code-review` | Verify work meets requirements before merge |
| `receiving-code-review` | Process review feedback with technical rigor |
| `verification-before-completion` | Run verification commands before claiming success |
| `finishing-a-development-branch` | Structured options to merge, PR, or clean up |
| `writing-skills` | Create, edit, and verify skills |

## When You Do Use a Skill

- Announce it briefly: "Using [skill] to [purpose]".
- If the skill has a checklist, create a `TodoWrite` todo per item.
- **Rigid** skills (TDD, debugging): follow exactly—don't adapt away the discipline.
- **Flexible** skills (patterns): adapt the principles to context.
- If multiple skills apply, do process skills (brainstorming, debugging) before implementation skills.
