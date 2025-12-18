# 🎓 Campus Life Platform

A comprehensive university management platform built with React and Node.js, featuring MySQL database integration.

## ✨ Features

- 👥 **User Management** - Students, Teachers, and Admins
- 📅 **Event Management** - Event proposals with voting system
- ⭐ **Teacher Reviews** - Rate and review teachers
- 📚 **Course Catalog** - Course information and ratings
- 🗳️ **Elections** - Student council elections
- 💬 **Q&A Forum** - Ask questions and get answers
- 📝 **Feedback System** - Campus services feedback
- 🔔 **Notifications** - Real-time notifications

## 🛠️ Tech Stack

### Frontend
- React.js
- Material-UI
- React Context API
- Axios
- Framer Motion

### Backend
- Node.js
- Express.js
- MySQL (Sequelize ORM)
- JWT Authentication
- bcryptjs

## 📋 Prerequisites

- Node.js (v14 or higher)
- MySQL (v8.0 or higher)
- npm or yarn

## 🚀 Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/campus-life-platform.git
cd campus-life-platform
```

### 2. Install Frontend Dependencies

```bash
npm install
```

### 3. Install Backend Dependencies

```bash
cd server
npm install
```

### 4. Set Up MySQL Database

```sql
CREATE DATABASE campus_life CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```

### 5. Configure Environment Variables

Create `server/.env`:

```env
PORT=3001
NODE_ENV=development

# MySQL Configuration
DB_HOST=localhost
DB_PORT=3306
DB_NAME=campus_life
DB_USER=root
DB_PASSWORD=your-mysql-password

# JWT Secret
JWT_SECRET=your-super-secret-jwt-key
JWT_EXPIRE=7d

# CORS Configuration
FRONTEND_URL=http://localhost:3000
```

### 6. Start Backend Server

```bash
cd server
npm run dev
```

### 7. Start Frontend (in a new terminal)

```bash
npm start
```

The application will be available at `http://localhost:3000`

## 📁 Project Structure

```
campus-life-platform/
├── src/                    # React frontend source
│   ├── components/         # React components
│   ├── pages/             # Page components
│   ├── services/          # API services
│   └── context/           # Context providers
├── server/                 # Node.js backend
│   ├── config/            # Configuration files
│   ├── controllers/       # Route controllers
│   ├── models/            # Sequelize models
│   ├── routes/            # API routes
│   └── middleware/        # Custom middleware
├── docs/                  # Documentation
└── public/                # Static files
```

## 🗄️ Database

The project uses MySQL with Sequelize ORM. All tables are created automatically when you start the server.

**Database Name:** `campus_life`

**Tables:**
- users, events, event_votes, event_feedback
- reviews, review_helpful
- courses, course_ratings
- elections, election_candidates, election_votes
- questions, answers, answer_helpful
- feedback, feedback_upvotes
- notifications

## 📚 Documentation

See the `docs/` folder for detailed documentation:
- MySQL Setup Guide
- Database Location Guide
- API Documentation
- Quick Start Guide

## 🔐 Security

- Passwords are hashed using bcrypt
- JWT tokens for authentication
- Environment variables for sensitive data
- CORS configured for security

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📝 License

This project is open source and available under the MIT License.

## 👨‍💻 Author

Your Name

## 🙏 Acknowledgments

- Material-UI for the UI components
- Sequelize for the ORM
- React team for the amazing framework

---

**Made with ❤️ for campus communities**
