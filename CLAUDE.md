# CLAUDE.md

This file provides guidance to Claude Code when working with code in this repository.

## Project Overview

A full-stack starter template combining React + Vite for the frontend with FastAPI for the backend. Designed for rapid prototyping -- hackathons, college projects, and quick MVPs. Includes comprehensive README with setup and usage documentation.

## Tech Stack

### Frontend
- **Language**: TypeScript
- **Framework**: React 18 + Vite 5
- **Routing**: React Router
- **Styling**: Tailwind CSS
- **Linting**: ESLint with Vite + React plugins

### Backend
- **Language**: Python 3
- **Framework**: FastAPI 0.115.5
- **ORM**: SQLAlchemy
- **Database**: PostgreSQL
- **Config**: python-dotenv

## Project Structure

```
react-vite-fastapi-starter/
├── package.json                 # Root -- concurrently runner
├── frontend/
│   ├── package.json             # Vite + React dependencies
│   ├── vite.config.ts           # Vite configuration
│   ├── src/
│   │   ├── components/          # React components
│   │   ├── pages/               # Page components
│   │   └── App.tsx              # Root component
│   └── public/                  # Static assets
├── backend/
│   ├── requirements.txt         # Python dependencies
│   ├── app/
│   │   ├── main.py              # FastAPI entry point
│   │   ├── models/              # SQLAlchemy models
│   │   └── routes/              # API route handlers
│   └── .env                     # Backend environment variables
├── README.md                    # Comprehensive setup documentation
└── .github/workflows/
    └── claude.yml               # Claude Code Actions workflow
```

## Development Commands

```bash
# Run both frontend and backend
npm run dev:all

# Frontend only
cd frontend
npm install
npm run dev                  # Vite dev server (http://localhost:5173)
npm run build                # Production build
npm run lint                 # ESLint check
npm run preview              # Preview build

# Backend only
cd backend
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
uvicorn app.main:app --reload    # FastAPI (http://localhost:8000)
```

## Environment & Config

### Backend (.env)
```bash
DATABASE_URL=postgresql://user:pass@localhost:5432/dbname
SECRET_KEY=<your-secret-key>
```

- Frontend environment variables: prefix with `VITE_` in `frontend/.env`
- Never commit `.env` files

## Code Style & Standards

### Frontend
- TypeScript strict mode
- ESLint with Vite + React plugins
- Tailwind CSS utility classes
- Component-based architecture with React Router

### Backend
- FastAPI dependency injection
- SQLAlchemy ORM patterns
- Async route handlers
- No Python linter configured (consider adding ruff)

## Architecture Notes

- Frontend proxies API requests to backend (configured in Vite)
- Backend serves REST API endpoints
- SQLAlchemy handles database schema and queries
- `concurrently` package runs both frontend and backend from root `package.json`
- Template is intentionally minimal -- extend as needed

## Troubleshooting

- CORS errors: Check FastAPI CORS middleware configuration
- Database connection: Verify PostgreSQL is running and DATABASE_URL is correct
- Frontend proxy issues: Check Vite proxy config in `vite.config.ts`
- Port conflicts: Frontend uses 5173, backend uses 8000
