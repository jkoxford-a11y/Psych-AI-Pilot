# BoodleBox Form Factory Specs

These files are the canonical source records for the Fall 2026 BoodleBox qualitative Check-In:

- `PSYC220-AI-BBX-ONBOARD-01-v1.activity.json`
- `PSYC224-AI-BBX-ONBOARD-01-v1.activity.json`
- `PSYC330-AI-BBX-ONBOARD-01-v1.activity.json`

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

All three use section `01`, activity `AI-BBX-ONBOARD-01`, and spec version `1`.

Do not populate the live factory with a BoodleBox spec until the existing PSYC101 Gemini production cleanup is complete. The current Activity/Prompts tabs still represent the Gemini production spec and should remain intact until the final synthetic Gemini response is deleted and its response workbook is rebuilt to clean zero-state.
