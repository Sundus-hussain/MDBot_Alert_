# CareNest – Real-Time Child Safety Tracker

CareNest is an AI-powered child safety app designed to track a child’s location in real-time, detect unsafe areas, and send emergency alerts to parents. Built with AWS, Leaflet JS, and Node.js, CareNest uses live data to ensure children are safe when they're outside.

watch the demo here https://www.youtube.com/shorts/fqpGo-vA10I?feature=share
 https://drive.google.com/file/d/1lycyOfxHrZc3pDfJy6-BUcc0mY0IEdJE/view
---

## Features

- **Live Location Tracking** using Leaflet.js
- **Emergency Panic Button** that sends location alerts to parents
- **Safe Zones Detection** (hospitals, police stations, parks)
- **Well-lit / Dark Streets Detection** (mock data)
- **Crime Incident Alerts** in nearby areas
- **Hosted with GitHub Pages**
- **Serverless Backend** using AWS Lambda & API Gateway

---

## Tech Stack

| Frontend | Backend | Mapping | Cloud |
|----------|---------|---------|-------|
| HTML, CSS, JavaScript | Node.js (AWS Lambda) | Leaflet.js, OpenStreetMap | AWS API Gateway, Lambda |

---


## How It Works

1. Child opens the CareNest app
2. App tracks live location via Leaflet.js
3. If in danger, child taps the panic button
4. Parent receives an alert with exact location
5. App shows nearby safe zones and dangerous areas (via mock data)

---

## Getting Started

# Open index.html in your browser

##for future reference
CareNest AWS Infrastructure Documentation (Backup for Rebuilding)

1. Frontend Setup

Tech Stack: HTML, JavaScript, Leaflet.js

Live Features:

Live Location Tracking using navigator.geolocation and Leaflet.js

Panic Button that sends location data to backend (Lambda via API Gateway)

2. Lambda Function

Function Name: SendEmergencyAlert

Region: eu-north-1

Trigger:

API Gateway: MDBotPanicAPI

Trigger ARN: arn:aws:execute-api:eu-north-1:222634403556:wos927xsmf/*/*/SendEmergencyAlert

Payload Sent:

{
  "childId": "child_001",
  "lat": <latitude>,
  "lng": <longitude>,
  "timestamp": "<ISO timestamp>"
}

Status: Trigger removed to prevent billing.

3. API Gateway (HTTP)

API Name: MDBotPanicAPI

API ID: wos927xsmf

Stage: prod

Route: /SendEmergencyAlert

Method: ANY

Authorization: NONE

Endpoint: https://wos927xsmf.execute-api.eu-north-1.amazonaws.com/prod/SendEmergencyAlert

CORS Enabled: Yes

Status: Default endpoint disabled, auto-deploy disabled.

4. SNS (Optional Notification Service)

Status: Active (can be deleted to avoid charges)

Use Case: Sends SMS/Email alerts to parent/guardian.

Action: Will need to be recreated during rebuild.

5. Hosting

Platform: GitHub Pages

Repository: https://github.com/Sundus-hussain/Mk.Dk_Bros

Frontend File: carenest.html

6. To Rebuild Later

When ready to rebuild:

Recreate Lambda with same logic (emergency alert receiver)

Recreate HTTP API Gateway, map /SendEmergencyAlert route to Lambda

Enable CORS

Optionally reconfigure SNS for alert delivery

Test with panic button from frontend

You can return to this doc anytime to recreate or modify your infrastructure safely.
