# Palm SC - Spanish Language Learning Platform

![Palm SC](https://img.shields.io/badge/version-1.0.0-brightgreen)
![React](https://img.shields.io/badge/frontend-React%2018-blue)
![Node.js](https://img.shields.io/badge/backend-Node.js%2B Express-green)
![Database](https://img.shields.io/badge/database-PostgreSQL-336791)

## 🚀 Quick Start

### Prerequisites
- Node.js 18+
- PostgreSQL 13+
- Redis 6+
- npm or yarn

### Installation

```bash
# Clone the repository
git clone https://github.com/Levijhelios/palm-sc.git
cd palm-sc

# Install all dependencies
npm run setup

# Create environment files
cp backend/.env.example backend/.env
cp frontend/.env.example frontend/.env

# Configure your database and API settings in .env files

# Run database migrations
npm run migrate

# Start development servers
npm run dev
```

The application will be available at:
- Frontend: http://localhost:3000
- Backend API: http://localhost:5000

## 📁 Project Structure

```
palm-sc/
├── frontend/                 # React TypeScript application
│   ├── src/
│   │   ├── components/      # Reusable UI components
│   │   ├── pages/           # Page components
│   │   ├── stores/          # Zustand state management
│   │   ├── utils/           # Utility functions
│   │   ├── services/        # API services
│   │   └── App.tsx
│   ├── public/
│   └── package.json
│
├── backend/                  # Node.js Express API
│   ├── src/
│   │   ├── routes/          # API endpoints
│   │   ├── controllers/     # Business logic
│   │   ├── models/          # Database models
│   │   ├── middleware/      # Express middleware
│   │   ├── services/        # Business services
│   │   ├── utils/           # Utilities
│   │   └── server.ts
│   ├── database/
│   │   └── schema.sql       # Database schema
│   ├── data/                # JSON vocabulary data
│   └── package.json
│
├── package.json             # Root package.json
├── README.md
└── .gitignore

```

## 🎯 Features Implemented

### ✅ Core Features
- [x] Responsive React frontend with TypeScript
- [x] Express.js REST API backend
- [x] PostgreSQL database with comprehensive schema
- [x] Redis integration for caching
- [x] JWT authentication system
- [x] User profile management
- [x] Warm beige theme with Tailwind CSS
- [x] Dark mode toggle
- [x] Animated Californian palm tree on home page

### ✅ Learning System
- [x] Three-phase progressive learning structure
- [x] Spanish vocabulary database (500+ words)
- [x] Adaptive difficulty algorithm (SuperMemo 2)
- [x] Spaced repetition system
- [x] Mastery tracking per word

### ✅ Gamification
- [x] Daily XP system (resets every 24 hours)
- [x] Achievement badges
- [x] XP graph visualization (line & bar charts)
- [x] Streak tracking
- [x] Progress percentage calculation

### ✅ User Interface
- [x] Beautiful home page with hero section
- [x] Login and registration pages
- [x] Dashboard with achievements
- [x] Settings page with multiple options
- [x] Profile management
- [x] Responsive mobile design

### ✅ Accessibility & Settings
- [x] Light/Dark mode toggle
- [x] Adjustable font size
- [x] Language preferences
- [x] Sound effects toggle
- [x] Notifications settings
- [x] Bug report system

## 🛠 Technology Stack

### Frontend
- **React 18** - UI framework
- **TypeScript** - Type safety
- **Tailwind CSS** - Styling
- **Framer Motion** - Animations
- **Recharts** - Data visualization
- **Zustand** - State management
- **React Router** - Navigation
- **Lucide Icons** - Icon library

### Backend
- **Node.js + Express** - REST API
- **TypeScript** - Type safety
- **PostgreSQL** - Relational database
- **Redis** - Caching & sessions
- **JWT** - Authentication
- **Bcryptjs** - Password hashing
- **Joi** - Input validation

## 📊 Learning Phases

### Phase 1: Foundation (500 words)
- Common greetings and courtesies
- Essential nouns (family, food, animals)
- Basic verbs (ser, estar, tener)
- Common adjectives
- Daily communication essentials

### Phase 2: Building (Sentence Construction)
- Simple SVO sentence structure
- Subject-verb-object agreement
- Tense introduction (present, past, future)
- Common phrases and expressions
- Contextual sentence formation

### Phase 3: Mastery (Conversational Fluency)
- Complex sentence formation
- Idiomatic expressions
- Advanced tenses
- Real-world conversation scenarios
- Cultural context and usage

## 🧠 Adaptive Algorithm

The platform uses the **SuperMemo 2 algorithm** with custom enhancements:

```
Ease Factor = previous_ease + 0.1 - (5 - quality) × (0.08 + (5 - quality) × 0.02)
Interval[n] = Interval[n-1] × EaseFactor
```

**Difficulty Adjustments:**
- Difficulty increases after 3+ consecutive correct answers
- Difficulty decreases after 2+ consecutive errors
- Response time affects XP rewards (up to 50% bonus for fast responses)
- Mastery level directly influences question selection

**XP Calculation:**
```
Base XP = 10 × difficulty_level
Speed Bonus = +50% for <3sec, +25% for <5sec
Total XP = Base XP × (1 + Speed Bonus)
```

## 🔐 Authentication

The app uses JWT-based authentication:

```
POST /api/auth/register  - Create new account
POST /api/auth/login     - Login with credentials
POST /api/auth/refresh   - Refresh access token
GET  /api/auth/verify    - Verify token validity
```

## 📈 Progress Tracking

Real-time tracking of:
- Daily XP (resets every 24 hours)
- Total XP (cumulative)
- Word mastery levels (0-100%)
- Learning phase progress
- Streak count
- Time spent on lessons
- Accuracy percentage

## 🎨 Design System

**Color Palette:**
- Primary Beige: `#F5E6D3`
- Warm Gold: `#D4AF37`
- Soft Terracotta: `#C9866B`
- Dark Beige: `#D4C4B0`
- Cream White: `#FFFEF9`

**Typography:**
- Font Family: Inter, Poppins
- Letter Spacing: -0.02em (headings)
- Line Height: 1.6 (body)

## 📦 Deployment

### Frontend (Vercel/Netlify)
```bash
cd frontend
npm run build
# Deploy the build folder
```

### Backend (Heroku/Railway)
```bash
cd backend
npm run build
# Set environment variables
# Deploy with Docker or direct push
```

## 🧪 Testing

```bash
# Run backend tests
npm run test

# Run frontend tests
cd frontend && npm test
```

## 📝 Environment Variables

### Backend (.env)
```
PORT=5000
NODE_ENV=development
DB_USER=postgres
DB_PASSWORD=your_password
DB_HOST=localhost
DB_PORT=5432
DB_NAME=palm_sc
JWT_SECRET=your_jwt_secret
REDIS_HOST=localhost
REDIS_PORT=6379
```

### Frontend (.env)
```
REACT_APP_API_URL=http://localhost:5000
REACT_APP_ENV=development
```

## 🐛 Known Issues & Future Improvements

- [ ] Multi-user multiplayer challenges
- [ ] Voice recognition for pronunciation
- [ ] AI-powered conversation practice
- [ ] Mobile app (React Native)
- [ ] Offline mode
- [ ] Advanced analytics dashboard
- [ ] Instructor/teacher dashboard
- [ ] Community forum
- [ ] Certified courses with certificates

## 📞 Support

For bug reports and feature requests, use the built-in bug report system in Settings.

## 📄 License

MIT License - See LICENSE file for details

## 👨‍💻 Contributors

- **Levijhelios** - Creator & Lead Developer

---

**Palm SC** - Master Spanish with Confidence 🌴✨

*Built with ❤️ for Spanish learners worldwide*
