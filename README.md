# Task Management API

This is a simple **Task Management API** built using **Node.js, Express, and MongoDB**. It allows users to create, retrieve, update, and delete tasks.

## Features
- Add a new task
- Retrieve all tasks
- Retrieve a task by ID
- Update a task
- Delete a task
- Filter tasks by status and due date

## Technologies Used
- **Node.js**
- **Express.js**
- **MongoDB with Mongoose**
- **dotenv (for environment variables)**

## Installation

1. Clone the repository:
   ```sh
   git clone https://github.com/your-repo/task-manager-api.git
   ```
2. Navigate to the project directory:
   ```sh
   cd task-manager-api
   ```
3. Install dependencies:
   ```sh
   npm install
   ```
4. Create a `.env` file in the root directory and add your MongoDB URI:
   ```env
   MONGO_URI=your_mongodb_connection_string
   ```
5. Start the server:
   ```sh
   node index.js
   ```

## API Endpoints

### 1️⃣ Add a New Task
- **Endpoint:** `POST /tasks`
- **Request Body:**
  ```json
  {
    "title": "Complete Assignment",
    "description": "Finish the DSA assignment",
    "status": "Pending",
    "dueDate": "2025-04-05"
  }
  ```
- **Response:**
  ```json
  {
    "_id": "your_task_id",
    "title": "Complete Assignment",
    "description": "Finish the DSA assignment",
    "status": "Pending",
    "dueDate": "2025-04-05T00:00:00.000Z",
    "__v": 0
  }
  ```

### 2️⃣ Get All Tasks
- **Endpoint:** `GET /tasks`
- **Response:**
  ```json
  [
    {
      "_id": "your_task_id",
      "title": "Complete Assignment",
      "description": "Finish the DSA assignment",
      "status": "Pending",
      "dueDate": "2025-04-05T00:00:00.000Z",
      "__v": 0
    }
  ]
  ```

### 3️⃣ Get a Task by ID
- **Endpoint:** `GET /tasks/:id`

### 4️⃣ Update a Task by ID
- **Endpoint:** `PUT /tasks/:id`
- **Request Body:** (Send only the fields you want to update)
  ```json
  {
    "title": "Submit Assignment",
    "description": "Submit the DSA assignment before deadline",
    "status": "Completed",
    "dueDate": "2025-04-04"
  }
  ```

### 5️⃣ Delete a Task by ID
- **Endpoint:** `DELETE /tasks/:id`

### 6️⃣ Get Tasks by Status
- **Endpoint:** `GET /tasks/status/:status`
- Example: `GET /tasks/status/Completed`

### 7️⃣ Get Tasks by Due Date
- **Endpoint:** `GET /tasks/dueDate/:dueDate`
- Example: `GET /tasks/dueDate/2025-04-05`

## Running in Postman
- Open **Postman**
- Use the given endpoints to send requests
- Set **Content-Type** to `application/json` for POST and PUT requests
