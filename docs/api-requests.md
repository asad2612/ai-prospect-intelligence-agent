# API Requests

This workflow uses multiple APIs and processing nodes to extract website data, analyze it using AI, deliver a sales brief via email, and store structured intelligence in Google Sheets.

---

## Website Extraction (HTTP Request)

### Method
GET

### Description
Fetches the raw HTML content of the target company's website.

### Steps
1. Send GET request  
2. Receive HTML response  
3. Pass HTML to the extraction node  

---

## HTML Extraction (n8n HTML Node)

### Method
DOM Parsing (internal n8n operation)

### Description
Extracts readable text from the website HTML using CSS selectors.  
Removes:

- scripts  
- styles  
- navigation  
- boilerplate  

### Output
- `page_text` -> cleaned website content passed to the AI model.

---

## OpenAI API (via n8n OpenAI Node)

### Method
POST (handled internally by n8n)

### Description
Sends cleaned website text to OpenAI for structured analysis.  
The model returns JSON containing:

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

### Notes
- The n8n OpenAI node abstracts the raw REST API call.  
- Strict JSON formatting is enforced through prompt rules.  
- Model used: `gpt-5.4`.

---

## Gmail API (Prospect Brief Delivery)

### Method
Send Email (via Gmail OAuth2)

### Description
Delivers a complete AI-generated sales brief to the workflow owner's inbox.  
The email includes:

- company summary  
- industry  
- ICP  
- challenges  
- automation opportunities  
- lead score  
- priority  
- outreach angle  
- cold email  
- LinkedIn message  
- discovery questions  

### Fields
- Recipient email  
- Subject line  
- Plain text body  
- OAuth2 credentials  

### Notes
- Uses authenticated Gmail API access.  
- Triggered automatically after AI processing and data cleaning.

---

## Google Sheets API

### Method
Append Row

### Description
Adds structured AI output to the Lead Intelligence Database.

### Fields
- Sheet ID  
- Sheet name  
- Column mapping  
- Values array  

---

## Error Handling

- 404 website not found  
- Empty HTML response  
- HTML extraction returning empty body  
- OpenAI JSON formatting errors  
- AI output parsing failures  
- Gmail API authentication failures  
- Email delivery failures  
- Google Sheets API rate limits  
- Rate limits from OpenAI or Gmail  
