Project Camp Backend

A scalable RESTful backend for collaborative project management, featuring authentication, role-based authorization, hierarchical tasks, project notes, file uploads, and email-based security workflows.

📌 Overview

Project Camp Backend is a production-style backend system designed to manage projects, tasks, subtasks, team members, and notes within a collaborative workspace.
It includes a complete authentication system, secure file handling, and fine-grained role-based permissions.

This project demonstrates strong backend engineering concepts including:

API design

Access control

Modular architecture

Database modeling

Secure workflows

Real-world functionalities

🛠 Tech Stack
Category	Technology
Runtime	Node.js
Framework	Express.js
Database	MongoDB + Mongoose
Authentication	JWT (Access + Refresh Tokens), Bcrypt
Email	Nodemailer
File Uploads	Multer
Security	CORS, Input Validation, RBAC
Architecture	MVC + Services Layer
🎯 Core Features
🔐 User Authentication & Authorization

User registration with email verification

Secure JWT login

Refresh token-based session renewal

Change password

Forgot/reset password (email-based)

Role-based access control

Logout flow

3 roles: Admin, Project Admin, Member

📁 Project Management

Create projects (Admin)

Update or delete projects (Admin)

View all projects user has access to

View project details including member count

👥 Team Member Management

Invite users to a project via email

View project members

Update member roles (Admin only)

Remove members from projects

📌 Task Management

Create tasks with title, description, and assignee

Update task content and status

Delete tasks

View all tasks in a project

File attachment support (multiple uploads)

Status levels: Todo, In Progress, Done

🧩 Subtask Management

Add subtasks to tasks

Update subtask details

Mark subtasks as complete

Delete subtasks (Admin/Project Admin)

📝 Project Notes

Create notes (Admin only)

View all notes

Update or delete notes (Admin only)

Note-level content access

❤️ System Health

/api/v1/healthcheck endpoint for monitoring server uptime and health

🧱 Architecture & Folder Structure
src/
│── controllers/        # Request handlers
│── services/           # Business logic
│── models/             # Mongoose schemas
│── routes/             # API routes
│── middlewares/        # Auth, RBAC, validation
│── utils/              # Token, email helpers
│── config/             # DB + environment setup
│── public/images       # Uploaded files
└── index.js            # Application entry point


This modular structure ensures scalability, clean separation of concerns, and easy maintenance.

🔑 Permission Matrix
Feature	Admin	Project Admin	Member
Create Project	✓	✗	✗
Update/Delete Project	✓	✗	✗
Manage Project Members	✓	✗	✗
Create/Update/Delete Tasks	✓	✓	✗
View Tasks	✓	✓	✓
Update Subtask Status	✓	✓	✓
Create/Delete Subtasks	✓	✓	✗
Create/Update/Delete Notes	✓	✗	✗
View Notes	✓	✓	✓
📡 API Endpoints
Authentication — /api/v1/auth/
POST /register
POST /login
POST /logout
GET  /current-user
POST /change-password
POST /refresh-token
GET  /verify-email/:verificationToken
POST /forgot-password
POST /reset-password/:resetToken
POST /resend-email-verification

Projects — /api/v1/projects/
GET    /
POST   /
GET    /:projectId
PUT    /:projectId
DELETE /:projectId

GET    /:projectId/members
POST   /:projectId/members
PUT    /:projectId/members/:userId
DELETE /:projectId/members/:userId

Tasks — /api/v1/tasks/
GET    /:projectId
POST   /:projectId
GET    /:projectId/t/:taskId
PUT    /:projectId/t/:taskId
DELETE /:projectId/t/:taskId

POST   /:projectId/t/:taskId/subtasks
PUT    /:projectId/st/:subTaskId
DELETE /:projectId/st/:subTaskId

Notes — /api/v1/notes/
GET    /:projectId
POST   /:projectId
GET    /:projectId/n/:noteId
PUT    /:projectId/n/:noteId
DELETE /:projectId/n/:noteId

Health Check — /api/v1/healthcheck/
GET /

🔒 Security Features

JWT authentication (access + refresh tokens)

Email verification workflow

Secure password reset process

Role-based access control middleware

Input validation on all endpoints

CORS configuration

File upload validation and path security

🗂 File Management

Multiple file attachments supported for tasks

Files stored under /public/images

Metadata stored (MIME type, size, URL)

Safe handling through Multer

✔ Success Criteria

The system fulfills the following requirements:

Secure user authentication and authorization

Complete project lifecycle support

Hierarchical task & subtask structure

Highly controlled access using RBAC

File attachment support

Email verification + password reset

Organized, well-documented API structure
