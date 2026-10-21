# 🚀 TaskFlow

### Organize Your Tasks. Simplify Your Workflow.

TaskFlow is a minimal, well-documented To-Do application built with the MERN stack. It combines a React + Vite frontend, an Express backend, and MongoDB for persistent task storage.

The project is designed to be easy to run locally, understand, and extend — whether you're exploring full-stack development or making your first open-source contribution.

![Node.js](https://img.shields.io/badge/Node.js-18%2B-brightgreen)
![React](https://img.shields.io/badge/React-18-blue)
![Vite](https://img.shields.io/badge/Vite-5.4-purple)
![MongoDB](https://img.shields.io/badge/Database-MongoDB-green)
![License](https://img.shields.io/badge/License-MIT-green)

---

## ✨ Features

- 📝 **Create Tasks** — Add new tasks using a simple input interface.
- 📋 **List Tasks** — View tasks in reverse chronological order, with the newest first.
- 🗑️ **Delete Tasks** — Remove tasks when they are no longer needed.
- 💾 **Persistent Storage** — Store tasks in MongoDB using Mongoose.
- 🔌 **REST API** — Use the `/api/todos` endpoints to communicate with the backend.
- ⚡ **Fast Development** — Build and develop with React and Vite.
- 🧩 **Simple Codebase** — Explore a focused full-stack application suitable for learning and experimentation.
- 🤝 **Open-Source Friendly** — Contribute documentation improvements, bug fixes, and useful enhancements.

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| React | Frontend user interface |
| Vite | Frontend development and build tooling |
| TypeScript | Type-safe frontend development |
| Tailwind CSS | Utility-first styling |
| Node.js | JavaScript runtime |
| Express.js | Backend server and REST API |
| MongoDB | Database for persistent storage |
| Mongoose | MongoDB object modeling |
| dotenv | Environment variable management |

## 📁 Project Structure

```text
TaskFlow/
├── App/
│   ├── src/
│   │   ├── App.tsx
│   │   ├── main.tsx
│   │   └── index.css
│   ├── server/
│   │   ├── config/
│   │   │   └── db.js
│   │   ├── models/
│   │   │   └── Todo.js
│   │   └── server.js
│   └── package.json
└── README.md
```

This tree illustrates the main documented files. Refer to the actual repository for the complete directory structure.

## 🚀 Getting Started

### Prerequisites

Before running TaskFlow, make sure you have:

- [Node.js](https://nodejs.org/) installed
- npm installed
- Git installed
- Access to a MongoDB database, either locally or through [MongoDB Atlas](https://www.mongodb.com/atlas)

### 1. Clone the Repository

```bash
git clone https://github.com/SouravDhumal/TaskFlow.git
cd TaskFlow
```

### 2. Set Up the Backend

Navigate to the backend directory:

```bash
cd App/server
npm install
```

Create a `.env` file inside `App/server/`:

```env
MONGODB_URI=your-mongodb-connection-string
PORT=5000
```

Replace the placeholder with your actual MongoDB connection string.

Start the backend using the development script defined in the backend's `package.json`. For example, if the project defines a `dev` script:

```bash
npm run dev
```

The API is expected to be available at `http://localhost:5000/api/todos` when the server is running on port 5000.

### 3. Set Up the Frontend

Open a separate terminal and navigate to the frontend directory:

```bash
cd App
npm install
npm run dev
```

Vite will display the local development URL in the terminal, usually `http://localhost:5173`.

Open that URL in your browser to access TaskFlow.

> **Note:** Confirm the actual npm scripts, folder layout, and frontend API configuration in the repository before running these commands. Use the scripts provided by the project.

## 🔌 API Documentation

TaskFlow exposes a REST API under `/api/todos`.

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/todos` | Retrieve tasks, newest first |
| POST | `/api/todos` | Create a task |
| DELETE | `/api/todos/:id` | Delete a task by ID |

### Create a Task

**Endpoint:** `POST /api/todos`

Example request body:

```json
{
  "text": "Complete my project"
}
```

The `text` field contains the task description.

### Retrieve Tasks

**Endpoint:** `GET /api/todos`

Returns the stored tasks as JSON.

### Delete a Task

**Endpoint:** `DELETE /api/todos/:id`

Replace `:id` with the ID of the task to delete.

> These examples document the expected API contract. Verify response formats and error handling against the current backend implementation.

## 🧠 How It Works

### Data Model

The `Todo` model, documented at `App/server/models/Todo.js`, contains:

- `text` — A required string containing the task description.
- `createdAt` — A date timestamp that defaults to the current time.

### API Flow

1. The React frontend sends a request to the `/api/todos` endpoint.
2. Express handles the request.
3. Mongoose reads or writes the task in MongoDB.
4. The backend returns a JSON response.
5. The frontend renders the resulting task list.

The main server file is documented as `App/server/server.js`. Check the repository for the exact implementation.

## 🔐 Environment & Security

Keep database credentials and other secrets out of version control.

- Store local configuration in `App/server/.env`.
- Never commit actual database passwords, API keys, or secret values.
- Ensure `.env` is excluded through `.gitignore`.
- Configure production environment variables through your hosting provider.
- Never share private connection strings in issues or pull requests.

Example local configuration:

```env
MONGODB_URI=your-mongodb-connection-string
PORT=5000
```

No external third-party API is required for the core task-management functionality documented here.

## 🌍 Deployment

TaskFlow can be deployed using separate frontend and backend hosting, or through a combined deployment where supported.

### Frontend

Build the frontend using the project's configured build script:

```bash
cd App
npm run build
```

Deploy the generated static files to a compatible static hosting service, such as Vercel or Netlify.

### Backend

Deploy the Express API to a compatible Node.js hosting provider, such as Render, Railway, or DigitalOcean App Platform.

Configure `MONGODB_URI` and any other required environment variables in the hosting dashboard.

### Database

Use a secured MongoDB database and configure network access and credentials for your deployment environment.

Before deploying, verify the production API URL, CORS configuration, frontend environment settings, and database connectivity.

*These are deployment options; they do not imply that a live TaskFlow instance is currently available.*

## 🤝 Contributing

Contributions are welcome! TaskFlow is a good place to learn about full-stack development, documentation, Git, and collaborative software development.

### Ways to Contribute

- 🐛 Report bugs and unexpected behaviour.
- 📝 Improve documentation and setup instructions.
- 🎨 Enhance the user interface and accessibility.
- ✨ Suggest or implement useful features.
- 🧹 Improve code readability and maintainability.
- 🧪 Add tests and improve error handling.

### Contribution Workflow

**1. Fork the repository**

Create a fork of TaskFlow using GitHub's Fork button.

**2. Clone your fork**

```bash
git clone https://github.com/YOUR_USERNAME/TaskFlow.git
cd TaskFlow
```

Replace `YOUR_USERNAME` with your GitHub username.

**3. Create a feature branch**

```bash
git checkout -b feature/your-feature-name
```

For bug fixes, you can use a branch such as:

```bash
git checkout -b fix/describe-the-bug
```

**4. Make your changes**

Follow the existing project structure and keep changes focused.

**5. Test your changes**

Run the relevant checks available in the project and manually test affected functionality.

**6. Commit your changes**

```bash
git add README.md
git commit -m "docs: improve README documentation"
```

**7. Push your branch**

```bash
git push origin feature/your-feature-name
```

Replace the branch name if you used a different one.

**8. Open a Pull Request**

Open your fork on GitHub and create a pull request against the original repository's `main` branch.

Explain what you changed, why it is useful, and how you tested it.

### Pull Request Checklist

- [ ] The changes address a clear improvement.
- [ ] Relevant functionality has been tested.
- [ ] Documentation is accurate and up to date.
- [ ] No credentials or `.env` files have been committed.
- [ ] The pull request describes the changes clearly.

Please check existing issues and contribution guidelines before starting work to avoid duplicate effort.

## 🗺️ Future Improvements

Potential enhancements include:

- [ ] Edit existing tasks.
- [ ] Mark tasks as completed or pending.
- [ ] Add task priorities and due dates.
- [ ] Introduce search, filtering, and sorting.
- [ ] Improve loading, empty, and error states.
- [ ] Add automated frontend and backend tests.
- [ ] Improve responsive design and accessibility.
- [ ] Introduce authentication and personal task lists.

These are ideas for future development, not claims that the features are already implemented. Check existing issues before starting work.

## 🐛 Troubleshooting

**MongoDB connection fails**

- Check the `MONGODB_URI` value.
- Confirm that your database is running or reachable.
- Verify your MongoDB credentials and network access settings.

**Frontend cannot reach the API**

- Confirm that the backend is running.
- Check the configured API URL and server port.
- Inspect the browser console and network requests for errors.

**`npm run dev` fails**

- Confirm that you are in the correct directory.
- Run `npm install`.
- Check the scripts defined in the relevant `package.json`.

**Tasks do not persist**

- Confirm that MongoDB is connected.
- Inspect backend logs for database errors.
- Check the API response in your browser's developer tools.

## 🙏 Acknowledgements

TaskFlow builds on the work of the open-source communities behind:

- [React](https://react.dev/)
- [Vite](https://vite.dev/)
- [TypeScript](https://www.typescriptlang.org/)
- [Tailwind CSS](https://tailwindcss.com/)
- [Node.js](https://nodejs.org/)
- [Express.js](https://expressjs.com/)
- [MongoDB](https://www.mongodb.com/)
- [Mongoose](https://mongoosejs.com/)

Thanks to everyone who uses, tests, and contributes to the project.

## 📄 License

Please refer to the repository's existing `LICENSE` file for the applicable licensing terms.

## ⭐ Support

If you find TaskFlow useful, consider giving the repository a star ⭐

Found a bug or have an idea? Check the existing issues or open a new one with clear details.

**Let's make TaskFlow better together!** 🚀
