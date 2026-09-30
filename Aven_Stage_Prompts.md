# Aven — three staged prompts

Use these with **Aven_Master_Brief.md** and the **Gym-app** repository attached in Codex. Run one prompt at a time. The first prompt is the current task; the second and third are ready for later.

Source repository: https://github.com/omaralawi1000-netizen/Setline  
Destination repository: https://github.com/omaralawi1000-netizen/Gym-app  
Initial source snapshot: ad6792bb858d30997e3e56e28cb6436f0b83cd82 (reports 1.68.0).

The working app name is Aven; Gym-app remains the repository name. Naming availability is unverified.

## Prompt 1 — Plan the product, features, visual system and motion

Act as a product designer, motion designer and frontend engineer. Plan **Aven**, a separate fitness app for everyday gym users, in the Gym-app repository. Read Aven_Master_Brief.md first and apply its current decisions. Use Impeccable when available. This pass is planning; do not implement the app or change Setline.

The goal is a broadly usable app with exceptional design craft: expressive, premium and approachable, with fast training controls. Carry over Setline's implemented features, including dictation, coaching, routines, nutrition, cardio, progress/body tracking, preferences and integrations. Give the new app a coherent identity and interaction model.

First inspect destination repository instructions and any current files. Then inspect Setline's current source, tests and documentation. Record the exact source commit used. Reconcile the older SPEC.md with PLAN.md and real code; do not use a stale document as the entire feature list. Inspect representative runtime flows if feasible. If source access is unavailable, identify the missing source and produce the unblocked design work; never present a complete feature audit based on memory.

Create an evidence-backed feature map: source capability, source paths, current behaviour, destination screen/workflow, data and voice requirements, edge cases, acceptance scenario and verification status. Account for every implemented capability. Preserve correct domain behaviour and data; identify inherited defects rather than copying them.

Follow the brief's recommended editorial sports direction: warm ivory, ink and cobalt; decisive hierarchy; readable large workout numbers; precise spacing; restrained materials; and a dotted voice orb. Design the whole product coherently, including dense workout controls, quiet settings and empty states. Present the recommendation concretely and explain its main trade-off. Do not reopen already delegated routine choices or ask me to pick CSS values.

Use the linked internet references. Study a relevant screen or interaction, identify exactly what it teaches and show how Aven adapts it. Assemble a small reference board with primary links and clearly labelled screenshots/recordings where available. Include reference versions/dates when known; do not pretend a screenshot proves timing, performance or current runtime behaviour. Do not buy assets or services.

Specify at least these moments:
- Today session surface expanding into the workout.
- Dotted orb moving continuously into and out of the coach composer.
- Real microphone energy driving listening motion.
- Clear interpretation/confirmation before committing commands according to risk.
- A saved set resolving into the correct row, with rest and Undo.
- Workout completion leading into a factual recap.

For each specify trigger, states, timing/easing intent, interruption behaviour, reduced-motion alternative and data commitment. Cover microphone permission/denial, silence, transcription, interpretation, ambiguity, cancellation, speaking, errors, offline use, keyboard changes and background/resume. Every workflow must also work by touch; hold gestures are optional shortcuts.

For the empty destination, assess the brief's React + TypeScript + Vite/PWA recommendation against project constraints. Recommend one stack and a small motion approach with reasons. Avoid overlapping libraries. Reuse source domain logic/tests where appropriate. Do not import Setline's old visual or no-framework restrictions into the new project without a concrete reason.

Separate private-prototype AI setup from public consumer AI: ordinary users should not need developer keys, shared credentials must remain server-side, and operating budget is an explicit launch decision. Do not expand this pass into paid infrastructure, accounts or subscriptions.

Produce four concise project documents:
1. PRODUCT.md — audience, real workflows, scope, assumptions and open product decisions.
2. FEATURE_PARITY.md — evidence-backed inventory and per-feature acceptance scenarios.
3. DESIGN.md — screen map, visual tokens, representative compositions, components, reference board and state/motion specification.
4. PLAN.md — architecture proposal, ordered milestones, first-session experiment, dependencies, risk and verification.

The first implementation milestone must be one real loop: start a workout, log by touch and dictation, review/correct/undo, rest, finish, reopen and find the correct saved result.

