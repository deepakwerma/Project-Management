<div align="center">

# 🌙 <span style="color:#00E5FF;">Project Management API</span>

A clean, scalable backend system for managing projects, tasks, teams, notes, authentication, and workflow automation.

Built with **Node.js, Express, MongoDB, JWT, and modern backend architecture.**

</div>

---

## ⭐ **Overview**

This Project Management API provides a production-style backend with:

- User authentication  
- Role-based access control (RBAC)  
- Projects, tasks, and subtasks management  
- Team collaboration features  
- Notes and documentation system  
- Email-based workflows  
- File upload support  

It demonstrates backend engineering best practices and a modular, scalable architecture suitable for real-world systems.

---

# 🛠️ **Tech Stack**

<div style="background:#0D0D0D; padding:18px; border-radius:12px;">

| Category | Technology |
|----------|------------|
| Runtime | Node.js |
| Server Framework | Express.js |
| Database | MongoDB + Mongoose |
| Authentication | JWT (Access + Refresh Tokens) |
| Password Hashing | bcrypt |
| Email Service | Nodemailer |
| File Uploads | Multer |
| Architecture | MVC + Services Layer |
| Security (Basic) | JWT, bcrypt, validation, RBAC |

</div>

---

# ✨ **Core Features**

## 🔐 Authentication & Authorization
- Register with email verification  
- Login with JWT (access + refresh tokens)  
- Logout  
- Forgot & reset password  
- Change password  
- Current user details  
- RBAC system: **Admin**, **Project Admin**, **Member**

---

## 📁 Projects
- Create, update, delete projects  
- View user-accessible projects  
- Automatic member count  
- Project details with hierarchical data  

---

## 👥 Team Management
- Add members to a project  
- Update member roles  
- Remove members  
- View all project members  
- Email-based invitations (optional)

---

## 📌 Tasks
- Create and assign tasks  
- Update task details  
- Task status: **Todo → In Progress → Done**  
- Multiple file attachments  
- View tasks in a project  

---

## 🧩 Subtasks
- Add subtasks to tasks  
- Update subtask status  
- Edit or delete subtasks  

---

## 📝 Notes
- Create project notes  
- Edit or delete notes (restricted by role)  
- View all notes for a project  

---

## ❤️ Health Check
```
GET /api/v1/healthcheck
```

---

# 🧱 **Folder Structure**

```
src/
│── controllers/        # Route handlers
│── services/           # Business logic
│── models/             # Mongoose schemas
│── routes/             # API routes
│── middlewares/        # Auth, RBAC, validation
│── utils/              # Email, tokens, helpers
│── config/             # Env and DB config
│── public/images       # Uploaded files
└── index.js            # Server entry point
```

---

# 🔑 **Permission Matrix**

<div style="background:#0D0D0D; padding:18px; border-radius:12px;">

| Feature                    | Admin | Project Admin | Member |
|---------------------------|:-----:|:-------------:|:------:|
| Create Projects            | ✔ | ✖ | ✖ |
| Update/Delete Projects     | ✔ | ✖ | ✖ |
| Manage Members             | ✔ | ✖ | ✖ |
| Create/Update/Delete Tasks | ✔ | ✔ | ✖ |
| View Tasks                 | ✔ | ✔ | ✔ |
| Update Subtask Status      | ✔ | ✔ | ✔ |
| Create/Delete Subtasks     | ✔ | ✔ | ✖ |
| Manage Notes               | ✔ | ✖ | ✖ |
| View Notes                 | ✔ | ✔ | ✔ |

</div>

---

# 📡 **API Endpoints**

## 🔐 Auth — `/api/v1/auth`
```
POST /register
POST /login
POST /logout
POST /refresh-token
POST /change-password
POST /forgot-password
POST /reset-password/:token
GET  /verify-email/:verificationToken
GET  /current-user
```

---

## 📁 Projects — `/api/v1/projects`
```
GET    /
POST   /
GET    /:projectId
PUT    /:projectId
DELETE /:projectId

# Members
GET    /:projectId/members
POST   /:projectId/members
PUT    /:projectId/members/:userId
DELETE /:projectId/members/:userId
```

---

## 📌 Tasks — `/api/v1/tasks`
```
GET    /:projectId
POST   /:projectId
GET    /:projectId/t/:taskId
PUT    /:projectId/t/:taskId
DELETE /:projectId/t/:taskId

# Subtasks
POST   /:projectId/t/:taskId/subtasks
PUT    /:projectId/st/:subTaskId
DELETE /:projectId/st/:subTaskId
```

---

## 📝 Notes — `/api/v1/notes`
```
GET    /:projectId
POST   /:projectId
GET    /:projectId/n/:noteId
PUT    /:projectId/n/:noteId
DELETE /:projectId/n/:noteId
```

---

# 🚀 **Future Enhancements**  

- Rate limiting (prevent abuse)  
- Helmet security headers  
- Token blacklist system  
- API activity logs  
- XSS & injection sanitization  
- CSRF protection  
- OTP-based login  
- WebSocket-based real-time updates  
- Admin dashboard (Next.js or React)  

---

<div align="center">

## 💙 Thanks for Checking Out the Project!

If you like this project, consider ⭐ starring the repository.

</div>
