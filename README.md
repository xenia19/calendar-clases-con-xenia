# 📅 Tutor Booking SaaS (Clases con Xenia)

![Status](https://img.shields.io/badge/Status-Live_Product-success?style=for-the-badge)
![Tech](https://img.shields.io/badge/React-Frontend-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Backend](https://img.shields.io/badge/Node.js-Automations-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)

> An independent online scheduling system for language lessons, featuring interactive booking, automatic reminders, and Google Calendar synchronization.

### 🎥 Live Demo (Booking & Canceling Flow)

https://github.com/user-attachments/assets/239aa53b-086b-4dcd-99bd-c1e90c4a766d

## 🔗 Links
* **Live App:** [clases-con-xenia.com](https://clases-con-xenia.com) *(Requires student login)*

## ✨ Key Features & Business Logic

| Feature | Description |
| :--- | :--- |
| 💳 **Credit-Based Booking** | **(Core Feature)** Students can purchase lesson packages in advance. The system automatically tracks their balance and deducts credits upon booking. Credits are refunded if a lesson is canceled in time. |
| 📅 **Interactive Calendar** | Daily, weekly, and monthly views using `react-big-calendar`. Custom time slots with blocked dates and dynamic timezone-aware availability. |
| 🔄 **Google Calendar Sync** | Automatic event creation for booked lessons and automatic deletion when lessons are canceled. |
| ⏰ **Automated Notifications** | Node.js cron jobs send personalized email reminders (via Sendinblue API) to students and the admin 24h before lessons. |
| 🔐 **User Authentication** | Email/password login and Google OAuth via Firebase Authentication. |
| ⚡ **Real-time Updates** | Live database synchronization with Firestore `onSnapshot`. |

## 🛠️ Tech Stack

* **Frontend:** React, `react-big-calendar`, `date-fns`, `moment-timezone`, CSS Modules
* **Backend & Database:** Firebase (Auth & Firestore)
* **Automations:** Node.js, GitHub Actions (for cron jobs)
* **Third-Party APIs:** Google Calendar API, Sendinblue (Brevo) API

## ⚙️ How It Works (User Flow)

1. **Authentication:** Users log in via email or Google OAuth.
2. **Balance Check:** The system reads the user's pre-paid lesson balance from Firestore.
3. **Booking:** * Users select available time slots.
   * Availability is calculated dynamically based on the tutor's timezone and overlapping existing bookings.
   * Upon confirmation, a credit is deducted from the user's balance.
4. **Synchronization:** The lesson is saved in Firestore, which triggers an update to the Google Calendar API.
5. **Reminders:** A GitHub Actions workflow runs a Node.js script daily to find upcoming lessons and dispatch email reminders via Sendinblue.

## 📦 Architecture Note
This project uses a modular architecture separating the React frontend from the Node.js automation scripts, making it easily extendable for new notification channels (e.g., WhatsApp/Telegram) or multi-language email templates.

---
*© 2026 Xenia Galaktionova. All rights reserved.*
