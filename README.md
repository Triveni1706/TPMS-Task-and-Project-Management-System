Optimized tool selection

Read [](file:///d%3A/Projects/project-management)

Read [](file:///d%3A/Projects/project-management/frontend/package.json)

Read [](file:///d%3A/Projects/project-management/backend/package.json)

Here's a comprehensive expanded README with more detailed information:

---

# 📋 TPMS – Task & Project Management System

A full-stack **MERN** (MongoDB, Express, React, Node.js) application designed for seamless team, project, and task management workflows. Perfect for organizations needing centralized task tracking, team collaboration, and progress monitoring.

## 🚀 Features

### Manager Features
- **Dashboard**: Comprehensive overview of all projects and team activities
- **Team Management**: Create and manage multiple teams within the organization
- **Project Management**: Create, organize, and track projects across teams
- **Task Assignment**: Assign tasks to team members with deadlines and descriptions
- **Progress Tracking**: Visual charts and analytics for project progress
- **Task Submission Review**: Review submitted tasks with file attachments

### Member Features
- **Task View**: See assigned tasks with detailed information
- **Task Submission**: Submit completed work with file uploads
- **Task Locking**: Automatic task locking after submission to prevent changes
- **Progress Dashboard**: Track personal task completion status

### Core Functionality
- **Role-Based Access Control**: Different permissions for Managers and Members
- **File Upload**: Members can upload project files (via Multer)
- **JWT Authentication**: Secure token-based authentication
- **Real-time Updates**: Live progress tracking with charts

## 🛠 Tech Stack

| Component | Technology | Version |
|-----------|-----------|---------|
| **Frontend** | React | 18.2.0 |
| **Frontend Build** | Vite | 5.0.0 |
| **Backend** | Node.js + Express | 5.2.1 |
| **Database** | MongoDB | (Latest) |
| **Authentication** | JWT (jsonwebtoken) | 9.0.3 |
| **Password Hashing** | bcryptjs | 3.0.3 |
| **File Upload** | Multer | 2.0.2 |
| **HTTP Client** | Axios | 1.6.0 |
| **Charts** | Chart.js + React-ChartJS-2 | 4.5.1 / 5.3.1 |
| **Routing** | React Router DOM | 6.22.0 |
| **CORS** | cors | 2.8.6 |

## 📁 Project Structure

```
project-management/
│
├── backend/                          # Node.js + Express Server
│   ├── config/
│   │   └── db.js                    # MongoDB connection configuration
│   ├── controllers/                  # Business logic handlers
│   │   ├── authController.js        # Authentication logic
│   │   ├── projectController.js     # Project CRUD operations
│   │   ├── taskController.js        # Task management
│   │   ├── teamController.js        # Team operations
│   │   ├── userController.js        # User management
│   │   └── reportController.js      # Progress & analytics reports
│   ├── middleware/                   # Express middleware
│   │   ├── authMiddleware.js        # JWT verification
│   │   ├── roleMiddleware.js        # Role-based access control
│   │   └── upload.js                # Multer file upload configuration
│   ├── models/                       # Mongoose schemas
│   │   ├── User.js
│   │   ├── Project.js
│   │   ├── Task.js
│   │   └── Team.js
│   ├── routes/                       # API endpoints
│   │   ├── authRoutes.js
│   │   ├── projectRoutes.js
│   │   ├── taskRoutes.js
│   │   ├── teamRoutes.js
│   │   ├── userRoutes.js
│   │   └── reportRoutes.js
│   ├── package.json
│   └── server.js                    # Entry point
│
├── frontend/                         # React + Vite Application
│   ├── public/                       # Static assets
│   ├── src/
│   │   ├── api/
│   │   │   └── axiosInstance.js     # Axios configuration with JWT
│   │   ├── auth/
│   │   │   ├── AuthContext.jsx      # Global authentication state
│   │   │   ├── ProtectedRoute.jsx   # Route protection wrapper
│   │   │   └── RoleRoute.jsx        # Role-based route protection
│   │   ├── components/               # Reusable UI components
│   │   │   ├── DashboardLayout.jsx
│   │   │   ├── Navbar.jsx
│   │   │   ├── TaskCard.jsx
│   │   │   ├── Loader.jsx
│   │   │   └── ManagerSidebar.jsx
│   │   ├── pages/
│   │   │   ├── Home.jsx
│   │   │   ├── Login.jsx
│   │   │   ├── Register.jsx
│   │   │   └── manager/              # Manager-specific pages
│   │   │       ├── ManagerDashboard.jsx
│   │   │       ├── CreateProject.jsx
│   │   │       ├── CreateTeamTest.jsx
│   │   │       ├── TeamDashboard.jsx
│   │   │       ├── ProjectsList.jsx
│   │   │       ├── TasksList.jsx
│   │   │       ├── TeamsList.jsx
│   │   │       ├── AssignTask.jsx
│   │   │       └── TrackProgress.jsx
│   │   │   └── member/               # Member-specific pages
│   │   │       └── MemberDashboard.jsx
│   │   ├── App.jsx
│   │   ├── main.jsx
│   │   ├── App.css
│   │   └── index.css
│   ├── index.html
│   ├── vite.config.js
│   ├── package.json
│   └── README.md
│
└── README.md                         # This file
```

## ⚙️ Installation & Setup

### Prerequisites
- **Node.js** (v14 or higher)
- **npm** or **yarn**
- **MongoDB** (local or Atlas connection string)
- **Git**

### Backend Setup

1. **Navigate to backend directory:**
   ```bash
   cd backend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Create `.env` file** in the backend directory:
   ```env
   PORT=5000
   MONGODB_URI=mongodb+srv://<username>:<password>@cluster.mongodb.net/<dbname>
   JWT_SECRET=your_secret_key_here
   NODE_ENV=development
   ```

4. **Start the server:**
   ```bash
   node server.js
   ```
   Server runs on `http://localhost:5000`

### Frontend Setup

1. **Navigate to frontend directory:**
   ```bash
   cd frontend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Create `.env` file** in the frontend directory:
   ```env
   VITE_API_URL=http://localhost:5000/api
   ```

4. **Start development server:**
   ```bash
   npm run dev
   ```
   Frontend runs on `http://localhost:5173`

## 🏃 Running the Application

### Development Mode

**Terminal 1 - Backend:**
```bash
cd backend
npm install  # First time only
node server.js
```

**Terminal 2 - Frontend:**
```bash
cd frontend
npm install  # First time only
npm run dev
```

### Production Build

**Frontend Build:**
```bash
cd frontend
npm run build
npm run preview
```

## 🔌 API Endpoints

### Authentication (`/api/auth`)
- `POST /register` - Register new user
- `POST /login` - User login
- `POST /logout` - User logout

### Users (`/api/users`)
- `GET /` - Get all users
- `GET /:id` - Get user by ID
- `PUT /:id` - Update user profile

### Teams (`/api/teams`)
- `POST /` - Create team
- `GET /` - Get all teams
- `GET /:id` - Get team details
- `PUT /:id` - Update team
- `DELETE /:id` - Delete team
- `POST /:id/members` - Add team members

### Projects (`/api/projects`)
- `POST /` - Create project
- `GET /` - Get all projects
- `GET /:id` - Get project details
- `PUT /:id` - Update project
- `DELETE /:id` - Delete project

### Tasks (`/api/tasks`)
- `POST /` - Create task
- `GET /` - Get all tasks
- `GET /:id` - Get task details
- `PUT /:id` - Update task
- `DELETE /:id` - Delete task
- `POST /:id/submit` - Submit task with file

### Reports (`/api/reports`)
- `GET /progress/:projectId` - Get project progress

## 📊 Key Concepts

### User Roles
- **Manager**: Can create teams, projects, assign tasks, and view progress
- **Member**: Can view assigned tasks, submit work, and upload files

### Task Lifecycle
1. Created by Manager
2. Assigned to Member
3. Member submits with file upload
4. Task becomes locked after submission
5. Manager can view submission and update status

### File Upload
- Members can upload files when submitting tasks
- Files are stored using Multer middleware
- File size limits are configurable in `middleware/upload.js`

## 🔐 Authentication & Security

- **JWT Tokens**: Secure token-based authentication
- **Password Hashing**: bcryptjs for password encryption
- **Role-Based Access Control**: Middleware enforces user permissions
- **Protected Routes**: Frontend routes are protected based on user role

## 📝 Environment Variables

### Backend `.env`
```env
PORT=5000
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
JWT_EXPIRE=7d
NODE_ENV=development
```

### Frontend `.env`
```env
VITE_API_URL=http://localhost:5000/api
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request



## 👩‍💻 Author

**Triveni Manjunath**

---

This expanded README provides a complete guide to the project structure, setup, features, and API documentation!