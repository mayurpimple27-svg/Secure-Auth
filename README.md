# 🔐 Authentication System

A full-stack authentication app built with **Node.js/Express** backend and **React/Vite** frontend. Features signup, email verification, login, password reset, and JWT-based session management.

## ✨ Features

- User registration with email verification (6-digit code)
- Secure login with JWT authentication
- Password reset via email
- Protected routes (authenticated + verified users only)
- Bcrypt password hashing
- HTTP-only cookies with CSRF protection
- Responsive UI with Tailwind CSS & animations

## 🛠️ Tech Stack

**Backend:** Node.js, Express, MongoDB, Mongoose, JWT, Bcrypt, Nodemailer
**Frontend:** React 19, Vite, React Router, Zustand, Axios, Tailwind CSS, Framer Motion

## 🚀 Quick Start

### Prerequisites
- Node.js v14+
- MongoDB (local or MongoDB Atlas)

### Setup

1. **Clone and install dependencies**
   ```bash
   npm install
   npm install --prefix Frontend
   ```

2. **Create `.env` file in root:**
   ```env
   PORT=5000
   NODE_ENV=development
   MONGO_URI=mongodb://localhost:27017/authentication
   JWT_SECRET=your_jwt_secret_key
   MAILTRAP_TOKEN=your_mailtrap_token
   CLIENT_URL=http://localhost:5173
   ```

3. **Run development servers**
   ```bash
   # Terminal 1 - Backend
   npm run dev

   # Terminal 2 - Frontend
   npm run dev --prefix Frontend
   ```

4. **Open** http://localhost:5173

## 📡 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/auth/signup` | Register new user |
| POST | `/api/auth/login` | Login |
| POST | `/api/auth/logout` | Logout |
| POST | `/api/auth/verify-email` | Verify email code |
| POST | `/api/auth/forgot-password` | Request password reset |
| POST | `/api/auth/reset-password/:token` | Reset password |
| GET | `/api/auth/check-auth` | Check if authenticated |

## 🔐 Security

- Passwords hashed with bcrypt (10 salt rounds)
- JWT tokens expire after 7 days
- Verification codes valid for 24 hours
- Password reset tokens valid for 1 hour
- HTTP-only, secure cookies with SameSite="strict"
- Email verification before full account access

## 📁 Project Structure

```
/
├── Backend/
│   ├── server.js
│   ├── Controllers/authController.js
│   ├── Routes/authRoute.js
│   ├── Models/userModel.js
│   ├── Middleware/verifyToken.js
│   ├── Utils/
│   └── Nodemailer/
│
└── Frontend/
    ├── src/
    │   ├── App.jsx
    │   ├── Pages/ (SignUp, Login, EmailVerification, etc.)
    │   ├── Components/
    │   └── store/authStore.js
```

## 🧪 Test the App

1. Sign up with email
2. Enter verification code from Mailtrap/email
3. Login with credentials
4. Test password reset flow
5. Check protected home page

## 🚨 Common Issues

| Issue | Fix |
|-------|-----|
| Port 5000 in use | Change `PORT` in .env |
| MongoDB error | Verify `MONGO_URI` and MongoDB is running |
| Emails not sending | Check Mailtrap token in .env |
| CORS errors | Ensure backend runs on port 5000 |

## 📦 Build & Deploy

```bash
# Production build
npm run build

# Start production server
npm start
```

For deployment, use MongoDB Atlas and set environment variables in your hosting platform.

## 📄 License

ISC
