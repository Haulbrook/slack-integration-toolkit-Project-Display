# 💬 Slack Integration Toolkit

A comprehensive Google Apps Script toolkit for integrating Slack with Google Workspace applications.

## 🎯 Overview

This toolkit provides reusable components for building Slack integrations, including webhook messaging, OAuth2 authentication, and interactive bot commands.

## ✨ Features

- **Webhook Messaging:** Send formatted messages to any Slack channel
- **OAuth2 Flow:** Complete authentication implementation
- **Interactive Messages:** Buttons, menus, and modal dialogs
- **Slash Commands:** Custom command handling
- **Error Handling:** Comprehensive logging and recovery

## 🛠️ Components

### 1. Webhook Messenger
```javascript
// Example: Send a notification
function sendSlackNotification(channel, message) {
  const webhook = PropertiesService.getScriptProperties()
    .getProperty('SLACK_WEBHOOK');
  
  const payload = {
    channel: channel,
    text: message,
    unfurl_links: false
  };
  
  UrlFetchApp.fetch(webhook, {
    method: 'post',
    contentType: 'application/json',
    payload: JSON.stringify(payload)
  });
}
```

### 2. OAuth2 Integration
- Token management
- Refresh token handling
- Secure storage in Script Properties

### 3. Interactive Messages
- Button click handlers
- Dropdown menus
- Modal form submissions

## 📊 Use Cases

| Application | Description |
|-------------|-------------|
| Crew Scheduling | Real-time schedule notifications |
| Tool Checkout | Automated checkout confirmations |
| Inventory Alerts | Low stock warnings |
| Status Updates | Daily operation summaries |

## 🔧 Architecture
Google Apps Script
│
├── Webhook Service
│       └── POST to Slack Webhooks
│
├── OAuth2 Service
│       └── Token management
│
└── Event Handler
└── Process Slack events

## 💡 Implementation Notes

- **Rate Limiting:** Built-in throttling for API calls
- **Security:** Tokens stored in Script Properties
- **Logging:** Comprehensive error tracking
- **Testing:** Modular design for easy testing

## 📫 Contact

**Trey Haulbrook**
- Email: Haulbrookai@gmail.com

---

*Toolkit developed from production integrations. Sample code demonstrates patterns used in real applications.*
