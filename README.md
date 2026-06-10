# AI Prospect Intelligence & Lead Scoring Agent

An AI-powered workflow that automates company research, extracts website insights, identifies business challenges, generates personalized outreach, scores leads, and stores structured intelligence in a centralized database.

This project demonstrates how AI, automation, and workflow orchestration can replace manual prospecting tasks typically performed by sales, GTM, and business development teams.

---

## 🚀 Key Features

- Automated company website extraction  
- AI-generated summaries, insights, and opportunity analysis  
- Lead scoring using structured qualification signals  
- Personalized outreach message generation  
- Google Sheets database integration  
- Automated email delivery of sales briefs  
- Reusable workflow for multiple target accounts  

---

## 🧠 Architecture Overview

![Workflow Diagram](assets/workflow-diagram.png)

---

## 🛠️ Technologies Used

- **n8n** – Workflow automation  
- **OpenAI GPT** – Insight generation, summarization, scoring  
- **HTTP Requests** – Website extraction  
- **HTML Parsing** – Clean text extraction  
- **Google Sheets API** – Data storage  
- **Gmail API** – Automated email delivery  
- **JavaScript (Code Node)** – Data cleaning & transformation  
- **Prompt Engineering** – Structured AI outputs  

---

## 📂 Repository Structure

```text
├── README.md
├── assets/
│   └── workflow-diagram.png
├── docs/
│   ├── workflow-overview.md
│   ├── logic-breakdown.md
│   ├── prompt-engineering.md
│   ├── data-structure.md
│   └── api-requests.md
├── sample-output.json
└── placeholder.txt
```

---

## 🔍 How It Works

1. **Company Input**  
   The workflow begins with a Set Node defining the company name and website URL.

2. **Website Extraction**  
   An HTTP Request node fetches the company's homepage HTML.

3. **HTML Parsing**  
   The HTML node extracts readable text from the `<body>` element, removing scripts, styles, and boilerplate.

4. **AI Prospect Intelligence**  
   The cleaned text is sent to OpenAI with a structured prompt that generates:  
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

5. **Structured Data Processing**  
   A Code Node cleans and formats the AI output into a consistent JSON object.

6. **Prospect Brief Delivery**  
   A Gmail node sends a complete sales intelligence brief to the workflow owner.

7. **Lead Intelligence Database Update**  
   A Google Sheets node appends all structured fields to a centralized database.

---

## 📊 Use Cases

- SDRs and BDRs automating top-of-funnel research  
- GTM teams enriching CRM data with AI insights  
- Founders validating ICP fit for outbound campaigns  
- Agencies performing automated prospect audits  
- Anyone replacing manual website research with AI  

---

## 🧪 Sample Output

A real example of the final structured JSON output is available in:
