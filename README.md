# MERN Todo List (Basic)

A minimal Todo app using the MERN stack:

- Frontend: React (Vite) in `src/`
- Backend: Node/Express in `server/`
- Database: MongoDB

No external URLs/APIs are used.

# MERN Todo List

A minimal, well-documented To‑Do application built with the MERN stack (React + Vite frontend, Express backend, MongoDB database). This repository contains a small, production-ready example you can run locally or deploy.

[![Node.js](https://img.shields.io/badge/Node.js-18+-brightgreen.svg)](https://nodejs.org/)
[![React](https://img.shields.io/badge/React-18-blue.svg)](https://reactjs.org/)
[![Vite](https://img.shields.io/badge/Vite-5.4.2-lightgrey.svg)](https://vitejs.dev/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-%2347A248.svg)](https://www.mongodb.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

## 🌟 Features

- Create new todos with a simple input
- List todos (newest first)
- Delete todos
- Persistent storage using MongoDB (via Mongoose)
- Small, focused REST API (`/api/todos`) that the React frontend consumes
- Fast frontend dev experience powered by Vite + React
- Tiny codebase suitable for learning, demos, and Hacktober contributions

## 🛠️ Technology Stack

- Frontend: React + Vite + TypeScript
- Styling: Tailwind CSS (configured in the project)
- Backend: Node.js + Express
- Database: MongoDB (Mongoose ODM)
- Dev tools: dotenv, nodemon-like watch via `node --watch`

## 📋 Prerequisites

- Node.js 18+ and npm
- A MongoDB connection string (MongoDB Atlas or local)

## 🚀 Quick Start

Follow these steps to run the project locally. There are two parts: the backend API and the frontend app. Both live under the `App/` folder.

### 1. Clone the Repository

First, clone the repository and navigate to the project directory:

```bash
git clone https://github.com/debugfest/mern-todo-list.git
cd mern-todo-list
```

### 2. Backend (API)

Open a terminal and run:

```bash
cd App/server
npm install
# Create a .env file in App/server with at least:
# MONGODB_URI='your-mongodb-connection-string'
# PORT=5000     # optional, defaults to 5000

# Start the server in watch mode
npm run dev
```

The API endpoints will be available at http://localhost:5000/api/todos by default.

Available endpoints:

- GET /api/todos — fetch all todos (sorted newest first)
- POST /api/todos — create a todo (body: `{ "text": "..." }`)
- DELETE /api/todos/:id — delete a todo by id

### 3. Frontend (React + Vite)

Open another terminal and run:

```bash
cd App
npm install
npm run dev
```

Vite will print the local dev URL (usually http://localhost:5173). Open it to use the app.

## 📁 Project Structure

```
mern-todo-list/
├─ App/                      # Frontend + backend (single folder for demo)
│  ├─ src/                   # React + TypeScript app (Vite)
│  │  ├─ App.tsx
│  │  ├─ main.tsx
│  │  └─ index.css
│  ├─ server/                # Express API
│  │  ├─ config/db.js        # MongoDB connection helper
│  │  ├─ models/Todo.js      # Mongoose schema for todos
│  │  └─ server.js           # Express routes and server boot
│  └─ package.json           # Frontend deps & scripts (Vite)
├─ README.md                 # <-- this file
├─ LICENSE
└─ CONTRIBUTING.md
```

## 🧠 How it works

### Data Model

The `Todo` model (see `App/server/models/Todo.js`) has:

- `text` (String, required) — the task description
- `createdAt` (Date) — timestamp, defaults to now

### API Flow

1. Frontend calls the REST API under `/api/todos`.
2. The backend (Express) uses Mongoose to read/write documents in MongoDB.
3. Todos are returned to the client as JSON and rendered in the React UI.

The main server file is `App/server/server.js` and exposes the routes listed in "Quick Start".

## 🔒 Environment & Security

- Keep your MongoDB connection string and other secrets out of version control. Add `App/server/.env` to your local environment (it's already listed as local-only in the repo).
- Example `.env`:

```env
MONGODB_URI='your-mongodb-connection-string'
PORT=5000
```

## 📦 Deployment

Local development is covered above. For production you can:

- Build the frontend with `cd App && npm run build` and serve the static files from a static host (Vercel, Netlify, or a simple Express static server).
- Deploy the API to a Node host (Render, Railway, DigitalOcean App Platform). Make sure to set `MONGODB_URI` in the host's environment settings.
- Optionally combine by serving the frontend build from the Express server and running the combined app on a single host.

## 🤝 Contributing

Contributions are welcome — small improvements, bug fixes, styling, and documentation all help!

How to contribute:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/awesome`)
3. Commit your changes (`git commit -m "Add awesome feature"`)
4. Push (`git push origin feature/awesome`)
5. Open a Pull Request

Please follow the guidelines in `CONTRIBUTING.md`.

## 🙏 Acknowledgments

- Express for the lightweight server framework
- Mongoose for easy MongoDB modeling
- Vite + React for a fast frontend dev experience
- Tailwind CSS for utility-first styling

---

If you found this project helpful, please give it a star ⭐

Made with ❤️ by the project contributors
