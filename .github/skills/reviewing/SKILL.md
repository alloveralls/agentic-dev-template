---
name: reviewing
description: Detect defects against the plan, architecture, code, and policies; classify findings without proposing improvements.
---

## Purpose

Report defects with required severity classifications and clear impact, without remediation.

## Inputs

- Artifacts under review (code, plan, architecture)
- Applicable policies and context

## Severity Levels

| Level  | Name     | Description                                                      | Action                             |
| ------ | -------- | ---------------------------------------------------------------- | ---------------------------------- |
| **P0** | Critical | Security vulnerability, data loss risk, correctness bug          | Must block merge                   |
| **P1** | High     | Logic error, significant SOLID violation, performance regression | Should fix before merge            |
| **P2** | Medium   | Code smell, maintainability concern, minor SOLID violation       | Fix in this PR or create follow-up |
| **P3** | Low      | Style, naming, minor suggestion                                  | Optional improvement               |

## Steps

1. Load required context: plan, architecture, policies, and artifacts.
2. Identify defects against requirements, policies, and correctness.
3. Classify each finding as P0, P1, P2, or P3.
4. Report precise locations and impacts using the required format.

## Outputs

- Markdown review in the following structure; no fixes or redesigns:

```markdown
## Review Summary

**Files reviewed**: X files, Y lines changed
**Overall assessment**: [APPROVE / REQUEST_CHANGES / COMMENT]

---

## Findings

### P0 - Critical

(none or list)

### P1 - High

- **[file:line]** Brief title
  - Description of issue
  - Suggested fix

### P2 - Medium

...

### P3 - Low

...
```

- If no issues, state what was checked, areas not covered, and residual risks.

## Failure modes

- Suggesting improvements or scope changes beyond defect reporting
- Missing required P0-P3 classifications or unclear locations
- Mixing detection with remediation
