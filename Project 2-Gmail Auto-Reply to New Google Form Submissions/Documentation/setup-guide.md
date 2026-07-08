# Gmail Auto Reply Automation - Setup Guide

## Google Sheet Setup

Create a Google Sheet:

Name:


Gmail Auto Reply Logs



Create columns:

| S.No | Date | Customer Email | Subject | Reply Status |
|---|---|---|---|---|
| 1 | 08-Jul-2026 | customer@gmail.com | Test | Sent |

---

## n8n Workflow Setup

Workflow:



Gmail Trigger
↓
IF (Check Subject)
↓
Edit Fields
↓
Gmail Send HTML Reply
↓
Google Sheets (Append Row)



---

## Node Configuration

### 1. Gmail Trigger

Purpose:
- Detect new incoming emails.

Settings:



Event:
New Email

Max Emails Per Poll:
1



---

### 2. IF Node

Purpose:
- Filter emails before replying.

Example:



Subject contains:
Test



Production example:



Subject contains:
Support



---

### 3. Edit Fields

Creates:



replySubject
replyMessage
customerEmail



---

### 4. Gmail Send

Settings:



Email Type:
HTML



Sends an automatic response to the customer.

---

### 5. Google Sheets

Action:



Append Row



Mapping:



S.No → Auto Increment
Date → {{$now}}
Customer Email → customer email
Subject → Email subject
Reply Status → Sent



---

## Result

When a new email arrives:



Customer Email
↓
n8n detects email
↓
Automatic HTML reply sent
↓
Email details saved in Google Sheet


