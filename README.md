````markdown
# Bashir Clinic Management System

Live Application: https://clinic-management-system-main3.vercel.app/

A modern clinic management system built with React, Firebase, and Tailwind CSS for doctors, receptionists, and administrators.

---

## Overview

This project helps streamline clinic operations by combining:

- patient appointments
- token queue management
- doctor prescriptions
- receptionist billing and invoice handling
- secure authentication with Firebase

---

## Key Features

- Role-based access for doctors and receptionists
- Email verification and protected routes
- Real-time appointment and token updates
- Prescription and billing workflows
- Responsive dashboard UI for desktop and mobile

---

## Screenshots


### Login Page
![Login Page](preview/login.png)

### Doctor Dashboard
![Doctor Dashboard](preview/doctor_dashboard.png)

### Receptionist Dashboard
![Receptionist Dashboard](preview/receptionist_dashboard.png)

---

## Prerequisites

- Node.js 16+
- npm or yarn
- Firebase project

---

## Firebase Setup

1. Create or select a Firebase project in the Firebase Console.
2. Enable Authentication with Email/Password.
3. Enable Firestore Database in test mode.
4. Copy your Firebase config values for the environment file.

---

## Environment Configuration

Create a `.env` file in the project root:

```bash
cp env.example.txt .env
```

Then update it with your Firebase values:

```env
VITE_FIREBASE_API_KEY=your_api_key
VITE_FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
VITE_FIREBASE_PROJECT_ID=your_project_id
VITE_FIREBASE_STORAGE_BUCKET=your_project.appspot.com
VITE_FIREBASE_MESSAGING_SENDER_ID=your_sender_id
VITE_FIREBASE_APP_ID=your_app_id
```

---

## Firebase Security Rules

Use the following Firestore rules for secure access control:

```javascript
rules_version = '2';

service cloud.firestore {
  match /databases/{database}/documents {
    match /staffData/{userId} {
      allow read, write: if request.auth != null && request.auth.uid == userId;
      allow create: if request.auth != null && request.auth.uid == userId;
    }

    match /appointments/{document} {
      allow read: if request.auth != null;
      allow write: if request.auth != null &&
        (resource == null || resource.data.createdBy == request.auth.uid);
    }

    match /prescriptions/{document} {
      allow read: if request.auth != null;
      allow write: if request.auth != null &&
        (resource == null || resource.data.doctorId == request.auth.uid);
    }

    match /medicines/{document} {
      allow read: if request.auth != null;
      allow write: if request.auth != null;
    }

    match /invoices/{document} {
      allow read: if request.auth != null;
      allow write: if request.auth != null &&
        (resource == null || resource.data.createdBy == request.auth.uid);
    }
  }
}
```

---

## Run Development Server

```bash
npm run dev
```

Open the app at:

http://localhost:5173

---

## Project Structure

```text
src/
├── components/
├── contexts/
├── firebase/
├── hooks/
├── pages/
│   ├── auth/
│   ├── doctor/
│   └── receptionist/
├── utils/
├── App.jsx
└── main.jsx
```

---

## Available Scripts

| Command | Description |
|----------|-------------|
| npm run dev | Start the development server |
| npm run build | Create a production build |
| npm run preview | Preview the production build |
| npm run lint | Run ESLint checks |

---

## Tech Stack

### Frontend
- React 19
- Vite
- Tailwind CSS 4
- React Router DOM
- React Hot Toast
- Lucide React

### Backend
- Firebase Authentication
- Firestore Database
- Firebase Security Rules

---

## Deployment

### Vercel

```bash
npm install -g vercel
vercel login
vercel
vercel --prod
```

---

## Author

| Field | Information |
|------|-------------|
| Name | Bashir Adam Ahmed Ali |
| Student ID | 210208999 |
| University | OSTIM Technical University |
| Department | Software Engineering |
| Course | WEX 428 - Workplace Experience III |
````
