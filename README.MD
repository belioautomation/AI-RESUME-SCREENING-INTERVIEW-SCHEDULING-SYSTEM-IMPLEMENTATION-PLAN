# 📄 AI Resume Screening & Interview Scheduling System — n8n Automation

![n8n](https://img.shields.io/badge/n8n-Automation-orange)
![Google Gemini](https://img.shields.io/badge/AI-Google%20Gemini-blue)
![Google Workspace](https://img.shields.io/badge/Platform-Google%20Workspace-green)
![JavaScript](https://img.shields.io/badge/Code-JavaScript-yellow)
![License](https://img.shields.io/badge/license-MIT-green)

An AI-powered recruitment automation workflow built using **n8n**, **Google Gemini AI**, **Google Workspace APIs**, and **Telegram Bot API**.

This system automatically collects job applications, processes resumes, evaluates candidates using artificial intelligence, ranks applicants, schedules interviews for qualified candidates, sends automated emails, and provides recruitment notifications.

**Stack:**  
n8n · Google Forms · Google Sheets · Google Drive · Google Gemini AI · Google Calendar · Gmail · Telegram Bot · JavaScript · AI Automation


---

# 🎯 Project Overview


## Problem

Traditional recruitment processes require significant manual effort from HR teams.

Common challenges include:

- Reviewing hundreds of resumes manually
- Slow candidate evaluation
- Difficulty ranking applicants consistently
- Manual interview scheduling
- Repetitive email communication
- Limited recruitment tracking and analytics


Recruiters often spend valuable time on administrative tasks instead of focusing on candidate engagement.


---

## Solution

This project creates an automated AI recruitment pipeline by:


1. Collecting applications through Google Forms
2. Detecting new applicants automatically
3. Downloading and processing resumes
4. Extracting resume information
5. Evaluating candidates using Google Gemini AI
6. Assigning candidate scores
7. Categorizing applicants automatically
8. Scheduling interviews for qualified candidates
9. Sending email notifications
10. Logging recruitment data
11. Generating recruitment analytics


The workflow acts as an AI recruitment assistant that reduces manual screening effort and improves hiring efficiency.


---

# ✨ Features


## Application Management

✅ Google Forms application collection  
✅ Automated applicant detection  
✅ Resume file processing  
✅ Candidate information extraction  


## Artificial Intelligence

✅ Google Gemini AI resume analysis  
✅ Candidate scoring system  
✅ AI-generated evaluation summary  
✅ Automated candidate ranking  
✅ Qualification classification  


## Recruitment Automation

✅ Interview scheduling  
✅ Google Calendar integration  
✅ Automated Gmail invitations  
✅ Candidate status tracking  


## Data Management

✅ Google Sheets recruitment database  
✅ Candidate history tracking  
✅ Recruitment analytics  
✅ Structured applicant records  


## Notifications

✅ Telegram recruiter alerts  
✅ Candidate email updates  
✅ Automated workflow monitoring  


---

# 🗺️ System Architecture


```mermaid
flowchart TD

A["📝 Google Forms Application"]

--> B["📊 Google Sheets Trigger"]

--> C["📂 Download Resume"]

--> D["📄 Extract PDF Text"]

--> E["🤖 Google Gemini AI"]

--> F["📝 JavaScript JSON Parser"]

--> G{"⭐ Candidate Score"}

G -->|80-100| H["✅ Qualified"]

G -->|50-79| I["🔎 Needs Review"]

G -->|Below 50| J["❌ Reject"]

H --> K["📅 Google Calendar"]

K --> L["📧 Gmail Invitation"]

L --> M["📱 Telegram Notification"]

M --> N["📊 Google Sheets"]

I --> N

J --> N

````

---

# 🏗️ Workflow Implementation

# Workflow 1: AI Resume Screening Pipeline

## Node 1 — Google Forms

### Purpose

Collect job applications from candidates.

Collected Information:

| Field            | Description            |
| ---------------- | ---------------------- |
| Full Name        | Applicant name         |
| Email Address    | Candidate contact      |
| Position Applied | Job role               |
| Resume           | Uploaded PDF           |
| Cover Letter     | Additional information |

Example:

```text
Applicant:

John Smith

Position:

Junior IT Support

Resume:

john_resume.pdf
```

---

# Node 2 — Google Sheets Trigger

### Purpose

Monitor new application submissions.

The trigger detects:

* New applicants
* Updated application records
* Resume links

Captured Data:

| Field          | Description         |
| -------------- | ------------------- |
| Applicant Name | Candidate identity  |
| Email          | Contact information |
| Resume URL     | Resume location     |
| Position       | Applied role        |

---

# Node 3 — Resume Processing

### Purpose

Download and prepare resume files for AI analysis.

Processing Flow:

```text
Resume PDF

↓

Download File

↓

Extract Text

↓

Send to Gemini AI
```

Extracted Information:

* Education
* Technical skills
* Experience
* Certifications
* Achievements

---

# Node 4 — Google Gemini AI

### Purpose

Analyze candidate resumes and generate recruitment insights.

The AI evaluates:

* Educational background
* Technical skills
* Work experience
* Certifications
* Job compatibility
* Overall candidate quality

Example Output:

```json
{
"score":88,

"rank":
"Qualified",

"recommendation":
"Interview",

"summary":
"Strong IT support candidate with relevant technical experience."
}
```

---

# Node 5 — Code Node (JSON Parser)

### Purpose

Convert AI output into structured recruitment data.

Processing:

```text
Gemini AI Response

↓

JavaScript Parsing

↓

Structured Candidate Data
```

Extracted Fields:

| Field          | Description         |
| -------------- | ------------------- |
| Score          | AI evaluation score |
| Rank           | Candidate category  |
| Recommendation | Hiring decision     |
| Summary        | AI evaluation       |

---

# Node 6 — IF Node

### Purpose

Automatically categorize candidates based on AI score.

Decision Logic:

```javascript
if(score >= 80)

Qualified


if(score >= 50)

Needs Review


else

Reject
```

Candidate Categories:

| Score    | Decision     |
| -------- | ------------ |
| 80-100   | Qualified    |
| 50-79    | Needs Review |
| Below 50 | Reject       |

---

# Node 7 — Google Calendar

### Purpose

Schedule interviews automatically for qualified candidates.

Created Information:

| Field           | Description    |
| --------------- | -------------- |
| Interview Date  | Scheduled time |
| Candidate Email | Guest          |
| Meeting Link    | Google Meet    |
| Position        | Applied role   |

---

# Node 8 — Gmail

### Purpose

Send automated recruitment emails.

Email Types:

## Qualified Candidates

Includes:

* Interview invitation
* Schedule details
* Google Meet link

## Rejected Candidates

Includes:

* Application status update
* Professional response

---

# Node 9 — Telegram Notification

### Purpose

Notify recruiters about recruitment activities.

Example:

```text
📌 New Candidate Evaluated


Name:

John Smith


Position:

Junior IT Support


Score:

88/100


Status:

Qualified


Recommendation:

Schedule Interview
```

---

# Node 10 — Google Sheets

### Purpose

Store all recruitment records.

Database Structure:

| Field          | Description    |
| -------------- | -------------- |
| Name           | Candidate name |
| Email          | Contact        |
| Position       | Applied role   |
| Score          | AI score       |
| Recommendation | AI decision    |
| Status         | Hiring stage   |
| Interview Date | Schedule       |
| Processed Date | Timestamp      |

---

# Node 11 — Recruitment Analytics

### Purpose

Generate automated recruitment insights.

Generated Metrics:

* Total applicants
* Qualified candidates
* Average score
* Rejection rate
* Recruitment summary

Reports are delivered through Telegram.

---

# 🔐 Credentials Required

| Service                | Purpose                |
| ---------------------- | ---------------------- |
| Google Forms           | Application collection |
| Google Sheets OAuth2   | Applicant database     |
| Google Drive OAuth2    | Resume access          |
| Google Gemini API      | AI evaluation          |
| Google Calendar OAuth2 | Interview scheduling   |
| Gmail OAuth2           | Email communication    |
| Telegram Bot API       | Notifications          |
| n8n Instance           | Workflow execution     |

---

# ⚙️ Setup Guide

## 1. Create Application Form

Create Google Form fields:

```text
Full Name

Email

Position Applied

Resume Upload

Cover Letter
```

Connect responses to Google Sheets.

---

## 2. Configure Resume Processing

Required:

```text
Google Drive Access

PDF Extraction Method

Resume Processing Workflow
```

Test resume extraction.

---

## 3. Configure Google Gemini AI

Create Gemini API credentials.

Required:

```text
Google AI API Key

Gemini Model Access
```

Test candidate evaluation.

---

## 4. Configure Google Calendar

Enable:

```text
Calendar API

Google Meet Creation

Event Scheduling
```

---

## 5. Configure Gmail

Setup:

```text
Gmail OAuth2

Email Templates

Candidate Notifications
```

---

## 6. Configure Telegram Bot

Steps:

1. Create bot using BotFather
2. Copy bot token
3. Add Telegram credentials
4. Configure recruiter chat ID

---

## 7. Import Workflow

Import:

```text
workflow.json
```

Configure:

* Google Workspace credentials
* Gemini API
* Telegram Bot

Activate workflow.

---

# 🧪 Testing Checklist

| Test Case               | Expected Result           |
| ----------------------- | ------------------------- |
| Submit application form | Applicant recorded        |
| Resume uploaded         | File processed            |
| PDF extraction runs     | Resume text generated     |
| Gemini analyzes resume  | Score created             |
| JSON parser executes    | Structured data generated |
| IF node runs            | Correct category selected |
| Calendar creates event  | Interview scheduled       |
| Gmail sends email       | Candidate notified        |
| Telegram sends alert    | Recruiter notified        |
| Sheets updates          | Candidate stored          |

---

# 📁 Repository Structure

```text
AI-Resume-Screening-and-Interview-Scheduling-System/

│
├── README.md
│
├── workflow.json
│
├── screenshots/
│   │
│   ├── workflow.png
│   ├── application-form.png
│   ├── resume-processing.png
│   ├── ai-analysis.png
│   ├── candidate-evaluation.png
│   ├── google-sheets.png
│   ├── google-calendar.png
│   ├── interview-email.png
│   ├── telegram-notification.png
│   └── workflow-execution.png
│
├── sample-data/
│   │
│   ├── sample-resume.pdf
│   └── sample-ai-output.json
│
└── LICENSE
```

---

# 📸 Screenshots

Recommended screenshots:

* Complete workflow
* Google Form submission
* Resume processing
* Gemini AI analysis
* Candidate evaluation output
* Google Sheets records
* Google Calendar interview
* Gmail invitation
* Telegram notification
* Workflow execution

---

# 🚀 Future Improvements

| Feature                | Implementation                      |
| ---------------------- | ----------------------------------- |
| Duplicate Detection    | Identify repeated applicants        |
| ATS Integration        | Connect recruitment systems         |
| Keyword Matching       | Compare resume with job description |
| AI Interview Questions | Generate role-specific questions    |
| Candidate Dashboard    | Recruitment analytics UI            |
| Database Storage       | PostgreSQL / Supabase               |
| Approval Workflow      | Human recruiter review              |
| Multi-language Support | Global recruitment                  |
| Notion Integration     | Candidate knowledge base            |

---

# 🎓 Skills Applied

## Automation

* n8n Workflow Automation
* Recruitment pipeline automation
* Event-driven workflows

## Artificial Intelligence

* Google Gemini AI
* Resume analysis
* Candidate scoring
* Prompt Engineering

## APIs

* Google Workspace APIs
* Gmail API
* Google Calendar API
* Telegram Bot API

## Programming

* JavaScript
* JSON parsing
* Data transformation
* Conditional logic

## Business Automation

* HR workflow automation
* Recruitment process optimization
* AI-powered decision support

---

# 📚 Learning Objectives

This project demonstrates:

* Building AI-powered HR automation systems
* Integrating Google Workspace with n8n
* Processing documents automatically
* Creating AI evaluation pipelines
* Designing complete business workflow automation

---

# 🙌 Acknowledgements

* n8n
* Google Gemini AI
* Google Workspace APIs
* Telegram Bot API

---

# 👨‍💻 Author

**Belio C. Sinangote**

BS Information Technology Student
Cebu Technological University (CTU)

GitHub:

[https://github.com/belioautomation](https://github.com/belioautomation)

This project is part of my **30-Day n8n Automation Portfolio**, showcasing practical automation solutions using **n8n, AI integrations, APIs, and business workflow automation**.

---

# 📄 License

MIT License

```
```
