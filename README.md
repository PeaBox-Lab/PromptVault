# PromptVault

> **1,000 structured AI prompt templates across 75 categories, stored as Markdown and designed for real work.**

PromptVault is an open-source, Markdown-first prompt knowledge base for research, software development, business strategy, HR, finance, marketing, analytics, regulated industries, professional operations, and personal productivity.

Instead of hiding prompts inside an application or database, PromptVault stores every prompt as an individual Markdown page. You can browse the library directly on GitHub, clone it for offline use, adapt templates in any text editor, or consume the machine-readable catalog in your own application.

[Browse the prompt catalog](./CATALOG.md) · [Read the user guide](./docs/USER_GUIDE.md) · [View contribution guidelines](./CONTRIBUTING.md) · [See release notes](./RELEASE_NOTES_v0.5.0.md)

---

## Why PromptVault?

Most prompt collections are long lists of short instructions with limited context. PromptVault is structured around practical execution. Templates may include:

- role and domain context;
- objective and decision to be supported;
- reusable `{{placeholders}}`;
- known facts and assumptions;
- scope, constraints, and exclusions;
- evidence and source requirements;
- analysis steps and decision criteria;
- risks, limitations, and counterarguments;
- required output structure;
- success measures and quality checks;
- follow-up actions and human-review gates.

The result is a library that works as both a ready-to-use collection and a reference for designing better prompts.

---

## Library at a glance

- **1,000** individual prompt templates
- **75** categories
- **1 Markdown page per prompt**
- **Model-agnostic** templates
- **Reusable placeholders** using `{{placeholder_name}}`
- **Central catalog** for human browsing
- **JSON catalog** for applications and automation
- **Research-grade patterns** for evidence, sources, uncertainty, and contradiction handling
- **Professional safeguards** for high-impact and regulated use cases
- **No runtime, API key, account, or database required**

---

## Coverage

PromptVault spans broad functional and industry use cases, including:

### Business and leadership

Business strategy, entrepreneurship, leadership, project management, change management, operations, procurement, negotiation, decision making, communications, and executive reporting.

### Technology and engineering

Software development, cloud and DevOps, APIs and integration, enterprise architecture, cybersecurity, privacy, quality engineering, automation, open source, GitHub, technical research, data science, and analytics.

### Product, customer, and growth

Product management, product discovery, UX research, marketing, sales, customer service, market intelligence, customer discovery, retail, ecommerce, media, and creator workflows.

### People and organization

HR, HR systems, workforce planning, talent management, organization design, career development, education, knowledge management, and learning.

### Finance and research

Finance, investing, banking, insurance, fintech, company intelligence, investment research, academic research, advanced research methods, economics, and social sciences.

### Industry use cases

Healthcare, life sciences, pharma, biotechnology, manufacturing, supply chain, energy, utilities, sustainability, agriculture, food, real estate, construction, automotive, mobility, aerospace, hospitality, travel, telecom, government, and public policy.

Open [CATALOG.md](./CATALOG.md) for the complete category index.

---

## Repository structure

```text
promptvault/
├── prompts/
│   ├── README.md
│   ├── writing/
│   │   ├── README.md
│   │   ├── 01-blog-post-builder.md
│   │   └── ...
│   ├── software-development/
│   ├── deep-research/
│   ├── healthcare-life-sciences/
│   ├── enterprise-architecture/
│   └── ... 70 more categories
├── docs/
│   └── USER_GUIDE.md
├── CATALOG.md
├── prompts.json
├── GITHUB_METADATA.md
├── CONTRIBUTING.md
├── CHANGELOG.md
├── RELEASE_NOTES_v0.5.0.md
├── LICENSE
└── README.md
```

---

## Quick start

### Option 1: Browse on GitHub

1. Open [CATALOG.md](./CATALOG.md).
2. Select a category.
3. Open a prompt page.
4. Copy the text inside the **Prompt** or **Copy-ready prompt** block.
5. Replace every `{{placeholder}}` with your context.
6. Paste the completed prompt into your preferred AI assistant.

