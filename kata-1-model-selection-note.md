# Kata 1 — Compare two models and commit the pick

**Time:** ~15 min · **Difficulty:** Beginner · **Audience:** all learners (any role)
**Micro-skill:** Running one recurring task through two models and committing a one-page selection note.

**Tools, cost, and access:**
- Primary: EPAM DIAL (free for EPAM; compares models side by side, epa.ms/chat)
- Alternatives: GitHub Copilot, Cursor, Claude
- If you lack the primary tool: use any two models in your approved toolchain.

---

## Challenge

Teams choose AI models by habit or by whoever set up the tool first — and that choice is never written down. This kata makes the decision explicit: run the same task through two models, compare the outputs, and commit a one-page note that any teammate can read and challenge.

*Anti-pattern this kills — AP-5 (Chat as Delivery): a model comparison lives in a chat window for about 30 seconds before it is forgotten; here it becomes a committed, versioned artefact. It also counters AP-2 (Tool Cargo Cult): you score models against explicit criteria instead of defaulting to whichever tool is installed.*

---

## Input

A real, recurring task from your current project (one concrete sentence), plus the 3–4 evaluation criteria you fix BEFORE running anything. This is kata 1 — no prior-kata artefact to consume.

---

## Goal

Commit `model-selection-note.md` to your team's shared location: a one-page note that names the task, scores two models against pre-fixed criteria, and states which model you picked and why.

---

## Superpower moment

You turned a gut-feel tool choice into a written, challengeable decision your whole team can reuse.

---

## Steps

Work on a **real, recurring task from your current project** — not a hypothetical.

1. **Name the task.** Write one sentence describing a specific, recurring task where you use (or plan to use) an AI model. Be concrete: *"Generate a first-draft test plan from a user story"* is better than *"testing help."*

2. **Define your evaluation criteria.** Before running anything, write down 3–4 criteria you will use to judge the outputs. Choose from what matters for your task — for example: accuracy, format compliance, completeness, tone, context window fit, cost per run, or data classification compliance. Write the criteria down first; do not change them after seeing the outputs.

3. **Run the same prompt on two models.** Use the exact same input prompt on both models. Choose from what is available in your project environment: GitHub Copilot, Cursor, Claude, Claude Code, or another model in your approved toolchain. Capture a representative excerpt of each output (3–10 lines is enough — not the full response).

4. **Score each output.** For each criterion, assign a score of 1–3 (1 = does not meet, 2 = partially meets, 3 = fully meets). One sentence of evidence per cell.

5. **Select one model and write your rationale.** Choose the model with the stronger score on your highest-priority criterion. Write 2–3 sentences: which model you selected, why, and what the losing model's main shortcoming was for this task.

6. **Commit the artefact.** Save the completed template as `model-selection-note.md` and commit it to your team's shared repository or designated shared location. A chat log is not a committed artefact.

> ⏱ **Time check:** Steps 1–2 = 3 min. Step 3 = 5 min. Steps 4–5 = 5 min. Step 6 = 2 min. If you are still running models at minute 10, stop, capture what you have, and write your rationale from the evidence you already hold.

> 🎓 **EPAM DIAL** (epa.ms/chat) gives you a single interface to compare multiple models side by side without switching tools — the natural environment for this kata. If your engagement permits, use it as Model A and Model B's runtime; otherwise use any two models in your approved toolchain.

---

## Tips — failure modes I have actually seen

- Criteria written after seeing the outputs → fix the criteria first, then run; reverse-engineered criteria only confirm the model you already liked.
- Different prompts on each model → paste one identical prompt verbatim into the artefact and run it unchanged on both.
- One output excerpt missing or both excerpts look the same → capture a distinct 3–10 line excerpt from each model before you score.
- Scorecard cells left empty → populate every cell with a 1–3 score and one sentence of evidence.
- Rationale that does not name the loser's shortcoming → state which model won, on which criterion, and exactly what the losing model failed at.
- Saved only in a chat window → commit the file to a shared location; a chat log is not the artefact.

---

## Output Template

Copy this template exactly. Fill in every field. Do not delete any section header.

