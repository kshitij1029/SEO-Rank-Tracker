# SEO Rank Tracker

A full-stack SEO monitoring platform for analysing website SEO health, tracking keyword rankings, and reviewing ranking history through a dashboard.

## Features

- **SEO website analysis** — inspect important on-page SEO elements, including page titles, meta descriptions, canonical and robots directives, headings, social metadata, links, and image alt text.
- **Keyword rank tracking** — monitor keyword positions for a target domain across Google search results.
- **Ranking history** — store and review historical ranking data over time.
- **Competitor insights** — identify other domains appearing in tracked search results.
- **AI-powered recommendations** — use Google Gemini to help explain SEO findings and suggest improvements.
- **Automated tracking** — scheduled jobs periodically refresh tracked keyword rankings.
- **Authentication** — user accounts with JWT-based authentication.

## Tech Stack

| Area | Technologies |
|---|---|
| Frontend | React, TypeScript, Vite, Tailwind CSS, React Router, Axios |
| Backend | Node.js, Express |
| Database | MongoDB, Mongoose |
| Browser automation | Browserbase, Playwright |
| AI | Google Gemini |
| Authentication | JWT, bcrypt |
| Scheduling | node-cron |

## Project Structure

```text
SEO-Rank-Tracker/
├── client/          # React + TypeScript frontend
└── server/          # Express API, database models and services
    ├── config/
    ├── controllers/
    ├── cron/
    ├── middleware/
    ├── models/
    ├── routes/
    └── services/
```

## Getting Started

### Prerequisites

- Node.js (use a current LTS release)
- npm
- MongoDB connection string
- Browserbase credentials for browser-based search/website automation
- Google Gemini API key for AI-powered analysis

### 1. Clone the repository

```bash
git clone https://github.com/kshitij1029/SEO-Rank-Tracker.git
cd SEO-Rank-Tracker
```

### 2. Configure the backend

```bash
cd server
npm install
```

Create a `.env` file in the `server/` directory and add the environment variables required by the backend. At minimum, configure your MongoDB connection string (`MONGODB_URI`), JWT signing secret, Browserbase credentials, and Gemini API key. Use the exact variable names referenced by the server configuration and services.

### 3. Configure the frontend

Open a second terminal:

```bash
cd client
npm install
```

If the frontend API base URL is environment-configured, create `client/.env` and set it to the URL where your backend API is running. Check the frontend configuration for the expected variable name.

### 4. Run the application

Start the backend:

```bash
cd server
npm run server
```

Start the frontend in another terminal:

```bash
cd client
npm run dev
```

The backend defaults to port `5000` unless `PORT` is configured. Vite prints the local frontend URL in the terminal.

## Available Scripts

### Client

| Command | Description |
|---|---|
| `npm run dev` | Start the Vite development server |
| `npm run build` | Type-check and build the frontend |
| `npm run lint` | Run ESLint |
| `npm run preview` | Preview the production build |

### Server

| Command | Description |
|---|---|
| `npm run server` | Start the backend with nodemon |
| `npm start` | Start the backend with Node.js |

## API Route Groups

The Express application mounts these API route groups:

- `/api/auth` — authentication
- `/api/rank` — keyword ranking and tracking
- `/api/analysis` — website SEO analysis

## Notes

- Keep API keys, database credentials, and JWT secrets out of source control.
- Do not commit your local `.env` files.
- Search rankings can vary by location, language, device, and time. Treat tracked positions as snapshots of the configured search results, not guaranteed universal rankings.
- Browser automation and AI analysis depend on the availability and limits of their external providers.
