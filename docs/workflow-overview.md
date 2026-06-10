# Workflow Overview

This document explains the end-to-end flow of the AI Prospect Intelligence & Lead Scoring Agent.

---

## 1. Company Input
The workflow begins with a company name or website URL provided by the user.

---

## 2. Website Extraction
An HTTP Request node fetches the company’s homepage HTML.  
A parsing step extracts readable text, removing scripts, navigation, and noise.

---

## 3. AI Analysis
The cleaned website text is sent to OpenAI GPT with structured prompts to generate:

- Company summary  
- Industry context  
- Key offerings  
- Pain points  
- Opportunities  
- ICP alignment  
- Lead score  

---

## 4. Lead Scoring
The AI model evaluates the company using signals such as:

- Relevance to ICP  
- Website clarity  
- Market positioning  
- Problem-solution fit  
- Growth indicators  

A score from **0-100** is generated.

---

## 5. Outreach Preparation
The workflow generates:

- Personalized outreach message  
- Discovery questions  
- Value proposition tailored to the company  

---

## 6. Database Update
All structured fields are appended to a Google Sheets database.

---

## 7. Output Delivery
The workflow returns:

- AI insights  
- Lead score  
- Outreach message  
- Google Sheets row link  

This makes the workflow reusable for any number of target companies.
