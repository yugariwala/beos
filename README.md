# Blood Emergency Platform (BEOS)

A full-stack blood emergency management platform connecting donors, hospitals, and blood banks in real-time.

## 🩸 Features

- **Real-time Updates**: Socket.IO for live notifications and alerts
- **Emergency Requests**: Quick blood request submission with urgency levels
- **Donor Management**: Track donors, availability, and blood types
- **Blood Bank Inventory**: Manage blood stock with batch tracking
- **Hospital Dashboard**: Request blood and track fulfillment
- **Admin Panel**: System-wide statistics and user management

## 🛠️ Technology Stack

### Frontend (TypeScript)
- React 18 with TypeScript
- Vite for build tooling
- React Router for navigation
- Framer Motion for animations
- Leaflet for maps
- Socket.IO Client for real-time updates

### Backend (Python)
- FastAPI framework
- SQLite with aiosqlite (async)
- Python-SocketIO for WebSockets
- JWT authentication with python-jose
- Pydantic for data validation

## 📁 Project Structure

```
beos/
├── frontend/                 # React TypeScript frontend
│   ├── src/
│   │   ├── components/      # Reusable UI components (.tsx)
│   │   ├── pages/           # Page components (.tsx)
│   │   ├── context/         # React contexts (.tsx)
│   │   ├── services/        # API and Socket services (.ts)
│   │   ├── types/           # TypeScript type definitions
│   │   └── hooks/           # Custom React hooks (.ts)
│   ├── package.json
│   └── tsconfig.json
│
├── backend_python/          # Python FastAPI backend
│   ├── main.py              # FastAPI application entry
│   ├── database/
│   │   ├── db.py            # Database connection & migrations
│   │   └── schema.sql       # SQLite schema
│   ├── models/              # Data models
│   ├── routes/              # API route handlers
│   ├── middleware/          # Auth middleware
│   ├── socket_handlers/     # Socket.IO handlers
│   └── requirements.txt
│
└── backend/                 # (Archived) Original Node.js backend
```

## 🚀 Getting Started

### Prerequisites
- Node.js 18+
- Python 3.10+
- npm or yarn

### Backend Setup (Python)

```bash
# Navigate to backend
cd backend_python

# Create virtual environment
python -m venv venv

# Activate virtual environment
# Windows:
venv\Scripts\activate
# Linux/Mac:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Run the server
python main.py
# or
uvicorn main:socket_app --reload --port 5000
```

### Frontend Setup

```bash
# Navigate to frontend
cd frontend

# Install dependencies
npm install

# Run development server
npm run dev
```

### Access the Application

- Frontend: http://localhost:5173
- Backend API: http://localhost:5000
- API Docs: http://localhost:5000/docs

## 📡 API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/api/health` | GET | Health check |
| `/api/dashboard` | GET | Dashboard statistics |
| `/api/auth/register` | POST | User registration |
| `/api/auth/login` | POST | User login |
| `/api/auth/me` | GET | Current user |
| `/api/donors` | CRUD | Donor management |
| `/api/hospitals` | CRUD | Hospital management |
| `/api/blood-banks` | CRUD | Blood bank management |
| `/api/requests` | CRUD | Blood request management |
| `/api/admin/*` | CRUD | Admin operations |

## 👤 Default Admin Account

- Email: `ariwalayug181@gmail.com`
- Password: `ariwalayug@2008`

## 🔧 Environment Variables

### Backend (.env)
```env
DB_PATH=blood_emergency.db
JWT_SECRET=your-secret-key
PORT=5000
```

### Frontend (.env)
```env
VITE_API_URL=http://localhost:5000
```

## 📦 Deployment

### Vercel (Frontend)
The frontend is configured for Vercel deployment with `vercel.json`.

### Backend
Deploy the Python backend using any ASGI-compatible hosting:
- Railway
- Render
- DigitalOcean App Platform
- AWS Lambda with Mangum

## 📄 License

MIT License - see LICENSE file for details.
