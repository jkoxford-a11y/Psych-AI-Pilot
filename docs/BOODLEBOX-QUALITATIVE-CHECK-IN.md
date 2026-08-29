# BoodleBox Qualitative Learning Check-In

Status: `design_ready_for_form_build`

Date: 2026-08-29

## Decision

Replace the separate `AI-Toolkit-Check-In.docx` workflow with a short Google Form that students keep open while they work through the existing BoodleBox Student AI Toolkit.

The toolkit remains the learning activity. The Form is a distributed observation/interpretation layer, not a second assignment and not a reflective essay.

Use the same four-digit pseudonymous course code infrastructure as the misconception workflow. Instantiate the same canonical Check-In separately for each pilot course so raw student responses remain course-specific.

Proposed canonical activity ID: `AI-BBX-ONBOARD-01`.

## Why change the current Check-In

The current Word document is already relatively light, but its five prompts mix three different functions:

1. proof that the student did a setup step;
2. a record of what the model did;
3. evidence of what the student concluded from the experience.

Those are not interchangeable. A student can report that a model bent toward a false claim without understanding why agreement is not evidence. A student can report that a citation supported a claim without understanding why citations still require verification.

The new design separates **observation from interpretation** at the places where that distinction matters, while keeping responses short.

## Audit of the existing five checkpoints

| Current checkpoint | Decision | Reason |
| --- | --- | --- |
| Setup: bot/course, sources, one preference | **Keep, sharpen** | Useful completion evidence, but ask what the configuration was intended to change rather than collecting a personal preference for its own sake. |
| Convince It of a Lie: model + whether it bent | **Split** | Model behavior is useful descriptive data, but it does not establish that the student understands sycophancy or evidential standards. |
| Model comparison | **Keep, sharpen** | High-value qualitative evidence if students name a task-relevant difference rather than merely a favorite model. |
| Verification: claim/search/source/support | **Split and simplify** | Standardize what happened, then separately ask what opening the source revealed that the citation alone could not. |
| Learning/offloading | **Keep, sharpen** | Directly captures whether students can protect the cognitive operation the assignment is meant to train. |

Add one final open prompt about **transfer and friction**. This is the main pilot-evaluation addition: what students expect to change in their behavior and what was confusing, limiting, or not worth the effort.

## Design principles

- Ask at the moment the student has just generated evidence worth interpreting.
- Keep behavioral observations separate from conceptual interpretations.
- Correctness does not determine participation credit.
- Require specificity, not length.
- Do not require screenshots, chat exports, or a second narrative document.
- Do not collect personal-context-file contents or sensitive information.
- Preserve at least one broad open prompt so unexpected themes can emerge.
- Use the same canonical prompt set in Cognitive and Lifespan, but separate Forms/workbooks by course.
- Cross-course pilot reporting should use instructor-reviewed de-identified themes/aggregates rather than raw student codes or distinctive identifiable responses.

## Proposed student flow

**Open Check-In → configure course bot → run sycophancy experiment → compare models → verify a retrieved claim/source → apply offloading boundary to a real task → final pilot reflection → submit.**

The Form should feel like a lab notebook: brief entries made immediately after each experiment.

## Proposed prompt set

### 1. `BBX-SETUP-EVID` — Setup evidence

**Type:** short answer  
**When:** After building/configuring the course bot.

> Name the course bot you built, one or two course sources you added, and one tutor instruction or configuration choice you made. What were you trying to make the bot do differently with that choice?

**Role:** substantive completion evidence plus qualitative information about how students configure AI for learning. Not a misconception item by default.

---

### 2. `BBX-SYC-OBS` — Sycophancy observation

**Type:** multiple choice  
**When:** Immediately after `Convince It of a Lie`.

> When you repeatedly pushed the false claim, what best describes the model's behavior?

Options:

1. It held its ground and continued to reject the false claim.
2. It softened or became less certain without fully reversing.
3. It reversed or substantially moved toward my false claim.
4. The interaction was mixed or difficult to classify.

**Role:** observation only. No response is treated as student correctness.

---

### 3. `BBX-SYC-INTERP` — Agreement is not evidence

**Type:** short answer  
**When:** Immediately after `BBX-SYC-OBS`.

> Whether your model held its ground or bent toward you, what would you need before treating a model's change toward your position as evidence that you were actually right? Explain briefly using what happened in your interaction.

**Role:** primary reasoning evidence for `AI-SYC-01`.

---

### 4. `BBX-MODEL-DIFF` — Model choice is task-dependent

**Type:** short answer  
**When:** After comparing models on the same discipline-relevant task.

> Which models did you compare? Give one specific difference that mattered for the task, and explain why that difference would make you choose one model over another for this kind of work.

**Role:** qualitative evidence about task-model matching. Avoids reducing the experiment to a popularity/preference vote.

---

### 5. `BBX-CITE-OBS` — Source-support observation

**Type:** multiple choice  
**When:** After opening at least one source used in the retrieval/search experiment.

> After opening the source and reading the relevant passage yourself, how well did it support the factual claim you checked?

Options:

1. Direct support
2. Partial support
3. No support
4. I could not determine the degree of support

**Role:** observation only. No option is inherently a failure to complete the experiment.

---

### 6. `BBX-CITE-REASON` — Citation is not verification

**Type:** short answer  
**When:** Immediately after `BBX-CITE-OBS`.

> What did opening the source let you determine that seeing the AI provide a citation or link by itself could not tell you?

**Role:** primary reasoning evidence for `AI-CITE-01`.

---

### 7. `BBX-OFFLOAD` — Task completion is not learning

**Type:** short answer  
**When:** After `Talk About Your Own Learning`.

> Choose one real assignment or study task from one of your courses. Name one part AI could appropriately support and one part you should probably do yourself because doing that cognitive work is what produces the learning. Explain why you divided the work that way in 2–4 sentences.

**Role:** primary reasoning evidence for `AI-OFFLOAD-01` and strong participation evidence.

---

### 8. `BBX-PILOT-OPEN` — Transfer + implementation friction

**Type:** paragraph  
**When:** Final checkpoint before submission.

> After doing these experiments, what is one thing you expect to do differently when you use AI for coursework? Also tell us one part of BoodleBox or this toolkit that was confusing, limiting, or not worth the effort. If nothing fits either part, say that rather than inventing an answer.

**Role:** open qualitative pilot evidence. Code later for emergent themes; do not force this into a predefined misconception taxonomy.

## Estimated burden

Eight Form items, but only six require writing and all are distributed across work students are already doing. Two are single-click observations. Target total writing: roughly 8–12 concise sentences across the entire toolkit.

This should be lower-friction than opening, maintaining, saving, and submitting a separate Word document while producing better analyzable data.

## Participation interpretation

Use `participation_0_3`; correctness is excluded.

- **3:** Essentially complete. Responses are specific enough to show the associated experiments/setup were actually attempted and the reasoning prompts contain substantive engagement.
- **2:** Substantially complete, but one checkpoint is missing, generic, or too shallow to establish meaningful engagement.
- **1:** Materially partial/perfunctory, but contains some meaningful evidence of participation.
- **0:** No meaningful canonical submission.

A misconception can earn full participation credit. A polished but generic answer that does not appear tied to the activity should not automatically earn full credit.

## Analysis plan

### Instructional/AI-literacy targets

Use the course-specific canonical responses to assess:

- `AI-SYC-01` — agreement/change is not evidence;
- `AI-CITE-01` — citation is not verification;
- `AI-OFFLOAD-01` — successful task completion is not equivalent to learning.

Do not infer those understandings from observation items alone.

### Pilot qualitative themes

Code `BBX-SETUP-EVID`, `BBX-MODEL-DIFF`, and `BBX-PILOT-OPEN` for themes such as:

- configuration strategies students actually use;
- course sources students find useful as context;
- task-dependent model preferences and why;
- reported changes in intended AI behavior;
- BoodleBox usability/friction;
- toolkit activities perceived as useful or unhelpful;
- unexpected affordances, risks, or misconceptions.

Begin with a small provisional codebook, but preserve an `other/emergent` route rather than forcing all responses into prior categories.

## Course separation and aggregation

Build separate instances for each pilot course, for example:

- `PSYC220 / 2026FA / <section> / AI-BBX-ONBOARD-01 / v1`
- `PSYC330 / 2026FA / <section> / AI-BBX-ONBOARD-01 / v1`

Each course keeps its own roster-valid codes, Form, response workbook, normalized data, and instructor-facing participation review.

For the cross-course pilot layer, retain only instructor-reviewed de-identified aggregate/theme evidence by default. Do not move names, student codes, submission IDs, or distinctive raw responses into a cross-course public/reporting artifact.

## What this replaces

Once the Form is production-tested and linked from the BoodleBox toolkit:

- remove the requirement to download/maintain/submit `AI-Toolkit-Check-In.docx`;
- replace the existing inline `Check-in` cues with direct links/cues to the relevant Form checkpoints;
- replace the final Responsible Use instruction to submit the Word document with `Submit your Check-In`;
- update the faculty `students.html` page to describe the centralized Check-In rather than a Word document.

Keep the Word file only as an archived fallback if desired; it should not remain in the normal student path.

## Governance boundary

These responses can be used immediately for instruction, participation preparation, and internal pilot/program evaluation under the institution's applicable policies. Before treating the dataset as generalizable human-subjects research, publishing identifiable quotations, or making research claims, confirm the relevant consent/IRB/institutional requirements.

## Next implementation gate

1. Instantiate `AI-BBX-ONBOARD-01` v1 in the Form Factory for PSYC220 and PSYC330 using their course/section scope.
2. Synthetic-test one instance end to end with an unknown four-digit code, then remove the synthetic Form response and rebuild to clean zero-state before student use.
3. Insert distributed Check-In cues/links into the existing BoodleBox toolkit pages.
4. Remove the Word-document requirement from the student and faculty paths.
5. After the first real cohort completes it, audit response quality before changing the prompt set. Do not add more questions unless the first data show a specific information gap.
