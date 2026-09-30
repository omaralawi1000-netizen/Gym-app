# Aven — master product and design brief

Date: 30 September 2026. Status: planning proposal; no new app has been implemented.

Working app name: **Aven**. Name, domain and trademark availability have not been checked. The repository remains **Gym-app**.

Destination: https://github.com/omaralawi1000-netizen/Gym-app  
Feature reference: https://github.com/omaralawi1000-netizen/Setline

## 1. The decision

Create a separate fitness app for everyday gym users: simple enough for beginners, fast enough for regular lifters, and visually distinctive enough to reward close inspection.

Carry over Setline's implemented capabilities and their underlying rules. Develop a new interface, information hierarchy and motion language. The original repository is read-only for this project.

Use one master brief and three focused prompts: planning, implementation, and review. The brief keeps decisions consistent; the smaller prompts keep each pass achievable. Do not prepare a different prompt for every button or screen.

A separate app makes sense as a deliberate product direction. It also creates maintenance work. Prove that the new experience is materially better with one complete workout flow before migrating the entire product. Finish the full feature transfer in subsequent milestones; do not quietly drop features to make the prototype look complete.

## 2. What we know, and what remains open

Confirmed: separate app and repository; all existing Setline features as the reference; dictation is central; creative premium design; broad appeal; exceptional motion; planning and prompts are the current deliverables.

Audience selection was delegated. Recommendation: everyday gym users who use a phone between sets, sometimes with headphones, in a noisy environment.

The connected GitHub repository is named Gym-app and was empty when inspected. Setline's inspected source snapshot is **ad6792bb858d30997e3e56e28cb6436f0b83cd82**, reporting version **1.68.0**.

Evidence read: repository tree, SPEC.md, PLAN.md, js/app.js, js/version.js and js/ui/dotorb.js. PLAN.md contains capabilities beyond the earlier SPEC.md. This is an initial inventory, not a completed runtime audit; the source app was not executed in this planning session.

Open: final name, destination stack, AI operating budget, accounts and commercial launch. Mobile web/PWA is the recommended first target. A native rewrite is not needed to evaluate this design.

## 3. Product promise and interface structure

**Open it, know what to do next, and record your training with very little friction.**

Keep four clearly labelled destinations:

| Destination | Primary job | Content |
|---|---|---|
| Today | Decide and begin | Next workout, weekly plan, useful coach note, daily check-in |
| Train | Perform and organise training | Active session, routines, exercise library, cardio |
| Food | Record nutrition | Meals, search, scans, favourites, protein/calorie targets |
| You | Understand and manage | Progress, records, history, body tracking, preferences, backups |

The coach is available through a recognisable dotted orb and a labelled entry. Provide a visible microphone control in relevant workflows. Voice must be easy to discover without knowing a hidden hold gesture.

Progress remains easy to reach from You and relevant workout summaries. Keeping it out of the main dock does not mean deleting it.

Show the most useful action first. Advanced controls remain available in contextual sheets. Use straightforward copy such as “Start workout,” “Listening,” “Review set” and “Saved.”

## 4. Recommended visual direction: editorial sports precision

Imagine a beautifully typeset training journal with the clarity of a sports timing display. The page earns its impact through proportion, typography and a few carefully designed interactions.

### Visual system

- **Light appearance:** warm ivory ground, deep ink text, cobalt primary actions, clean white raised surfaces. Avoid decorative paper grain that reduces legibility.
- **Dark appearance:** deep ink ground, slightly lifted graphite surfaces, warm off-white text, a contrast-checked cobalt accent. Follow the user's theme preference; do not force a theme change when entering a workout.
- **Hierarchy:** strong page titles, generous workout numerals, compact supporting labels, readable secondary text. Use tabular numbers and stable widths for timers and weights.
- **Composition:** one dominant action surface; supporting information arranged as deliberate rows and sections. Alternate density based on task. A workout can be denser than Today.
- **Shapes:** consistent moderate corner radii; prominent buttons have a clear touch surface. Roundedness should distinguish controls from content.
- **Materials:** mostly solid surfaces. A restrained translucent dock or coach sheet is enough. Blur and glow must not carry all the identity.
- **Imagery:** purposeful icons, existing exercise/anatomy assets where useful, and the dotted orb. Avoid stock athlete photography.
- **Typography implementation:** select one suitable variable sans with readable small text and tabular figures; verify licensing and actual font metrics before bundling. System fallback must remain coherent.

