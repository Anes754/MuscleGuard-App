# MuscleGuard AI — Full Stack App

## Stack
- Frontend: HTML + CSS + JS (Plotly.js for charts)
- Backend:  FastAPI (Python)
- Database: MongoDB (Motor async driver)

## Folder Structure
muscleguard/
├── backend/
│   ├── main.py            ← FastAPI app
│   ├── schemas.py         ← Pydantic models
│   ├── model.py           ← ML predictor
│   ├── database.py        ← MongoDB helper
│   ├── requirements.txt
│   ├── .env               ← MONGO_URL config
│   └── muscle_loss_model.pkl  ← place your model here
│
└── frontend/
    ├── index.html         ← Page 1: Profile
    ├── workouts.html      ← Page 2: Workout Data
    ├── results.html       ← Page 3: AI Results
    ├── plan.html          ← Page 4: Workout Plan
    ├── css/style.css
    └── js/api.js

## Setup

### 1. Install MongoDB
Download from: https://www.mongodb.com/try/download/community
Or use MongoDB Atlas (free cloud): https://cloud.mongodb.com

### 2. Backend setup
cd backend
pip install -r requirements.txt
# Copy your muscle_loss_model.pkl into backend/
# Edit .env and set your MONGO_URL
python main.py

### 3. Frontend setup
Open frontend/index.html in your browser
OR use Live Server in VS Code

### 4. MongoDB Atlas (cloud) setup
1. Go to cloud.mongodb.com
2. Create free cluster
3. Get connection string
4. Paste into backend/.env as:
   MONGO_URL=mongodb+srv://user:pass@cluster.mongodb.net/

## API Endpoints
POST /predict      - Run ML prediction
POST /save         - Save result to MongoDB
GET  /history/{id} - Get user history
