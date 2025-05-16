# CyberShield

**CyberShield** is a full-stack, AI-powered platform for real-time cyberbullying detection and moderation. It proactively scans user-generated content (posts, comments, private chats) using XML-RoBERTa for text and Google’s Gemini API for images. Offensive content is flagged or blocked, with instant alerts sent to users and moderators. A built-in **CyberTool** interface lets users clean flagged text/images before reposting. CyberShield’s goal is to foster a safe, respectful online community.

---

## 🚀 Key Features

* **JWT Authentication**
  Secure signup, login, and password recovery.

* **Post Feed**
  Create posts (text + image + mood), view, like & comment.

* **Real-Time Moderation**
  On-the-fly scanning of captions, comments, and chat messages.

* **CyberTool Cleaning**
  Interactive endpoints to sanitize flagged text or images.

* **Alerts & Notifications**
  In-app notifications for any flagged content.

* **Profile Management**
  View & edit user details (avatar, bio).

* **MongoDB Persistence**
  Durable storage for users, posts, comments, chats, flags, and logs.

---

## 🛠 Tech Stack

**Frontend**: React.js, Tailwind CSS, React Context & Hooks
**Backend**: FastAPI, Uvicorn, Pydantic
**Database**: MongoDB (Motor)
**NLP Model**: XML-RoBERTa
**Image API**: Google Gemini

---

## 📦 Monorepo Structure

**frontend/**
• public/
• src/

* pages/ (Home, Login, Signup, Profile, Posts, Chatbot, Cybertools, UploadPost)
* components/ (Navbar, PostItem, CommentBox, ChatWindow)
* context/ (AuthContext, AlertContext)
* App.js, index.js

**backend/malay/**
• routes/

* users.py (signup, login, profile)
* posts.py (posts, comments, like)
* chatbot.py (chat users, messages, send)
* cybertool.py (clean text, clean image)
  • models.py, database.py
  • services/generator.py
  • config.py, main.py

---
Backend Repository link: https://github.com/Ayesha-Arshad-Ai/cybershiled

## ⚙️ Installation & Running

### Prerequisites

Node.js ≥ 16 & npm (frontend)
Python ≥ 3.9 & pip (backend)
MongoDB local at mongodb://localhost:27017

### 1. Frontend Setup

1. `cd frontend/`
2. `npm install`
3. Create `.env.local` with
   `REACT_APP_API_URL=http://localhost:8000`
4. `npm start`

   * Runs at [http://localhost:3000](http://localhost:3000)

### 2. Backend Setup

1. `cd backend/malay/`
2. `pip install -r requirements.txt`
3. Create `.env` with

   ```
   MONGO_URI=mongodb://localhost:27017
   JWT_SECRET=your_jwt_secret
   GEMINI_KEY=your_gemini_api_key
   ```
4. `uvicorn main:app --reload`

   * Runs at [http://localhost:8000](http://localhost:8000)

---

## 🔗 API Overview

**Authentication**

* POST /signup → register
* POST /login → receive JWT

**Posts & Comments**

* GET /posts
* POST /posts (JWT required)
* POST /posts/{id}/comments
* POST /posts/{id}/like

**Chat**

* GET /chat/users/{token}
* GET /chat/{id}/{token}/messages
* POST /chat/send

**CyberTool Cleaning**

* POST /cybertool/text
* POST /cybertool/image

---

## 🤝 Contributing

1. Fork the repo
2. Create a feature branch (`git checkout -b feature/xyz`)
3. Commit changes (`git commit -m "Add feature"`)
4. Push (`git push origin feature/xyz`)
5. Open a Pull Request

Please follow existing code style and include tests or docs for new features.

---

## 📄 License

This project is licensed under the **MIT License**.