```markdown
# Model Selection Note

**Date:** 2026-08-03
**Author:** Karalina Lapko - Data Analyst
**Project:** UBS
**Task:** Generate a first implementation proposal for a new or changed Power BI reporting requirement, including data source analysis, transformation approach, validation, and implementation planning.
**Committed location:** TBD [Repo path or shared folder URL]

---

## Evaluation Criteria

| # | Criterion | Why it matters for this task |
|---|-----------|------------------------------|
| 1 | Technical accuracy | The proposed implementation must correctly interpret the requirement and suggest a technically feasible approach for Power BI and the underlying data pipeline. |
| 2 | Completeness of analysis | The proposal should cover all key aspects, including assumptions, data sources, transformations, risks, validation, and implementation steps. |
| 3 | Practical applicability | The proposal should be actionable and usable as a starting point for implementation without significant rework. |
| 4 | Data quality and risk awareness | The proposal should proactively identify potential data quality issues, missing mappings, and implementation risks that could affect report accuracy. |

---

## Prompt Used

You are a Senior Data Analyst/Data Engineer working on an enterprise Power BI reporting solution for operational management.

I need your help preparing the first implementation proposal for a new reporting requirement for the Crew OneView dashboard.

Based on the business requirement below, generate a structured implementation proposal.

Include the following sections:

1. Business requirement summary
2. Questions and assumptions that should be clarified
3. Recommended data sources
4. Recommended data transformation approach
5. Suggested data model considerations
6. Recommended DAX calculation approach (high level, no need for full code)
7. Data quality risks and validation checks
8. Potential implementation risks
9. Recommended Power BI visualization considerations
10. Proposed implementation plan

Business requirement:

The Engineering Productivity section currently contains a metric showing the percentage of manual deployment tasks using data from GSNOW.

The metric currently includes both WMA and non-WMA deployment tasks.

During a discussion with the business SME, I received a mapping of Assignment Groups with a flag indicating whether each Assignment Group belongs to WMA or non-WMA.

The metric needs to be updated so that it reports only WMA deployment tasks while excluding non-WMA tasks.

Assume the Assignment Group mapping is provided in an Excel file maintained by the business.

Focus on the implementation approach rather than writing code.
---

## Output Comparison

### Model A: Sonnet 5 (Claude)
> [Representative excerpt — 3–10 lines. Use blockquote. Do not paste the full response.]
10. Proposed Implementation Plan
Phase	Activities	Owner
1. Discovery & Sign-off	Confirm open questions (Section 2) with SME/business owner; agree on historical restatement approach, unmapped-group handling, and file governance location	Analyst + Business SME
2. Source Preparation	Migrate/confirm Excel mapping to a governed, refreshable location (SharePoint/Gateway-compatible); document expected structure and update process	Analyst / IT support
3. Data Model Build	Build Dim_AssignmentGroup_WMA, establish relationship to GSNOW fact table, apply key standardization in Power Query	Data Engineer/Analyst
4. DAX Update	Update existing manual % measure(s) with WMA filter logic; add supporting QA measure(s) for unmapped-group tracking	Analyst
5. QA & Validation	Run reconciliation checks (Section 7); validate metric against manual spot-check calculation for a sample period	Analyst + Business SME
6. Visualization Update	Update visual labeling, add data quality indicator, implement toggle if required	Analyst
7. UAT & Sign-off	Business review of updated metric, including historical view if restated	Business SME
8. Deployment & Communication	Publish to production workspace; communicate definitional change to report consumers; document mapping maintenance process	Analyst + Business Owner
9. Post-Go-Live Monitoring	Monitor for unmapped Assignment Groups and refresh failures for a defined period (e.g., 2–4 weeks)

### Model B: GPT
> [Representative excerpt — 3–10 lines. Use blockquote. Do not paste the full response.]

10. Proposed Implementation Plan
Phase	Activity
1	Review SME mapping and confirm classification rules
2	Create Assignment Group mapping table
3	Load mapping into the reporting solution
4	Standardize Assignment Group values and join to deployment task data
5	Add Business Area (WMA/Non-WMA) attribute to the data model
6	Update DAX measures or leverage the new dimension to filter existing measures
7	Validate record counts, mapping coverage, and metric outputs against the current report
8	Update Power BI visuals to support WMA and Non-WMA reporting
9	Perform user acceptance testing with the SME
10	Deploy to production and establish an ownership process for maintaining the Assignment Group mapping

## Scorecard

| Criterion | GPT score (1–3) | GPT evidence | Model B score (1–3) | Model B evidence |
|-----------|---------------------|------------------|---------------------|------------------|
| Technical accuracy |2|The proposed solution is technically correct but remains generic, with limited discussion of enterprise reporting considerations such as historical restatement, refresh dependencies, and governance. |3| The proposal demonstrates a strong understanding of enterprise Power BI implementation, covering data modeling, refresh strategy, historical reporting, and governance implications.|
| Completeness of analysis |3| The response covers all requested sections, including assumptions, transformations, risks, DAX approach, and implementation plan.|3|The response covers all requested sections while providing additional implementation considerations, business context, and operational recommendations. |
| Practical applicability |2|The proposal provides a solid starting point but would require additional design decisions before implementation, particularly around governance and long-term maintenance. |3| The proposal can be used almost directly as an implementation planning document, with concrete recommendations for data modeling, governance, QA, and deployment.|
| Data quality and risk awareness |2| Common data quality issues such as missing mappings and duplicates are identified, but operational risks and refresh dependencies are only briefly addressed.|3|The proposal proactively identifies enterprise-level risks including governance, refresh dependencies, historical comparability, ownership, and monitoring, together with concrete validation recommendations |
| **Total** |9/12| |12/12| |

---

## Decision

**Selected model:** Claude Sonnet 5

**Rationale:** [2–3 sentences. State which model won, on which criterion, and what the losing model's main shortcoming was.]

Claude Sonnet 5 was selected because it performed best on the highest-priority criterion—technical accuracy. Beyond providing a technically correct solution, it considered enterprise implementation aspects such as governance, historical data handling, refresh dependencies, and long-term maintainability. GPT produced a well-structured and complete proposal, but its recommendations were more generic and required additional engineering decisions before implementation.

## Active Constraint

**What could change this decision within 30 days:**
[One sentence — e.g., token budget cap, client tool approval, context window requirement changes]

The decision may change if GitHub Copilot with enterprise agents becomes available and demonstrates better integration with our development environment and reporting workflows.

## Revision history

| Version | Date | Change |
|---------|------|--------|
| 1.0 | YYYY-MM-DD | Initial commit |
```

---

## Outcome

You can now turn a model choice into a committed, peer-readable selection note that scores two models against criteria you fixed up front — and the model you pick here is the one you build a reusable template with in Kata 2.