Suggested palette starting points, to be tested rather than treated as verified contrast pairs: ivory #F4F1EB, ink #16181C, cobalt #2549E8, white #FFFFFF, dark surface #23262C. Use separate semantic tokens for text, focus, feedback and charts.

### First viewport

Today opens with a clear date and “Today” title, then a large next-session surface: routine name, compact exercise summary, and a full-width Start workout action. A small week strip and one useful coach note follow. The orb has a distinct home in the dock without competing with the workout action.

Use real routine names. Do not invent readiness scores or medical-looking metrics that the product cannot calculate.

### The three signature moments

1. **The session opens from its own surface.** Starting a routine expands the selected Today surface into the workout. Preserve the routine title's relationship to its source. Data and controls become available immediately; motion supports orientation.
2. **The voice orb has one continuous identity.** Opening the coach carries the same dotted object into the composer. Pose, colour and audio state stay continuous. It settles precisely into place without overshoot.
3. **A spoken set becomes a real set.** “Bench press, 80 kilos, eight reps” creates a readable interpretation. After the command follows the established confirmation policy, its result settles into the correct set row and the rest state appears. The stored state determines the animation.

These are the main craft investments. Ordinary settings and lists should feel consistent and precise, with quieter motion.

### Design trade-off

This direction offers more visual distinction than a standard dark fitness dashboard. Its risk is becoming too sparse or typographically theatrical. Keep the active workout dense enough for useful information and keep controls readable. Professional admiration is subjective; it must be supported by a working prototype and performance evidence.

## 5. Motion specification

Motion describes what the app is doing. Every major transition needs a trigger, destination, interruption rule, reduced-motion version and relationship to committed data.

| Moment | Proposed behaviour | Important condition |
|---|---|---|
| Press | Small tactile response that follows touch and releases cleanly | Cancelled gestures restore state |
| Navigate | Short directional transition; meaningful shared elements retain position | Rapid navigation reaches the latest requested screen |
| Start workout | Selected session surface expands into the active session | Never delay saving or starting |
| Open coach | Dotted orb travels continuously into the composer; sheet enters around it | Preserve pose and handle keyboard/viewport changes |
| Listen | Dots separate and recover according to measured audio energy | Silence stays calm; microphone status also appears as text |
| Process | A controlled phase change distinct from listening and speaking | Represents an actual pending request |
| Interpret | Clear command preview and confidence-dependent controls | Ambiguity never looks like a saved success |
| Save set | Correct row receives a brief confirmation; rest begins | Exactly one committed operation |
| Undo | Reverse the meaningful change and restore the previous state | Persistence and PR calculations agree with the interface |
| Speak | Orb responds to playback energy, with clear speaking status | New recording cancels speech without overlapping capture |
| Complete session | A restrained finish moment leads into a factual recap | Display real results, then remain readable |
| Chart interaction | Immediate touch feedback and a stable tooltip | Values are understandable without relying on animation |

Starting timing ranges, to tune in the prototype: press feedback 90–140 ms; ordinary changes 160–240 ms; sheets and shared elements 260–380 ms; a rare completion accent 400–600 ms. These are design proposals, not universal performance rules.

Use restrained springs where touch or spatial continuity benefits. Use crisp easing for simple entrances. Avoid identical bounce on every element, repeated page-wide staggers, perpetual background clouds and slow word-by-word delivery of important information.

The orb should have explicit idle, requesting-permission, recording, transcribing, interpreting, awaiting-confirmation, speaking and error states. Do not show it listening when no microphone stream is open. Hide or stop expensive rendering when out of view. Reduced-motion mode uses a still orb, text status and immediate state changes or brief opacity transitions.

A shrinking dock may support the active session if it keeps essential controls obvious and has a clear return path. Do not hide labels during normal browsing solely for spectacle.

## 6. Initial Setline feature-transfer map

Verify source implementation, tests and runtime behaviour before marking any row complete. Each final inventory row needs source paths, destination paths, state/data requirements, acceptance evidence and a status: unverified, planned, implemented, verified or blocked.

