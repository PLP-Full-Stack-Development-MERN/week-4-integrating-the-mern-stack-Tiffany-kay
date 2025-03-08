# MERN Task Manager

## Project Overview
This is a full-stack task manager application built using the **MERN stack** (MongoDB, Express, React, Node.js). It allows users to create, view, update, and delete tasks. Each task includes a title, description, status, and due date. The project demonstrates the integration of a RESTful API with a React frontend, proper project structure, and state management.

---

## Features
- **Create, Read, Update, and Delete (CRUD) Tasks**
- RESTful API development using Express and MongoDB
- Frontend implementation with React and Tailwind CSS
- Dynamic state management using React hooks (useState, useEffect)
- Fully responsive design
- Backend deployed on **Render**
- Frontend deployed on **Vercel**

---

## Technologies Used
- **Backend:** Node.js, Express.js, MongoDB, Mongoose
- **Frontend:** React.js, Axios, Tailwind CSS
- **State Management:** React hooks
- **Deployment:** Render (backend), Vercel (frontend)

---

## Installation

### Prerequisites
1. Node.js installed on your system
2. MongoDB Atlas or a local MongoDB instance running

### Steps
1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd mern-task-manager
   ```

2. Set up the backend:
   ```bash
   cd backend
   npm install
   ```
   - Create a `.env` file and add:
     ```
     MONGO_URI=mongodb+srv://<username>:<password>@cluster.mongodb.net/task-manager
     PORT=5000
     ```
   - Start the backend server:
     ```bash
     npm start
     ```

3. Set up the frontend:
   ```bash
   cd ../frontend
   npm install
   npm run dev
   ```

4. Open your browser and navigate to:
   ```
   http://localhost:5173
   ```

---

## API Documentation
The backend provides the following API endpoints:

### **Create a Task**
- **URL:** `/api/tasks`
- **Method:** POST
- **Body:** 
  ```json
  {
    "title": "Task Title",
    "description": "Task description",
    "status": "pending",
    "dueDate": "YYYY-MM-DD"
  }
  ```
- **Response:**
  ```json
  {
    "_id": "12345",
    "title": "Task Title",
    "description": "Task description",
    "status": "pending",
    "dueDate": "YYYY-MM-DD",
    "createdAt": "2025-03-08T00:00:00.000Z",
    "updatedAt": "2025-03-08T00:00:00.000Z"
  }
  ```

### **Retrieve All Tasks**
- **URL:** `/api/tasks`
- **Method:** GET
- **Response:** An array of task objects.

### **Update a Task**
- **URL:** `/api/tasks/:id`
- **Method:** PUT
- **Body:** Include fields to update, e.g.:
  ```json
  {
    "status": "completed"
  }
  ```
- **Response:** The updated task.

### **Delete a Task**
- **URL:** `/api/tasks/:id`
- **Method:** DELETE
- **Response:**
  ```json
  {
    "message": "Task deleted successfully"
  }
  ```

---

## File Structure

### Backend
```
backend/
├── models/
│   └── Task.js       # Mongoose Task model
├── routes/
│   └── taskRoutes.js # Task-related API routes
├── .env              # Environment variables (MONGO_URI, PORT)
├── index.js          # Entry point for the server
```

### Frontend
```
frontend/
├── src/
│   ├── components/
│   │   ├── TaskList.jsx  # Display list of tasks
│   │   ├── TaskForm.jsx  # Add and update tasks
│   │   └── TaskItem.jsx  # Individual task details (optional)
│   ├── App.jsx           # Main React component
│   ├── index.jsx         # React DOM rendering
│   └── index.css         # Tailwind CSS configuration
├── tailwind.config.js    # Tailwind CSS configuration
├── postcss.config.js     # Tailwind/PostCSS settings
```

---

## Usage
1. Start the backend server:
   ```bash
   cd backend
   npm start
   ```
2. Start the frontend server:
   ```bash
   cd frontend
   npm run dev
   ```
3. Open your browser and interact with the app at:
   ```
   http://localhost:5173
   ```

---

## Deployment

### Backend Deployment
1. Push the backend folder to a GitHub repository.
2. Deploy to Render:
   - Create a new Web Service in Render.
   - Connect it to your GitHub repository.
   - Add `MONGO_URI` in the environment variables section.
   - Deploy the service.

### Frontend Deployment
1. Push the frontend folder to a GitHub repository.
2. Deploy to Vercel:
   - Connect Vercel to your GitHub repository.
   - Deploy the project.

---

## Features
- **TaskList Component:** Displays all tasks fetched from the backend.
- **TaskForm Component:** Provides a form to create or update tasks.
- **CRUD Operations:** Backend supports creating, reading, updating, and deleting tasks through RESTful APIs.
- **Responsive Design:** Tailwind CSS ensures a user-friendly, responsive interface.

---

## Testing
- Use **Postman** to test all API endpoints.
- Verify the frontend's functionality:
  - Add, edit, and delete tasks.
  - Ensure tasks update dynamically.

