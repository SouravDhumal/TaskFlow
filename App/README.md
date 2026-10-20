# TaskFlow

A full-stack To-Do application built with the MERN stack (MongoDB, Express.js, React, Node.js). This app allows users to add and delete tasks with a clean, minimal interface designed for desktop use.

## 🚀 Tech Stack

### Frontend
- **React.js** (with Vite)
- **TypeScript**
- **Tailwind CSS** for styling
- **Axios** for HTTP requests
- **Lucide React** for icons

### Backend
- **Node.js**
- **Express.js**
- **MongoDB** (with Mongoose ODM)
- **CORS** for cross-origin requests
- **dotenv** for environment variables

## 📁 Folder Structure

```
project/
├── src/                    # Frontend React application
│   ├── App.tsx            # Main React component
│   ├── main.tsx           # React entry point
│   └── index.css          # Global styles
├── server/                 # Backend Express server
│   ├── config/
│   │   └── db.js          # MongoDB connection
│   ├── models/
│   │   └── Todo.js        # Todo Mongoose model
│   ├── server.js          # Express server and API routes
│   ├── package.json       # Backend dependencies
│   └── .env               # Environment variables
├── package.json           # Frontend dependencies
└── README.md              # This file
```

## ✨ Features

- ✅ Add new to-do tasks
- ✅ Delete existing tasks
- ✅ Real-time updates
- ✅ Clean and minimal UI
- ✅ RESTful API architecture
- ✅ MongoDB database persistence

## 🔧 Setup Instructions

### Prerequisites

- Node.js (v16 or higher)
- npm or yarn
- MongoDB Atlas account (or local MongoDB installation)

### Step 1: Clone the Repository

```bash
git clone <repository-url>
cd project
```

### Step 2: Configure MongoDB

1. Open `server/.env` file
2. Replace `<db_password>` with your actual MongoDB password:

```env
MONGODB_URI=mongodb+srv://mokshjaindev_db_user:YOUR_PASSWORD@cluster0.sc3tiok.mongodb.net/?retryWrites=true&w=majority&appName=Cluster0
PORT=5000
```

### Step 3: Install Dependencies

#### Install Frontend Dependencies
```bash
npm install
```

#### Install Backend Dependencies
```bash
cd server
npm install
cd ..
```

### Step 4: Run the Application

You need to run both the frontend and backend servers:

#### Option 1: Run in Separate Terminals

**Terminal 1 - Start Backend Server:**
```bash
cd server
npm start
```
Backend will run on http://localhost:5000

**Terminal 2 - Start Frontend:**
```bash
npm run dev
```
Frontend will run on http://localhost:3000

#### Option 2: Run Concurrently (if you install concurrently)

Install concurrently:
```bash
npm install -g concurrently
```

Then run both servers:
```bash
concurrently "cd server && npm start" "npm run dev"
```

### Step 5: Access the Application

Open your browser and navigate to:
```
http://localhost:3000
```

## 🔌 API Endpoints

The backend exposes the following RESTful API endpoints:

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/todos` | Fetch all to-dos |
| POST | `/api/todos` | Add a new to-do |
| DELETE | `/api/todos/:id` | Delete a specific to-do |

### Example API Requests

**Get all todos:**
```bash
curl http://localhost:5000/api/todos
```

**Add a new todo:**
```bash
curl -X POST http://localhost:5000/api/todos \
  -H "Content-Type: application/json" \
  -d '{"text":"Buy groceries"}'
```

**Delete a todo:**
```bash
curl -X DELETE http://localhost:5000/api/todos/TASK_ID
```

## 🎨 UI Features

- Clean gradient background
- Card-based layout
- Hover effects on tasks
- Smooth transitions
- Empty state messaging
- Task counter
- Keyboard support (press Enter to add task)

## 🛠️ Development Scripts

### Frontend
```bash
npm run dev        # Start development server
npm run build      # Build for production
npm run preview    # Preview production build
npm run lint       # Run ESLint
```

### Backend
```bash
npm start          # Start server
npm run dev        # Start with auto-reload (if configured)
```

## 📝 Code Comments

The codebase includes clear comments explaining:
- Component structure and logic
- API endpoint functionality
- Database schema definition
- MongoDB connection setup
- State management

## 🔒 Environment Variables

### Backend (.env)
```
MONGODB_URI=your_mongodb_connection_string
PORT=5000
```

## 🐛 Troubleshooting

### MongoDB Connection Issues
- Verify your MongoDB connection string is correct
- Ensure your IP address is whitelisted in MongoDB Atlas
- Check that your database user has proper permissions

### CORS Errors
- Ensure the backend is running on port 5000
- Verify CORS is enabled in `server.js`

### Port Already in Use
```bash
# Kill process on port 5000
lsof -ti:5000 | xargs kill -9

# Kill process on port 3000
lsof -ti:3000 | xargs kill -9
```


