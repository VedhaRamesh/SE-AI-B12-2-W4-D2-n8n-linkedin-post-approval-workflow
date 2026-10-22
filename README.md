# LinkedIn Post Approval Workflow (n8n + AI Agents)

An automated content generation and human-in-the-loop approval workflow built in n8n.

## Overview
1. **Trigger:** Form submission captures a content topic.
2. **Drafting (Writer Agent):** AI drafts a tailored LinkedIn post (hook, 120–150 words, CTA, max 3 hashtags).
3. **Refining (Reviewer Agent):** A second AI evaluates the draft on clarity, engagement, and CTA, rewriting the weakest element.
4. **Human-in-the-Loop (Gmail):** Sends the draft to Gmail with interactive Approve / Reject buttons and halts execution until a decision is made.
5. **Persistence (Google Sheets):** On approval, appends the topic, final post, timestamp, and status directly into Google Sheets.

## Architecture
- **Orchestration:** n8n
- **LLMs:** OpenAI (GPT-4.1-mini / GPT-5-mini)
- **Integrations:** n8n Form Trigger, Gmail (Send and Wait for Response), Google Sheets API