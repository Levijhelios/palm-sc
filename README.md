# Palm SC - Complete Spanish Learning Platform

A comprehensive, AI-powered Spanish language learning application inspired by Duolingo and Pimsleur, featuring adaptive algorithms, gamification, and beautiful UI.

## 🎯 Quick Start Guide

### Prerequisites
- Node.js 18+
- PostgreSQL 13+
- Redis 6+
- npm or yarn

### Installation Steps

```bash
# 1. Clone the repository
git clone https://github.com/Levijhelios/palm-sc.git
cd palm-sc

# 2. Install all dependencies
npm run setup

# 3. Setup environment variables
cp backend/.env.example backend/.env
cp frontend/.env.example frontend/.env

# Edit the .env files with your configuration

# 4. Initialize database
npm run migrate

# 5. Start development servers
npm run dev
```

The application will be available at:
- **Frontend**: http://localhost:3000
- **Backend API**: http://localhost:5000

## 📚 Project Structure

```
palm-sc/
├── frontend/                  # React TypeScript SPA
│   ├── src/
│   │   ├── components/       # Reusable UI components
│   │   ├── pages/            # Page components
│   │   ├── stores/           # Zustand state management
│   │   ├── utils/            # Utility functions
│   │   ├── services/         # API services
│   │   └── App.tsx
│   ├── public/
│   ├── tsconfig.json
│   └── package.json
│
├── backend/                   # Express.js REST API
│   ├── src/
│   │   ├── routes/           # API endpoints
│   │   ├── controllers/      # Business logic
│   │   ├── models/           # Database models
│   │   ├── middleware/       # Auth & validation
│   │   ├── services/         # Business services
│   │   ├── utils/            # Utilities
│   │   └── server.ts
│   ├── database/
│   │   └── schema.sql
│   ├── data/
│   │   └── spanish-vocabulary-*.json
│   ├── tsconfig.json
│   └── package.json
│
├── package.json              # Root monorepo
├── README.md
├── IMPLEMENTATION_GUIDE.md
└── .gitignore
```

## ✨ Key Features

### 🎓 Three-Phase Learning System
- **Phase 1: Foundation** - 500+ essential daily words
- **Phase 2: Building** - Simple sentence construction
- **Phase 3: Mastery** - Advanced conversations

### 🧠 Adaptive Learning Algorithm
- SuperMemo 2 spaced repetition
- Difficulty auto-adjusts based on performance
- Response time bonuses
- Smart question selection

### 🎮 Gamification System
- Daily XP (resets every 24 hours)
- Achievement badges with unlock conditions
- Streak tracking for consistency
- Visual progress graphs (line & bar charts)

