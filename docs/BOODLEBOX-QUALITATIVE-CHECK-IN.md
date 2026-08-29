# BoodleBox Qualitative Learning Check-In

Status: `design_ready_for_three_course_form_build`

Date: 2026-08-29

## Decision

Replace the separate `AI-Toolkit-Check-In.docx` workflow with a short Google Form that students keep open while they work through the existing BoodleBox Student AI Toolkit.

The toolkit remains the learning activity. The Form is a distributed observation/interpretation layer, not a second assignment and not a reflective essay.

Use the same four-digit pseudonymous course-code infrastructure as the misconception workflow. Instantiate the Check-In separately for all three Fall 2026 BoodleBox pilot courses so raw student responses remain course-specific:

- `PSYC220` Cognitive Psychology
- `PSYC224` Statistics for the Behavioral and Natural Sciences
- `PSYC330` Lifespan Developmental Psychology

Canonical activity ID: `AI-BBX-ONBOARD-01`.

## Why change the current Check-In

The current Word document is already relatively light, but its five prompts mix three different functions:

1. proof that the student did a setup step;
2. a record of what the model did;
3. evidence of what the student concluded from the experience.

Those are not interchangeable. A student can report that a model bent toward a false claim without understanding why agreement is not evidence. A student can report that a citation supported a claim without understanding why citations still require verification.

The new design separates **observation from interpretation** at the places where that distinction matters while keeping responses short.

## Design architecture

Use **seven common items plus one course-context item**. Total burden remains eight Form items.

The common spine gives cross-course evidence about:

- configuration/context;
- sycophancy and evidential standards;
- citation/source verification;
- cognitive offloading;
- intended transfer and implementation friction.

The eighth item asks how AI functioned in the actual intellectual work of that course. It uses the same prompt ID, `BBX-COURSE-USE`, but course-specific wording.

The toolkit's model-comparison experiment remains. It no longer gets a dedicated Check-In response because its marginal value is lower than collecting one course-grounded use case, and removing that response prevents the instrument from growing to nine items.

## Audit of the existing five checkpoints

| Current checkpoint | Decision | Reason |
| --- | --- | --- |
| Setup: bot/course, sources, one preference | **Keep, sharpen** | Useful completion evidence, but ask what the configuration was intended to change rather than collecting a personal preference for its own sake. |
| Convince It of a Lie: model + whether it bent | **Split** | Model behavior is useful descriptive data, but it does not establish that the student understands sycophancy or evidential standards. |
| Model comparison | **Keep as toolkit experiment; stop collecting separately** | Students should experience model differences, but a separate response adds less pilot value than a course-grounded use case. |
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
- Keep seven prompt IDs and wording identical across PSYC220, PSYC224, and PSYC330.
- Use one stable course-context prompt ID with course-specific wording.
- Keep Forms/workbooks/roster validation separate by course.
- Cross-course pilot reporting should use instructor-reviewed de-identified themes/aggregates rather than raw student codes or distinctive identifiable responses.

## Proposed student flow

**Open Check-In → configure course bot → run sycophancy experiment → compare models → verify a retrieved claim/source → apply an offloading boundary → try the bot on a real course-relevant task → final pilot reflection → submit.**

The Form should feel like a lab notebook: brief entries made immediately after each experiment.

## Common prompt set

### 1. `BBX-SETUP-EVID` — Setup evidence

**Type:** short answer  
**When:** After building/configuring the course bot.

> Name the course bot you built, one or two course sources you added, and one tutor instruction or configuration choice you made. What were you trying to make the bot do differently with that choice?

**Role:** substantive completion evidence plus qualitative information about how students configure AI for learning.

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

### 4. `BBX-CITE-OBS` — Source-support observation

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

### 5. `BBX-CITE-REASON` — Citation is not verification

**Type:** short answer  
**When:** Immediately after `BBX-CITE-OBS`.

> What did opening the source let you determine that seeing the AI provide a citation or link by itself could not tell you?

**Role:** primary reasoning evidence for `AI-CITE-01`.

---

### 6. `BBX-OFFLOAD` — Task completion is not learning

**Type:** short answer  
**When:** After `Talk About Your Own Learning`.

> Choose one real assignment or study task from this course. Name one part AI could appropriately support and one part you should probably do yourself because doing that cognitive work is what produces the learning. Explain why you divided the work that way in 2–4 sentences.

**Role:** primary reasoning evidence for `AI-OFFLOAD-01` and strong participation evidence.

---

### 7. `BBX-COURSE-USE` — Course-context use

**Type:** short answer  
**When:** After trying the course bot on one course-relevant task.

Use one of the following course-specific wordings.

#### PSYC220 Cognitive Psychology

> Use your course bot on a question that requires you to distinguish or connect two cognitive psychology ideas. What did the AI help you see, and what part did you still have to judge, explain, or verify yourself?

**Purpose:** capture AI as a conceptual-learning tool rather than merely an answer generator.

#### PSYC224 Statistics

> Describe one time the AI helped you understand a statistical idea or an R problem. What did it help with, and what did you still have to determine, check, or interpret yourself?

**Purpose:** capture tutoring/troubleshooting use while preserving learner responsibility for statistical reasoning and interpretation.

#### PSYC330 Lifespan Developmental Psychology

