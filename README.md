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
# AI Prospect Intelligence & Lead Scoring Agent

An AI-powered n8n workflow that automates company research: it extracts website content, generates concise intelligence, ranks opportunities with a lead score, and stores structured prospect data in Google Sheets (optionally sends a sales brief via Gmail).

This repository demonstrates how AI, automation, and lightweight orchestration replace time-consuming manual prospecting tasks for SDRs, BDRs, GTM teams, and founders.

---

## 🚀 Key Features

- Automated website extraction and text cleaning
- AI-generated company summaries, ICP hints, and opportunity analysis
- Rule- and model-based lead scoring (structured signals)
- Personalized outreach (cold email + LinkedIn copy)
- Google Sheets as a centralized lead intelligence store
- Optional automated sales-brief delivery via Gmail
- Reusable n8n workflow that can be imported and adapted

---

## 🧠 Architecture Overview

![Workflow Diagram](assets/workflow-diagram.png)

---

## 🛠️ Technologies Used

- n8n — Workflow automation and orchestration
- OpenAI GPT — Summarization, signal extraction, and message generation
- HTTP / HTML parsing — Fetch and clean website content
- Google Sheets API — Centralized storage for lead intelligence
- Gmail API — Optional brief delivery
- JavaScript (n8n Code Node) — Data cleaning & transformation
- Prompt engineering — Structured LLM outputs for predictable fields

---

## 📂 Repository Structure

```text
├── README.md
├── assets/
│   ├── google-sheets-output.png
│   ├── n8n-workflow.png
│   ├── workflow-diagram.png
│   └── placeholder.txt
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

## 🔍 How It Works (quick)

1. Company input (name + URL) is provided to the workflow.
2. The workflow fetches the website HTML and extracts readable text (removes scripts/styles/boilerplate).
3. Cleaned text is submitted to OpenAI with a structured prompt that returns: summary, industry, ICP cues, challenges, automation opportunities, lead score, priority, outreach angle, cold email, LinkedIn message, and discovery questions.
4. A Code Node normalizes and validates the AI output into a consistent JSON shape.
5. The result is appended to Google Sheets and (optionally) emailed as a prospect brief.

---

## 🧭 Getting started

Prerequisites

- n8n (self-hosted or cloud)
- OpenAI API key (or compatible LLM endpoint)
- Google APIs credentials for Sheets and Gmail (optional)

Quick steps

1. Import the n8n workflow (use the visual export in `assets/n8n-workflow.png` as a guide).
2. Configure credentials: OpenAI, Google Sheets, Gmail (if using email delivery).
3. Tweak the prompt (see `docs/prompt-engineering.md`) and the data mapping in the Code Node.
4. Run the workflow for a test company and inspect the output row in Google Sheets and `sample-output.json`.

Notes

- This repo contains documentation in `docs/` to help customize prompts, data schema, and API request formats.

---

## 📊 Use Cases

- SDRs / BDRs automating top-of-funnel research
- GTM teams enriching CRM records with AI-derived signals
- Founders validating ICP fit quickly for outreach
- Agencies scaling prospect audits and outreach personalization

---

## 🧪 Sample Output

A real example of the final structured JSON output is available in `sample-output.json` (also shown below for reference). The JSON contains normalized fields that are safe to append directly to a Google Sheet or import into a CRM.

---

## ✅ Contributing

If you'd like to contribute improvements (better prompts, scoring rules, or connectors), please open an issue or submit a pull request. Keep changes small and include tests or a sample export when modifying the data shape.

---

## 📬 Contact

For questions or collaboration, open an issue or contact the repository owner.

---

## ⚖️ License

This project is provided under no specific license in the repository. Add a LICENSE file if you want to apply an open-source license.

---

## Next steps / Ideas

- Export the n8n workflow JSON and add it to the repo for one-click import
- Add a small script to convert `sample-output.json` rows into CSV for quick upload to CRMs
- Add end-to-end tests that run the Code Node transformer against sample prompts to ensure stable fields

Completion: README updated for clarity, added getting-started guidance, and linked to `sample-output.json`.
