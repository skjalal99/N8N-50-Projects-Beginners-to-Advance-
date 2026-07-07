# 🚀 n8n Lead Management Automation System

## Overview

A production-ready lead capture and CRM automation workflow built with n8n.

This automation receives customer inquiries from a website form, validates and processes lead information, prevents duplicate submissions, stores leads in Google Sheets CRM, sends automated confirmation emails, and returns API responses.

---

## Problem

Businesses often collect leads manually through forms and spreadsheets.

This creates problems:

* Manual data entry
* Duplicate records
* Slow customer responses
* Missed sales opportunities

This workflow automates the complete lead management process.

---

## Workflow Architecture

Website Form

↓

n8n Webhook

↓

Lead Data Processing

↓

Email Validation

↓

Duplicate Lead Check

↓

Decision

↓

New Lead → Google Sheets CRM → Gmail Confirmation

Duplicate Lead → Duplicate Response

↓

API Response

---

## Features

✅ Webhook-based lead capture
✅ Data formatting and validation
✅ Duplicate lead detection
✅ Google Sheets CRM storage
✅ Automated customer confirmation email
✅ API JSON responses
✅ Production-style workflow structure

---

## n8n Nodes Used

* Webhook
* Edit Fields / Set
* IF Condition
* Google Sheets
* Merge
* Gmail
* Respond to Webhook

---

## Sample Input

```json
{
  "name": "Ahmed Ali",
  "email": "ahmed@example.com",
  "phone": "+966500000000",
  "company": "Automation Labs",
  "interest": "n8n Automation"
}
```

---

## Success Response

```json
{
  "status": "success",
  "message": "Lead saved successfully"
}
```

---

## Duplicate Response

```json
{
  "status": "duplicate",
  "message": "Lead already exists"
}
```

---

## Setup Instructions

1. Install n8n

2. Import workflow JSON:

```
workflow/lead-management-workflow.json
```

3. Configure credentials:

* Google Sheets
* Gmail

4. Update webhook URL

5. Connect your website form or application

6. Activate workflow

---

## Example Use Cases

* Website contact forms
* SaaS demo requests
* Marketing campaigns
* Consulting inquiries
* Customer onboarding

---

## Future Improvements

* AI lead scoring
* CRM integration
* Slack sales notifications
* PostgreSQL database
* Analytics dashboard
* Automated follow-up sequences

---

## Built With

* n8n
* Google Sheets
* Gmail
* Webhooks
* REST API

---

## Author

Automation Engineering Portfolio Project

Built with n8n 🚀
