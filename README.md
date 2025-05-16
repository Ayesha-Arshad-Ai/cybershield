```markdown
# CyberShield

**CyberShield** is a full-stack, AI-powered platform for real-time cyberbullying detection and moderation. It proactively scans user-generated content (posts, comments, private chats) using XML-RoBERTa for text and Google’s Gemini API for images. Offensive content is flagged or blocked, with instant alerts sent to users and moderators. A built-in **CyberTool** interface lets users clean flagged text/images before reposting. CyberShield’s goal is to foster a safe, respectful online community.

---

## 🚀 Key Features

- **JWT Authentication**: Secure signup, login, password recovery  
- **Post Feed**: Create posts (text + image + mood), view, like & comment  
- **Real-Time Moderation**: On-the-fly scanning of captions, comments, chat messages  
- **CyberTool Cleaning**: Interactive endpoints to sanitize flagged text or images  
- **Alerts & Notifications**: In-app notifications for any flagged content  
- **Profile Management**: View & edit user details (avatar, bio)  
- **MongoDB Persistence**: Durable storage for users, posts, comments, chats, flags, logs  

---

## 🛠 Tech Stack

| Layer               | Technology             |
| ------------------- | ---------------------- |
| **Frontend**        | React.js, Tailwind CSS |
| **State Management**| React Context + Hooks  |
| **Backend**         | FastAPI (Python)       |
| **Database**        | MongoDB (Motor)        |
| **NLP Model**       | XML-RoBERTa            |
| **Image API**       | Google Gemini          |
| **Server**          | Uvicorn (ASGI)         |

---

## 📦 Monorepo Structure

```

/  (root)
├── frontend/                # React SPA
│   ├── public/              # static assets
│   └── src/
│       ├── pages/           # Home, Login, Signup, Profile, Posts, Chatbot, Cybertools, UploadPost
│       ├── components/      # Navbar, PostItem, CommentBox, ChatWindow
│       ├── context/         # AuthContext, AlertContext
│       ├── App.js           # routes & layout
│       └── index.js         # ReactDOM entry
└── backend/                 # FastAPI services
└── malay/
├── routes/
│   ├── users.py     # /signup, /login, /profile
│   ├── posts.py     # /posts, /posts/{id}/comments, /like
│   ├── chatbot.py   # /chat/users, /chat/{id}/messages, /chat/send
│   └── cybertool.py # /cybertool/text, /cybertool/image
├── models.py        # Pydantic schemas
├── database.py      # MongoDB connection & collections
├── services/
│   └── generator.py # AI integration & cleaning logic
├── config.py        # MONGO\_URI, JWT\_SECRET, GEMINI\_KEY
└── main.py          # FastAPI app setup & router includes

````

---

## ⚙️ Installation & Running

### Prerequisites

- **Node.js** ≥ 16 & **npm** (Frontend)  
- **Python** ≥ 3.9 & **pip** (Backend)  
- **MongoDB** running locally on `mongodb://localhost:27017`  

---

### 1. Frontend Setup

```bash
cd frontend/
npm install
````

Create `.env.local` in `frontend/`:

```env
REACT_APP_API_URL=http://localhost:8000
```

Run the React dev server:

```bash
npm start
```

Frontend available at [http://localhost:3000](http://localhost:3000).

---

### 2. Backend Setup

```bash
cd backend/malay/
pip install -r requirements.txt
```

Create `.env` in `backend/malay/`:

```env
MONGO_URI=mongodb://localhost:27017
JWT_SECRET=your_jwt_secret
GEMINI_KEY=your_gemini_api_key
```

Run the FastAPI server:

```bash
uvicorn main:app --reload
```

Backend API available at [http://localhost:8000](http://localhost:8000).

---

## 🔗 API Overview

### Authentication

* `POST /signup` Register new user
* `POST /login` Authenticate & receive JWT

### Posts & Comments

* `GET /posts` List all posts
* `POST /posts` Create a post (JWT required)
* `POST /posts/{id}/like` Like a post
* `POST /posts/{id}/comments` Add comment

### Chat

* `GET /chat/users/{token}` List chat users
* `GET /chat/{id}/{token}/messages` Fetch chat history
* `POST /chat/send` Send chat message

### CyberTool Cleaning

* `POST /cybertool/text` Sanitize flagged text
* `POST /cybertool/image` Sanitize flagged image

---

## 🤝 Contributing

1. Fork this repo
2. Create a feature branch (`git checkout -b feature/xyz`)
3. Commit your changes (`git commit -m "Add feature"`)
4. Push (`git push origin feature/xyz`)
5. Open a Pull Request

Please adhere to existing code style and include tests or documentation for new features.

---

## 📄 License

This project is licensed under the **MIT License**.

```

---

Simply place this single `README.md` at your repository root. It covers both **frontend** and **backend** contexts, gives clear setup steps, and presents a unified overview of CyberShield.
```