### Option 2: Download the repository

1. Select **Code → Download ZIP** on GitHub.
2. Extract the archive.
3. Open `CATALOG.md` or `prompts/README.md` in a Markdown editor.
4. Search the repository using Visual Studio Code, Obsidian, Typora, or another Markdown-capable tool.

### Option 3: Clone with Git

```bash
git clone https://github.com/<your-github-username>/promptvault.git
cd promptvault
```

Replace `<your-github-username>` after publishing the repository.

### Option 4: Search from the command line

Search titles and content with `ripgrep`:

```bash
rg -n "market research|competitive analysis" prompts/
```

Find placeholders used across the library:

```bash
rg -o '\{\{[a-zA-Z0-9_]+\}\}' prompts/ | sort | uniq
```

List prompts in a category:

```bash
find prompts/software-development -name '*.md' -type f | sort
```

---

## How to use a prompt

A template may contain placeholders such as:

```text
Analyze {{company}} in the {{industry}} sector for {{decision}}.
Use a {{time_horizon}} time horizon and evaluate it against
{{decision_criteria}}.
```

Replace the placeholders with specific information:

```text
Analyze Microsoft in the enterprise software and cloud sector for
possible inclusion in a five-year long-term equity portfolio.
Use a five-year time horizon and evaluate it against revenue durability,
free cash flow, competitive position, capital allocation, valuation,
and downside risk.
```

Good inputs are specific enough to constrain the response while leaving the model room to perform the requested analysis.

---

## Recommended prompt workflow

For important tasks, use PromptVault as a workflow rather than a one-shot command.

### 1. Select

Choose the prompt that most closely matches the real decision or deliverable, not merely the broad topic.

### 2. Customize

Replace every placeholder. Add audience, geography, date range, source limitations, constraints, and desired output format.

### 3. Supply evidence

Attach or paste the relevant documents, data, notes, transcripts, code, policies, or research sources. Do not ask the model to infer information you can provide directly.

### 4. Generate

Run the completed prompt in your chosen AI assistant.

### 5. Review

Check factual accuracy, source traceability, calculations, assumptions, omissions, risks, and instruction adherence.

### 6. Refine

Use focused follow-ups such as:

```text
Challenge the three most important assumptions in the analysis.
```

```text
Identify which conclusions would change if {{assumption}} were false.
```

```text
Rewrite the recommendation for {{executive_audience}} in no more than
{{word_limit}} words.
```

### 7. Save responsibly

Keep the customized prompt and validated output with the relevant project files. Remove confidential information before sharing publicly.

---

## Prompt anatomy

A strong prompt commonly contains the following components:

```text
Role or responsibility
+ Context
+ Objective
+ Inputs
+ Constraints
+ Method
+ Evidence rules
+ Output contract
+ Quality criteria
+ Failure controls
```

Example:

```text
You are supporting {{team}} with {{decision}}.

Context:
{{context}}

Use the following sources:
{{sources}}

Evaluate these alternatives:
{{alternatives}}

Apply these criteria and weights:
{{criteria_and_weights}}

Return:
1. Executive summary
2. Evidence table
3. Options comparison
4. Risks and counterarguments
5. Recommendation
6. Open questions

Do not invent missing facts or sources. Mark unsupported claims as
Unverified and explain how they can be validated.
```

---

## Working with `prompts.json`

`prompts.json` provides a machine-readable catalog for search tools, websites, desktop applications, agents, and automation workflows.

A catalog entry follows this general shape:

```json
{
  "id": "category-01",
  "title": "Prompt title",
  "category": "Category name",
  "path": "prompts/category/01-prompt-title.md",
  "placeholders": [
    "context",
    "objective",
    "output_format"
  ]
}
```

### Python example

