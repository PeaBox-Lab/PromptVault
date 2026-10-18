# PromptVault User Guide

This guide explains how to browse, select, customize, run, evaluate, organize, and contribute PromptVault templates.

## Contents

1. [Understanding the library](#1-understanding-the-library)
2. [Finding the right prompt](#2-finding-the-right-prompt)
3. [Customizing placeholders](#3-customizing-placeholders)
4. [Supplying context and source material](#4-supplying-context-and-source-material)
5. [Running a prompt](#5-running-a-prompt)
6. [Evaluating the output](#6-evaluating-the-output)
7. [Improving weak results](#7-improving-weak-results)
8. [Using prompts for research](#8-using-prompts-for-research)
9. [Using prompts with documents and data](#9-using-prompts-with-documents-and-data)
10. [Creating prompt chains](#10-creating-prompt-chains)
11. [Organizing a personal collection](#11-organizing-a-personal-collection)
12. [Using the JSON catalog](#12-using-the-json-catalog)
13. [Creating a new prompt](#13-creating-a-new-prompt)
14. [Privacy, security, and professional review](#14-privacy-security-and-professional-review)
15. [Troubleshooting](#15-troubleshooting)

---

## 1. Understanding the library

PromptVault contains 1,000 individual Markdown prompt pages grouped into 75 categories.

Start from one of three entry points:

- `README.md` for the project overview;
- `CATALOG.md` for the central category catalog;
- `prompts/README.md` for folder-oriented navigation.

Each category folder contains its own `README.md` and individual prompt files.

A typical prompt page includes:

- title;
- stable prompt ID;
- category;
- purpose;
- copy-ready prompt;
- placeholder list;
- usage instructions;
- quality or review checklist.

### Naming convention

```text
prompts/<category>/<number>-<prompt-name>.md
```

Example:

```text
prompts/software-development/04-code-reviewer.md
```

---

## 2. Finding the right prompt

### Browse by category

Use `CATALOG.md` when you know the function or industry, such as:

- Deep Research
- Software Development
- HR Systems
- Investment Research
- Healthcare and Life Sciences
- Cybersecurity and Privacy
- Cloud and DevOps
- Open Source and GitHub

### Search by outcome

Search for the deliverable or decision rather than a broad subject.

Better searches:

```text
vendor evaluation
market entry
incident postmortem
systematic review
API design
workforce plan
investment thesis
```

Less useful searches:

```text
business
technology
research
```

### Search in Visual Studio Code

1. Open the repository folder.
2. Press `Ctrl+Shift+F` on Windows/Linux or `Cmd+Shift+F` on macOS.
3. Search for a phrase such as `evidence register`.
4. Restrict files to `prompts/**/*.md` if needed.

### Search with `ripgrep`

```bash
rg -n -i "root cause|incident review" prompts/
```

Search only titles:

```bash
rg -n '^# ' prompts/
```

Search a category:

```bash
rg -n -i "risk" prompts/cybersecurity-privacy/
```

### Selection rule

Prefer the prompt whose **output and decision** match your situation. A specialized `Vendor Security Assessment` prompt is normally better than a generic `Research Plan` prompt if the actual deliverable is a vendor-security decision.

---

## 3. Customizing placeholders

Placeholders use double braces:

```text
{{objective}}
{{audience}}
{{context}}
{{geography}}
{{time_horizon}}
{{output_format}}
```

Replace every placeholder with a real value or explicitly write `Not provided`.

### Before customization

```text
Create a {{deliverable}} for {{audience}} about {{topic}}.
Use a {{tone}} tone and include {{key_points}}.
```

### After customization

```text
Create a two-page decision memo for senior HR leadership about replacing
regional leave-management tools with a common HRIS process. Use a direct,
evidence-led tone and include current pain points, regional exceptions,
implementation risks, governance, and recommended next steps.
```

### Good placeholder values

A good value is:

- specific;
- factually correct;
- relevant to the requested output;
- understandable without hidden context;
- explicit about uncertainty.

### Handling unknown values

Do not silently leave placeholders unresolved. Use:

```text
Time horizon: Not provided. Ask for it before making time-dependent recommendations.
```

or:

```text
Market size: Unknown. Build a research plan and do not simulate a figure.
```

---

## 4. Supplying context and source material

Prompts improve when the model receives usable evidence.

Possible inputs include:

- meeting notes or transcripts;
- policies and process documents;
- source code and logs;
- product requirements;
- customer interviews;
- survey data;
- spreadsheets;
- contracts;
- research papers;
- financial statements;
- official documentation;
- market reports that you are permitted to use.

### Context block

When a prompt lacks a dedicated context section, prepend:

```text
## Context
Organization: {{organization}}
Audience: {{audience}}
Current situation: {{current_state}}
Decision required: {{decision}}
Known constraints: {{constraints}}
Sources supplied: {{sources}}
Information not available: {{unknowns}}
```

### Source instructions

For document-grounded work, add:

```text
Use only the supplied documents for factual claims. Cite the document name and
section or page where possible. If the documents do not support a conclusion,
mark it Unsupported rather than filling the gap from general knowledge.
```

### Data instructions

For analytical work, add:

```text
Before analysis, describe the available fields, data types, missing values,
duplicates, outliers, date coverage, and likely quality limitations. Do not
infer unavailable columns or silently remove records.
```

---

## 5. Running a prompt

PromptVault templates can be used with Microsoft Copilot, ChatGPT, Claude, Gemini, local models, or another compatible assistant.

### Basic workflow

1. Copy the prompt block.
2. Replace placeholders.
3. Attach permitted source material.
4. Paste the completed prompt.
5. Review the model's interpretation before relying on the output.

### Use a staged run for complex tasks

Do not always submit the entire problem in one step. A safer sequence is:

#### Stage 1: Scope

```text
Review the objective and context. Identify ambiguities, missing inputs, scope
boundaries, and the questions that must be answered. Do not complete the full
analysis yet.
```

#### Stage 2: Evidence plan

```text
Create a source and evidence plan. For each research question, specify the
preferred primary sources, acceptable secondary sources, date range, and
verification method.
```

#### Stage 3: Analysis

Run the customized PromptVault template with the available evidence.

#### Stage 4: Challenge

```text
Red-team the analysis. Identify unsupported claims, hidden assumptions,
contradictory evidence, omitted alternatives, calculation risks, and scenarios
that would reverse the recommendation.
```

#### Stage 5: Finalize

```text
Revise the output using the valid critique. Preserve unresolved uncertainty and
include a final evidence register and open-question list.
```

---

## 6. Evaluating the output

Do not judge an answer only by fluency. Use a review rubric.

### Accuracy

- Are claims supported by supplied or verifiable evidence?
- Do citations exist and support the exact claim?
- Are dates, figures, names, and policy references correct?
- Are calculations reproducible?

### Completeness

- Were all prompt sections addressed?
- Are alternatives, risks, and limitations covered?
- Are important unknowns visible?

### Instruction adherence

- Did the output match the requested format?
- Did it respect word limits, tone, audience, and scope?
- Did it avoid excluded topics or sources?

### Decision usefulness

- Does it answer the actual decision?
- Are recommendations specific and implementable?
- Are owners, dependencies, triggers, or decision gates clear?

### Evidence quality

- Are primary sources prioritized?
- Are conflicts between sources surfaced?
- Is evidence strength distinguished from confidence in the recommendation?

### Safety and review

- Does the answer overreach into professional judgment?
- Does it expose confidential or personal information?
- Has a qualified reviewer checked consequential conclusions?

### Simple scoring rubric

Score each dimension from 1 to 5:

```text
Accuracy:              __ / 5
Completeness:          __ / 5
Instruction adherence: __ / 5
Decision usefulness:   __ / 5
Evidence quality:      __ / 5
Risk handling:         __ / 5
Total:                 __ / 30
```

For important use cases, define a minimum acceptable score before operational use.

---

## 7. Improving weak results

### Problem: the answer is generic

Add real organizational context, named alternatives, constraints, metrics, and output requirements.

```text
Replace generic advice with actions applicable to {{organization}}, given
{{constraints}}. Include owners, dependencies, decision gates, and measurable
success criteria.
```

### Problem: the answer is too long

```text
Compress the analysis into a one-page executive brief. Retain the decision,
three most important findings, material risks, recommendation, and immediate
next actions. Move supporting detail into an appendix.
```

### Problem: claims are unsupported

```text
Create a claim-evidence table. For every material claim, show the source,
relevant evidence, publication date, evidence strength, and limitation. Mark
claims without support as Unverified.
```

### Problem: the answer ignores trade-offs

```text
Compare the alternatives using {{criteria_and_weights}}. Show where each option
wins, loses, and becomes unacceptable. Include sensitivity to changes in the
three most important assumptions.
```

### Problem: the model invents missing information

```text
Do not infer missing facts. Replace unsupported values with Not provided. List
the specific questions or source documents required to close each gap.
```

### Problem: the response follows the prompt but is not useful

Clarify the action expected from the reader:

```text
The output will be used by {{decision_maker}} to decide {{decision}} on
{{decision_date}}. Organize the answer around that decision rather than around
the general topic.
```

---

## 8. Using prompts for research

### Define the research question

A strong research question is bounded by population or subject, geography, time, decision, and evidence standard.

Weak:

```text
Research the HR technology market.
```

Stronger:

```text
Assess whether a large Europe-based services organization should standardize
core HR, leave, time, and compensation processes on a single HR platform over
the next three years. Compare implementation fit, regional compliance,
integration complexity, operating model, total cost, and adoption risk.
```

### Specify a source hierarchy

```text
Priority 1: laws, regulators, standards, audited filings, official datasets,
contracts, and official product documentation.

Priority 2: peer-reviewed research, recognized professional bodies, and
established research institutions.

Priority 3: reputable news and expert practitioner publications.

Discovery only: vendor marketing, community posts, aggregators, and AI summaries.
```

### Require an evidence register

```text
| Claim | Source | Publisher | Date | Evidence used | Strength | Limitation |
```

### Handle contradictions

```text
Do not average conflicting evidence. Describe the disagreement, compare source
quality and recency, identify possible reasons for the difference, and show how
each interpretation affects the decision.
```

### Prevent invented research

```text
If external search or source access is unavailable, do not simulate findings.
Produce a research protocol that identifies the sources, queries, data, and
validation steps needed.
```

---

## 9. Using prompts with documents and data

### Multiple documents

Provide an inventory:

```text
Document A: Current HR process specification, dated {{date}}
Document B: Regional policy exceptions, dated {{date}}
Document C: Integration architecture, dated {{date}}
```

Then request:

```text
Identify agreements, contradictions, gaps, dependencies, and decisions across
the documents. Cite the source document for each finding.
```

### Meeting transcript

Use a prompt that asks for:

- executive summary;
- decisions;
- action items;
- owner;
- due date;
- dependency;
- unresolved question;
- risk or escalation;
- exact supporting excerpt when permitted.

### Code and logs

Include:

- language and version;
- operating system;
- dependency versions;
- exact command;
- expected behavior;
- actual behavior;
- complete error message;
- recent changes;
- constraints on the fix.

Never paste real secrets, access tokens, private keys, passwords, or production credentials.

### Structured data

Ask for:

1. schema inspection;
2. data-quality report;
3. assumptions;
4. analysis methodology;
5. calculations;
6. validation checks;
7. findings;
8. limitations;
9. reproducible transformation steps.

---

## 10. Creating prompt chains

A prompt chain divides a complex workflow into auditable stages.

### Example: product opportunity assessment

1. Customer-problem research
2. Market sizing
3. Competitive landscape
4. Solution concept
5. Product requirements
6. Risk pre-mortem
7. MVP plan
8. Validation experiment
9. Executive decision memo

### Example: technical feature delivery

1. Requirements clarification
2. Architecture options
3. Security and privacy review
4. API and data design
5. Implementation plan
6. Test strategy
7. Deployment plan
8. Documentation
9. Release notes
10. Post-release review

### Chain handoff format

At the end of each stage, request:

```text
Return a handoff block containing:
- confirmed facts;
- decisions made;
- unresolved questions;
- assumptions;
- risks;
- inputs required by the next stage.
```

This prevents later stages from silently changing earlier assumptions.

---

## 11. Organizing a personal collection

### Use Git branches

```bash
git checkout -b personal-library
```

Keep upstream templates unchanged and store adaptations under a separate path:

```text
my-prompts/
├── work/
├── research/
├── development/
└── personal/
```

### Add front matter to personal prompts

```yaml
---
title: Executive HR transformation brief
category: HR Systems
status: validated
owner: Rajesh Kumar
version: 1.2
last_tested: 2026-10-19
models_tested:
  - Microsoft Copilot
sensitivity: internal
---
```

### Version prompts

Document meaningful changes:

```text
v1.0 — Initial template
v1.1 — Added evidence register
v1.2 — Added regional compliance review and decision gates
```

### Do not publish sensitive customizations

Before committing, inspect changes:

```bash
git diff
```

Check staged files:

```bash
git diff --cached
```

Search for likely secrets before publishing:

```bash
rg -n -i "api[_-]?key|secret|token|password|private[_-]?key" .
```

---

## 12. Using the JSON catalog

The catalog supports application development and automation.

### Common uses

- build a searchable website;
- create a desktop prompt manager;
- generate category menus;
- detect placeholders;
- build prompt packs;
- add favorites and collections;
- validate missing files;
- publish a static documentation site.

### Load the catalog with Python

```python
import json
from pathlib import Path

root = Path(".")
catalog = json.loads((root / "prompts.json").read_text(encoding="utf-8"))

assert len(catalog) == 1000

for item in catalog:
    prompt_file = root / item["path"]
    if not prompt_file.exists():
        print("Missing:", prompt_file)
```

### Search titles and categories

```python
query = "research"
results = [
    item for item in catalog
    if query.lower() in item["title"].lower()
    or query.lower() in item["category"].lower()
]

for item in results:
    print(f"{item['category']}: {item['title']}")
```

---

## 13. Creating a new prompt

### Step 1: define the job

Write one sentence:

```text
This prompt helps {{user}} produce {{deliverable}} so that {{decision_or_action}}.
```

### Step 2: identify inputs

Typical input groups:

- context;
- audience;
- decision;
- source material;
- alternatives;
- criteria;
- constraints;
- geography;
- time horizon;
- output format.

### Step 3: define the method

Describe the analytical or production steps. Avoid vague instructions such as `analyze deeply` unless depth is defined through concrete tasks.

### Step 4: define the output contract

Specify headings, fields, length, schema, or decision criteria.

### Step 5: add failure controls

Examples:

```text
Do not invent missing facts.
```

```text
Separate verified facts from assumptions.
```

```text
Flag any recommendation requiring legal or regulatory review.
```

```text
Show calculations and units.
```

### Step 6: add a quality checklist

Make acceptance criteria observable.

### Step 7: test

Test with:

- a normal input;
- incomplete input;
- conflicting evidence;
- unusual edge case;
- requests outside scope.

### Step 8: add to the repository

1. Create the Markdown page.
2. Add it to the category `README.md`.
3. Add it to `CATALOG.md`.
4. Add its metadata to `prompts.json`.
5. Validate links, IDs, placeholders, and spelling.

---

## 14. Privacy, security, and professional review

### Do not submit prohibited data

Examples include:

- passwords, API keys, access tokens, or private keys;
- personal data without a lawful and approved purpose;
- confidential employee records;
- patient or health information in an unapproved system;
- privileged legal material;
- unreleased financial information;
- customer data;
- protected source code;
- classified or export-controlled information.

### Minimize data

Use only the information necessary for the task. Replace names and identifiers with pseudonyms when possible.

### Follow organizational policy

Your organization's approved AI tools, data-classification rules, retention settings, geographic restrictions, and contractual obligations take precedence over this repository.

### Preserve human accountability

Use qualified human review for consequential decisions involving employment, health, finance, law, safety, security, compliance, or public impact.

---

## 15. Troubleshooting

### I cannot find the right prompt

Search by deliverable, decision, method, and industry. If nothing fits, start with a general research or strategy template and specialize the role, inputs, method, and output.

### The model asks too many questions

Provide values for the required placeholders. Tell the model which unknowns should be treated as `Not provided`, and which are important enough to stop the task.

### The output is repetitive

Add:

```text
Remove repeated findings. State each material point once, then reference it from
later sections rather than restating it.
```

### The output is overconfident

Add:

```text
Assign confidence as High, Medium, or Low to each major conclusion. Explain the
evidence, assumptions, and missing information behind the rating.
```

### The output contains fake citations

Require source-grounded operation and independently verify each source. If the tool cannot access sources, request a research plan instead of findings.

### The output is too technical

Specify the audience and a glossary:

```text
Write for {{audience}}. Explain specialized terms on first use and include a
short glossary. Preserve technical accuracy.
```

### The output lacks implementation detail

Add:

```text
For each recommendation provide owner, prerequisites, dependencies, first step,
completion evidence, risk, and decision gate.
```

### The output format varies across runs

Use an exact Markdown outline or JSON schema and instruct the model not to add undeclared fields.

---

## Final checklist

Before using a PromptVault output for real work:

- [ ] All placeholders were replaced.
- [ ] The audience and decision are explicit.
- [ ] Relevant source material was supplied.
- [ ] Facts and citations were verified.
- [ ] Calculations were checked.
- [ ] Assumptions and unknowns are visible.
- [ ] Risks and alternatives were considered.
- [ ] Confidential information was handled appropriately.
- [ ] Qualified review was completed where required.
- [ ] The final output is actionable and matches the requested format.