> Use the AI on a developmental claim or source-based question from this course. What did it help you locate or understand, and what did you still have to judge, interpret, or verify yourself?

**Purpose:** capture course-content and source-supported reasoning rather than generic AI satisfaction.

---

### 8. `BBX-PILOT-OPEN` — Transfer + implementation friction

**Type:** short answer / paragraph-length response  
**When:** Final checkpoint before submission.

> After doing these experiments, what is one thing you expect to do differently when you use AI for coursework? Also tell us one part of BoodleBox or this toolkit that was confusing, limiting, or not worth the effort. If nothing fits either part, say that rather than inventing an answer.

**Role:** open qualitative pilot evidence. Code later for emergent themes; do not force this into a predefined misconception taxonomy.

## Estimated burden

Eight Form items total. Six require writing; two are single-click observations. Target total writing remains roughly 8–12 concise sentences distributed across work students are already doing.

This should be lower-friction than opening, maintaining, saving, and submitting a separate Word document while producing better analyzable data.

## Participation interpretation

Use `participation_0_3`; correctness is excluded.

- **3:** Essentially complete. Responses are specific enough to show the associated experiments/setup were actually attempted and the reasoning prompts contain substantive engagement.
- **2:** Substantially complete, but one checkpoint is missing, generic, or too shallow to establish meaningful engagement.
- **1:** Materially partial/perfunctory, but contains some meaningful evidence of participation.
- **0:** No meaningful canonical submission.

A misconception can earn full participation credit. A polished but generic answer that does not appear tied to the activity should not automatically earn full credit.

## Analysis plan

### Shared AI-literacy targets

Use the course-specific canonical responses to assess:

- `AI-SYC-01` — agreement/change is not evidence;
- `AI-CITE-01` — citation is not verification;
- `AI-OFFLOAD-01` — successful task completion is not equivalent to learning.

Do not infer those understandings from observation items alone.

### Course-context themes

Use `BBX-COURSE-USE` to examine different instructional roles for AI:

- **PSYC220:** conceptual differentiation, comparison, explanation, and learner judgment;
- **PSYC224:** statistical tutoring, R troubleshooting, interpretation, and checking;
- **PSYC330:** developmental-content reasoning, source use, interpretation, and verification.

The prompt ID stays constant so the same analytic pipeline can recognize the item, but the prompt text and coding frame remain course-specific.

### Pilot qualitative themes

Code `BBX-SETUP-EVID`, `BBX-COURSE-USE`, and `BBX-PILOT-OPEN` for themes such as:

- configuration strategies students actually use;
- course sources students find useful as context;
- ways students use AI for actual disciplinary work;
- what students retain as learner-owned judgment;
- reported changes in intended AI behavior;
- BoodleBox usability/friction;
- toolkit activities perceived as useful or unhelpful;
- unexpected affordances, risks, or misconceptions.

Begin with a small provisional codebook, but preserve an `other/emergent` route rather than forcing all responses into prior categories.

## Course separation and aggregation

Build three separate v1 instances:

- `PSYC220 / 2026FA / 01 / AI-BBX-ONBOARD-01 / v1`
- `PSYC224 / 2026FA / 01 / AI-BBX-ONBOARD-01 / v1`
- `PSYC330 / 2026FA / 01 / AI-BBX-ONBOARD-01 / v1`

Each course keeps its own roster-valid codes, Form, response workbook, normalized data, and instructor-facing participation review.

For the cross-course pilot layer, retain only instructor-reviewed de-identified aggregate/theme evidence by default. Do not move names, student codes, submission IDs, or distinctive raw responses into a cross-course public/reporting artifact.

## What this replaces

Once all three Forms are production-tested and linked from the BoodleBox toolkit:

- remove the requirement to download/maintain/submit `AI-Toolkit-Check-In.docx`;
- replace the existing inline `Check-in` cues with direct links/cues to the relevant Form checkpoints;
- replace the final Responsible Use instruction to submit the Word document with `Submit your Check-In`;
- update the faculty `students.html` page to describe the centralized Check-In rather than a Word document.

Keep the Word file only as an archived fallback if desired; it should not remain in the normal student path.

## Governance boundary

These responses can be used immediately for instruction, participation preparation, and internal pilot/program evaluation under the institution's applicable policies. Before treating the dataset as generalizable human-subjects research, publishing identifiable quotations, or making research claims, confirm the relevant consent/IRB/institutional requirements.

## Next implementation gate

1. Prepare Form Factory v1 specs for PSYC220, PSYC224, and PSYC330 with the seven common items plus the appropriate `BBX-COURSE-USE` wording.
2. After the remaining Gemini/Form Factory v0.3.3 cleanup is installed and the Gemini production Form is returned to clean zero-state, load and build the three BoodleBox instances.
3. Synthetic-test PSYC224 first because the current Form Factory/roster path is already exercised there; then verify the PSYC220 and PSYC330 roster counts during build.
4. Remove each synthetic Form response and rebuild each response workbook to clean zero-state before student use.
5. Insert distributed Check-In cues/links into the existing BoodleBox toolkit pages.
6. Remove the Word-document requirement from the student and faculty paths only after the replacement Forms are production-tested.
7. After the first real cohort completes the Check-In, audit response quality before changing the prompt set. Do not add more questions unless the first data show a specific information gap.
