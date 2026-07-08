# Gmail Auto Reply Automation using n8n

## Overview

This project is an automated email response system built using n8n.

The workflow monitors incoming Gmail messages, checks the email subject, sends an automatic HTML reply, and logs every processed email into Google Sheets.

## Workflow

Gmail Trigger
↓
IF Condition (Email Filter)
↓
Edit Fields
↓
Gmail HTML Reply
↓
Google Sheets Logging


## Features

✅ Detect new incoming Gmail messages  
✅ Filter emails based on subject  
✅ Automatically send HTML email replies  
✅ Extract customer information  
✅ Maintain email activity logs  
✅ No manual follow-up required  


## Tools Used

- n8n
- Gmail API
- Google Sheets API


## How It Works

### 1. Gmail Trigger

The workflow listens for new incoming emails.

### 2. IF Node

Checks whether the email matches the required condition.

Example:

Subject contains:

Test or Support


### 3. Edit Fields

Formats the customer information:

- Customer email
- Reply subject
- Reply message


### 4. Gmail Reply

Sends a professional HTML email response automatically.


### 5. Google Sheets Logging

Stores:

- Serial number
- Date
- Customer email
- Subject
- Reply status


## Example Use Cases

- Customer support automation
- Lead response systems
- Sales inquiry handling
- Business email assistants


## Setup

1. Install n8n.
2. Connect Gmail OAuth credentials.
3. Connect Google Sheets credentials.
4. Import workflow JSON.
5. Configure email conditions.
6. Activate workflow.


## Future Improvements

- AI-generated email replies
- CRM integration
- Sentiment analysis
- Email classification
- Slack notifications


## Author

skjalal99