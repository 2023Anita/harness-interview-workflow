# Harness Diagram Workflow: Harness Interview Workflow

Created: 2026-07-05T14:41:49+00:00

## Success Contract

- Audience:
- Subject: Harness Interview Workflow
- Primary story:
- Source: /Users/anita/Documents/GitHub project/harness-interview-workflow/skills/harness-interview-workflow/SKILL.md
- Required outputs: `.gif`, `.png`, `.excalidraw`
- Acceptance checks: no text overlap, no truncation warnings, animated GIF, editable Excalidraw

## Field Mapping

- `inputs`: four source inputs or triggers
- `core.cards`: three primary stages
- `decision`: quality gate
- `loop_label`: main control loop
- `retry_label`: revision path
- `left_panel`: intake or source context
- `center_panel`: build packets, layers, or internal state
- `right_panel`: final deliverables

## Render Command

```bash
python3 "/Users/anita/.codex/skills/lanshu-arch-harness/scripts/render_animated_diagram.py" \
  --spec "/Users/anita/Documents/GitHub project/harness-interview-workflow/assets/architecture/harness-interview-workflow/harness-interview-workflow.spec.json" \
  --outdir "/Users/anita/Documents/GitHub project/harness-interview-workflow/assets/architecture/harness-interview-workflow" \
  --basename "harness-interview-workflow" \
  --verify \
  --check
```

## Visual QA

- Top input labels have breathing room.
- Decision diamond text does not collide with arrows or loop labels.
- Core cards read left-to-right.
- Bottom panels are scannable.
- No renderer warnings are present.
