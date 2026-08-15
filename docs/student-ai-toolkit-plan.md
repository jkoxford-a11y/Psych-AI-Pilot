# Student AI Toolkit — Implementation Plan

## Purpose

Create a permanent student-facing AI toolkit for all Psychology majors in the Psychology AI Integration Pilot. All Psychology majors have BoodleBox access. The toolkit is self-guided for Fall 2026; faculty may later make some or all of it required without changing the underlying structure.

The toolkit should teach AI literacy through short explanations plus direct experience. It should not become a long textbook-style page. Reuse the existing `competencies.html` visual language: short principle first, then an expandable **What it looks like** comparison where useful.

Core design rule: **what to do first; why it matters second; optional detail behind disclosures.**

## Student-facing organizing idea

> Good AI use is active, not passive. Give the system the context it needs, choose how you want it to interact with you, compare models, and keep checking whether its answers deserve your trust.

The student should finish the toolkit with:

- one custom BoodleBox bot for each class;
- a reusable personal AI context file;
- a running course-notes ledger for each class;
- a Socratic tutor instruction set;
- experience comparing models and adding/removing context;
- experience with sycophancy and verification;
- a simple habit for handing long chats to fresh sessions;
- a basic understanding of privacy, academic integrity, cognitive offloading, and environmental cost.

## Information architecture

### `students.html` — Student AI Toolkit landing page

Keep this short. Use a checklist of links:

1. Learn the four things to know about AI → `student-ai-basics.html`
2. Set up BoodleBox for your classes → `student-setup.html`
3. Try the five experiments → `student-experiments.html`
4. Learn responsible-use habits → `student-responsible-use.html`
5. About the Psychology AI Pilot → `index.html`

The landing page should say the sequence is self-guided for now.

### `student-ai-basics.html` — Using AI Well

Four student-language competencies, each short enough to scan.

#### 1. Context matters

Define **context** before using the term repeatedly:

> Context is the information AI has available when it responds. That can include what you type in the current conversation, the instructions and knowledge attached to a custom bot, and information the AI retrieves with tools or search.

Important distinction:

- If needed information is not in context, output is often generic or based on assumptions.
- A model can hallucinate even in a short chat.
- Long or overloaded chats add a different risk: the model can miss, blur, mis-weight, or contradict information that appeared earlier.

Operational student rule of thumb, explicitly labeled as a practical heuristic rather than a technical limit:

> Around 30 substantive back-and-forth messages is a good warning point to consider a fresh chat. Start sooner if you have pasted a lot of material, changed topics repeatedly, or notice the AI forgetting instructions or contradicting earlier work.

#### 2. Fluent does not mean correct

AI can confidently generate incorrect facts, fabricated details, bad summaries, or poor advice. Important claims must be checked against an appropriate source.

Do not imply that hallucination is caused only by long context.

#### 3. AI adapts to you

Define **sycophancy** simply: AI can bend toward what the user appears to want or believe rather than maintaining an independently justified answer.

Explain why this matters:

> Agreement can feel like evidence. A tutor that politely confirms a misconception can leave you more confident and less correct. Sycophancy can therefore produce poor advice, reinforce bad interpretations, and damage learning.

Show a naive/competent toggle using a psychology misconception if possible.

#### 4. Models differ

Students should learn that models differ in depth, speed, skepticism, verbosity, style, and reliability.

Working heuristic:

> Smaller/faster models are useful for simple work, but speed often comes with reduced capability. For difficult reasoning or information where mistakes matter, switch to a stronger model and still verify the result.

Do not say that small models are always wrong or that large models are always correct.

## `student-setup.html` — Set Up Your AI

### Ask BoodleBox about BoodleBox

The Bot Builder is already obvious on the left side, so do not waste space on UI screenshots or navigation instructions.

Student habit:

> If you do not know how to do something in BoodleBox, ask the bot.

Examples: creating a custom bot, adding knowledge, replacing a knowledge file, comparing models.

Then introduce desirable difficulty separately:

> For course content, do not automatically ask AI the instant something becomes difficult. Some struggle is useful for learning. A good first conversation with your bot is: “Explain desirable difficulty and help me decide when AI is helping me learn versus doing the thinking for me.”

### One custom bot for every class

Students should make one custom bot for each class so the bot can retain stable course instructions and materials.

Initial setup:

1. Create the class bot.
2. Add the supplied Socratic tutor instructions.
3. Add the syllabus.
4. Add the running course-notes ledger.
5. Add other high-value course materials within BoodleBox’s 10-knowledge-source limit.
6. Keep the knowledge current across the semester.

### Starter Socratic tutor instructions

Provide an exact copyable instruction block. It should:

- help the student understand and remember rather than simply answer;
- ask the student what they think first when productive;
- use questions, hints, examples, analogies, and counterexamples;
- resist unsupported claims rather than automatically agree;
- flag uncertainty;
- distinguish course-material information from other knowledge when possible;
- ask for retrieval/application periodically;
- aim to make the student less dependent on AI over time.

### Course Notes Ledger

Because BoodleBox allows only 10 knowledge sources, do not use one source per class meeting.

Have students maintain one running document per course, e.g. `PSYC 220 Course Notes Ledger`.

After class:

1. Type or transcribe handwritten notes into the ledger.
2. Check the transcription against the original notes.
3. Date each class section.
4. Preserve terminology actually used by the instructor.
5. Add new material to the same running document.
6. Replace/update the bot’s ledger knowledge source as needed.

Explain the point in one sentence:

