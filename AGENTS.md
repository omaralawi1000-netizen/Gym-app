# Gym-app / Aven project guidance

## Read first

Read Aven_Master_Brief.md and the relevant stage in Aven_Stage_Prompts.md before substantial work. Once created, PRODUCT.md, FEATURE_PARITY.md, DESIGN.md and PLAN.md carry current product, design and implementation decisions. The user's latest corrections take precedence.

## Repository scope

Gym-app is the destination for the new app. Setline is the feature reference and is read-only unless the user explicitly authorises changes there. Locate repositories from the environment; do not assume fixed mount paths.

Inspect the source implementation, tests and current documentation. Record the source revision and distinguish documented capabilities from verified runtime behaviour. Source UI constraints and its original single-user architecture do not automatically constrain this new app.

## Stage selection

Execute the stage the user requests. Prompt 1 produces the plan and project documents without implementing the app. Prompt 2 implements the next complete milestone. Prompt 3 reviews and repairs that milestone. Do not execute all three stages in one task unless explicitly requested.

## Design and motion

Use the installed Impeccable skill when available. If it is unavailable, inspect Setline's bundled .claude/skills/impeccable/SKILL.md and relevant references as design guidance. Keep any context or output in Gym-app; do not initialise, edit or install hooks in Setline. Report actual tool limitations instead of claiming a skill ran.

Use the master brief's linked references, state-driven voice orb, coherent visual system, touch alternatives and reduced-motion requirements. Avoid overlapping animation libraries and unnecessary rewrites of correct domain logic.

## Completion

Resolve routine choices within the authorised stage. Preserve complete feature coverage, real persistence and meaningful verification. Record assumptions and blockers plainly. Report proposed, implemented and tested work separately. Do not deploy or merge without authorisation.
