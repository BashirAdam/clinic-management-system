````markdown
# Bashir Clinic - Management System

Live Application: https://clinic-management-system-main3.vercel.app/

A modern clinic management system built with React, Firebase, and Tailwind CSS.

---

# Screenshots

## Login Page
![Login Page](IMAGE_PLACEHOLDER_LOGIN)

## Doctor Dashboard
![Doctor Dashboard](IMAGE_PLACEHOLDER_DOCTOR_DASHBOARD)

## Doctor Appointments
![Doctor Appointments](IMAGE_PLACEHOLDER_DOCTOR_APPOINTMENTS)

## Doctor Prescriptions
![Doctor Prescriptions](IMAGE_PLACEHOLDER_DOCTOR_PRESCRIPTIONS)

## Receptionist Dashboard
![Receptionist Dashboard](IMAGE_PLACEHOLDER_RECEPTIONIST_DASHBOARD)

## Receptionist Appointments
![Receptionist Appointments](IMAGE_PLACEHOLDER_RECEPTIONIST_APPOINTMENTS)

## Receptionist Billing
![Receptionist Billing](IMAGE_PLACEHOLDER_RECEPTIONIST_BILLING)

## Token Management
![Token Management](IMAGE_PLACEHOLDER_TOKEN_MANAGEMENT)

---

# Prerequisites

- Node.js (v16 or higher)
- npm or yarn
- Firebase project

---

# Firebase Setup

1. Go to Firebase Console
2. Create a new project or select existing one
3. Enable Authentication (Email/Password)
4. Enable Firestore Database (test mode)
5. Get your Firebase configuration

---

# Environment Configuration

```bash
cp env.example.txt .env
```

Update `.env` file:

```env
VITE_FIREBASE_API_KEY=your_api_key
VITE_FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
VITE_FIREBASE_PROJECT_ID=your_project_id
VITE_FIREBASE_STORAGE_BUCKET=your_project.appspot.com
VITE_FIREBASE_MESSAGING_SENDER_ID=your_sender_id
VITE_FIREBASE_APP_ID=your_app_id
```

---

# Firebase Security Rules Configuration

Important: Configure Firestore security rules for proper access control.

Go to Firestore Database → Rules tab and replace with:

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

# Run Development Server

```bash
npm run dev
```

Visit:
http://localhost:5173

---

# Project Structure

```text
src/
├── components/
│   ├── LogoutButton.jsx
│   ├── ProtectedRoute.jsx
│   ├── EmailVerificationStatus.jsx
│   └── TokenDisplay.jsx
├── contexts/
│   └── AuthContext.jsx
├── firebase/
│   └── config.js
├── hooks/
│   └── useAuth.js
├── pages/
│   ├── auth/
│   │   ├── Login.jsx
│   │   ├── Signup.jsx
│   │   ├── ForgotPasswordForm.jsx
│   │   └── VerifyEmail.jsx
│   ├── doctor/
│   │   ├── Doctor.jsx
│   │   ├── appointment/
│   │   ├── prescriptions/
│   │   └── token/
│   ├── receptionist/
│   │   ├── Receptionist.jsx
│   │   ├── appointment/
│   │   ├── billing/
│   │   ├── prescriptions/
│   │   └── token/
│   └── Home.jsx
├── utils/
│   └── authUtils.js
├── App.jsx
└── main.jsx
```

---

# Available Scripts

| Command | Description |
|----------|-------------|
| npm run dev | Start development server |
| npm run build | Build production |
| npm run preview | Preview build |
| npm run lint | Run linting |

---

# Security Features

- Email verification required for activation
- Role-based access control
- Protected routes
- Secure password reset via email
- Firestore security rules
- Authentication state management

---

# Email Verification System

- Automatic email sent on signup
- Real-time verification status
- Manual refresh option
- Firebase Authentication integration

---

# Tech Stack

## Frontend
- React 19
- Vite
- Tailwind CSS 4
- React Router DOM
- React Hot Toast
- Lucide React

## Backend
- Firebase Authentication
- Firestore Database
- Firebase Security Rules

## Development Tools
- ESLint
- PostCSS
- Autoprefixer

---

# Responsive Design

- Mobile-first approach
- Tablet and desktop support
- Touch-friendly UI
- Cross-browser compatibility

---

# Real-time Features

- Live Firebase updates
- Real-time dashboards
- Instant notifications
- Live patient queue system

---

# Data Management

- Patient records management
- Appointment scheduling
- Prescription system
- Billing and invoices
- Token queue system

---

# Deployment

## Vercel Deployment

```bash
npm install -g vercel
vercel login
vercel
vercel --prod
```

---

# Author

| Field | Information |
|------|-------------|
| Name | Bashir Adam Ahmed Ali |
| Student ID | 210208999 |
| University | OSTIM Technical University |
| Department | Software Engineering |
| Course | WEX 428 - Workplace Experience III |

---


---
````
