# BoodleBox Form Factory Specs

These files are the canonical source records for the Fall 2026 BoodleBox qualitative Check-In:

- `PSYC220-AI-BBX-ONBOARD-01-v2.activity.json`
- `PSYC224-AI-BBX-ONBOARD-01-v2.activity.json`
- `PSYC330-AI-BBX-ONBOARD-01-v2.activity.json`

The v1 files are retained as preproduction history. PSYC224 v1 was used for the first synthetic production-path test; that test exposed that the course-use item incorrectly assumed prior Statistics/R use. v2 replaces the course-specific retrospective item with a common first-use task that students complete during onboarding.

The live Form Factory does **not** import these JSON files directly. Its authoritative build input is the `Activity` and `Prompts` tabs in the Google Sheet-bound Form Factory.

Use the JSON files as the version-controlled source when populating those tabs. For each course:

1. copy the top-level activity fields into the `Activity` tab;
2. copy the prompt objects into the `Prompts` tab (`prompt_id`, `text`, `type`, pipe-separated options, `required`, optional `help_text`);
3. run `Validate Current Spec` and confirm the expected active roster count;
4. run `Build Form` only after validation passes.

Expected Fall 2026 roster counts:

- `PSYC220`: 14
- `PSYC224`: 15
- `PSYC330`: 22

All three use section `01`, activity `AI-BBX-ONBOARD-01`, and spec version `2`.

`BBX-COURSE-USE` is now identical across courses:

> Use your course bot now on one real question, concept, assignment, or problem from this course. What did the AI help you understand or do, and what did you still need to judge, check, explain, or do yourself?

This keeps the item usable for first-time BoodleBox users while preserving the intended evidence about AI contribution versus learner-owned judgment.
