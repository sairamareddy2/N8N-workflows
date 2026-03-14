# 📚 Student Assignment Reminder Automation (n8n)

![n8n](https://img.shields.io/badge/Automation-n8n-orange)
![Google Sheets](https://img.shields.io/badge/Data-Google%20Sheets-green)
![Gmail](https://img.shields.io/badge/Notification-Gmail-red)
![Status](https://img.shields.io/badge/Project-Completed-blue)

## 🚀 Project Overview

This project is an **automated reminder system built with n8n** that helps instructors or teams automatically notify students about upcoming assignment deadlines.

The workflow reads assignment data from **Google Sheets**, checks if the assignment is due soon, sends a **personalized reminder email via Gmail**, and updates the sheet to prevent duplicate notifications.

This eliminates manual follow-ups and ensures students never miss deadlines.

---

## ⚙️ Workflow Architecture

```
Schedule Trigger
      ↓
Get Rows from Google Sheets
      ↓
IF Node (Check Due Date)
      ↓
Send Email via Gmail
      ↓
Update Row in Google Sheets
```

---

## 🛠 Technologies Used

* **n8n** – Workflow automation platform
* **Google Sheets API** – Data storage
* **Gmail API** – Sending reminder emails
* **JavaScript Expressions** – Dynamic email content

---

## 📊 Google Sheet Structure

Create a Google Sheet with the following columns:

| Name | Assignment  | Email                                         | DueDate    | ReminderSent |
| ---- | ----------- | --------------------------------------------- | ---------- | ------------ |
| Ram  | AI Project  | [student@email.com](mailto:student@email.com) | 2026-03-14 | No           |
| Sai  | OS Homework | [student@email.com](mailto:student@email.com) | 2026-03-15 | No           |

### Column Description

| Column           | Purpose                                  |
| ---------------- | ---------------------------------------- |
| **Name**         | Student name                             |
| **Assignment**   | Assignment title                         |
| **Email**        | Student email address                    |
| **DueDate**      | Assignment deadline (YYYY-MM-DD format)  |
| **ReminderSent** | Tracks whether reminder was already sent |

---

## 📧 Email Template Used

```
Subject: Assignment Reminder

Hello {{Name}},

This is a reminder that your assignment:

{{Assignment}}

is due on {{DueDate}}.

Please submit it before the deadline.

Best Regards,
Course Instructor
```

---

## ⚡ How the Workflow Works

### 1️⃣ Schedule Trigger

Runs the workflow automatically (for example once per day).

### 2️⃣ Get Rows from Google Sheets

Reads assignment data from the sheet.

### 3️⃣ IF Condition

Checks if the assignment deadline matches the reminder condition.

Example:

```
DueDate = tomorrow
```

### 4️⃣ Send Gmail Reminder

Sends an automated email reminder to the student.

### 5️⃣ Update Row in Sheet

Updates:

```
ReminderSent = Yes
```

This prevents sending the same reminder again.

---

## 📂 Project Structure

```
student-assignment-reminder/
│
├── workflow.json
├── README.md
└── screenshots/
      └── workflow.png
```

---

## 🖼 Example Workflow

```
Schedule Trigger → Google Sheets → IF → Gmail → Update Row
```

---

## 🔧 Setup Instructions

### 1️⃣ Install n8n

Using npm:

```
npm install n8n -g
```

Start n8n:

```
n8n start
```

---

### 2️⃣ Connect Google Sheets

1. Create Google Cloud API credentials
2. Enable **Google Sheets API**
3. Add credentials inside n8n
4. Select your spreadsheet

---

### 3️⃣ Connect Gmail

1. Add Gmail credentials in n8n
2. Authorize your Google account
3. Grant email sending permission

---

### 4️⃣ Configure the Workflow

Update these values:

* Spreadsheet name
* Sheet name
* Email template
* Schedule trigger

---

## 🧪 Example Scenario

| Name | Assignment | Email                                         | DueDate    | ReminderSent |
| ---- | ---------- | --------------------------------------------- | ---------- | ------------ |
| Ram  | AI Project | [student@email.com](mailto:student@email.com) | 2026-03-14 | No           |

If today's date is **2026-03-13**, the workflow:

✔ Detects assignment due tomorrow
✔ Sends reminder email
✔ Updates `ReminderSent = Yes`

---

## 📈 Possible Improvements

* 📱 WhatsApp or Telegram reminders
* 📊 Dashboard for assignment tracking
* 🤖 AI-generated personalized reminders
* 📅 Multiple reminder stages (3 days, 1 day, due date)
* 🔔 Slack notifications for instructors

---

## 💡 Learning Outcomes

Through this project you learn:

* Workflow automation with **n8n**
* API integrations (Google Sheets & Gmail)
* Event-driven automation
* No-code / low-code development
* Practical automation for productivity

---

## 👨‍💻 Author

**Automation Project built using n8n**

GitHub: https://github.com/sairamareddy2
