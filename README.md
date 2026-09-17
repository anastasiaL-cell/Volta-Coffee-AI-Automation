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
