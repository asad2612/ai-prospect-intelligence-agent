# Logic Breakdown

This document explains the node-by-node logic of the AI Prospect Intelligence & Lead Scoring Agent workflow, following the exact execution order defined in the n8n JSON.

---

## 1. Start Prospect Analysis  
Initial trigger that begins the workflow execution.  
No data is provided at this stage.

---

## 2. Company Input (Set Node)  
Defines the input values used throughout the workflow:

- `company_name`  
- `website_url`  

These values are manually set or dynamically injected before analysis begins.

---

## 3. Website Data Collection (HTTP Request)  
Sends a GET request to the company's website URL.  
Returns the full HTML content of the homepage.

Output is passed directly to the extraction node.

---

## 4. Website Content Extraction (HTML Node)  
Parses the raw HTML and extracts readable text using a CSS selector (`body`).  
Removes:

- scripts  
- styles  
- navigation  
- boilerplate  

Outputs a clean `page_text` string for AI analysis.

---

## 5. AI Prospect Intelligence Engine (OpenAI Node)  
Processes the cleaned website text and generates structured JSON containing:

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

Strict JSON formatting rules are enforced in the prompt.

---

## 6. Structured Data Processing (Code Node)  
Cleans and parses the AI output:

- Removes markdown formatting  
- Parses JSON safely  
- Converts discovery questions array into bullet-point text  
- Outputs a final structured object ready for delivery and storage  

This ensures consistent formatting across Gmail and Google Sheets.

---

## 7. Prospect Brief Delivery (Gmail Node)  
Sends a complete sales intelligence brief to the workflow owner's inbox.  
The email includes all AI-generated insights, outreach content, and scoring fields.

Triggered immediately after data processing.

---

## 8. Lead Intelligence Database (Google Sheets Node)  
Appends a new row to the Google Sheets database with:

- company name  
- website  
- date added  
- industry  
- ICP  
- challenges  
- automation opportunities  
- lead score  
- priority  
- outreach angle  
- discovery questions  
- status  

This creates a persistent, reusable sales intelligence repository.