> Your AI gets better as the context you maintain gets better.

### Personal AI Context file

Provide an interview prompt that asks one question at a time and creates a reusable academic context file. It may include:

- year in college;
- major/minor and academic interests;
- current subjects;
- career interests;
- preferred answer length (terse vs. expansive);
- desired vocabulary level (plain language vs. learning new/sophisticated words);
- examples/analogies/questions/direct explanation preferences;
- tone;
- how much challenge/pushback the student wants;
- whether the AI should require an attempt before helping;
- how uncertainty/disagreement should be communicated;
- recurring AI behaviors the student finds helpful or annoying.

The file should also include intellectual safeguards because personalization is not only about style. Ask whether the student wants AI to:

- challenge unsupported claims;
- distinguish confidence from evidence;
- flag uncertainty;
- surface alternative explanations;
- warn when external verification is appropriate;
- explain what evidence changed its answer if it reverses itself.

Explicitly avoid sensitive personal information.

### Long-chat handoff

Give students a copyable handoff instruction:

> Create a handoff for a fresh chat. Preserve my goal, important context, decisions we have made, unresolved questions, relevant terminology, and what we should do next. Do not add new conclusions.

Then start a new conversation with the same class bot and paste the handoff.

## `student-experiments.html` — Experiments Worth Trying

Keep each experiment extremely short: what to do + what to notice. No assignment-style apparatus.

### 1. Give It Context

- Use the class tutor with instructions but no course knowledge.
- Ask several course questions.
- Add syllabus/notes/course materials.
- Ask the same questions again.
- Notice what improves and what still requires checking.

Lesson: context changes output.

### 2. Convince It of a Lie

Use a harmless, clearly false premise such as:

> “The adult human heart normally has five chambers.”

- Verify first that the claim is false.
- Try to persuade Sonnet 4.5 to accept it.
- Push back if the model resists.
- Ask: “Why did you agree with me? What evidence changed?” if it changes position.
- Repeat with Opus 4.8.

Expected classroom hypothesis: Sonnet may be easier to move and Opus may push back more strongly, but do **not** promise the outcome. Model behavior varies and model menus change.

Lesson: sycophancy can reinforce error and damage learning.

### 3. Find the Model You Work Well With

Choose one small task related to the student’s major or discipline. At minimum try:

- GPT-5.6
- Claude Opus 5
- one other model of interest

Use the same task. Compare depth, concision, skepticism, vocabulary, usefulness, and whether each model catches bad assumptions.

Prompt students to ask: **Which model made me think better?** not merely “Which answer did I like best?”

If model labels change, use the closest current equivalents and preserve the comparison logic.

### 4. Catch It Being Wrong

Find one factual or interpretive claim from AI that matters enough to check. Verify it using an appropriate external or course source. Correct the AI if necessary.

Lesson: generated is not verified.

### 5. Talk About Your Own Learning

Ask the bot to explain desirable difficulty, cognitive offloading, and when AI help stops being help. Use a real current course task as the example.

Lesson: AI should support learning, not replace the part of the task that produces learning.

## `student-responsible-use.html` — Responsible Use

Keep this concise and practical. Combine related issues rather than spawning many small pages.

### Learning vs. offloading

Some struggle is the learning mechanism. Use AI after an attempt when the attempt itself is what builds the skill.

### Verification

Check claims in proportion to their consequence. Fluency and confidence are not evidence.

### Privacy

Do not put sensitive personal, medical, clinical, financial, password/account, or identifiable client/research-participant information into course bots.

### Academic integrity

AI rules can differ by course and assignment. The student remains responsible for work submitted under their name and should follow the instructor’s disclosure/process requirements.

### Environmental concerns

AI use has real computing and energy costs; exact impact varies by model, provider, hardware, and data center. Avoid moralizing or unsupported quantitative claims. Practical guidance: use the simplest model that reliably does the job, plan before repeatedly regenerating, and do not confuse easy access with zero resource cost.

### Model choice

For simple work, faster/smaller models can be efficient. For complex reasoning or higher-consequence information, use a stronger model and verify important claims regardless of model.

## Visual / UX requirements

- Preserve `shared.css` typography, spacing, colors, and component vocabulary.
- Reuse `.concept`, `.disclosure`, `.naive-competent`, `.nc-block`, and card patterns from `competencies.html`.
- Student pages should be highly scannable.
- Prefer short paragraphs and numbered steps.
- Use disclosures for prompts/examples rather than showing long prompt text inline.
- No dense introductory essay.
- No large assignment rubrics, grading apparatus, or faculty-facing implementation notes on student pages.
- No unnecessary screenshots of the BoodleBox UI.
- Keep claims modest and operational.

## Navigation

Create a first-class `Students` destination. New student pages should link among themselves and back to the Pilot overview. When integrating into the existing site navigation, add `Students` without removing the existing faculty/pilot destinations.

## Files

- `students.html`
- `student-ai-basics.html`
- `student-setup.html`
- `student-experiments.html`
- `student-responsible-use.html`
- `student-toolkit.css` (student-only extensions; leave `shared.css` intact unless a genuinely global style is needed)

## Implementation / audit instruction for another coding agent

Read this file first, then inspect `competencies.html`, `activities.html`, `index.html`, and `shared.css`. Implement the student toolkit without adding instructional prose beyond what is needed to express this spec. Preserve the site’s existing visual language, especially the expandable **What it looks like** pattern. After implementation, audit internal links, navigation, mobile layout, duplication with existing competency/activity material, and whether any page has become unnecessarily dense.
