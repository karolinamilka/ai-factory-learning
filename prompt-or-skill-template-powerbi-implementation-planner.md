# Prompt Template: [Task Name]

**Date:** 2026-08-09
**Author:** Karalina Lapko - Data Analyst
**Project:** UBS
**Model:** Claude
**DIAL location:** [DIAL shared link or folder path]
**Committed location:** [Repo path]

---

## Purpose

[One sentence: what this prompt does, for whom, and at which SDLC stage it is used.]

Generate a structured implementation proposal for a new or changed Power BI reporting requirement to help Data Analysts and Data Engineers during the Solution Design stage of the SDLC.

## Variable Placeholders

| Placeholder | Description | Example value |
|---|---|---|
| `{{placeholder_1}}` | [What this variable contains] | [Realistic example] |
| `{{placeholder_2}}` | [What this variable contains] | [Realistic example] |
| `{{placeholder_3}}` | [What this variable contains] | [Realistic example] |

Placeholder |	Description |	Example value
{{business_requirement}} |	Description of the new or changed reporting requirement. |	Separate MA and non-MA deployment tasks based on Assignment Group mapping.
{{current_solution}} |	Summary of the current implementation, if one exists. |	The metric currently calculates the percentage of manual deployment tasks using all GSNOW deployment records.
{{available_data_sources}} |	Available datasets, reference tables, or files relevant to the requirement. |	GSNOW Deployment Tasks, Assignment Group mapping (Excel), Date dimension.
{{report_context}} |	Report, dashboard, or business area affected by the change.	CTL360 – Engineering Productivity section.
{{constraints}}	Technical or business constraints that should be considered. |	Assignment Group mapping is maintained manually in Excel on SharePoint.

## Output Format Instruction

[Tell the model exactly what format to return. Be specific: e.g., "Return a markdown table with columns X, Y, Z. Maximum 10 rows. No preamble."]

Return the response in Markdown using numbered section headings. Include only the requested sections. Use concise, implementation-focused language suitable for technical design review. Present risks, assumptions, and validation checks as bullet lists. Present the implementation plan as a markdown table with the columns: Phase, Activity, and Expected Outcome. Do not generate implementation code unless explicitly requested.

## Prompt Body

[Full prompt text. Use {{placeholder}} syntax for all variable inputs. The prompt must be runnable by a teammate with zero explanation from you.]

You are a Senior Data Analyst / Data Engineer working on enterprise Power BI reporting solutions.

Your task is to analyze a new or changed reporting requirement and prepare a structured implementation proposal that can be reviewed before development begins.

## Context

**Report / Dashboard**
{{report_context}}

**Business Requirement**
{{business_requirement}}

**Current Solution**
{{current_solution}}

**Available Data Sources**
{{available_data_sources}}

**Technical or Business Constraints**
{{constraints}}

---

## Instructions

Before proposing a solution:

- Understand the business objective.
- Identify any missing or ambiguous information.
- Do not make assumptions without stating them explicitly.
- Prefer scalable and maintainable solutions over quick fixes.
- Consider future reuse of the solution where appropriate.
- Highlight any potential impact on the existing data model, reports, or calculations.
- Consider data quality, refresh, governance, and maintainability.
- Do not generate implementation code unless explicitly requested.

---

## Produce the following sections:

1. Business Requirement Summary
2. Clarifying Questions
3. Assumptions
4. Impact Assessment
5. Recommended Data Sources
6. Recommended Data Transformation Approach
7. Data Model Considerations
8. High-Level DAX / Calculation Approach
9. Data Quality Risks and Validation Checks
10. Implementation Risks
11. Recommended Power BI Visualization Considerations
12. Proposed Implementation Plan

Use concise technical language suitable for design review.

Return the response in Markdown.

- Use numbered headings.
- Use bullet lists where appropriate.
- Present the implementation plan as a markdown table with the columns:
  - Phase
  - Activity
  - Expected Outcome

Do not include introductory or concluding text outside of the requested sections.

## Test Run (Author)
**Input values used:**
{{report_context}}
Crew OneView – Engineering Productivity

{{business_requirement}}
Separate WMA and non-WMA deployment tasks based on Assignment Group mapping.

{{current_solution}}
The metric currently calculates the percentage of manual deployment tasks using all GSNOW deployment records.

{{available_data_sources}}
GSNOW Deployment Tasks, Assignment Group mapping (Excel), Date dimension.

{{constraints}}
Assignment Group mapping is maintained manually in an Excel file stored on SharePoint.

**Output quality:** [One sentence — was the output usable as-is, or did you revise?]

The output was usable as a first implementation proposal without requiring prompt changes. Minor project-specific details would still require human review before implementation.

## Peer Review

**Reviewer:** [Name — Role]
**Date reviewed:** YYYY-MM-DD
**Model used by reviewer:** [Model name]

**Reviewer input values used:**
- `{{placeholder_1}}` = [value reviewer used]
- `{{placeholder_2}}` = [value reviewer used]

| Review question | Reviewer answer |
|---|---|
| Could you run the template without asking the author anything? | Yes / No — [one sentence] |
| Was the output format what you expected? | Yes / No — [one sentence] |
| Would you use this template on your own work? | Yes / No — [one sentence] |
| One concrete improvement suggestion | [One sentence] |

---

## Revision History

| Version | Date | Change | Author |
|---|---|---|---|
| 1.0 | YYYY-MM-DD | Initial commit | [Name] |
| 1.1 | YYYY-MM-DD | Post-review update | [Name] |