# Coding Vision

Behavioral guidelines to reduce common LLM coding mistakes. Merge with project-specific instructions as needed.

**Tradeoff:** These guidelines bias toward caution over speed. For trivial tasks, use judgment.

## 1. Think Before Coding

**Don't assume. Don't hide confusion. Surface tradeoffs.**

Before implementing:
- State your assumptions explicitly. If uncertain, ask.
- If multiple interpretations exist, present them - don't pick silently.
- If a simpler approach exists, say so. Push back when warranted.
- If something is unclear, stop. Name what's confusing. Ask.

## 2. Simplicity First

**Minimum code that solves the problem. Nothing speculative.**

- No features beyond what was asked.
- No abstractions for single-use code.
- No "flexibility" or "configurability" that wasn't requested.
- No error handling for impossible scenarios.
- If you write 200 lines and it could be 50, rewrite it.

Ask yourself: "Would a senior engineer say this is overcomplicated?" If yes, simplify.

## 3. Surgical Changes

**Touch only what you must. Clean up only your own mess.**

When editing existing code:
- Don't "improve" adjacent code, comments, or formatting.
- Don't refactor things that aren't broken.
- Match existing style, even if you'd do it differently.
- If you notice unrelated dead code, mention it - don't delete it.

When your changes create orphans:
- Remove imports/variables/functions that YOUR changes made unused.
- Don't remove pre-existing dead code unless asked.

The test: Every changed line should trace directly to the user's request.

## 4. Goal-Driven Execution

**Define success criteria. Loop until verified.**

Transform tasks into verifiable goals:
- "Add validation" → "Write tests for invalid inputs, then make them pass"
- "Fix the bug" → "Write a test that reproduces it, then make it pass"
- "Refactor X" → "Ensure tests pass before and after"

For multi-step tasks, state a brief plan:
```
1. [Step] → verify: [check]
2. [Step] → verify: [check]
3. [Step] → verify: [check]
```

Strong success criteria let you loop independently. Weak criteria ("make it work") require constant clarification.

## 5. Documentation

**Smart documentation: a lot, but what really is useful.**

- Use docstrings and comments throughout the code.
- Avoid comments about WHAT when it is already clearly and immediately understandable from the code itself.
- Prefer commenting about the WHY of an implementing decision.
- Use both WHAT + WHY when both are needed.

## 6. Smart Architecture

**Everything has a reason to exist and a clear place to belong. Don't mix responsibilities.**

- Give each module, file, and document a specific purpose. Keep related information together instead of scattering or duplicating it across code and documentation. Don't add layers or files without a concrete need.
- Keep `README.md` minimal and human-readable: what the project is, how to get started, and essential usage or setup information. Update it when those facts materially change, not for every implementation detail or minor code change. It is an entry point, not a development diary or changelog.
- Keep `AGENTS.md` focused on durable, project-wide guidance: conventions, architectural boundaries, and essential build or test commands. Update it when those instructions change, not after every commit. Avoid transient implementation details and task summaries that make it stale as soon as the code moves on.
- Put implementation-specific WHAT and WHY beside the relevant code, using JSDoc, docstrings, or focused comments when needed. Explain non-obvious behavior, constraints, and decisions where maintainers will encounter them; and not in a README wall of text they must search separately.
- Put broader explanations that cannot live beside one piece of code in focused documentation, and link to them rather than copying them everywhere. Keep change history in Git or an existing changelog, not in project introductions or agent instructions.

The test: Does this belong here, and does it help the reader working here? If not, move it to the right place or leave it out.

---

**These guidelines are working if:** fewer unnecessary changes in diffs, fewer rewrites due to overcomplication, and clarifying questions come before implementation rather than after mistakes.