| Area | Capabilities to investigate and carry over |
|---|---|
| Strength sessions | Routines and empty sessions; exercise lookup/custom exercises; sets and notes; edit/delete/undo; previous performance; rest adjustments; finish/discard; history |
| Training intelligence | Double progression, suggested load steps, warm-ups, plate calculator, exercise reordering, starter programs, pasted programs and coach-created plans |
| Voice and dictation | English/Danish recognition; gym audio preparation; exercise aliases; local command parsing; fallback interpretation; corrections; hands-free commands; typed fallback |
| Voice output | Spoken confirmations, streaming coach replies, selectable voices, device voice fallback, audio cleanup and headphone/music recovery |
| Coach | Grounded conversation, real workout/food/body context, remembered facts, proposals, explicit changes, undo, weekly check-ins and session debriefs |
| Today and planning | Weekday schedules, next session, one-off changes, daily check-in, pinned notes and goal reminders |
| Nutrition | Meals and item quantities, food lookup, barcode/photo flows, favourite/usual meals, repeat meals, calories/protein, water and targets |
| Cardio | Existing session types, timers and source GPS/tracking workflows |
| Progress and body | PRs, estimated 1RM, exercise charts, volume/muscle summaries, goals, bodyweight trends, measurements, monthly photos and shareable summaries |
| Personalisation | English/Danish UI, units, rest, microphone interaction, voice, motion, haptics, themes, existing customisation options |
| Data and integrations | Persistence, active-session restoration, schema changes, backup export/import and Google Drive backup |
| Platform and support | PWA/offline shell, wake lock, update handling, rest notifications/actions, home-screen shortcuts and bug/idea reporting |

The list is a starting map. The builder must discover anything omitted. Documentation claims do not count as verification, and inherited defects do not need to be reproduced.

Voice examples for acceptance: start a routine; “80 kilos for eight”; “same again”; correct the last set; adjust or skip rest; ask for previous performance; finish with confirmation. Include Danish equivalents and ambiguous/noisy inputs.

## 7. Technical proposal and mass-market implications

For the empty repository, recommend **React + TypeScript + Vite**, a PWA shell, semantic components and CSS design tokens. A component structure helps manage the larger stateful interface, and TypeScript can clarify contracts across ported features. This is a proposal for the build stage, not a scaffold created during planning.

Use CSS/native animation for simple feedback. Add one motion library only where it improves shared elements, gestures or interruption handling. If Motion is chosen, use its current official documentation. Keep the existing canvas orb approach as the initial candidate; a thoughtful renderer can be distinctive without adding a full 3D engine.

Reuse and adapt source domain logic, validation and meaningful tests when their behaviour is correct. Separate workout/data rules, provider adapters and rendering. Do not inherit Setline's old palette, layout or no-framework requirement as constraints on the new repository.

Avoid overlapping animation libraries. Rive is an optional reference for state-based interaction, not a required dependency. Add it only for a named asset with a measurable benefit.

Setline was designed around one person's API keys. A broadly usable app should not require ordinary users to acquire provider keys. Plan a provider boundary and make this distinction explicit:

- **Private prototype:** existing developer/BYOK setup can be supported through advanced configuration; touch logging remains available without AI.
- **Public consumer release:** managed AI needs server-side credentials, cost/rate controls and a chosen operating budget. Treat this as a launch decision, not something beautiful screens can solve.

Do not silently build a paid backend, subscriptions, social feed or account system. OAuth origins, callback configuration, reporting destinations and storage names need to be checked for the new app identity.

## 8. Internet references and what each one contributes

These are selected references for specific design jobs, not a claim that one product is “the best” in every respect. Inspect the actual screen or interaction before reproducing any detail. Product screenshots, recorded interactions and technical documentation serve different purposes.

