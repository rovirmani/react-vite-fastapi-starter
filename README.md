# react-vite-fastapi-starter

A modern full-stack starter template using React + Vite for the frontend and FastAPI for the backend. Perfect for hackathons, college projects, and quick prototypes.

## Features

- **Frontend**
  - React 18 with Vite for fast development
  - React Router for navigation
  - Tailwind CSS for styling
  - Axios for API requests
  - Environment variable support

- **Backend**
  - FastAPI for high-performance API
  - CORS configuration
  - Environment variable support
  - Modular route structure

## Getting Started

### Prerequisites
- Python 3.8+
- Node.js 16+
- npm or yarn

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/react-vite-fastapi-starter.git
cd react-vite-fastapi-starter
```

2. Set up the backend:
```bash
cd backend
python -m venv venv
source venv/bin/activate  # On Windows: .\venv\Scripts\activate
pip install -r requirements.txt
```

3. Set up the frontend:
```bash
cd frontend
npm install
```

4. Set up environment variables:
```bash
# In frontend directory
cp .env.example .env

# In backend directory
cp .env.example .env
```

### Development

Start both frontend and backend servers with a single command:
```bash
cd frontend
npm run dev:all
```

Or run them separately:

Frontend:
```bash
cd frontend
npm run dev
```

Backend:
```bash
cd backend
uvicorn app.main:app --reload
```

The frontend will be available at http://localhost:5173
The backend API will be available at http://localhost:8000

## Project Structure
```
.
├── backend/
│   ├── app/
│   │   ├── __init__.py
│   │   ├── main.py          # FastAPI app configuration
│   │   ├── api/             # API routes
│   │   └── core/            # Core functionality
│   ├── .env.example         # Example environment variables
│   └── requirements.txt     # Python dependencies
├── frontend/
│   ├── src/
│   │   ├── App.jsx         # Main React component
│   │   ├── main.jsx        # React entry point
│   │   └── index.css       # Global styles
│   ├── .env.example        # Example environment variables
│   ├── package.json        # Node dependencies
│   └── tailwind.config.js  # Tailwind configuration
└── README.md
```

## Environment Variables

### Frontend (.env)
- `VITE_API_URL`: Backend API URL (default: http://localhost:8000/api)

### Backend (.env)
- `PORT`: Server port (default: 8000)
- `HOST`: Host address (default: 0.0.0.0)
- `CORS_ORIGINS`: Allowed frontend origins (default: http://localhost:5173)

## Next Steps

Here are some common additions you might want to consider based on your project needs:

1. **Database Integration**
   - PostgreSQL with SQLAlchemy
   - MongoDB
   - Supabase
   - Firebase

2. **Authentication**
   - JWT authentication
   - OAuth2 with social logins
   - Session-based auth

3. **Additional Frontend Features**
   - State management (Redux, Zustand)
   - Form handling (React Hook Form, Formik)
   - UI components (shadcn/ui, Material-UI)

4. **Deployment**
   - Vercel 
   - Railway
   - Heroku
   - Render
   - and many more

5. **Testing**
   - Frontend: Jest, React Testing Library
   - Backend: pytest

## Common Use Cases

This starter is perfect for:
- College projects requiring a full-stack application
- Hackathon projects needing quick setup
- MVPs and prototypes
- Learning full-stack development

## Contributing

Feel free to open issues and pull requests!

## License

MIT License - feel free to use this starter for any project!
