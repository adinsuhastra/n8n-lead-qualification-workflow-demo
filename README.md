# n8n Lead Qualification Workflow Demo

A self-made n8n-style automation portfolio demo for lead intake, qualification, routing, follow-up preparation, and human approval.

This is not client work. It is a fictional demo created to show automation planning and workflow logic.

## Purpose

This project demonstrates how a small lead qualification workflow could be designed in n8n without using real leads, scraping, external APIs, credentials, or paid tools.

The workflow is intentionally safe and local-first. It shows the structure of an automation rather than connecting to live business systems.

## What The Workflow Simulates

1. Manual Trigger / webhook-style lead intake.
2. Lead data validation.
3. Lead scoring logic.
4. Hot / Warm / Cold routing.
5. Follow-up draft generation.
6. Human approval checkpoint before outreach.
7. Output/reporting step.

## n8n Node Mapping

| Workflow Step | n8n-Style Node |
|---|---|
| Start workflow | Manual Trigger |
| Load fictional sample leads | Set |
| Validate and score leads | Code |
| Route Hot leads | IF |
| Prepare follow-up draft | Set |
| Require review before outreach | Human Approval / Wait-style checkpoint |
| Generate output report | Set |

## Files

- `README.md` - project overview
- `workflow_notes.md` - planning and review notes
- `automation_flow.md` - process logic and decision rules
- `n8n_workflow_export.json` - safe demo-only n8n-style workflow export
- `sample_input_leads.json` - fictional input leads
- `sample_output_results.json` - expected demo output
- `implementation_notes.md` - real deployment considerations and safety rules

## Tools Used

- Codex
- ChatGPT
- Local workspace
- GitHub

No n8n installation is required to review this repository.

## Safety Notes

- No real leads or personal data are included.
- No scraping is performed.
- No external APIs are called.
- No credentials are included.
- No automated outreach is sent.
- Follow-up drafts are for review only.
- Human approval is required before any real client-facing action.

## How This Supports Automation Roles

This project is useful as a junior AI automation / AI-agent operator portfolio sample because it shows:

- workflow decomposition
- validation and scoring logic
- routing rules
- human-in-the-loop thinking
- structured output/reporting
- safe automation boundaries
- clear documentation

It should be presented honestly as a design demo, not proof of paid production n8n delivery.
