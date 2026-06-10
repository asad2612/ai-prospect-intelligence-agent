# Prompt Engineering

This workflow uses a single, highly structured prompt to ensure consistent, machine-readable AI outputs. The prompt is designed to extract business insights, generate outreach content, and assign a lead score in one unified step.

---

## Unified Website Intelligence Prompt

The cleaned website text is passed into a single OpenAI prompt that instructs the model to return a strictly formatted JSON object containing:

- company_name  
- company_summary  
- industry  
- target_customers  
- business_challenges  
- ai_automation_opportunity  
- lead_score  
- priority  
- outreach_angle  
- linkedin_message  
- cold_email  
- discovery_questions  

The prompt includes:

- a predefined JSON schema  
- explicit field definitions  
- strict formatting rules  
- instructions to return **JSON only**  
- constraints on lead_score (1-100)  
- constraints on priority (High / Medium / Low)  
- rules for discovery questions (3-5 items)

This ensures deterministic, parseable output.

---

## Prompt Structure

The prompt contains:

### **1. Role Assignment**
The model is instructed to act as a GTM analyst preparing sales intelligence.

### **2. Input Context**
- company name  
- extracted website text  

### **3. JSON Schema**
A full JSON template is included to enforce structure.

### **4. Output Rules**
- no markdown  
- no explanations  
- no additional text  
- valid JSON only  
- concise fields  
- fixed categories  

---

## Why a Single Prompt?

Using one unified prompt ensures:

- consistent formatting  
- fewer parsing errors  
- faster execution  
- tightly coupled insights and outreach  
- predictable structure for Google Sheets  

---

## Prompt Design Principles

- Clear role definition  
- Strict JSON schema  
- Deterministic formatting  
- Minimal ambiguity  
- Explicit constraints  
- Output validation through post-processing  
