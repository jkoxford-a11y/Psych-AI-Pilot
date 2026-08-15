# Claude Review Handoff — Student AI Toolkit

Use this prompt when handing the implementation to Claude:

> Work in the `Psych-AI-Pilot` repo on branch `student-ai-toolkit`.
>
> First read `docs/student-ai-toolkit-plan.md`. Treat it as the source of truth for intent, scope, terminology, and what should remain simple. Then inspect the current diff against `main`, especially:
> - `students.html`
> - `student-ai-basics.html`
> - `student-setup.html`
> - `student-experiments.html`
> - `student-responsible-use.html`
> - `student-toolkit.css`
> - the existing `competencies.html`, `activities.html`, `index.html`, and `shared.css`
>
> Audit the implementation before changing it. Focus on:
> 1. factual/technical overclaiming;
> 2. whether any student page is too dense;
> 3. whether the four competencies are understandable to a first-time student;
> 4. whether BoodleBox setup instructions are simple and actionable;
> 5. whether the sycophancy exercise explains why sycophancy can damage learning rather than treating it as a novelty;
> 6. whether the context definition clearly distinguishes missing context, hallucination, and long-chat degradation;
> 7. whether the model-comparison language avoids promising fixed behavior from specific models;
> 8. duplication with existing faculty-facing activities;
> 9. mobile/readability problems and broken internal links.
>
> Preserve the current structure unless the audit finds a real problem. Do not expand the pages with generic AI-literacy prose, extra warnings, assignment apparatus, screenshots, or long explanations. The design rule is: **what to do first; why it matters second; optional detail behind disclosures.**
>
> After substantive review, integrate the toolkit into the site: add a first-class `Students` destination to the existing top-level navigation and add a clear entry point from `index.html`. Preserve all existing navigation destinations and the established visual design.
>
> Make any fixes directly on `student-ai-toolkit`. At the end, summarize only: what you changed, what you deliberately left alone, and any unresolved factual/product-version issue that needs Jon’s decision.
