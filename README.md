# 🌟 FINE - Finance Intelligent Ecosystem

> A personal finance tracking application with emotional intelligence features, combining transaction tracking, goal setting, and AI-powered insights.

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![React](https://img.shields.io/badge/React-19-61dafb.svg)](https://reactjs.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.110-009688.svg)](https://fastapi.tiangolo.com/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Latest-47A248.svg)](https://www.mongodb.com/)

---

## 🎯 Features

### 💰 Financial Management
- **Transaction Tracking**: Log income and expenses with categories
- **Balance Overview**: Real-time balance, income, and expense tracking
- **Goal Setting**: Create and track financial goals with deadlines
- **Category Analysis**: Breakdown spending by category

### 🧠 Emotional Intelligence
- **Mood Tracking**: Tag transactions with your emotional state
- **Emotional Spending Analysis**: Understand how mood affects spending
- **AI-Powered Insights**: Get personalized financial advice based on behavior patterns

### 🔒 Security
- **JWT Authentication**: Secure user sessions
- **Password Hashing**: Bcrypt encryption for passwords
- **Protected Routes**: Frontend and backend route protection

---

## 🚀 Quick Start

### Prerequisites
- **Python 3.8+** - [Download](https://www.python.org/downloads/)
- **Node.js 16+** - [Download](https://nodejs.org/)
- **MongoDB** - [Download](https://www.mongodb.com/try/download/community)
- **Ollama** (Optional, for FREE AI) - [Download](https://ollama.ai/)

### ⚡ Automated Setup (Windows)

```powershell
# Run the automated setup script
setup.bat

# Then start the servers:
start-backend.bat    # In one terminal
start-frontend.bat   # In another terminal
```

### 📖 Manual Setup

See **[SETUP_GUIDE.md](SETUP_GUIDE.md)** for detailed instructions.

**Quick steps:**

```powershell
# 1. Install backend dependencies
cd backend
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt

# 2. Install frontend dependencies
cd ../frontend
npm install

# 3. Start MongoDB
net start MongoDB

# 4. (Optional) Install Ollama for FREE AI
# Download from https://ollama.ai/download
ollama pull llama2

# 5. Start backend
cd backend
uvicorn server:app --reload --host 0.0.0.0 --port 8000

# 6. Start frontend (new terminal)
cd frontend
npm start
```

**Open:** http://localhost:3000

---

## 🔑 API Key Configuration

### ✅ Option 1: FREE - Ollama (Recommended)

**No API key needed!** Just install Ollama:

```powershell
# Download from: https://ollama.ai/download
ollama pull llama2
```

**In `backend/.env`:**
```env
USE_OLLAMA=true
OLLAMA_BASE_URL=http://localhost:11434/v1
OLLAMA_MODEL=llama2
```

### ❌ Option 2: PAID - Emergent AGI API

**Requires API key:**

```env
USE_OLLAMA=false
EMERGENT_LLM_KEY=your-api-key-here
```

---

## 📱 Application Pages

### 1. **Authentication** (`/auth`)
- User registration and login
- JWT token management

### 2. **Dashboard** (`/`)
- Balance overview with visual charts
- Income/expense summary
- Recent transactions
- Category breakdown (pie & bar charts)
- Spending trends visualization

### 3. **Transactions** (`/transactions`)
- Add income/expense entries
- Categorize transactions
- Tag with mood
- View transaction history

### 4. **Goals** (`/goals`)
- Create financial goals
- Set target amounts and deadlines
- Track progress

### 5. **Insights** (`/insights`)
- AI-powered financial analysis
- Mood-based spending patterns
- Personalized recommendations
- Financial tips

### 6. **AI Chatbot** (`/chatbot`) 🆕
- Natural language chat interface
- Ask questions about your finances
- Get personalized financial advice
- Context-aware responses based on your data
- Powered by Ollama (100% free!)

---

## 🛠️ Technology Stack

### Backend
- **Framework**: FastAPI (Python)
- **Database**: MongoDB with Motor (async driver)
- **Authentication**: PyJWT + Bcrypt
- **AI**: OpenAI SDK (Ollama/Emergent API)
- **Validation**: Pydantic

### Frontend
- **Framework**: React 19
- **Routing**: React Router v7
- **HTTP Client**: Axios
- **UI Library**: Radix UI
- **Styling**: Tailwind CSS
- **Notifications**: Sonner
- **Forms**: React Hook Form + Zod

### DevOps
- **Build Tool**: Webpack (via CRACO)
- **Package Manager**: npm/yarn
- **Code Quality**: ESLint, Prettier

---

## 📂 Project Structure

```
fine-jain-main/
├── backend/
│   ├── server.py          # FastAPI application
│   ├── requirements.txt   # Python dependencies
│   ├── .env              # Environment variables
│   └── .env.example      # Template
├── frontend/
│   ├── src/
│   │   ├── pages/        # Dashboard, Auth, Transactions, Goals, Insights
│   │   ├── components/   # Reusable UI components
│   │   ├── hooks/        # Custom React hooks
│   │   └── lib/          # Utilities
│   ├── package.json
│   ├── .env
│   └── .env.example
├── setup.bat             # Automated setup script
├── start-backend.bat     # Start backend server
├── start-frontend.bat    # Start frontend app
├── SETUP_GUIDE.md        # Detailed setup instructions
└── README.md             # This file
```

---

## 🧪 API Documentation

Once the backend is running, visit:

**Interactive API Docs:** http://localhost:8000/docs

### Key Endpoints:

```
POST   /api/auth/register         - Register new user
POST   /api/auth/login            - Login user
GET    /api/auth/me               - Get current user

POST   /api/transactions          - Create transaction
GET    /api/transactions          - Get all transactions
DELETE /api/transactions/{id}     - Delete transaction

POST   /api/goals                 - Create goal
GET    /api/goals                 - Get all goals
PATCH  /api/goals/{id}            - Update goal progress
DELETE /api/goals/{id}            - Delete goal

POST   /api/insights/analyze      - Generate AI insights
GET    /api/insights/mood-analysis - Get mood spending data

POST   /api/chatbot/chat          - Chat with AI assistant

GET    /api/dashboard/stats       - Get dashboard statistics
```

---

## 🔧 Configuration

### Backend (`.env`)

```env
# MongoDB
MONGO_URL=mongodb://localhost:27017/
DB_NAME=fine_db

# JWT
JWT_SECRET=your-secret-key

# CORS
CORS_ORIGINS=http://localhost:3000

# AI (Ollama - FREE)
USE_OLLAMA=true
OLLAMA_BASE_URL=http://localhost:11434/v1
OLLAMA_MODEL=llama2
```

### Frontend (`.env`)

```env
REACT_APP_BACKEND_URL=http://localhost:8000
```

---

## 🐛 Troubleshooting

### MongoDB Not Starting
```powershell
net start MongoDB
# Or manually:
mongod --dbpath "C:\data\db"
```

### Ollama Not Found
```powershell
# Install from: https://ollama.ai/download
ollama pull llama2
ollama serve
```

### Port Already in Use
```powershell
# Kill process on port 8000/3000
netstat -ano | findstr :8000
taskkill /PID <PID> /F
```

### Frontend Build Issues
```powershell
cd frontend
rm -rf node_modules package-lock.json
npm install
```

---

## 📝 Usage Guide

1. **Register/Login**: Create an account at http://localhost:3000/auth
2. **Add Transactions**: Go to Transactions page and log your expenses/income
3. **Set Goals**: Create financial goals with targets
4. **View Dashboard**: Check your balance and spending overview
5. **Get Insights**: Generate AI-powered financial advice based on your behavior

---

## 🌟 Future Enhancements

- [ ] Budget limits and alerts
- [ ] Export reports (PDF, CSV)
- [ ] Bank API integration for auto-import
- [ ] Mobile app (React Native)
- [ ] Recurring transactions
- [ ] Multi-currency support
- [ ] Savings recommendations
- [ ] Bill reminders

---

## 🤝 Contributing

Contributions are welcome! Please:
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

---

## 📄 License

This project is open source and available under the MIT License.

---

## 💡 Support

For detailed setup instructions, see **[SETUP_GUIDE.md](SETUP_GUIDE.md)**

For issues:
- Check API docs: http://localhost:8000/docs
- Review MongoDB/Ollama logs
- Ensure all services are running

---

**Built with ❤️ using FastAPI, React, and AI**
