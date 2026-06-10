# Prompt Engineering

This workflow uses structured prompts to ensure consistent, high-quality AI outputs.

---

## Website Analysis Prompt

The website text is passed into a prompt that requests:

- Company summary  
- Industry  
- Key offerings  
- Pain points  
- Opportunities  
- ICP fit  
- Lead score justification  

The output is formatted as JSON for easy parsing.

---

## Outreach Prompt

A second prompt generates:

- Personalized outreach message  
- Discovery questions  
- Value proposition  
- CTA  

The tone is professional, concise, and tailored to the company’s context.

---

## Lead Scoring Prompt

A dedicated prompt evaluates:

- Relevance  
- Market maturity  
- Problem awareness  
- Fit with ICP  
- Growth potential  

The model returns a score from 0-100 with reasoning.

---

## Prompt Design Principles

- Clear role assignment  
- Structured JSON outputs  
- Explicit field definitions  
- Deterministic formatting  
- Minimal ambiguity  
