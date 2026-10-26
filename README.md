# AI-Powered Meeting Notes Classifier & Task Automation System Using N8N

### Intelligent Meeting-to-Action Workflow Using n8n, Groq AI, Google Sheets & Gmail

## 📌 Project Overview

An AI-powered workflow automation system that transforms unstructured meeting notes into organized, actionable tasks.

Built using **n8n and Groq AI**, the system automatically identifies responsibilities, extracts deadlines, generates structured task records, stores them in Google Sheets, and distributes a professionally formatted meeting summary via email.

The project demonstrates practical applications of **AI agents, natural language processing, workflow orchestration, and business process automation**.

## 🎯 Problem Statement

Manually reviewing meeting notes, identifying assigned responsibilities, maintaining task records, and preparing follow-up emails can be repetitive and time-consuming.

This system automates the meeting-to-task conversion process, reducing manual data entry and improving the organization of meeting action items.

## 🚀 Key Features

- **AI-Powered Task Extraction:** Identifies actionable tasks from unstructured meeting notes.
- **Intelligent Classification:** Extracts task owners, action items, deadlines, and status.
- **Structured JSON Processing:** Converts AI-generated responses into standardized task records.
- **Automatic Task ID Generation:** Generates identifiers such as TASK-001 and TASK-002 for each submission.
- **Google Sheets Integration:** Automatically appends extracted tasks to a centralized task tracker.
- **Automated Email Reporting:** Generates and sends a professionally formatted HTML meeting summary.
- **Missing Information Handling:** Uses default values when task owners or deadlines are unspecified.

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| n8n | Workflow automation and orchestration |
| Groq API | LLM inference |
| GPT-OSS-20B | AI-based meeting analysis and task extraction |
| JavaScript | JSON parsing, task formatting, and HTML generation |
| Google Sheets API | Task record storage |
| Gmail API | Automated email notifications |
| n8n Forms | Meeting notes submission interface |

## ⚙️ Workflow Architecture

**Step 1 — Meeting Notes Submission**

Users enter unstructured meeting notes through an n8n form.

**Step 2 — AI Agent Processing**

A Groq-powered AI agent analyzes the notes and identifies actionable tasks, extracting owners, descriptions, deadlines, and task status.

**Step 3 — Data Transformation**

A JavaScript node parses the AI-generated JSON and converts each task into an individual structured record with a generated task ID.

**Step 4 — Automated Task Management**

The workflow executes two branches:

- Google Sheets: Appends extracted tasks to the task tracker.
- Gmail: Generates an HTML task summary and emails it to the configured recipient.

### Workflow Flow

Meeting Notes Form → AI Agent (Groq LLM) → JavaScript Processing → Google Sheets + HTML Email Generation → Gmail Notification

## 📊 Example

### Input Meeting Notes

"Rahul will complete the dashboard by Friday. Priya needs to prepare the project documentation by Monday. The team should review the final prototype."

### Expected Structured Output

| Task ID | Owner | Action Item | Due Date | Status |
|---|---|---|---|---|
| TASK-001 | Rahul | Complete dashboard | Friday | Pending |
| TASK-002 | Priya | Prepare project documentation | Monday | Pending |
| TASK-003 | Team | Review final prototype | Not Specified | Pending |

*This is an illustrative example. Actual extraction depends on the model's interpretation of the submitted notes.*

## 🔧 Setup and Installation

1. Install or access an n8n instance.
2. Import the provided workflow JSON into n8n.
3. Configure Groq API credentials and the required language model.
4. Connect a Google Sheets account and select the task-tracking spreadsheet.
5. Configure Gmail OAuth credentials and the notification recipient.
6. Test the workflow by submitting sample meeting notes through the n8n form.
7. Activate the workflow after successful testing.

### Google Sheets Columns

- `task_id`
- `owner`
- `action_item`
- `due_date`

## 💡 Use Cases

- Corporate meeting action tracking
- Project management and team coordination
- Startup team meeting automation
- Client meeting follow-up
- Academic project discussions
- Internal business operations

## 📈 Future Enhancements

- Automatic meeting transcription integration
- Task status updates and deadline monitoring
- Personalized email notifications for individual task owners
- Duplicate task detection and persistent task IDs
- Dashboard for task progress and completion analytics
- Integration with Slack, Trello, and Notion

## 📌 Current Scope

The workflow currently **creates new task records** in Google Sheets rather than updating existing records. Task status defaults to Pending and is included in the generated email summary. Task IDs are generated per submission.

## 🏁 Conclusion

This project demonstrates how AI agents and low-code automation can transform unstructured meeting discussions into structured, trackable action items.

By combining LLM-powered information extraction, automated spreadsheet recording, and email reporting, it provides a practical foundation for intelligent meeting management and business workflow automation.
