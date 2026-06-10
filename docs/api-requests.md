# API Requests

This workflow uses HTTP requests for website extraction and Google Sheets integration.

---

## Website Extraction

### Method
GET

### Description
Fetches the HTML content of the company website.

### Steps
1. Send GET request  
2. Extract HTML  
3. Clean text using regex  
4. Pass cleaned text to AI node  

---

## Google Sheets API

### Method
Append Row

### Description
Adds structured AI output to the database.

### Fields
- Sheet ID  
- Range  
- Values array  

---

## Error Handling

- 404 website not found  
- Empty HTML response  
- AI output parsing errors  
- Google Sheets API rate limits  
