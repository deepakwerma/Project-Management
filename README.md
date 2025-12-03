# 🚀 Backend Project

A scalable backend for collaborative project management with secure authentication, role-based authorization, hierarchical tasks, project notes, file uploads, and email-based workflows.

---

## ⭐ **Overview**

**Project Camp Backend** is a production-style RESTful API designed to manage:

- Projects  
- Tasks & Subtasks  
- Team Members  
- Project Notes  

It demonstrates strong backend engineering concepts including:

- Clean architecture  
- API design  
- Role-based access control (RBAC)  
- Secure authentication  
- Email verification  
- File uploads  
- Modular code structure  

---

# 🛠️ **Tech Stack**

| Category | Technology |
|----------|------------|
| Runtime | Node.js |
| Framework | Express.js |
| Database | MongoDB + Mongoose |
| Authentication | JWT (Access + Refresh Tokens) |
| Email Service | Nodemailer |
| File Uploads | Multer |
| Architecture | MVC + Services Layer |
| Security | CORS, RBAC, Validation |

---

# ✨ **Core Features**

## 🔐 **Authentication & Authorization**
- Register with email verification  
- JWT login  
- Access + Refresh token flow  
- Forgot/reset password  
- Change password  
- Logout  
- Role system: **Admin**, **Project Admin**, **Member**

---

## 📁 **Project Management**
- Create projects (Admin)  
- Update/delete projects (Admin)  
- View user-accessible projects  
- Project details with member count  

---

## 👥 **Team Member Management**
- Invite users via email  
- View project members  
- Update member roles (Admin only)  
- Remove members from project  

---

## 📌 **Task Management**
- Create tasks  
- Update task information  
- Delete tasks  
- Assign tasks  
- Task status tracking: **Todo → In Progress → Done**  
- Attach multiple files  
- View all tasks in a project  

---

## 🧩 **Subtask Management**
- Add subtasks  
- Update subtask details  
- Mark subtasks as complete  
- Delete subtasks (Admin/Project Admin only)

---

## 📝 **Project Notes**
- Create notes (Admin only)  
- View notes  
- Update/delete notes (Admin only)  

---

## ❤️ **System Health**
```

GET /api/v1/healthcheck

```

---

# 🧱 **Architecture & Folder Structure**

```

src/
│── controllers/        # Request handlers
│── services/           # Business logic
│── models/             # Mongoose schemas
│── routes/             # API routes
│── middlewares/        # Auth, RBAC, validation
│── utils/              # Helpers (email, tokens, etc.)
│── config/             # Environment & DB config
│── public/images       # Uploaded files
└── index.js            # Application entry point

```

---

# 🔑 **Permission Matrix**

| Feature                    | Admin | Project Admin | Member |
|---------------------------|:-----:|:-------------:|:------:|
| Create Project             | ✔ | ✖ | ✖ |
| Update/Delete Project      | ✔ | ✖ | ✖ |
| Manage Project Members     | ✔ | ✖ | ✖ |
| Create/Update/Delete Tasks | ✔ | ✔ | ✖ |
| View Tasks                 | ✔ | ✔ | ✔ |
| Update Subtask Status      | ✔ | ✔ | ✔ |
| Create/Delete Subtasks     | ✔ | ✔ | ✖ |
| Create/Update/Delete Notes | ✔ | ✖ | ✖ |
| View Notes                 | ✔ | ✔ | ✔ |

---

# 📡 **API Endpoints**

## **Authentication — `/api/v1/auth/`**
```

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

```

---

## **Projects — `/api/v1/projects/`**
```

GET    /
POST   /
GET    /:projectId
PUT    /:projectId
DELETE /:projectId

GET    /:projectId/members
POST   /:projectId/members
PUT    /:projectId/members/:userId
DELETE /:projectId/members/:userId

```

---

## **Tasks — `/api/v1/tasks/`**
```

GET    /:projectId
POST   /:projectId
GET    /:projectId/t/:taskId
PUT    /:projectId/t/:taskId
DELETE /:projectId/t/:taskId

POST   /:projectId/t/:taskId/subtasks
PUT    /:projectId/st/:subTaskId
DELETE /:projectId/st/:subTaskId

```

---

## **Notes — `/api/v1/notes/`**
```

GET    /:projectId
POST   /:projectId
GET    /:projectId/n/:noteId
PUT    /:projectId/n/:noteId
DELETE /:projectId/n/:noteId

```

---

## **System Health — `/api/v1/healthcheck`**
```

GET /

```

---

# 🔒 **Security Features**
- JWT authentication with refresh tokens  
- Email verification workflow  
- Secure password reset  
- Role-based authorization middleware  
- Input validation on all endpoints  
- CORS protection  
- Secure file upload handling  

---

# 🗂️ **File Management**
- Multiple file uploads for tasks  
- Files stored under `/public/images`  
- Metadata stored (size, MIME type, URL)  
- Secure upload processing via Multer  

---

# ✔ **Success Criteria**
- Secure user authentication & authorization  
- Complete project lifecycle management  
- Hierarchical task & subtask system  
- Strong RBAC enforcement  
- Email verification + password reset  
- Organized, well-documented API structure  

---

