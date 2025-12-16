# Clases Con Xenia – Lesson Booking Calendar

> An independent online scheduling system for language lessons, featuring interactive booking, automatic reminders, and Google Calendar synchronization.

---

## 🌟 Features

* **📅 Interactive Booking Calendar**

  * Daily, weekly, and monthly views using `react-big-calendar`
  * Custom time slots with blocked dates and dynamic availability
  * Timezone-aware scheduling 

* **👤 User Authentication**

  * Email/password login with Firebase Authentication
  * Google OAuth login
  * Email verification and password reset

* **🔄 Firebase Integration**

  * Firestore database to store lessons, user credits, and bookings
  * Live updates with `onSnapshot`

* **⏰ Automated Lesson Notifications**

  * Personalized email reminders to students and admin via Sendinblue API
  * Tracks notification status in Firestore
  * Fully automated workflow using GitHub Actions

* **📅 Google Calendar Sync**

  * Automatic event creation for booked lessons
  * Event deletion when lessons are canceled
  * Works with dynamic time zones

* **⚙️ Customizable & Extendable**

  * Modular architecture for frontend and backend
  * Easily extendable for new channels, languages, or templates

---

## 🖼 Screenshots

> Since the live site requires login, screenshots demonstrate core functionality.

### Booking Calendar

![Calendar view](screenshots/calendar.png)

---

## 💻 Tech Stack

* **Frontend:** React, react-big-calendar, date-fns, moment-timezone, CSS
* **Backend / Notifications:** Firebase (Auth & Firestore), Node.js, Sendinblue API
* **APIs:** Google Calendar API
* **Deployment:** GitHub Pages (frontend), GitHub Actions (notifications)

---

## 🚀 Live Demo

[https://clases-con-xenia.online](https://clases-con-xenia.online)

---

## ⚡ How It Works

1. **Booking Lessons**

   * Users select time slots on the calendar
   * Slot availability depends on timezone, blocked dates, and overlapping bookings
   * Lessons are saved in Firestore

2. **Authentication & User Flow**

   * Email/password login or Google OAuth
   * Users can see upcoming lessons, balance, and delete their bookings

3. **Notifications**

   * Automated reminders sent to students and admin before lessons
   * Email content customizable via Sendinblue templates
   * Status tracked in Firestore

4. **Google Calendar Sync**

   * Once authorized, lessons are automatically added to Google Calendar
   * Deleting a lesson removes the event from Google Calendar

