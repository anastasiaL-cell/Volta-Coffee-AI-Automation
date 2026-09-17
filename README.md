# Volta Coffee – AI-Powered Wholesale Order Automation

## Project Overview

AI-powered n8n workflow for automating the processing of wholesale coffee orders submitted as unstructured text.

The workflow uses Google Gemini to extract structured order information and classify incoming requests. Rule-based routing then determines whether an order can follow the standard process or requires human review.

## Tech Stack

**n8n | Google Gemini | Airtable | Gmail | Slack | Webhooks | JSON | Structured Output Parser**

## Workflow

1. Receive incoming orders via Webhook
2. Standardize the input data
3. Analyze the order using an AI Agent with Google Gemini
4. Extract customer, product, quantity, and order information into structured JSON
5. Classify the order
6. Route the order according to predefined business rules

### Order Classification

| Classification | Action |
|---|---|
| `standard` | Store order in Airtable and create Gmail confirmation draft |
| `needs_review` | Send Slack notification for manual review |
| `needs_clarification` | Send Slack notification for clarification |

## Workflow Architecture

<img width="1602" height="648" alt="test1_2" src="https://github.com/user-attachments/assets/34def881-83b7-4946-be6f-dd6883d7f13b" />


## Human-in-the-Loop

The AI Agent analyzes and structures incoming orders but does not make final business decisions. Standard orders are documented automatically, while unusual or incomplete orders are routed to employees for review. Customer emails are created as Gmail drafts rather than sent automatically.

## Testing & Validation

The workflow was validated using three representative order scenarios:

| Test Case | Expected Routing | Result |
|---|---|---|
| Standard order | Airtable + Gmail draft | ✅ Passed |
| Special / large order | Slack – manual review | ✅ Passed |
| Incomplete order | Slack – clarification request | ✅ Passed |

All three test cases were successfully classified and routed according to the defined business rules.

## Limitations

The current prototype does not include ERP/CRM integration or automatic email sending. Ambiguous orders and special cases intentionally require human review.

## Repository Contents

- `workflow/` – exported n8n workflow
- `images/` – workflow architecture
- `docs/` – project documentation and test results

> **Note:** External service credentials and API keys are not included and must be configured separately in n8n.

