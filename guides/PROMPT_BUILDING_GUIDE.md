# Prompt Building Guide

A useful prompt is a compact operating specification, not merely a request. Build it in layers.

## 1. Start with the decision or outcome

Weak: `Research this market.`

Better: `Determine whether {{company}} should enter {{market}} within {{time_horizon}}, using {{decision_criteria}}.`

The model needs to know what the output will be used for. This determines scope, evidence threshold, depth, and format.

## 2. Provide only relevant context

Include the organization, audience, geography, time horizon, known facts, constraints, alternatives, and prior decisions. Separate facts from assumptions.

## 3. Assign expertise through responsibilities

Instead of `Act as an expert`, specify responsibilities: define the method, challenge weak evidence, compare alternatives, quantify uncertainty, and produce an implementable recommendation.

## 4. Decompose complex work

Use stages: frame the question, define scope, gather evidence, analyze, test counterarguments, recommend, and plan execution. Decomposition reduces omissions and makes results auditable.

## 5. Define an evidence contract

For research prompts, state acceptable sources, recency, jurisdictions, citation fields, and how conflicts should be handled. Never ask the model to invent unavailable research.

## 6. Define the output contract

Specify headings, fields, tables, schemas, length, audience, tone, and decision criteria. When machine-processing the result, provide an exact JSON schema.

## 7. Add failure controls

Require the model to mark unknowns, distinguish assumptions, surface contradictions, avoid fabricated citations, expose calculations, and identify where specialist review is needed.

## 8. Add acceptance criteria

Examples:

- Every recommendation traces to a finding.
- Every material factual claim has a source.
- Each risk has likelihood, impact, trigger, and mitigation.
- Unknowns are listed by decision impact.
- All placeholders are resolved.

## 9. Use iterative prompting

Use a sequence rather than one giant request when the task is complex:

1. Scope and question decomposition.
2. Evidence collection plan.
3. Analysis and contradiction review.
4. Draft output.
5. Red-team critique.
6. Final revision against a rubric.

## 10. Evaluate prompts systematically

Create 5–20 representative test inputs. Score outputs for factuality, completeness, instruction adherence, structure, usefulness, and safety. Compare prompt versions on the same inputs before adoption.
