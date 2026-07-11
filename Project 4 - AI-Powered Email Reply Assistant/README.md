
AI-Powered Email Reply Assistant using n8n

Overview

An AI-powered email automation workflow built with n8n that automatically reads incoming emails, analyzes the content using an AI model, generates professional replies, and sends responses through Gmail.

This project demonstrates how AI and workflow automation can reduce repetitive email handling tasks for businesses, support teams, and customer service operations.

Features

* Monitor incoming Gmail messages automatically
* Extract sender, subject, and email content
* Generate intelligent replies using AI
* Use OpenRouter AI models
* Automatically send email responses
* Reduce manual email processing
* Build scalable AI communication workflows

Workflow Architecture

Incoming Email

↓

Gmail Trigger

↓

Format Email Data

↓

Basic LLM Chain

↓

OpenRouter Chat Model

↓

Generate AI Reply

↓

Gmail Send Reply

Nodes Used

1. Gmail Trigger

Purpose:

Monitors incoming Gmail messages and starts the automation workflow.

Configuration:

* Trigger: New Email Received
* Filter: Inbox
* Status: Unread Emails

2. Format Email Data (Set Node)

Purpose:

Cleans and structures incoming email data before sending it to AI.

Extracted Fields:

* sender
* subject
* email_body

Example Input:

{
"sender": "[customer@example.com](mailto:customer@example.com)",
"subject": "Pricing Question",
"email_body": "I want to know your subscription plans."
}

3. Basic LLM Chain

Purpose:

Creates the AI prompt and sends email information to the language model.

Prompt Logic:

You are a professional customer support email assistant.

Create a professional reply.

Rules:

* Be polite
* Be concise
* Answer the customer question
* Ask for clarification if needed
* Do not mention AI

4. OpenRouter Chat Model

Purpose:

Provides AI intelligence for generating email replies.

Model Used:

google/gemma-4-26b-a4b-it:free

Parameters:

Temperature:
0.3

Max Tokens:
200

Top P:
1

5. Gmail Send Message

Purpose:

Sends the AI-generated reply back to the customer.

Email Type:

Text

Example Input Email

Subject:

Support Request

Message:

Hello,

I need help with my account.

Example AI Output

Hello,

Thank you for contacting us.

We would be happy to assist you with your account issue.

Could you please provide more details about the problem you are experiencing?

Best regards,

Customer Support Team

Requirements

Software:

* n8n
* Gmail Account
* OpenRouter API Key

API Integrations

Gmail API

Used for:

* Receiving emails
* Sending automated replies

OpenRouter API

Used for:

* AI text generation
* Email response creation

Installation

Step 1: Import Workflow

1. Open n8n
2. Go to Workflows
3. Select Import
4. Upload the workflow JSON file

Step 2: Configure Credentials

Add Gmail OAuth2 credentials.

Required for:

* Reading incoming emails
* Sending replies

Add OpenRouter API credentials.

Required for:

* AI response generation

Step 3: Activate Workflow

Enable the workflow.

New emails will automatically trigger AI-generated replies.

Project Structure

ai-powered-email-reply-assistant-n8n/

workflow/

* ai-email-reply-assistant.json

screenshots/

* workflow.png
* execution.png

examples/

* sample-email.json

README.md

LICENSE

Future Improvements

AI Email Classification

Automatically classify emails:

* Support
* Sales
* Spam
* Urgent

Human Approval System

Add approval before sending:

AI Draft

↓

Human Approval

↓

Send Email

CRM Integration

Connect with:

* HubSpot
* Salesforce
* Airtable

Conversation Memory

Store previous customer interactions for better AI responses.

Skills Demonstrated

* n8n Workflow Automation
* AI Workflow Engineering
* OpenRouter API Integration
* Gmail API Integration
* Prompt Engineering
* No-Code / Low-Code Automation
* Business Process Automation

Use Cases

* Customer Support Automation
* Sales Email Assistant
* Lead Response Automation
* Business Inbox Management
* Internal Email Automation

License

MIT License

Author

Your Name


