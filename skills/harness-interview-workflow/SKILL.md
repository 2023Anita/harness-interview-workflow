---
name: harness-interview-workflow
description: Run an interview-style harness before complex Codex tasks. Use when the user asks for /harness-interview-workflow, harness采访式工作流, blindspot scanning, unknown discovery, interview mode, plan-before-execution, approval-gated workflows, or when a task needs clarification before coding, writing, research, publishing, repo changes, Obsidian work, GitHub work, or reusable workflow creation.
---

# Harness Interview Workflow

## Overview

Use this skill to slow Codex down before expensive work. The skill turns a vague or complex request into a structured interview: discover unknowns, ask only the highest-leverage questions, propose routes, and wait for explicit approval before execution.

## Operating Contract

1. Restate the user's goal and likely deliverable.
2. Do a blindspot scan before proposing execution.
3. Ask at most 1-3 questions per round.
4. Prioritize questions whose answers change architecture, risk, deliverable shape, or verification.
5. Give 2-3 route options when enough context exists.
6. Stop after the plan if the user asked for a plan or has not approved execution.
7. If the user confirms execution, create a normal implementation plan and use approval gates for risky actions.
8. Maintain implementation notes when execution uncovers edge cases or deviations.

## Blindspot Scan

Classify the request into four unknown types:

```text
Known knowns:
Known unknowns:
Unknown knowns:
Unknown unknowns:
Highest-risk misunderstanding:
Smallest next move:
```

Use plain Chinese by default when working with Anita unless the user asks otherwise.

## Interview Mode

Ask only the next 1-3 questions. Prefer this order:

1. What answer would change the architecture or core route?
2. What answer would change risk boundaries or approval requirements?
3. What answer would change the final artifact format?
4. What answer would change verification or acceptance criteria?
5. What answer only affects style?

Avoid long forms. If a question is optional, continue with a conservative assumption and label it.

## Reference Handling

When the user provides an article, repo, screenshot, code, old project, template, or example, classify the reference before using it:

- `must reuse`: preserve structure, semantics, names, or content.
- `style reference`: borrow feel or pattern, do not copy.
- `do not imitate`: use only to understand constraints.
- `fact source`: cite or preserve factual provenance where needed.

If the classification is unclear, ask one short clarification question.

## Route Proposal

After enough context, provide options like:

```text
方案 A：最小可行版
适合：
会做：
不会做：
风险：
验证：

方案 B：稳妥完整版
适合：
会做：
不会做：
风险：
验证：

方案 C：高质量扩展版（可选）
适合：
会做：
不会做：
风险：
验证：

推荐：
等待用户确认：
```

Do not execute until the user chooses a route or says a clear confirmation such as `确认执行`, `继续`, or `按推荐方案执行`.

## Execution After Approval

When the user confirms execution, use this plan shape:

```text
Goal:
Success criteria:
Current context:
Constraints:
Risks:
Approval required:
Workflow artifact path:
Work packets:
Integration policy:
Verification:
Reusable artifacts:
```

For complex or reusable work, create a workflow artifact:

```text
.workflow/<slug>/
|-- plan.md
|-- state.json
|-- orchestration.md
|-- packets/
|-- results/
`-- final-report.md
```

If `codex-dynamic-workflows` is available and the work is broad, use it together with this skill.

## Implementation Notes

For execution tasks, keep notes in the task's natural location, usually `implementation-notes.md` or `.workflow/<slug>/results/implementation-notes.md`:

```markdown
# Implementation Notes

## Original Plan
## Decisions
## Deviations
## Edge Cases
## User Confirmations
## Verification
## Follow-up
```

When an edge case forces a deviation, choose a conservative path, record why, and continue only if it remains inside the user's approval boundary.

## Final Response

For plan-only work, return:

- blindspot scan summary
- questions asked or assumptions made
- route options
- recommended route
- clear approval question

For executed work, return:

- completed artifacts and paths
- verification evidence
- skipped checks
- remaining risks
- how to reuse the workflow

For complex changes, add a short after-action quiz so the user can confirm they understand what changed.
