# Data Structure

This document defines the input, output, and storage schemas used by the AI Prospect Intelligence & Lead Scoring Agent.  
The goal is to ensure consistent data flow across all workflow components (n8n -> OpenAI -> Google Sheets -> JSON output).

---

## 📥 Input Schema

The workflow accepts two primary inputs:

```json
{
  "company_name": "string",
  "website_url": "string"
}
```

### Notes
- `company_name` is used for context and personalization.
- `website_url` is used for HTML extraction and analysis.
- If only one is provided, the workflow still runs (fallback logic included).

---

## 🧠 AI Output Schema

The OpenAI node returns a structured JSON object with all insights, analysis, and scoring fields.

```json
{
  "summary": "string",
  "industry": "string",
  "offerings": "string",
  "pain_points": "string",
  "opportunities": "string",
  "icp_fit": "string",
  "lead_score": "number",
  "outreach_message": "string",
  "discovery_questions": "string"
}
```

### Field Descriptions

| Field | Description |
|-------|-------------|
| summary | High-level overview of the company |
| industry | Industry classification inferred from website |
| offerings | Products/services the company provides |
| pain_points | Problems the company likely faces |
| opportunities | Areas where your solution can help |
| icp_fit | How well the company matches your Ideal Customer Profile |
| lead_score | AI-generated score (0-100) with reasoning |
| outreach_message | Personalized outreach message |
| discovery_questions | Tailored questions for a sales conversation |

---

## 📊 Google Sheets Schema

The workflow appends a new row to Google Sheets for every processed company.

### Columns

company  
website  
summary  
industry  
offerings  
pain_points  
opportunities  
icp_fit  
lead_score  
outreach_message  
discovery_questions  
timestamp  

### Notes
- `timestamp` is generated automatically inside n8n.
- All fields are stored as plain text for maximum compatibility.
- This sheet acts as a reusable sales intelligence database.

---

## 🧾 JSON Output Example

A real example of the final structured output is available in:

sample-output.json

This file demonstrates the exact format returned by the workflow and stored in Google Sheets.

---

## 🔄 Data Flow Summary

Input -> Website Extraction -> AI Analysis -> Lead Scoring -> Outreach Generation -> Google Sheets -> JSON Output

Each stage uses the schemas above to maintain consistency and reliability across the entire automation system.
