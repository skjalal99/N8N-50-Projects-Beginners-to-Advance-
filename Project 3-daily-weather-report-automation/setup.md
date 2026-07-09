Daily Weather Report Automation Setup Guide

Overview

This n8n workflow automatically fetches daily weather information from the OpenWeather API and sends a formatted HTML email report using Gmail.

The workflow demonstrates:

- API integration
- HTTP requests
- Data transformation
- Email automation


Workflow Architecture

Schedule Trigger
        ↓
HTTP Request (OpenWeather API)
        ↓
Set Node (Format Weather Data)
        ↓
Code Node (Generate HTML Email)
        ↓
Gmail (Send Report)


Requirements

Tools:

- n8n (Cloud or Self-Hosted)
- Google Account
- Gmail OAuth2 credentials
- OpenWeather API Key


OpenWeather API Setup

1. Create an account on OpenWeather.

Website:

https://openweathermap.org/


2. Generate an API Key from the API Keys section.

Example:

YOUR_OPENWEATHER_API_KEY


Import Workflow

1. Open n8n dashboard.

2. Go to:

Workflows → Import from File

3. Upload:

daily-weather-report.json


Workflow Nodes

The workflow contains:

Schedule Trigger
        ↓
HTTP Request
        ↓
Set Node
        ↓
Code Node
        ↓
Gmail


Node Configuration


1. Schedule Trigger

Purpose:

Runs the weather automation automatically every day.

Recommended settings:

Trigger:
Every Day

Time:
07:00 AM


2. HTTP Request Node

Purpose:

Fetches weather data from OpenWeather API.


Method:

GET


URL:

https://api.openweathermap.org/data/2.5/weather


Query Parameters:

Parameter: q
Value: Riyadh


Parameter: appid
Value: YOUR_OPENWEATHER_API_KEY


Parameter: units
Value: metric


Example Request:

q=Riyadh

appid=YOUR_OPENWEATHER_API_KEY

units=metric


OpenWeather API Response Example:

{
  "name": "Riyadh",
  "main": {
    "temp": 42,
    "humidity": 20
  },
  "weather": [
    {
      "description": "clear sky"
    }
  ],
  "wind": {
    "speed": 5
  }
}


3. Set Node

Purpose:

Extracts required weather information.

Fields:

- City
- Temperature
- Humidity
- Condition
- Wind Speed


Example Output:

{
  "city": "Riyadh",
  "temperature": 42,
  "humidity": 20,
  "condition": "clear sky",
  "windspeed": 5
}


4. Code Node

Purpose:

Creates the HTML email content.

Generated information:

- Location
- Temperature
- Weather condition
- Humidity
- Wind speed


5. Gmail Node

Purpose:

Sends the final weather report email.


Authentication Setup:

1. Open Gmail Node.

2. Click Create Credential.

3. Connect Google Account.

4. Allow email permissions.


Gmail Settings:

Operation:

Send Email


Email Type:

HTML


Message:

{{$json.message}}


Testing Workflow

1. Test HTTP Request Node.

Expected result:

Weather data received from OpenWeather API.


2. Test Code Node.

Expected result:

HTML weather report generated.


3. Test Gmail Node.

Expected result:

Weather report email delivered successfully.


Activate Workflow

After successful testing:

Enable:

Active Workflow


The automation will now send daily weather reports automatically.


Customization

Change City:

Update the HTTP Request query parameter:

Example:

q=London

q=Tokyo

q=New York


Possible Upgrades


Multiple City Weather Reports

Workflow:

Multiple Weather APIs
        ↓
Combine Data
        ↓
Send Email Report


Weather Alerts

Example:

Temperature > 40°C

↓

Send Warning Email


AI Weather Summary

Workflow:

Weather API
        ↓
AI Model
        ↓
Personalized Weather Advice
        ↓
Email


Technologies Used

- n8n
- OpenWeather API
- Gmail API
- JavaScript
- HTML Email


Skills Demonstrated

- Workflow Automation
- REST API Integration
- JSON Data Processing
- Email Automation
- Low-Code Development


License

MIT License