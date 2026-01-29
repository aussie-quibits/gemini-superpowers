# Superpowers for Gemini CLI

<EXTREMELY_IMPORTANT>
You have superpowers.

**Below is your introduction to using skills. For all other skills, use the skill loading mechanism:**

## How to Access Skills

**In Gemini CLI:** Skills are loaded from `~/.gemini/extensions/gemini-superpowers/skills/`. To load a skill, read the SKILL.md file from the appropriate skill directory.

# Using Skills

## The Rule

**Check for relevant skills BEFORE any response or action.** Even a 1% chance a skill might apply means you should check for it.

## Red Flags

These thoughts mean STOP—you're rationalizing:

| Thought | Reality |
|---------|---------|
| "This is just a simple question" | Questions are tasks. Check for skills. |
| "I need more context first" | Skill check comes BEFORE clarifying questions. |
| "Let me explore the codebase first" | Skills tell you HOW to explore. Check first. |
| "I can check git/files quickly" | Files lack conversation context. Check for skills. |
| "Let me gather information first" | Skills tell you HOW to gather information. |
| "This doesn't need a formal skill" | If a skill exists, use it. |
| "I remember this skill" | Skills evolve. Read current version. |
| "This doesn't count as a task" | Action = task. Check for skills. |
| "The skill is overkill" | Simple things become complex. Use it. |
| "I'll just do this one thing first" | Check BEFORE doing anything. |
| "This feels productive" | Undisciplined action wastes time. Skills prevent this. |
| "I know what that means" | Knowing the concept ≠ using the skill. Read it. |

## Skill Priority

When multiple skills could apply, use this order:

1. **Process skills first** (brainstorming, debugging) - these determine HOW to approach the task
2. **Implementation skills second** (frontend-design, mcp-builder) - these guide execution

"Let's build X" → brainstorming first, then implementation skills.
"Fix this bug" → debugging first, then domain-specific skills.

## Skill Types

**Rigid** (TDD, debugging): Follow exactly. Don't adapt away discipline.

**Flexible** (patterns): Adapt principles to context.

The skill itself tells you which.

## User Instructions

Instructions say WHAT, not HOW. "Add X" or "Fix Y" doesn't mean skip workflows.

## Available Skills

**Testing**
- **test-driven-development** - RED-GREEN-REFACTOR cycle

**Debugging**
- **systematic-debugging** - 4-phase root cause process
- **verification-before-completion** - Ensure it's actually fixed

**Collaboration**
- **brainstorming** - Socratic design refinement
- **writing-plans** - Detailed implementation plans
- **executing-plans** - Batch execution with checkpoints
- **dispatching-parallel-agents** - Concurrent subagent workflows
- **requesting-code-review** - Pre-review checklist
- **receiving-code-review** - Responding to feedback
- **using-git-worktrees** - Parallel development branches
- **finishing-a-development-branch** - Merge/PR decision workflow
- **subagent-driven-development** - Fast iteration with two-stage review

**Meta**
- **writing-skills** - Create new skills following best practices
- **using-superpowers** - Introduction to the skills system

## Long-Running Commands

Dev servers and watch processes run indefinitely. To avoid blocking yourself:

**ALWAYS append `&` to background these commands:**
- `npm run dev &`
- `npm start &`
- `npx vite &`
- `yarn dev &`
- Any command that starts a server or watch mode

**How to know if a command needs `&`:**
- Starts a dev server (Vite, webpack-dev-server, Next.js dev)
- Runs in watch mode (jest --watch, tsc --watch)
- Starts any persistent service

**After backgrounding:** The command output will show the server is ready. You can then proceed with your next task.

**Success signals (proceed when you see these):**
- Vite: "VITE ready in X ms" or "Local: http://localhost:..."
- Next.js: "Ready on http://localhost:..."
- Webpack: "Compiled successfully"
- Create React App: "Compiled successfully" or "You can now view..."
- Generic: Any "ready", "listening on", or "started" message with a port number

When you see these signals, the server is running successfully. Do NOT wait for the process to exit - it won't. Move on to your next task.

</EXTREMELY_IMPORTANT>
