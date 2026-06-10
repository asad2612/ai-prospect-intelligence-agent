# Data Structure

This document defines the input, AI output, and storage schemas used by the AI Prospect Intelligence & Lead Scoring Agent.  
The goal is to maintain consistent data flow across all workflow components (n8n -> OpenAI -> Gmail -> Google Sheets).

---

## Input Schema

The workflow begins with a Set Node that defines two required inputs:

```json
{
  "company_name": "string",
  "website_url": "string"
}

Notes
- These values are manually set or injected before execution.
- Both fields are required because the workflow does not include fallback logic.

---

## AI Output Schema

The OpenAI node returns a strictly formatted JSON object containing all analysis, scoring, and outreach fields.

```json
{
  "company_name": "string",
  "company_summary": "string",
  "industry": "string",
  "target_customers": "string",
  "business_challenges": "string",
  "ai_automation_opportunity": "string",
  "lead_score": "number",
  "priority": "string",
  "outreach_angle": "string",
  "linkedin_message": "string",
  "cold_email": "string",
  "discovery_questions": "string or array"
}
```

### Field Descriptions

| Field | Description |
|-------|-------------|
| company_name | Name of the company being analyzed |
| company_summary | High-level overview generated from website text |
| industry | Short industry classification |
| target_customers | ICP or audience inferred from the website |
| business_challenges | Key pain points extracted from content |
| ai_automation_opportunity | Where AI or automation can add value |
| lead_score | AI-generated score (1-100) |
| priority | High / Medium / Low |
| outreach_angle | One-sentence personalized hook |
| linkedin_message | Short LinkedIn outreach message |
| cold_email | Full cold email tailored to the company |
| discovery_questions | 3-5 tailored sales discovery questions |

---

## Google Sheets Schema

Each processed company is appended as a new row in the Lead Intelligence Database.

### Columns
- Company Name
- Website
- Date Added
- Industry
- Target Customers (ICP)
- AI / Automation Opportunity
- Key Pain Points
- Lead Score
- Priority
- Personalized Outreach Angle
- Discovery Call Questions
- Status

### Notes
- Date Added is generated automatically using `$now`.
- All fields are stored as plain text for compatibility.
- The sheet acts as a persistent sales intelligence repository.

---

## Data Flow Summary

Input -> Website Extraction -> HTML Parsing -> AI Analysis -> Data Cleaning -> Gmail Delivery -> Google Sheets Storage

Each stage uses the schemas above to maintain consistency and reliability across the entire automation system.
