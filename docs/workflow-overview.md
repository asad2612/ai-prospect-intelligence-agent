# Workflow Overview

This document explains the end-to-end flow of the AI Prospect Intelligence & Lead Scoring Agent, following the exact execution sequence defined in the n8n workflow.

---

## 1. Company Input  
The workflow begins with a Set Node that defines two key inputs:

- `company_name`  
- `website_url`  

These values drive all downstream analysis.

---

## 2. Website Data Collection  
An HTTP Request node fetches the raw HTML content of the company's homepage using the provided URL.

This step retrieves the full HTML document for processing.

---

## 3. Website Content Extraction  
An HTML Extraction node parses the HTML and extracts readable text from the `<body>` element.

This step removes:

- scripts  
- styles  
- navigation  
- boilerplate  

The result is a clean `page_text` string ready for AI analysis.

---

## 4. AI Prospect Intelligence  
The cleaned website text is sent to the OpenAI node with a structured prompt.  
The model generates a complete JSON object containing:

- company summary  
- industry  
- target customers  
- business challenges  
- AI/automation opportunities  
- lead score  
- priority  
- outreach angle  
- cold email  
- LinkedIn message  
- discovery questions  

This single step handles both **analysis** and **outreach generation**.

---

## 5. Structured Data Processing  
A Code Node cleans and formats the AI output:

- removes markdown  
- parses JSON  
- formats discovery questions into bullet points  
- outputs a consistent, structured object  

This ensures clean data for both email delivery and database storage.

---

## 6. Prospect Brief Delivery  
A Gmail node sends a complete sales intelligence brief to the workflow owner.  
The email includes all AI-generated insights, scoring, and outreach content.

This provides immediate, actionable intelligence.

---

## 7. Lead Intelligence Database Update  
A Google Sheets node appends a new row to the central database, storing:

- company details  
- insights  
- challenges  
- opportunities  
- lead score  
- outreach angle  
- discovery questions  
- status  

This creates a reusable, scalable sales intelligence repository.
