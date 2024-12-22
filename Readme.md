Task Management API
A RESTful API for managing tasks built with Node.js, Express, and MongoDB.
Prerequisites

Node.js (v14 or higher)
MongoDB (v4.4 or higher)
npm or yarn package manager

Installation

Clone the repository:

bashCopygit clone <your-repository-url>
cd task-management-api

Install dependencies:

bashCopynpm install

Create a .env file in the root directory with the following contents:

CopyPORT=3000
MONGODB_URI=mongodb://localhost:27017/tasks

Start the server:

bashCopynpm start
The server will start running on http://localhost:3000
API Endpoints
Tasks
GET /tasks
Get all tasks.
Response
jsonCopy[
{
"_id": "60f1a7b9e6b5f32b4c9e1234",
"title": "Complete project",
"description": "Finish the API documentation",
"status": "pending",
"createdAt": "2024-12-22T10:00:00.000Z",
"updatedAt": "2024-12-22T10:00:00.000Z"
}
]
GET /tasks/:id
Get a single task by ID.
Response
jsonCopy{
"\_id": "60f1a7b9e6b5f32b4c9e1234",
"title": "Complete project",
"description": "Finish the API documentation",
"status": "pending",
"createdAt": "2024-12-22T10:00:00.000Z",
"updatedAt": "2024-12-22T10:00:00.000Z"
}
POST /tasks
Create a new task.
Request Body
jsonCopy{
"title": "Complete project",
"description": "Finish the API documentation",
"status": "pending"
}
Response
jsonCopy{
"\_id": "60f1a7b9e6b5f32b4c9e1234",
"title": "Complete project",
"description": "Finish the API documentation",
"status": "pending",
"createdAt": "2024-12-22T10:00:00.000Z",
"updatedAt": "2024-12-22T10:00:00.000Z"
}
PUT /tasks/:id
Update an existing task.
Request Body
jsonCopy{
"status": "completed"
}
Response
jsonCopy{
"\_id": "60f1a7b9e6b5f32b4c9e1234",
"title": "Complete project",
"description": "Finish the API documentation",
"status": "completed",
"createdAt": "2024-12-22T10:00:00.000Z",
"updatedAt": "2024-12-22T10:00:00.000Z"
}
DELETE /tasks/:id
Delete a task.
Response
jsonCopy{
"message": "Task deleted"
}
Error Handling
The API returns appropriate HTTP status codes and error messages:

200: Success
201: Resource created
400: Bad request
404: Resource not found
500: Server error

Development
To run the server in development mode with automatic restart:
bashCopynpm install nodemon --save-dev
npx nodemon index.js
