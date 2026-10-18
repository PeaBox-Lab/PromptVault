# Content Calendar

**Prompt ID:** `marketing-09`  
**Category:** Marketing  
**Collection:** Core Library  
**Prompt style:** Structured practitioner template

## What this prompt is for

Use this prompt to produce a detailed, decision-ready **content calendar**. It is designed to make context, evidence, assumptions, constraints, and the expected output explicit.

## Copy-ready prompt

```text
You are an expert in marketing. Create a channel-ready campaign brief for **Content Calendar**.

## Inputs
- Primary subject: {{product}}
- Context or audience: {{target_audience}}
- Key requirement: {{objective}}
- Output or constraint: {{channel}}
- Special focus: {{focus_area}}

## Instructions
1. Restate the objective in one sentence and identify missing critical inputs.
2. Organize the response into clearly labeled sections appropriate to content calendar.
3. Distinguish facts supplied by the user from assumptions and recommendations.
4. Use concrete examples, decision criteria, and measurable outcomes where relevant.
5. Do not invent facts. Mark unknowns as `Not provided` and list the evidence needed.
6. Finish with a practical quality checklist and next actions.

## Output standard
Return a concise but complete channel-ready campaign brief. Use tables only when comparison improves clarity. Ensure every recommendation traces back to the stated objective and constraints.
```

## Placeholder guide

- `{{channel}}`: Replace with the relevant input; use `Not provided` when unknown.
- `{{focus_area}}`: Replace with the relevant input; use `Not provided` when unknown.
- `{{objective}}`: Replace with the relevant input; use `Not provided` when unknown.
- `{{product}}`: Replace with the relevant input; use `Not provided` when unknown.
- `{{target_audience}}`: Replace with the relevant input; use `Not provided` when unknown.

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
