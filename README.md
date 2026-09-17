# ☕ Volta Coffee – AI-Powered Wholesale Order Automation

An AI-powered n8n workflow that automates the processing of
wholesale coffee orders submitted as unstructured text.

The workflow uses Google Gemini to extract structured order data
and classify incoming requests. Rule-based routing then determines
whether an order can be processed automatically or requires
human review.

## Workflow

Webhook → Data Preparation → AI Agent (Gemini)
→ Structured Output → Classification
→ Airtable / Gmail Draft / Slack

## Tech Stack

n8n | Google Gemini | Airtable | Gmail | Slack |
Webhooks | JSON | Structured Output Parser

## Workflow Architecture

<img width="1602" height="648" alt="test1_2" src="https://github.com/user-attachments/assets/2a89f734-1a63-45a4-a28c-2bf6431da530" />

## Intelligent Order Routing

| Classification | Action |
|---|---|
| `standard` | Store order in Airtable + create Gmail draft |
| `needs_review` | Send Slack notification for manual review |
| `needs_clarification` | Send Slack notification requesting clarification |

## Human-in-the-Loop Design

The AI does not make final business decisions.

Routine orders can be processed automatically, while unusual
or incomplete orders are routed to employees through Slack.

Customer emails are created as Gmail drafts and are not
sent automatically.



