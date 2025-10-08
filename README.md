# Gym Performance Tracker

A full-stack web application for tracking gym performance and workouts.

## Tech Stack

### Frontend
- React 18
- TypeScript
- Vite
- React Router
- Axios

### Backend
- Node.js
- Express
- TypeScript
- SQLite with better-sqlite3

## Project Structure

```
gym-tracker/
├── frontend/          # React frontend application
│   ├── src/
│   ├── package.json
│   └── vite.config.ts
├── backend/           # Express backend API
│   ├── src/
│   ├── package.json
│   └── tsconfig.json
└── package.json       # Root package.json for monorepo
```

## Getting Started

### Installation

Install all dependencies for both frontend and backend:

```bash
npm run install:all
```

Or install individually:

```bash
# Install root dependencies
npm install

# Install frontend dependencies
cd frontend && npm install

# Install backend dependencies
cd backend && npm install
```

### Development

Run both frontend and backend concurrently:

```bash
npm run dev
```

Or run them separately:

```bash
# Run frontend (on port 5173)
npm run dev:frontend

# Run backend (on port 3000)
npm run dev:backend
```

### Build

Build both applications:

```bash
npm run build
```

## Current Status

This is a minimal skeleton/boilerplate with infrastructure in place. The project is ready for development but has no gym tracking features implemented yet.

### What's Implemented

**Frontend:**
- Basic React placeholder with "Gym Performance Tracker" heading
- Simple counter button demo (no real functionality)
- No routing, forms, or UI components yet

**Backend:**
- Single API endpoint: `GET /api/health` - Health check only
- No CRUD operations implemented
- CORS enabled for frontend communication

**Database:**
- SQLite database initialized with complete schema
- All tables created and ready to use

### What's Missing

- All API endpoints (users, exercises, workouts CRUD operations)
- Authentication/user management
- Frontend UI components and pages
- Business logic and database queries
- Forms for data entry
- Data visualization/analytics

## API Endpoints

Currently implemented:
- `GET /api/health` - Health check endpoint

## Database Schema

The application uses SQLite with the following tables:

### users
- `id` - Primary key
- `username` - Unique username
- `email` - Unique email address
- `created_at` - Timestamp

### exercises
- `id` - Primary key
- `name` - Exercise name
- `category` - Exercise category (e.g., strength, cardio)
- `description` - Optional description
- `created_at` - Timestamp

### workouts
- `id` - Primary key
- `user_id` - Foreign key to users table
- `date` - Workout date
- `notes` - Optional workout notes
- `created_at` - Timestamp

### workout_exercises
Junction table linking workouts to exercises:
- `id` - Primary key
- `workout_id` - Foreign key to workouts table
- `exercise_id` - Foreign key to exercises table
- `sets` - Number of sets performed
- `reps` - Number of repetitions per set
- `weight` - Weight used (optional)
- `notes` - Optional exercise notes

## License

MIT
