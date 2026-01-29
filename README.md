# Gemini Superpowers

Superpowers is a complete software development workflow for Gemini CLI, built on top of a set of composable "skills" and initial instructions that make sure your agent uses them.

**Adapted from [obra/superpowers](https://github.com/obra/superpowers) for Gemini CLI.**

## How it works

It starts from the moment you fire up Gemini CLI. As soon as it sees that you're building something, it *doesn't* just jump into trying to write code. Instead, it steps back and asks you what you're really trying to do.

Once it's teased a spec out of the conversation, it shows it to you in chunks short enough to actually read and digest.

After you've signed off on the design, your agent puts together an implementation plan that's clear enough for an enthusiastic junior engineer with poor taste, no judgement, no project context, and an aversion to testing to follow. It emphasizes true red/green TDD, YAGNI (You Aren't Gonna Need It), and DRY.

Next up, once you say "go", it launches a *subagent-driven-development* process, having agents work through each engineering task, inspecting and reviewing their work, and continuing forward.

## Installation

### Option 1: Extension Installation (Recommended)

1. **Clone the repository:**
```bash
git clone https://github.com/obra/gemini-superpowers.git ~/.gemini/extensions/gemini-superpowers
```

2. **Register the extension:**

Add to your `~/.gemini/settings.json`:
```json
{
  "extensions": [
    "~/.gemini/extensions/gemini-superpowers"
  ]
}
```

3. **Restart Gemini CLI**

### Option 2: Global Context File

If you prefer a simpler setup, copy the GEMINI.md file to your home directory:

```bash
cp ~/.gemini/extensions/gemini-superpowers/GEMINI.md ~/.gemini/GEMINI.md
```

Then symlink the skills directory:
```bash
ln -s ~/.gemini/extensions/gemini-superpowers/skills ~/.gemini/skills/superpowers
```

### Verify Installation

Ask Gemini: "Do you have superpowers?"

It should respond affirmatively and mention the available skills.

## The Basic Workflow

1. **brainstorming** - Activates before writing code. Refines rough ideas through questions, explores alternatives, presents design in sections for validation. Saves design document.

2. **using-git-worktrees** - Activates after design approval. Creates isolated workspace on new branch, runs project setup, verifies clean test baseline.

3. **writing-plans** - Activates with approved design. Breaks work into bite-sized tasks (2-5 minutes each). Every task has exact file paths, complete code, verification steps.

4. **subagent-driven-development** or **executing-plans** - Activates with plan. Dispatches fresh subagent per task with two-stage review (spec compliance, then code quality), or executes in batches with human checkpoints.

5. **test-driven-development** - Activates during implementation. Enforces RED-GREEN-REFACTOR: write failing test, watch it fail, write minimal code, watch it pass, commit. Deletes code written before tests.

6. **requesting-code-review** - Activates between tasks. Reviews against plan, reports issues by severity. Critical issues block progress.

7. **finishing-a-development-branch** - Activates when tasks complete. Verifies tests, presents options (merge/PR/keep/discard), cleans up worktree.

**The agent checks for relevant skills before any task.** Mandatory workflows, not suggestions.

## What's Inside

### Skills Library

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

### Custom Commands

- `/brainstorm <idea>` - Start interactive design refinement
- `/write-plan <design>` - Create implementation plan
- `/execute-plan <plan-file>` - Execute plan with checkpoints

## Philosophy

- **Test-Driven Development** - Write tests first, always
- **Systematic over ad-hoc** - Process over guessing
- **Complexity reduction** - Simplicity as primary goal
- **Evidence over claims** - Verify before declaring success

## Updating

```bash
cd ~/.gemini/extensions/gemini-superpowers
git pull
```

Restart Gemini CLI to load updates.

## Contributing

Skills live directly in this repository. To contribute:

1. Fork the repository
2. Create a branch for your skill
3. Follow the `writing-skills` skill for creating and testing new skills
4. Submit a PR

See `skills/writing-skills/SKILL.md` for the complete guide.

## Credits

This is an adaptation of [obra/superpowers](https://github.com/obra/superpowers) by Jesse Vincent for use with Gemini CLI instead of Claude Code.

## License

MIT License - see LICENSE file for details
