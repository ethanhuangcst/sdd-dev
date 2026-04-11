# Rule - Incremental Delivery

## Complete one user story fully before starting the next.

## Definition of "complete"
A user story is complete when all conditions in the `DoD` rule are satisfied.

## Granularity
- **The unit of delivery is a single user story**, not a feature or epic.
- A feature (e.g. "每日菜谱") contains multiple user stories — implement them one at a time.
- Do not bundle multiple user stories into one implementation cycle, even if they seem related.

## Behavior
- Never start a new user story while the current one is unfinished.
- If you discover a dependency on another user story mid-way, implement the minimum needed to unblock the current story — do not pivot to building the dependency as a full story.
- If a user story cannot be completed due to a blocker, pause and tell me what is blocking it before moving on.
- New requirements discovered during implementation → use `/new-requirement` to capture them as new user stories, do NOT mix them into the current story.

## What this prevents
- Partially implemented features left in the codebase
- Context-switching that leaves multiple things half-done
- "I'll come back to this" code that never gets finished
- Acceptance criteria that were never clearly defined before coding started
