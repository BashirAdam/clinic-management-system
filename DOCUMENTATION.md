````markdown
<div align="center">
  <img src="./images/logo.png" width="80" alt="Clinic Logo" />
  <h1>🏥 Bashir Clinic - Management System</h1>
</div>

> A complete full-stack clinic management system for modern healthcare facilities

## 🌐 Live Demo

https://clinic-management-system-main3.vercel.app

---

## 📸 Screenshots

| Login Page | Doctor Dashboard |
|------------|------------------|
| ![Login Page](./images/screenshot-login.png) | ![Doctor Dashboard](./images/screenshot-doctor.png) |

| Receptionist Dashboard | Billing Page |
|------------------------|--------------|
| ![Receptionist Dashboard](./images/screenshot-receptionist.png) | ![Billing Page](./images/screenshot-billing.png) |

---

## 📋 Demo Credentials

| Role | Email | Password |
|------|-------|----------|
| 👨‍⚕️ Doctor | demo@clinic.com | demo123 |
| 📋 Receptionist | reception@clinic.com | demo123 |

---

## ⚡ Quick Setup Commands

```bash
# Clone the repository
git clone https://github.com/BashirAdam/clinic-management-system.git

# Enter project directory
cd clinic-management-system

# Install dependencies
npm install

# Create environment file
cp env.example.txt .env

# Add your Firebase config to .env file

# Run the application
npm run dev
````

Open in browser:

```text
http://localhost:5173
```

---

## 🚀 Deploy to Vercel

```bash
# Install Vercel CLI
npm install -g vercel

# Login to Vercel
vercel login

# Deploy
vercel

# Add environment variables
vercel env add VITE_FIREBASE_API_KEY
vercel env add VITE_FIREBASE_AUTH_DOMAIN
vercel env add VITE_FIREBASE_PROJECT_ID
vercel env add VITE_FIREBASE_STORAGE_BUCKET
vercel env add VITE_FIREBASE_MESSAGING_SENDER_ID
vercel env add VITE_FIREBASE_APP_ID

# Final production deploy
vercel --prod
```

---

## 🔧 Technologies Used

| Category       | Technology         |
| -------------- | ------------------ |
| Frontend       | React 19 + Vite    |
| Styling        | Tailwind CSS 4     |
| Database       | Firebase Firestore |
| Authentication | Firebase Auth      |
| Deployment     | Vercel             |

---

## 📁 Project Structure

```text
clinic-management-system/
├── public/
│   └── doctor.ico
├── src/
│   ├── pages/
│   │   ├── Login.jsx
│   │   ├── doctor/
│   │   └── receptionist/
│   ├── contexts/
│   ├── firebase/
│   ├── hooks/
│   └── utils/
├── images/
│   ├── logo.png
│   ├── screenshot-login.png
│   ├── screenshot-doctor.png
│   ├── screenshot-receptionist.png
│   └── screenshot-billing.png
├── .env
├── README.md
└── package.json
```

---

## 👨‍🎓 Author

| Field      | Information                                                         |
| ---------- | ------------------------------------------------------------------- |
| Name       | Bashir Adam Ahmed Ali                                               |
| Student ID | 210208999                                                           |
| Email      | [210208999@ostimteknik.edu.tr](mailto:210208999@ostimteknik.edu.tr) |
| University | OSTIM Technical University                                          |
| Department | Computer Engineering                                                |
| Course     | WEX 428 - Workplace Experience III                                  |
| Term       | Spring 2026                                                         |
| GitHub     | https://github.com/BashirAdam                                       |
| Live Demo  | https://clinic-management-system-main3.vercel.app                   |

---

## 📄 License

MIT License

---

### Last Updated

May 2026

### Status

✅ Production Ready

```
```
