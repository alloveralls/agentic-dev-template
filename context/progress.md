<!-- Purpose: progress logging. Rotate to context/progress/YYYY-MM.md when this file grows large. Use entry format: `- YYYY-MM-DD HH:MM TZ | Who | What | Decision (採用/却下+理由) | Next actions` and include related diff/PR/commit ids. -->

## 2026-01-06
- Reviewed current docs (AGENTS.md, CLAUDE.md, WORKFLOW.md, skills/*, policies/*) to assess gaps raised in points A–E.
- Drafted improvement proposals for skill spec/location, stack definition, quality gates, git workflow, and progress logging; no repo changes applied yet.
- Created `.github/skills` and moved existing skill files there; added `.claude/skills` symlinks and `.codex/skills` symlinks (later writes to `.codex` are now denied).
- Added README.md guidance plus templates `stack.md` and `quality_gates.md` for users to declare stack and quality gates.
- Moved `stack.md` and `quality_gates.md` into `policies/` and updated README references accordingly.
- Migrated reviewer agent to `.claude/agents/reviewer.md` with sub-agent front matter format; removed `agents/reviewer.agent.md`.
- Attempted to add `.codex/boot.md` and `.codex/agents/reviewer.md` per request; writes to `.codex` are denied (`Operation not permitted`). Pending user unlocking or permission to modify `.codex`.
- Split shared vs agent-specific boot flow: updated `AGENTS.md` to point Claude to `.claude/boot.md` and Codex to `codex_boot.md` (temporary stand-in for `.codex/boot.md`); added those boot files.
- Attempted to stage/commit changes, but `.git` is read-only (cannot create `.git/index.lock` or new files); commit pending write access to `.git`.
- Performed repository-level defect review (docs/policies/skills). Logged findings and left files unchanged.
- Clarified WORKFLOW.md roles and single-review-per-stage flow per user request.
- Unified WORKFLOW.md language to English and removed model names from the assumed roles section.
- Committed `chore: align agent boot flow` and `chore: clarify reviewer skill usage` after gaining git write access.
- Rebuilt skills to Copilot directory/SKILL.md format under `.github/skills/*` and recreated symlinks in `.claude/skills` and `.codex/skills`; committed as `chore: restructure skills to copilot format`.
- Implemented Git/PR improvements: updated `policies/commit_pr_rules.md` (branch strategy, conventional commits, PR requirements), added `.github/pull_request_template.md`, and added `.github/workflows/ci.yml` scaffold (env-driven lint/format/test commands with lockfile-aware installs).
- Added progress logging guidance/rotation note in `context/progress.md`.
- Made CI a placeholder (`.github/workflows/ci.yml` now workflow_dispatch + instructions) pending stack/quality gate selection; updated README templates to reflect CI TODO.
