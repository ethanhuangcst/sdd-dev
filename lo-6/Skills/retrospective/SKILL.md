---
name: retrospective
description: Post-task retrospective - extracts lessons learned and saves them as ADRs (Architecture Decision Records) in the project repository
triggers:
  - User says "retrospective", "回顾", "总结经验", "lessons learned"
  - A feature or task has just been completed
  - User invokes /retrospective
---

# Retrospective Skill

After completing a task or feature, extract lessons learned and save them as ADRs in the project repository.

## When to Use

- After completing a feature (post-DoD)
- After resolving a difficult bug
- After making a significant architectural or process decision
- When the user explicitly requests a retrospective

## Process

### Step 1: Review What Happened

Look back at the completed work and identify:

**What went well?**
- Approaches that worked better than expected
- Decisions that proved correct
- Tools or patterns that were effective

**What was difficult?**
- Blockers encountered and how they were resolved
- Approaches that failed before finding the right one
- Unexpected complexity or edge cases

**What would you do differently?**
- Better approaches discovered in hindsight
- Things to avoid next time
- Process improvements

### Step 2: Filter for ADR-worthy Insights

Save as ADR only if the insight is:
- **A decision** - a choice was made between alternatives
- **Non-obvious** - not derivable from reading the code or specs
- **Durable** - likely still relevant in the future
- **Team-relevant** - useful for anyone working on this project

Skip:
- Ephemeral task details
- Things already documented in code or specs
- Obvious best practices

### Step 3: Determine ADR Number

Check existing ADRs in `docs/adr/` to get the next number:
```bash
ls docs/adr/
```

If `docs/adr/` doesn't exist, create it first.

### Step 4: Write the ADR

Create `docs/adr/ADR-{NNN}-{short-title}.md`:

```markdown
# ADR-{NNN}: {Title}

## 状态
已采纳 | 已废弃 | 已取代（被 ADR-XXX 取代）

## 背景
[What situation or problem led to this decision?]

## 决策
[What was decided? Be specific.]

## 原因
[Why was this chosen over alternatives? What alternatives were considered?]

## 后果
[What are the results of this decision? Trade-offs, risks, follow-up actions.]

## 日期
{YYYY-MM-DD}
```

### Step 5: Commit the ADR

```bash
git add docs/adr/ADR-{NNN}-{short-title}.md
git commit -m "docs: add ADR-{NNN} {short title}"
```

## Output Format

```
## Retrospective Summary

**Completed:** [feature/task name]

**ADRs created:**
- ADR-001-use-postgresql.md — chose PostgreSQL over MongoDB for relational data needs
- ADR-002-tdd-workflow.md — adopted TDD as standard development workflow

**Skipped (not ADR-worthy):**
- [anything considered but not saved]
```

## Important Notes

- Quality over quantity — 1 good ADR beats 5 mediocre ones
- ADRs are immutable records — never edit a past decision; create a new ADR that supersedes it
- ADRs live in `docs/adr/` and are committed to git — they are team assets
- Use Chinese or English consistently with the rest of the project's documentation
