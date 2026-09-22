# Job Application Tracker (n8n Workflow)

An automated workflow built in [n8n](https://n8n.io) to track job applications — capturing application details as they come in and logging them into a central tracker, so you always know the status of every application without manual data entry.

## Features

- Automatically captures new job application data (from email, form submission, or manual trigger)
- Parses and structures key details: company name, role, date applied, status, source
- Logs entries into a spreadsheet/database for easy tracking
- Optionally sends notifications/reminders on status updates or follow-ups

## Tech Stack

- **n8n** — workflow automation engine
- **[Data store — e.g. Google Sheets / Airtable / Notion]** — application data storage
- **[Trigger — e.g. Gmail, Webhook, Typeform]** — captures new applications

## Workflow Overview

1. **Trigger** — Workflow starts when [describe trigger, e.g. a new email arrives / form is submitted]
2. **Parse/Extract** — Relevant fields (company, role, date, status) are extracted
3. **Store** — Data is written to [Google Sheets / Airtable / database]
4. **Notify (optional)** — A notification is sent via [Telegram / Email / Slack] to confirm logging or flag follow-ups needed

## Setup & Installation

1. Clone this repository:
```bash
   git clone https://github.com/your-username/job-application-tracker-n8n.git
```
2. Import the workflow JSON (`workflow.json`) into your n8n instance:
   - Open n8n → **Workflows** → **Import from File**
   - Select `workflow.json`
3. Configure credentials for the nodes used (e.g. Gmail, Google Sheets, Telegram) in n8n's **Credentials** manager.
4. Update any environment-specific values (sheet ID, webhook URL, etc.) in the relevant nodes.
5. Activate the workflow.

## Environment Variables / Credentials Needed

| Service | Purpose |
|---|---|
| [e.g. Gmail API] | Detect incoming application confirmation emails |
| [e.g. Google Sheets API] | Store tracked applications |
| [e.g. Telegram Bot Token] | Send status notifications |

## Usage

Once activated, the workflow runs automatically whenever [trigger event] occurs. You can view all tracked applications in [Google Sheet / Airtable base link].

## Project Background

Built as part of the TS Academy AI & Automation course, as a hands-on exercise in designing practical automation workflows with n8n.

## License

This project is open source under the [MIT License](LICENSE).