Finish with a short recommended plan and its material open decisions. Do not merge, deploy, push changes to Setline or start implementation during this planning pass. Planning documents in Gym-app are within scope.

## Prompt 2 — Build the next complete milestone

Implement the next unfinished milestone from PLAN.md in **Gym-app**. Read Aven_Master_Brief.md, PRODUCT.md, FEATURE_PARITY.md and DESIGN.md first. Honour any newer user corrections. Use Impeccable for interface work when available. Setline is the source reference and remains read-only.

Start by checking the repository state and identify the selected milestone. Carry it through to a working, reviewable result; do not spread effort across unfinished versions of every feature. On the first build, implement the complete workout loop described in the plan. Later invocations implement the next feature-transfer milestone until the inventory is complete.

Build the actual design, not generic scaffolding with an animated orb pasted on top. Match the specified hierarchy, typography, colours, density, control states and motion. Maintain the same visual quality across Today, active workout, coach and quieter utility screens.

Use real local data and implemented flows. Keep demonstration data isolated and labelled; never make unimplemented providers or workflows appear operational. If a milestone requires AI credentials/configuration that are unavailable, finish all independent work and state that exact integration limitation.

Reuse verified source domain rules and meaningful tests; avoid unnecessary rewrites. Keep provider and persistence boundaries explicit. State updates and saving must not wait for animation. Voice results must not double-log sets or apply stale commands after the workout changes. Confident low-risk commands and consequential actions follow the documented confirmation policy.

Treat the signature transitions as engineered behaviour:
- One continuous orb identity and clock where handoffs require it.
- Real audio drives recording/speaking visuals; text status remains visible.
- Layout and keyboard changes do not leave floating objects in the wrong place.
- Rapid taps, interruption, cancellation and unmounting clean up correctly.
- Reduced motion retains all meaning and functionality.
- Offscreen or background visuals stop unnecessary work.

Verify the milestone with appropriate logic tests, browser interaction checks and real persistence/recovery scenarios. Inspect mobile and desktop captures in one batched pass, repair material defects together, then confirm once. Check both themes and reduced motion. A browser timing trace is useful; do not claim real-phone performance without measuring it.

Update FEATURE_PARITY.md and PLAN.md with implementation paths, evidence and remaining work. Finish with what works, how it was checked, anything blocked and the next milestone. Do not claim full parity until every required row is verified. Do not merge or deploy unless separately authorised.

## Prompt 3 — Review, repair and prove the experience

Review the current **Aven** implementation in Gym-app against Aven_Master_Brief.md, PRODUCT.md, FEATURE_PARITY.md, DESIGN.md and PLAN.md. Use Impeccable for design assessment and available browser tools for behaviour. Setline remains read-only.

Assess the actual app, not only code or screenshots. Check whether an everyday user can start, log, dictate, correct, finish and understand the result without a tour. Check that all transferred features remain discoverable and useful.

Review in this order:
1. Data correctness, persistence and feature coverage.
2. Core task clarity and input/voice state.
3. Interaction interruption, accessibility and recovery.
4. Layout, typography, visual consistency and motion craft.
5. Performance and recurring unnecessary rendering.

Compare the implementation to the exact linked reference screens/behaviours used in DESIGN.md. Distinguish observed defects from aesthetic preferences. The quality goal is coherent craft across the product, not a greater number of animated effects.

Exercise ambiguity, microphone denial, provider timeout, silence, offline logging, rapid navigation, keyboard opening, gesture cancellation, larger text, reduced motion and session restoration. Verify that previews never pretend to be saved, spoken input cannot cause duplicate actions, and Undo repairs both data and presentation.

Fix consequential defects that fall within the agreed implementation scope. Retain useful polish. Remove an effect only when its behaviour, clarity, accessibility or cost makes the experience worse, and explain the reason.

Keep review bounded: inspect a representative batch of screens and workflows, fix identified defects in one batch, then confirm. Run meaningful tests after relevant changes. Measure what is available; label real-device checks that still require a phone. Do not invent results, frame rates, audit scores or user feedback.

Update the feature map and milestone status. Deliver a concise report of repaired defects, passed evidence, remaining blockers and whether the current milestone is ready for the next stage. Do not publish, merge or create new external commitments unless authorised.