| Reference | What to study | Application to Aven |
|---|---|---|
| [Oura app redesign](https://ouraring.com/blog/new-app-design/) | Daily focus and separation of immediate information from longer trends | Today has one clear priority; deeper progress lives elsewhere |
| [Hevy workout UI](https://www.hevyapp.com/features/track-workouts/) | Set logging, previous values, rest and exercise controls | Active sessions remain useful under time pressure |
| [Gentler Streak: Apple's design interview](https://developer.apple.com/news/?id=3m0ht22s) | Approachable fitness language and coherent visual character | Premium feels welcoming and humane |
| [Linear's 2026 interface refresh](https://linear.app/now/behind-the-latest-design-refresh) | Attention hierarchy, quieter navigation, consistent control placement | Many features remain understandable |
| [Motion layout animations](https://motion.dev/docs/react-layout-animations) | Live examples and shared-element implementation | Session expansion and coherent sheet/composer transitions |
| [Rive state machines](https://rive.app/docs/editor/state-machine/state-machine) | Animation states and transition logic | Orb behaviour maps to actual voice states |
| [Gentler Streak interaction recordings](https://60fps.design/apps/gentler-streak) | Specific recordings of sliders, graphs and recaps | Observe timing and response; some archive content requires Pro |

Free official examples are sufficient to begin; buying a reference subscription is unnecessary for this sprint. The recording archive was located, but clips were not played and timed in this session.

For motion alternatives and touch sizing, use [W3C interaction animation guidance](https://www.w3.org/WAI/WCAG22/Understanding/animation-from-interactions.html) and [W3C target-size guidance](https://www.w3.org/WAI/WCAG22/Understanding/target-size-minimum.html). Aven's proposed 44–48 CSS px primary touch targets are a usability choice above the AA minimum, not a quotation of that minimum.

Create a small reference board during the planning pass: one relevant image or recording per design job, original link, what it teaches and the proposed adaptation. Reference imagery is inspiration; do not reuse proprietary graphics as production assets.

## 9. Milestones

| Milestone | Deliverable | Evidence before proceeding |
|---|---|---|
| 1 — Feature and design plan | Source inventory, reference board, full screen map, tokens, motion/state specification, architecture choices | Every source capability accounted for; proposed design consistent across Today, workout, coach, Food and settings |
| 2 — One complete session | Today → start → dictate → interpret → save → correct/undo → rest → finish → recap | Real persistence; manual fallback; coherent motion; resume after closing |
| 3 — Full feature transfer | Remaining coaching, plans, food, cardio, progress/body, integrations and settings | Inventory closed with verified rows or plainly documented blockers |
| 4 — Production review | Correctness, accessibility, performance, real-phone recordings and repaired defects | Core acceptance scenarios pass; no misleading controls or claims |

**First sprint focus:** prove the voice-and-workout experience. Reserve three to five focus sessions of about 60 minutes for the initial prototype and review; revise the estimate after the source inventory. This is a time budget for a first experiment, not a promise that the whole app fits it.

Keep Setline's scope stable while evaluating Aven. Running two simultaneous redesigns would displace implementation and user testing.

Try the prototype with three to five everyday gym users. Give them tasks rather than a guided tour: start a session, log a set by touch, try dictation, correct it and find the recap.

- Continue if core tasks are clear, data is correct and the signature motion remains useful on a real phone.
- Change the interaction if users miss voice entry, mistake previews for saved sets, or motion makes tasks harder.
- Pause the full transfer if the new flow offers no meaningful benefit over Setline or the maintenance/AI cost is unacceptable.

## 10. Quality and delivery bar

- Verify every preserved workflow and all consequential workout calculations.
- Confirm data saving independently of animation completion and handle duplicate/stale voice results.
- Test microphone denial, silence, noisy input, provider failure, offline use, interruptions, keyboard changes, cancelled gestures and closing mid-session.
- Make charts, controls and feedback readable in both themes, with larger text, keyboard and reduced motion.
- Provide visible alternatives to hold, swipe and drag actions.
- Aim for fluid rendering on a mid-range phone; measure frame behaviour rather than claiming 60 fps from a desktop recording.
- Keep timers timestamp-based. Treat offline logging and remote AI availability as separate capabilities.
- Review source backup/import and integration assumptions before migration. Never include keys in backups or public reports.
- Use meaningful logic tests and browser interaction checks. Capture the main mobile screens and a desktop layout, fix material defects in one batch, then confirm once.
- Report implemented, tested and blocked work separately. An attractive prototype is not proof of full feature parity.

The next action is Prompt 1 in Aven_Stage_Prompts.md, used with this brief and the Gym-app repository. This turn ends with planning artifacts; it does not change either repository.

