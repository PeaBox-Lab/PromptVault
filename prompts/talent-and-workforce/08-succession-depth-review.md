# Succession Depth Review

**Prompt ID:** `talent-and-workforce-08`  
**Category:** Talent and Workforce  
**Collection:** Advanced Library  
**Prompt style:** Research-grade analytical workflow

## What this prompt is for

Use this prompt to produce a detailed, decision-ready **succession depth review**. It is designed to make context, evidence, assumptions, constraints, and the expected output explicit.

## Copy-ready prompt

```text
You are a senior practitioner specializing in **Talent and Workforce**. Complete a rigorous **Succession Depth Review** for the decision described below.

## Working context
- Decision or outcome required: {{decision}}
- Organization / product / subject: {{subject}}
- Intended audience: {{audience}}
- Geography or jurisdiction: {{geography}}
- Time horizon: {{time_horizon}}
- Known facts and supplied evidence: {{known_facts}}
- Constraints and non-negotiables: {{constraints}}
- Alternatives or comparison set: {{alternatives}}
- Desired output format: {{output_format}}

## Task
1. Translate the decision into a precise problem statement and 3–7 answerable sub-questions.
2. Define scope, exclusions, terminology, decision criteria, and an evidence threshold before analysis.
3. Analyze the subject using the methods most appropriate to **Succession Depth Review**. Explain why each method fits.
4. Test the strongest conclusion against at least two plausible counterarguments or failure scenarios.
5. Identify missing data, conflicts, uncertainties, dependencies, and potential bias.
6. Produce a recommendation only when supported by the available evidence. Otherwise state what must be validated next.

## Evidence and validation
- Separate user-provided facts, assumptions, calculations, and recommendations.
- Identify the minimum evidence required to validate each important conclusion.
- Flag legal, policy, security, financial, or operational claims requiring specialist review.

## Required output
1. **Executive answer**: direct response to the decision in no more than 150 words.
2. **Scope and method**: boundaries, definitions, method, and evaluation criteria.
3. **Findings**: evidence-led findings ordered by decision impact.
4. **Analysis**: implications, trade-offs, patterns, and second-order effects.
5. **Options matrix**: compare alternatives using weighted criteria supplied in {{decision_criteria}}.
6. **Risks and counterevidence**: probability, impact, early warning signals, and mitigations.
7. **Recommendation**: recommended path, rationale, conditions, and explicit non-recommendations.
8. **Action plan**: actions, owners, dependencies, decision gates, and target dates.
9. **Evidence register**: claim, source, date, evidence strength, and limitation.
10. **Open questions**: unresolved questions ranked by their ability to change the decision.

## Quality rules
- Never fabricate sources, quotations, statistics, credentials, dates, or URLs.
- If external research is unavailable, provide a research plan rather than simulated findings.
- Quantify uncertainty and show calculations where numerical conclusions are used.
- Use exact, operational language; avoid generic advice and unsupported superlatives.
- Make the deliverable usable without additional interpretation by a practitioner.
```

## Placeholder guide

- `{{alternatives}}`: Replace with the relevant input; use `Not provided` when unknown.
- `{{audience}}`: Replace with the relevant input; use `Not provided` when unknown.
- `{{constraints}}`: Replace with the relevant input; use `Not provided` when unknown.
- `{{decision}}`: Replace with the relevant input; use `Not provided` when unknown.
- `{{decision_criteria}}`: Replace with the relevant input; use `Not provided` when unknown.
- `{{geography}}`: Replace with the relevant input; use `Not provided` when unknown.
- `{{known_facts}}`: Replace with the relevant input; use `Not provided` when unknown.
- `{{output_format}}`: Replace with the relevant input; use `Not provided` when unknown.
- `{{subject}}`: Replace with the relevant input; use `Not provided` when unknown.
- `{{time_horizon}}`: Replace with the relevant input; use `Not provided` when unknown.

## How to adapt it

1. Start with the decision, not the document. State what must be decided or changed.
2. Replace every placeholder. Do not leave silent blanks.
3. Remove sections that genuinely do not apply, but retain evidence and uncertainty controls.
4. Add examples of acceptable output when terminology or format could be ambiguous.
5. For research work, specify approved sources, recency limits, geography, and citation format.
6. Run the prompt once for structure, then refine weak sections with targeted follow-up prompts.

## Best used when

- The output will support a real decision, plan, review, or stakeholder discussion.
- Inputs come from multiple documents, interviews, datasets, or subject-matter experts.
- Unsupported assumptions or invented facts would create material risk.

## Quality check

- [ ] Objective and audience are explicit.
- [ ] Scope and exclusions are clear.
- [ ] Facts, assumptions, and recommendations are separated.
- [ ] Required evidence and source quality are defined.
- [ ] Output structure and level of detail are specified.
- [ ] Unknowns and contradictions are visible.
- [ ] Next actions have owners or decision gates.