### 🎨 Premium UI/UX
- Warm beige theme (#F5E6D3) with gold accents
- Smooth animations with Framer Motion
- Dark mode support
- Fully responsive design
- Adjustable font sizes
- Accessible components

### 👤 User Management
- Secure JWT authentication
- Profile customization
- Progress persistence
- Session management
- Bug reporting system

## 🛠 Technology Stack

### Frontend
- **React 18** + TypeScript
- **Tailwind CSS** - Styling
- **Framer Motion** - Animations
- **Recharts** - Data visualization
- **Zustand** - State management
- **React Router** - Navigation
- **Lucide Icons** - UI icons

### Backend
- **Node.js** + Express
- **TypeScript** - Type safety
- **PostgreSQL** - Database
- **Redis** - Caching
- **JWT** - Authentication
- **Bcryptjs** - Password hashing

## 📊 Database Schema

The application includes 12 optimized tables:

- `users` - User accounts & settings
- `learning_phases` - Phase definitions
- `spanish_vocabulary` - Complete Spanish word database
- `user_vocabulary_progress` - Mastery tracking
- `lessons` - Lesson content
- `user_lesson_progress` - Lesson completion
- `questions` - Quiz questions
- `user_question_responses` - Answer history
- `user_xp_history` - XP tracking
- `achievements` - Badge definitions
- `user_achievements` - Earned badges
- `user_streaks` - Activity streaks
- `bug_reports` - Issue reporting
- `user_sessions` - Session management

## 🚀 Available Scripts

### Root Commands
```bash
npm run setup           # Install all dependencies
npm run dev           # Start both frontend & backend
npm run build         # Build both applications
npm run migrate       # Run database migrations
npm run test          # Run all tests
npm run lint          # Lint all code
```

### Backend Commands
```bash
cd backend
npm run dev           # Start dev server with hot reload
npm run build         # Compile TypeScript
npm start            # Run compiled application
npm run migrate      # Database migrations
npm test             # Run tests
npm run lint         # ESLint
```

### Frontend Commands
```bash
cd frontend
npm start            # Development server
npm run build        # Production build
npm test             # Run tests
npm run lint         # ESLint
```

## 🔐 Environment Variables

### Backend (.env)
```
PORT=5000
NODE_ENV=development
DATABASE_URL=postgresql://user:password@localhost:5432/palm_sc
REDIS_URL=redis://localhost:6379
JWT_SECRET=your-secret-key
JWT_EXPIRES_IN=24h
REFRESH_TOKEN_SECRET=your-refresh-secret
REFRESH_TOKEN_EXPIRES_IN=7d
CORS_ORIGIN=http://localhost:3000
```

### Frontend (.env)
```
REACT_APP_API_URL=http://localhost:5000
REACT_APP_ENV=development
```

## 📝 API Endpoints (Planned)

### Authentication
- `POST /api/auth/register` - Create account
- `POST /api/auth/login` - Login
- `POST /api/auth/refresh` - Refresh token
- `GET /api/auth/verify` - Verify token

### Learning
- `GET /api/lessons` - Get available lessons
- `GET /api/lessons/:id` - Get lesson details
- `GET /api/vocabulary` - Get vocabulary list
- `POST /api/questions/next` - Get next question
- `POST /api/responses` - Submit answer

### Progress
- `GET /api/progress` - Get user progress
- `GET /api/xp-history` - Get XP history
- `GET /api/achievements` - Get achievements

### Settings
- `PUT /api/users/profile` - Update profile
- `PUT /api/users/settings` - Update settings
- `POST /api/bug-reports` - Report bug

## 🎨 Design System

### Color Palette
- **Primary Beige**: #F5E6D3
- **Gold Accent**: #D4AF37
- **Warm Terracotta**: #C9866B
- **Dark Beige**: #D4C4B0
- **Cream**: #FFFEF9

### Typography
- **Font Family**: Inter, Poppins
- **Headings**: Bold, -0.02em letter spacing
- **Body**: Regular, 1.6 line height

### Spacing & Sizing
- **Gutter**: 2rem
- **Button**: px-6 py-3
- **Border Radius**: 0.5rem - 0.75rem

## 📈 Learning Algorithm Details

### SuperMemo 2 Implementation
```
EF' = EF + (0.1 - (5 - q) × (0.08 + (5 - q) × 0.02))
Interval[n] = Interval[n-1] × EF'
```

Where:
- `q` = Quality (0-5)
- `EF` = Easiness Factor
- Minimum EF: 1.3

### XP Calculation
```
Base XP = 10 × difficulty_level
Speed Bonus = +50% for <3sec, +25% for <5sec
Total XP = Base XP × (1 + Speed Bonus)
```

### Difficulty Adjustment
- Increase after 3+ consecutive correct
- Decrease after 2+ consecutive incorrect
- Resets on wrong answer
- Maximum difficulty: 5, Minimum: 1

## 🔄 Deployment

### Frontend (Vercel/Netlify)
```bash
cd frontend
npm run build
# Deploy build/ folder
```

### Backend (Heroku/Railway)
```bash
cd backend
npm run build
# Set environment variables
# Deploy
```

## 🧪 Testing

```bash
# Backend tests
cd backend && npm test

# Frontend tests
cd frontend && npm test

# All tests
npm run test
```

## 🐛 Known Limitations

- [ ] Real-time multiplayer features
- [ ] Voice recognition for pronunciation
- [ ] AI conversation practice (planned)
- [ ] Mobile app (React Native)
- [ ] Offline mode
- [ ] Community features

## 📞 Support & Contributing

Found a bug or have a feature request? Use the built-in bug reporting system in Settings → Support.

## 📄 License

MIT License - See LICENSE file for details

## 👨‍💻 Author

**Levijhelios** - Creator & Lead Developer

---

## 🌟 Acknowledgments

This platform was inspired by:
- **Duolingo** - Gamification and UX
- **Pimsleur** - Progressive learning structure
- **SuperMemo** - Spaced repetition algorithm

## 📚 Resources

- [React Documentation](https://react.dev)
- [Express.js Guide](https://expressjs.com)
- [PostgreSQL Docs](https://www.postgresql.org/docs)
- [TypeScript Handbook](https://www.typescriptlang.org/docs)

---

**Palm SC** - *Master Spanish with Confidence* 🌴✨

Made with ❤️ for Spanish learners worldwide
