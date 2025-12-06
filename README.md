<h1 align="center">🚀 Project Management API</h1>
<p align="center">A scalable backend for managing projects, tasks, teams, notes, and authentication workflows.</p>

---

## ⚠️ **Security Notice**

This project currently includes **only basic security**:

- ✔ JWT Authentication (Access + Refresh Tokens)  
- ✔ Password hashing using **bcrypt**  
- ✔ Basic Validation  
- ✔ Role-Based Access Control (RBAC)  

However, **it is NOT production-secure yet**. Missing security features:

- ❌ Rate Limiting  
- ❌ Security Headers (Helmet)  
- ❌ Brute Force Protection  
- ❌ XSS / Injection Sanitization  
- ❌ CSRF Protection  
- ❌ Logging & Intrusion Detection  

> **Do NOT use this backend in production without adding the missing protections.**

---

## ⭐ **Overview**

A modular REST API for:

- Project & team management  
- Task & subtask hierarchy  
- Notes system  
- Email workflows  
- Authentication & access control  
- File uploads  

Built using clean code, scalable folder structure, and modern backend practices.

---

## 🛠️ **Tech Stack**

| Category | Technology |
|----------|------------|
| Runtime | Node.js |
| Framework | Express.js |
| Database | MongoDB (Mongoose) |
| Auth | JWT (Access + Refresh) |
| Hashing | bcrypt |
| Email | Nodemailer |
| File Uploads | Multer |
| Architecture | MVC + Service Layer |
| Security (Basic) | JWT, bcrypt, validator |

---

## ✨ **Features**

### 🔐 **Authentication**
- Register + Email verification  
- Login  
- Refresh tokens  
- Forgot/Reset password  
- Change password  
- Logout  
- Role-based access: **Admin**, **Project Admin**, **Member**

---

### 📁 **Project Management**
- Create, update, delete projects (Admin)  
- View accessible projects  
- Member management  
- Project metadata with member count  

---

### 👥 **Team Members**
- Invite via email  
- Update roles  
- Remove users  
- View member list  

---

### 📌 **Tasks**
- Create tasks  
- Update/Delete tasks  
- Assign members  
- Status flow: **Todo → In Progress → Done**  
- Attach multiple files  
- List project tasks  

---

### 🧩 **Subtasks**
- Add subtasks  
- Update or mark complete  
- Delete subtasks  

---

### 📝 **Notes**
- Add notes (Admin only)  
- Edit/Delete notes  
- View all notes  

---

### ❤️ **Health Check**
```
GET /api/v1/healthcheck
```

---

## 🧱 **Folder Structure**

```
src/
│── controllers/       # Request handlers
│── services/          # Business logic
│── models/            # Mongoose schemas
│── routes/            # All route definitions
│── middlewares/       # Auth, RBAC, validation
│── utils/             # Token, email, helpers
│── config/            # DB + env config
│── public/images      # Uploaded files
└── index.js           # App entry
```

---

## 🔑 **Permission Matrix**

| Feature | Admin | Project Admin | Member |
|--------|:-----:|:-------------:|:------:|
| Create Projects | ✔ | ✖ | ✖ |
| Modify/Delete Projects | ✔ | ✖ | ✖ |
| Manage Members | ✔ | ✖ | ✖ |
| Create/Modify Tasks | ✔ | ✔ | ✖ |
| View Tasks | ✔ | ✔ | ✔ |
| Update Subtasks | ✔ | ✔ | ✔ |
| Add/Delete Subtasks | ✔ | ✔ | ✖ |
| Manage Notes | ✔ | ✖ | ✖ |
| View Notes | ✔ | ✔ | ✔ |

---

## 📡 **API Endpoints**

### **Auth – `/api/v1/auth`**
```
POST /register
POST /login
POST /logout
POST /refresh-token
POST /forgot-password
POST /reset-password/:resetToken
POST /change-password
POST /resend-email-verification
GET  /verify-email/:verificationToken
GET  /current-user
```

---

### **Projects – `/api/v1/projects`**
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

### **Tasks – `/api/v1/tasks`**
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

### **Notes – `/api/v1/notes`**
```
GET    /:projectId
POST   /:projectId
GET    /:projectId/n/:noteId
PUT    /:projectId/n/:noteId
DELETE /:projectId/n/:noteId
```

---

## 🔒 **Current Security**
- JWT Access Tokens  
- Refresh Tokens  
- bcrypt password hashing  
- Email verification workflow  
- Input validation  
- Basic RBAC middleware  
- CORS protection  
- File upload filtering  

---

## 🧩 **Security To Improve (Recommended)**
Add these before production:

- Helmet headers  
- Rate limiting  
- IP throttling  
- XSS sanitization  
- CSRF protection  
- Audit logs  
- Token blacklist  
- Suspicious login detection  

---

## ✔ **Project Goals**
- Modular, scalable architecture  
- Complete project/task lifecycle  
- Secure authentication foundation  
- Clean and well-documented API  
- Real-world backend engineering practices  

---

