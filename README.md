# Automated LinkedIn Job Intelligence Pipeline (n8n + Apify + LLM + Google Sheets)
End-to-end LinkedIn job intelligence pipeline using n8n, Apify, and LLM enrichment with structured storage in Google Sheets.


## Project Summary
This project is an end-to-end job intelligence automation pipeline that collects, enriches, and stores LinkedIn job postings in a structured format for analysis and tracking.
The workflow automates:
•	Job scraping from LinkedIn
•	Data transformation & normalization
•	AI-based job description enrichment
•	Duplicate prevention
•	Structured storage in Google Sheets
Built using n8n, this project demonstrates practical skills in:
•	Workflow automation
•	API integration
•	ETL design
•	LLM integration
•	Data modeling
•	Cloud-based deployment
________________________________________
## Architecture Overview
Trigger
→ Configure Search Parameters
→ Scrape Jobs (Apify Actor)
→ Retrieve Dataset
→ LLM Enrichment (Gemini)
→ JavaScript Data Transformation
→ Append/Update Google Sheet
________________________________________
## Technology Stack
•	Workflow Engine: n8n
•	Web Scraping Platform: Apify
•	Large Language Model: Google Gemini
•	Data Storage: Google Sheets
•	Transformation Layer: JavaScript (Custom Logic)
•	Deployment: Docker (Self-hosted n8n)
________________________________________
### Step-by-Step Workflow
#### 1️. Trigger Node
•	Manual or Cron-based execution
•	Enables scheduled scraping (e.g., daily job monitoring)
________________________________________
#### 2️. Dynamic Parameter Configuration (Edit Node)
Allows flexible job search configuration:
•	Job title
•	Location
•	Experience level
•	Job type
•	Time filter
•	Maximum number of jobs
Example:
{
  "job_title": "Data Analyst",
  "location": "Germany",
  "experience_level": "3",
  "job_type": "F",
  "job_post_time": "r604800",
  "jobs_entries": 25
}
This design allows reusability across different roles and countries.
________________________________________
#### 3️. Apify – Run LinkedIn Job Scraper Actor
The workflow triggers an actor on Apify to:
•	Extract job postings
•	Capture company information
•	Generate a structured dataset
The Actor returns a Dataset ID used in the next step.
________________________________________
#### 4️. Apify – Get Dataset Items
Retrieves structured job data including:
•	Company name
•	Job title
•	Job description
•	Apply URL
•	Publication date
•	Company profile URL
This acts as the data ingestion layer.
________________________________________
#### 5️. LLM Processing (Google Gemini)
Integrated with Google Gemini
Used for:
•	Cleaning job descriptions
•	Extracting key skills
•	Identifying sector/industry
•	Structuring unstructured content
This adds an intelligent enrichment layer to the pipeline.
________________________________________
#### 6️. JavaScript Transformation Node
Custom ETL logic:
•	Field normalization
•	Date formatting
•	Removing duplicates
•	Standardizing column naming
•	Preparing structured output
Final structured schema:
•	company_name
•	email_address
•	company_url
•	company_website
•	sector
•	experience
•	job_title
•	job_apply_url
•	job_description
•	published_date
This demonstrates practical data modeling and transformation skills.
________________________________________
#### 7️. Google Sheets – Append or Update Row
Data is stored in Google Sheets.
Features:
•	Unique key check (job_apply_url)
•	Prevents duplicates
•	Maintains historical tracking
•	Enables job pipeline management
________________________________________
### Business Value
This automation provides:
•	Centralized job tracking
•	Reduced manual effort
•	Structured dataset for market analysis
•	Skill demand insights
•	Application management
It can be extended into:
•	Job market analytics dashboard (Power BI)
•	Skill trend analysis
•	Automated application system
•	Job scoring engine
________________________________________
### Data Engineering Concepts Demonstrated
•	API Orchestration
•	Dataset handling
•	ETL pipeline design
•	Data normalization
•	Duplicate handling
•	LLM-based enrichment
•	Automation scheduling
•	Cloud integration
________________________________________
### Credentials Used
•	Apify API Key
•	Google Sheets OAuth
•	Google Gemini API Key
All managed securely within n8n credential manager.
________________________________________
### Future Enhancements
•	Job scoring based on resume match
•	Automatic cover letter generation
•	Email notification for high-match jobs
•	Power BI dashboard for job trend analysis
•	PostgreSQL data warehouse integration
________________________________________
#### About Me
Data Analyst with:
•	5+ years experience
•	SQL, Power BI, AWS
•	Data modeling & ETL
•	Python & automation
•	Workflow orchestration
This project demonstrates practical automation and data engineering capabilities beyond traditional BI reporting.

