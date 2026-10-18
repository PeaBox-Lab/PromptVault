# Architecture Decision Governance

**Prompt ID:** `enterprise-architecture-08`  
**Category:** Enterprise Architecture  
**Collection:** Expansion Library  
**Prompt style:** Detailed practitioner workflow

## Purpose

Use this template for a detailed, implementation-oriented **architecture decision governance** with explicit assumptions, evidence controls, risks, and measurable outcomes.

## Copy-ready prompt

```text
You are a senior practitioner in **Enterprise Architecture**. Produce a rigorous **Architecture Decision Governance** that is ready for a real decision or implementation.

## Context
- Objective or decision: {{objective}}
- Subject / organization / product: {{subject}}
- Audience: {{audience}}
- Geography / jurisdiction: {{geography}}
- Time horizon: {{time_horizon}}
- Known facts and evidence: {{known_facts}}
- Constraints and non-negotiables: {{constraints}}
- Alternatives: {{alternatives}}
- Success measures: {{success_measures}}

## Method
1. Reframe the objective into a precise problem statement and decision criteria.
2. Separate verified facts, user-provided facts, assumptions, calculations, and recommendations.
3. Decompose the analysis into the dimensions that materially affect **Architecture Decision Governance**.
4. Compare alternatives consistently; state trade-offs rather than hiding them.
5. Identify failure modes, dependencies, edge cases, unknowns, and evidence gaps.
6. Challenge the leading conclusion with counterarguments and plausible adverse scenarios.
7. Recommend a path only when supported by evidence; otherwise specify the validation needed.

## Required output
1. Executive answer
2. Scope and assumptions
3. Method and decision criteria
4. Detailed findings
5. Options / alternatives matrix
6. Risks, dependencies, and mitigations
7. Recommendation with rationale
8. Implementation or next-action plan
9. Measures of success
10. Open questions and evidence gaps

## Evidence rules
- Never invent sources, facts, statistics, quotations, URLs, policies, or technical capabilities.
- When research is required, prioritize authoritative primary sources and identify publication dates.
- If evidence is unavailable, label the claim `Unverified` and explain how to verify it.
- Show material calculations and assumptions.
- For legal, medical, financial, security, or regulated decisions, flag areas requiring qualified specialist review.

## Output style
Use specific, operational language. Prefer decision-useful detail over generic explanation. Use tables only for genuine comparison. Conclude with a quality checklist.
```

## Placeholders

- `{{alternatives}}`: supply the relevant context or write `Not provided`.
- `{{audience}}`: supply the relevant context or write `Not provided`.
- `{{constraints}}`: supply the relevant context or write `Not provided`.
- `{{geography}}`: supply the relevant context or write `Not provided`.
- `{{known_facts}}`: supply the relevant context or write `Not provided`.
- `{{objective}}`: supply the relevant context or write `Not provided`.
- `{{subject}}`: supply the relevant context or write `Not provided`.
- `{{success_measures}}`: supply the relevant context or write `Not provided`.
- `{{time_horizon}}`: supply the relevant context or write `Not provided`.

## Adaptation notes

- Replace every placeholder before use.
- Add organization-specific standards, policies, data dictionaries, or acceptance criteria where relevant.
- For research-heavy work, specify allowed sources, recency, citation style, and evidence threshold.
- For implementation work, add owners, environments, dependencies, non-functional requirements, and definition of done.
- Run a red-team pass before finalizing high-impact recommendations.

## Quality checklist

- [ ] Objective, audience, scope, and constraints are explicit.
- [ ] Facts are distinct from assumptions and recommendations.
- [ ] Alternatives are compared using consistent criteria.
- [ ] Risks, edge cases, dependencies, and unknowns are visible.
- [ ] No evidence or sources are fabricated.
- [ ] Actions and success measures are concrete.
