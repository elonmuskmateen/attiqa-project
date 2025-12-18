# Backend and Database Setup Guide

## Complete Backend Infrastructure Created! 🎉

I've created a full-featured backend API with MongoDB database for your Campus Life Platform.

## 📁 Project Structure

```
server/
├── config/
│   └── database.js          # MongoDB connection
├── controllers/             # Business logic
│   ├── authController.js
│   ├── eventController.js
│   ├── reviewController.js
│   ├── courseController.js
│   ├── electionController.js
│   ├── questionController.js
│   └── feedbackController.js
├── middleware/
│   ├── auth.js              # JWT authentication
│   └── async.js             # Async error handler
├── models/                  # MongoDB schemas
│   ├── User.js
│   ├── Event.js
│   ├── Review.js
│   ├── Course.js
│   ├── Election.js
│   ├── Question.js
│   ├── Feedback.js
│   └── Notification.js
├── routes/                  # API routes
│   ├── auth.js
│   ├── events.js
│   ├── reviews.js
│   ├── courses.js
│   ├── elections.js
│   ├── questions.js
│   └── feedback.js
├── server.js                # Main server file
├── package.json
└── README.md
```

## 🚀 Quick Start

### 1. Install Backend Dependencies
```bash
cd server
npm install
```

### 2. Install MongoDB

**Option A: Local MongoDB**
- Download from https://www.mongodb.com/try/download/community
- Install and start MongoDB service

**Option B: MongoDB Atlas (Cloud)**
- Sign up at https://www.mongodb.com/cloud/atlas
- Create a free cluster
- Get connection string

### 3. Configure Environment

Create `server/.env` file:
```env
PORT=3001
NODE_ENV=development
MONGODB_URI=mongodb://localhost:27017/campus-life
JWT_SECRET=your-super-secret-jwt-key-change-this-in-production
JWT_EXPIRE=7d
FRONTEND_URL=http://localhost:3000
```

### 4. Start Backend Server
```bash
cd server
npm run dev    # Development mode with auto-reload
# or
npm start      # Production mode
```

### 5. Update Frontend Environment

Create/update `src/.env`:
```env
REACT_APP_API_URL=http://localhost:3001/api
```

### 6. Install Frontend Dependencies (if needed)
```bash
npm install axios
```

## 📊 Database Models

### User Model
- Students, Teachers, Admins
- Authentication with JWT
- Role-based access control

### Event Model
- Event proposals with voting
- Schedule conflict detection
- Feedback system

### Review Model
- Teacher reviews with moderation
- Multi-dimensional ratings
- Helpfulness voting

### Course Model
- Course information
- Ratings and reviews
- Enrollment tracking

### Election Model
- Student council elections
- Candidate registration
- Secure voting

### Question Model
- Q&A forum
- Answers with helpfulness
- Official responses

### Feedback Model
- Campus services feedback
- Priority levels
- Admin responses

## 🔐 Authentication

All protected routes require JWT token in header:
```
Authorization: Bearer <token>
```

## 📡 API Endpoints

### Authentication
- `POST /api/auth/register` - Register user
- `POST /api/auth/login` - Login user
- `GET /api/auth/me` - Get current user

### Events
- `GET /api/events` - Get all events
- `POST /api/events` - Create event
- `POST /api/events/:id/vote` - Vote on event

### Reviews
- `GET /api/reviews/teachers` - Get all teachers
- `POST /api/reviews` - Submit review
- `PUT /api/reviews/:id/helpful` - Mark helpful

### Courses
- `GET /api/courses` - Get all courses
- `POST /api/courses/:id/rate` - Rate course

### Elections
- `GET /api/elections` - Get all elections
- `POST /api/elections/:id/vote` - Vote in election

### Questions
- `GET /api/questions` - Get all questions
- `POST /api/questions` - Create question
- `POST /api/questions/:id/answer` - Answer question

### Feedback
- `GET /api/feedback` - Get all feedback
- `POST /api/feedback` - Create feedback

## 🔄 Frontend Integration

I've updated:
- ✅ `src/config/axios.js` - Axios instance with auth
- ✅ `src/services/authService.js` - Authentication service
- ✅ `src/services/eventService.js` - Event service (updated)
- ✅ `src/services/reviewService.js` - Review service (updated)

**Next Steps:**
1. Update remaining services (courseService, electionService, etc.)
2. Update Login component to use authService
3. Update AppContext to use backend API

## 🧪 Testing

Test the API using Postman or curl:

```bash
# Login
curl -X POST http://localhost:3001/api/auth/login \
  -H "Content-Type: application/json" \
  -d '{"username":"student1","password":"pass123"}'

# Get events (with token)
curl http://localhost:3001/api/events \
  -H "Authorization: Bearer YOUR_TOKEN"
```

## 📝 Seed Data (Optional)

Create a seed script to populate initial data:
```javascript
// server/scripts/seed.js
const User = require('../models/User');
// ... seed users, events, etc.
```

## 🎯 Next Steps

1. ✅ Backend server created
2. ✅ Database models created
3. ✅ API routes created
4. ✅ Authentication implemented
5. ⏳ Update frontend services
6. ⏳ Update Login component
7. ⏳ Test full integration

## 🐛 Troubleshooting

**MongoDB Connection Error:**
- Ensure MongoDB is running
- Check MONGODB_URI in .env
- Verify network/firewall settings

**CORS Errors:**
- Check FRONTEND_URL in backend .env
- Ensure frontend URL matches

**Authentication Errors:**
- Verify JWT_SECRET is set
- Check token expiration
- Ensure token is sent in Authorization header

## 📚 Documentation

See `server/README.md` for detailed API documentation.

