# AI Resume Builder

An AI-assisted full-stack resume builder that helps users create, edit, and manage professional resumes with section-based customization, modern templates, and export-friendly preview flows.

## Project Structure

```text
AI-RESUME-BUILDER/
├── ResumeBuilder/   # Frontend (React + Vite)
└── Backend/         # API server (Express + MongoDB)
```

## Features

- Authentication with Clerk.
- Dashboard for creating and managing multiple resumes.
- Resume editor with configurable sections:
  - Personal details
  - Summary
  - Experience
  - Education
  - Skills
  - Projects
  - Achievements
- Live resume preview with template options.
- Drag-and-drop section organization.
- AI integration (Gemini/LLM service hooks in frontend services).
- CRUD backend APIs for resume data.

## Tech Stack

### Frontend (`ResumeBuilder`)

- React 18 + Vite
- React Router
- Clerk auth
- Tailwind CSS
- Framer Motion
- Axios

### Backend (`Backend`)

- Node.js + Express
- MongoDB + Mongoose
- CORS + dotenv

## Prerequisites

- Node.js 18+
- npm
- MongoDB connection string
- Clerk project credentials
- Google Generative AI key (optional for AI features)

## Environment Variables

Create these files before running the app.

### `Backend/.env`

```env
DATABASE_URL=<your_mongodb_connection_string>
PORT=4000
```

### `ResumeBuilder/.env`

```env
VITE_CLERK_PUBLISHABLE_KEY=<your_clerk_publishable_key>
VITE_GOOGLE_AI_API_KEY=<your_google_ai_api_key>
```

## Installation

Install dependencies for both apps:

```bash
cd ResumeBuilder && npm install
cd ../Backend && npm install
```

## Run Locally

Open two terminals.

### 1) Start backend

```bash
cd Backend
npm run dev
```

Backend runs on `http://localhost:4000` by default.

### 2) Start frontend

```bash
cd ResumeBuilder
npm run dev
```

Frontend runs on the Vite dev URL (typically `http://localhost:5173`).

## API Endpoints (Backend)

Base route: `/api/v1`

- `POST /resume` – Create a resume
- `GET /resumes?userEmail=<email>` – Get resumes by user email
- `GET /resume?resumeid=<id>` – Get a single resume by resume ID
- `PUT /resume` – Update a resume
- `DELETE /resume/:resumeid` – Delete a resume

## Available Scripts

### Frontend (`ResumeBuilder`)

- `npm run dev` – Start dev server
- `npm run build` – Build for production
- `npm run preview` – Preview production build
- `npm run lint` – Run ESLint

### Backend (`Backend`)

- `npm run dev` – Start with nodemon
- `npm start` – Start with node

## Notes

- The frontend currently includes API calls to a hosted backend URL in several components. If you run everything locally, update those URLs to your local backend base URL where needed.
- Keep all secrets in environment variables and avoid committing API keys.

## License

This project is licensed under the terms in `LICENCE`.
