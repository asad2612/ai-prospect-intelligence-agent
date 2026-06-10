# Logic Breakdown

This document explains the node-by-node logic of the workflow.

---

## 1. Start Node
Receives company name or URL.

---

## 2. HTTP Request Node
Fetches website HTML.

---

## 3. HTML Parsing Node
Removes:
- scripts  
- styles  
- navigation  
- footer  
- boilerplate  

Outputs clean text.

---

## 4. AI Analysis Node
Generates:
- summary  
- insights  
- pain points  
- opportunities  
- ICP fit  
- lead score  

---

## 5. Lead Scoring Node
Extracts the score from the AI output.

---

## 6. Outreach Generation Node
Creates:
- personalized outreach  
- discovery questions  

---

## 7. Google Sheets Node
Appends all fields to the database.

---

## 8. Return Node
Returns structured output to the user.
