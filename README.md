# Smart_Scheduler_Agent

An **Automated Scheduling and CRM Workflow** powered by Conversational AI, integrated with **Google Calendar**, **Airtable**, **Gmail**, and orchestrated using **n8n**.

---

## 🧠 Overview

Smart Scheduler Agent is a no-code automation workflow that enables conversational booking and end-to-end scheduling via API integrations. It intelligently:

- Parses natural language inputs
- Checks calendar availability
- Books appointments
- Sends email confirmations
- Logs customer data in a CRM (Airtable)

> **Note**: All credentials in this workflow are dummy placeholders. Replace with your actual credentials before using.

---

## ✨ Features

- **Conversational Booking**  
  Understands natural language to extract booking details like name, date, time, and purpose.

- **Calendar Availability Checking**  
  Ensures requested time slots are free before confirming.

- **Automated Responses**  
  Confirms or denies bookings automatically based on availability.

- **Google Calendar Integration**  
  Creates events automatically with user and booking details.

- **Gmail Notifications**  
  Sends confirmation emails to users and booking details to admins.

- **Airtable CRM Logging**  
  Logs user info (name, date, time, purpose, phone) for CRM tracking.

- **Security Built-in**  
  No sensitive credentials are stored in the template. Add your own securely in n8n.

---

## 🔄 Workflow Breakdown

### 🛎️ Trigger
- **Webhook** – Accepts incoming booking requests (e.g., from a chatbot, frontend form, or voice assistant).

### 🧹 Pre-processing
- Aggregates and processes the **10 most recent user messages** to maintain context.

### 🤖 AI Agent
- Uses OpenAI to **extract booking intent**: name, date, time, phone number, and purpose.

### 📅 Availability Check
- Uses Google Calendar API to check if the time slot is free.

### ✅ Booking Decision

- **If Available**:
  - Sends a friendly confirmation
  - Creates a calendar event
  - Sends email via Gmail
  - Logs booking in Airtable

- **If Unavailable**:
  - Sends an apology message
  - Prompts for an alternate time

### 📧 Notification
- **Gmail** – Sends confirmation to the user.
- **Airtable** – Updates the CRM with the booking details.

---

## 🛠️ Installation & Setup

### 🔧 Prerequisites
Ensure you have:
- An **n8n instance** (self-hosted or cloud)
- API credentials for:
  - OpenAI (for language understanding)
  - Google Calendar
  - Gmail
  - Airtable

### 📥 Import Workflow
1. Clone or download this repository.
2. Import `Smart_scheduler_Agent.json` into your n8n instance.
3. Replace all **dummy credentials** with your actual values via **n8n Credentials Manager**.

### 🔐 Required Credentials

| Service         | Fields Required              | Where to Get It                              |
|-----------------|------------------------------|-----------------------------------------------|
| OpenAI          | Model, API Key               | [platform.openai.com](https://platform.openai.com) |
| Google Calendar | OAuth2 API                   | [Google Cloud Console](https://console.cloud.google.com) |
| Gmail           | OAuth2 API                   | [Google Cloud Console](https://console.cloud.google.com) |
| Airtable        | API Key, Base/Table Info     | [airtable.com/api](https://airtable.com/api) |

---

## 🚀 Usage

1. Deploy and activate the workflow in n8n.
2. Configure all credentials.
3. Send booking messages to the webhook endpoint.
4. The system will:
   - Parse booking details
   - Check availability
   - Confirm/deny booking
   - Send email
   - Update CRM

---

## 🧩 Customization

- Modify the **prompt template** for AI extraction as needed.
- Edit **email templates** for personalized communication.
- Customize **Airtable fields** to match your CRM schema.
- Add more integrations (e.g., SMS, Slack) as needed.

---

## 🛠️ Troubleshooting

| Issue | Possible Cause | Solution |
|-------|----------------|----------|
| API errors | Invalid credentials | Ensure all keys/tokens are correctly set |
| Calendar check fails | Invalid calendar ID | Verify access and ID in Google Calendar |
| Emails not sent | Gmail scope/config issues | Check OAuth2 config and permission scopes |
| Airtable not updating | Mismatched table/fields | Match base/table/field names exactly |

---

## 🔒 Security

- **Never** commit real API credentials to public repositories.
- Use **environment variables** or **n8n’s encrypted credential storage** in production.

---

## 📜 License

This workflow is provided **as-is** for educational and demonstration purposes. Use it responsibly and in accordance with your organization's data and privacy policies.

---

## 🤝 Contributing

1. Fork this repo
2. Modify as per your needs
3. Submit PRs for:
   - Features
   - Bug fixes
   - Documentation improvements

> Make sure to **only use sanitized or mock data** when contributing publicly.

---

## 🧩 Support

For questions or enhancements, open an issue or contact the maintainer directly.

---

## 📝 Note

All API credentials in the sample `.json` are **placeholders**. Replace them with your actual credentials before deploying.

---