```python
import json
from pathlib import Path

catalog = json.loads(Path("prompts.json").read_text(encoding="utf-8"))

research_prompts = [
    item for item in catalog
    if "research" in item["category"].lower()
]

for item in research_prompts[:10]:
    print(item["title"], "->", item["path"])
```

### JavaScript example

```javascript
import catalog from "./prompts.json" with { type: "json" };

const securityPrompts = catalog.filter((item) =>
  item.category.toLowerCase().includes("security")
);

console.log(securityPrompts);
```

---

## Research and evidence standards

Research-oriented prompts should be adapted to specify:

- the exact research question;
- decision being supported;
- geography and jurisdiction;
- date range and recency threshold;
- source hierarchy;
- acceptable and excluded sources;
- citation format;
- method of triangulation;
- treatment of contradicting sources;
- confidence or evidence-strength method;
- known limitations and unresolved questions.

Recommended source hierarchy:

1. Laws, regulations, standards, official filings, audited reports, government datasets, original research, contracts, and official product documentation.
2. Peer-reviewed research, respected professional bodies, established research institutions, and reputable analyst material.
3. Established news organizations and expert practitioner publications.
4. Vendor claims, community posts, aggregators, anonymous content, and AI-generated summaries, used primarily for discovery and verified independently.

Never treat a citation-shaped answer as verified evidence. Open the source, confirm that it exists, check the relevant passage, and verify that it supports the claim.

---

## Professional and high-impact use

PromptVault includes templates touching healthcare, finance, legal work, cybersecurity, public policy, engineering, HR, and other consequential domains.

These templates are intended for:

- research planning;
- evidence organization;
- drafting and summarization;
- scenario analysis;
- requirements gathering;
- issue spotting;
- decision support;
- preparing questions for qualified professionals.

They are not substitutes for licensed medical, legal, financial, engineering, safety, or regulatory judgment. Validate material outputs against authoritative sources and route consequential decisions to appropriately qualified reviewers.

Do not place secrets, credentials, personal data, medical records, privileged legal material, controlled information, or confidential company data into an AI service unless your organization has approved the service and the specific data use.

---

## Supported AI assistants

The prompts are intentionally model-agnostic. They can be adapted for tools such as Microsoft Copilot, ChatGPT, Claude, Gemini, locally hosted models, or application-specific agents.

Results will vary by model, enabled tools, context-window limits, access to external sources, and organization-level policies. A prompt requiring current research will only produce source-grounded results when the chosen tool has appropriate search or document access.

---

## Contributing

Contributions are welcome. New prompts should:

- solve a specific, credible use case;
- use descriptive titles and stable IDs;
- use lowercase kebab-case filenames;
- expose reusable inputs as `{{placeholders}}`;
- define the required output;
- separate facts, assumptions, and recommendations where relevant;
- include evidence and uncertainty controls for research tasks;
- include human-review guidance for high-impact use;
- avoid secrets, personal data, fabricated claims, and copyrighted source text;
- be added to the category index, `CATALOG.md`, and `prompts.json`.

See [CONTRIBUTING.md](./CONTRIBUTING.md) for the repository contribution process.

---

## Roadmap

Potential future improvements include:

- richer metadata and task classification;
- beginner, intermediate, and advanced difficulty levels;
- prompt quality scores and automated linting;
- related-prompt links;
- example inputs and validated example outputs;
- prompt chains and multi-step workflows;
- YAML and JSON prompt schemas;
- automated catalog generation;
- a local PromptVault desktop or web interface;
- favorites, collections, version history, and import/export;
- community review and domain-expert validation.

---

## Release

Current release: **v0.5.0 — 1,000 Prompt Library**

See [RELEASE_NOTES_v0.5.0.md](./RELEASE_NOTES_v0.5.0.md) and [CHANGELOG.md](./CHANGELOG.md).

---

## License

PromptVault is released under the MIT License. See [LICENSE](./LICENSE).

---

## Acknowledgment

PromptVault is maintained as part of the PeaBox product and open-source experimentation ecosystem.
