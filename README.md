CyberShield
CyberShield is a full-stack, AI-powered platform for real-time cyberbullying detection and moderation. It proactively scans user-generated content (posts, comments, and private chats) using advanced natural language processing (XML-RoBERTa) for text and Google’s Gemini API for images. Offensive or abusive content is automatically flagged or blocked, with immediate alerts sent to affected users and moderators. A dedicated CyberTool interface allows moderators to review and manually clean any flagged content. CyberShield’s goal is to maintain a safe online community by preventing and responding to harmful interactions.
Features
User Authentication (JWT): Secure signup/login with JSON Web Tokens to protect API endpoints and user sessions.
Post Creation: Users can create new posts with text and optional images (posts can be tagged with a mood).
Real-Time Moderation: All comments and private chat messages are analyzed on-the-fly. CyberShield blocks or flags cyberbullying before content appears.
CyberTool Interface: An admin interface for moderators to view and manually clean or delete flagged content.
Alerts & Notifications: Instant alerts are sent to users and moderators whenever content is flagged for potential cyberbullying.
MongoDB Persistence: All data (users, posts, comments, chats, flags) is stored in MongoDB for durability and fast access.
Tech Stack
React.js: Frontend UI library for building the user interface.
Tailwind CSS: Utility-first CSS framework for styling and responsive design.
FastAPI: Python backend framework for building RESTful APIs.
MongoDB: NoSQL database serving as the persistence layer.
XML-RoBERTa: Advanced NLP model used for text-based cyberbullying analysis.
Google Gemini API: Image analysis/generation API used to detect abusive or inappropriate content in images.
