# Zen Skills

Nine development skills for clean, simple, small, transparent code.

Prioritize correctness, clarity, simplicity, explicitness, maintainability, then appropriate performance. Minimize unnecessary complexity, not line count. Improve through focused changes and verification.

## Install

Follow the [installation guide](INSTALL.md) for user-wide or project-local installation in Codex, usage, updates, and removal.

## Choose a skill

| Skill | Use |
|---|---|
| [zen-python](skills/zen-python/SKILL.md) | Python implementation, design, data models, errors, tests, performance, idioms, and tooling. |
| [zen-work](skills/zen-work/SKILL.md) | Understand the task, make a complete change, check it, and finish. |
| [zen-design](skills/zen-design/SKILL.md) | Resolve consequential uncertainty and produce useful designs or plans. |
| [zen-build](skills/zen-build/SKILL.md) | Implement or refactor the smallest complete change. |
| [zen-debug](skills/zen-debug/SKILL.md) | Establish causes before correcting unexpected behavior. |
| [zen-verify](skills/zen-verify/SKILL.md) | Choose meaningful checks and match claims to evidence. |
| [zen-review](skills/zen-review/SKILL.md) | Check correctness, what can disappear, and what can become clearer. |
| [zen-coordinate](skills/zen-coordinate/SKILL.md) | Delegate when the benefit justifies the coordination cost. |
| [zen-improve](skills/zen-improve/SKILL.md) | Observe friction, change one thing, check its effect, and retain or discard it. |

Use zen-python for Python work, zen-work for a complete development task, or a focused skill for the activity at hand. Skills are guidance, not a mandatory nine-stage process. Select one workflow owner and avoid simultaneously invoking conflicting lifecycle instructions from another package.

## Package structure

The eight general development skills each contain their own philosophy and procedures in SKILL.md. They do not require companion documents or sibling skills.

zen-python is copied from the original skill, including its eight reference guides. It loads relevant guides selectively. Keep its entire folder together; its references are internal to the package. It may use available specialized skills when useful and includes fallback guidance when they are absent.

The general skills follow zen-python's style: concrete choices, short explanations, practical exceptions, and a final check for what can disappear or become clearer. All skills still follow the user's task, repository conventions, and existing authorization.

## Maintain and verify

Keep common principles consistent while including only the detail each skill needs. Check each skill's metadata, instructions, and local references after edits. Use realistic task evaluations when changing behavior; structural checks alone do not prove better coding outcomes.

This repository contains skill instructions, not a plugin installer or execution framework. No third-party source archive or separate philosophy document is needed to use it.
