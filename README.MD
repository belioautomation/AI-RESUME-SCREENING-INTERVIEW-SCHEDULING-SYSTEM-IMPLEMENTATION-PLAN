# 📄 AI Resume Screening and Interview Scheduling System using n8n

An AI-powered recruitment automation workflow built with **n8n**, **Google Gemini AI**, **Google Workspace**, and **Telegram**. This workflow automatically collects job applications, extracts resume content, evaluates candidates using AI, ranks applicants, schedules interviews for qualified candidates, logs recruitment data, and notifies both recruiters and applicants.

Designed as part of my **30-Day n8n Automation Portfolio**, this project demonstrates end-to-end HR automation, AI-powered candidate screening, workflow orchestration, and business process automation.

---

# 📌 Features

* 📝 Collects job applications through Google Forms
* 📂 Monitors new application responses in Google Sheets
* 📄 Downloads and extracts resume content from PDF files
* 🤖 Uses Google Gemini AI to evaluate candidates
* ⭐ Assigns AI-generated candidate scores
* 🏆 Ranks applicants based on qualifications
* 🔀 Automatically categorizes candidates (Shortlist, Review, Reject)
* 📅 Schedules interviews using Google Calendar
* 📧 Sends interview invitations and rejection emails via Gmail
* 📲 Notifies recruiters through Telegram
* 📊 Logs recruitment data into Google Sheets
* 📈 Generates weekly recruitment analytics

---

# 🛠 Technologies Used

* n8n
* Google Forms
* Google Sheets API
* Google Drive API
* Google Calendar API
* Gmail API
* Google Gemini AI
* Telegram Bot API
* JavaScript

---

# 📂 Workflow Architecture

```text
Google Forms
      │
      ▼
Google Sheets Trigger
      │
      ▼
Download Resume
      │
      ▼
Extract PDF Text
      │
      ▼
Google Gemini AI
      │
      ▼
Code (Parse JSON)
      │
      ▼
IF (Candidate Score)
      │
 ┌────┴─────────────┐
 ▼                  ▼
Qualified      Review / Reject
 │                  │
 ▼                  ▼
Google Calendar     Gmail
 │                  │
 ▼                  ▼
Gmail         Google Sheets
 │
 ▼
Telegram
 │
 ▼
Google Sheets
```

---

# ⚙️ Workflow Process

## 1. Application Intake

Applicants submit their information using Google Forms.

Collected information:

* Full Name
* Email Address
* Position Applied
* Resume (PDF)
* Cover Letter (Optional)

---

## 2. Resume Processing

The workflow automatically:

* Detects a new application
* Downloads the uploaded resume
* Extracts text from the PDF
* Prepares the resume for AI analysis

---

## 3. AI Candidate Evaluation

Google Gemini analyzes each resume based on:

* Education
* Technical Skills
* Work Experience
* Certifications
* Overall Candidate Quality

Example AI Output

```json
{
  "score": 88,
  "rank": "Qualified",
  "recommendation": "Interview",
  "summary": "Strong IT support candidate with relevant technical experience."
}
```

---

## 4. Decision Logic

Candidates are automatically categorized.

| Score    | Decision     |
| -------- | ------------ |
| 80–100   | Qualified    |
| 50–79    | Needs Review |
| Below 50 | Reject       |

---

## 5. Interview Scheduling

Qualified candidates automatically receive:

* Google Calendar interview
* Google Meet link
* Invitation email
* Telegram notification to HR

---

## 6. Candidate Logging

Every applicant is stored in Google Sheets.

Columns include:

* Name
* Email
* Position
* Score
* Recommendation
* Status
* Interview Date
* Processed Date

---

## 7. Weekly Analytics

A scheduled workflow generates recruitment statistics such as:

* Total Applicants
* Qualified Candidates
* Average Candidate Score
* Rejection Rate
* AI-generated recruitment summary

The report is automatically delivered to Telegram.

---

# 📁 Repository Structure

```text
AI-Resume-Screening-and-Interview-Scheduling-System/
│
├── README.md
├── workflow.json
├── screenshots/
│   ├── workflow.png
│   ├── application-form.png
│   ├── ai-analysis.png
│   ├── candidate-log.png
│   ├── interview-email.png
│   ├── telegram-notification.png
│   ├── google-calendar.png
│   └── workflow-execution.png
│
├── sample-data/
│   ├── sample-resume.pdf
│   └── sample-ai-output.json
│
└── LICENSE
```

---

# 📷 Screenshots

Include screenshots of:

* Complete Workflow
* Google Form
* Resume Processing
* AI Analysis
* Candidate Evaluation
* Google Sheets Results
* Google Calendar Event
* Gmail Invitation
* Telegram Notification
* Workflow Execution

---

# 🎯 Skills Demonstrated

* AI Workflow Automation
* Recruitment Process Automation
* Google Workspace Integration
* PDF Document Processing
* Prompt Engineering
* AI Candidate Evaluation
* Conditional Workflow Logic
* Google Calendar Automation
* Email Automation
* Telegram Notifications
* JavaScript Data Processing
* Business Process Automation

---

# 🚀 Future Improvements

* Duplicate applicant detection
* Resume similarity checking
* ATS keyword matching
* AI interview question generation
* Candidate ranking dashboard
* HR analytics dashboard
* Multi-language support
* Notion or Airtable integration
* Database-backed candidate storage
* Recruiter approval workflow

---

# 📄 License

This project is licensed under the MIT License.

---

# 👨‍💻 Author

**Belio C. Sinangote**

BS Information Technology Student
Cebu Technological University (CTU)

**GitHub:** https://github.com/belioautomation

This project is part of my **30-Day n8n Automation Portfolio**, showcasing practical workflow automation using **n8n**, AI integrations, APIs, and business process automation.

