<div align="center">

# 🌓 <span style="color:#00E5FF;">Project Management API</span>

A scalable backend for managing projects, tasks, teams, authentication & workflows.  
Built with Node.js, Express, MongoDB, and JWT.

</div>

---

<div style="background:#111; padding:20px; border-radius:10px;">

## ⚠️ <span style="color:#FF5757;">Security Notice</span>

This backend currently uses **only basic security**:

- ✔ JWT Authentication (Access + Refresh Tokens)  
- ✔ Password hashing using **bcrypt**  
- ✔ Basic request validation  
- ✔ RBAC (Role-Based Access Control)

### ❗ Missing Production Security
> *This project is not production-ready yet.*

- ❌ Rate limiting  
- ❌ Helmet Security Headers  
- ❌ Brute-force login protection  
- ❌ XSS / Injection sanitization  
- ❌ CSRF protection  
- ❌ IP throttling  
- ❌ Logging / monitoring  

</div>

---

## 🌟 **Overview**

This is a modular and scalable REST API for:

- Project & team management  
- Task & subtask tracking  
- Notes system  
- Email workflows  
- Authentication & role permissions  
- File upload handling  

---

# 🛠️ **Tech Stack**

<div style="background:#0D0D0D; padding:15px; border-radius:10px;">

| Category | Technology |
|----------|------------|
| Runtime | Node.js |
| Framework | Express.js |
| Database | MongoDB + Mongoose |
| Authentication | JWT |
| Password Hashing | bcrypt |
| File Uploads | Multer |
| Email Service | Nodemailer |
| Architecture | MVC + Service Layer |
| Security | JWT, bcrypt, validation |

</div>

---

# ✨ **Features**

## 🔐 Authentication
- Register + Email verification  
- Login / Logout  
- Access + Refresh tokens  
- Forgot & Reset password  
- Change password  
- Role-based access (Admin, Project Admin, Member)

---

## 📁 Projects
- Create / Update / Delete (Admin)  
- View accessible projects  
- Member count & project details  

---

## 👥 Team Members
- Invite via email  
- Update roles  
- Remove members  
- View all members  

---

## 📌 Tasks
- Create, update, delete  
- Assign users to tasks  
- Status: **Todo → In Progress → Done**  
- Multiple file uploads  

---

## 🧩 Subtasks
- Add subtasks  
- Update or mark as complete  
- Delete subtasks  

---

## 📝 Notes
- Admin-only create/update/delete  
- View all project notes  

---

# 🧱 **Folder Structure**

```
src/
│── controllers/
│── services/
│── models/
│── routes/
│── middlewares/
│── utils/
│── config/
│── public/images
└── index.js
```

---

# 🔑 **Permission Matrix**

<div style="background:#0D0D0D; padding:15px; border-radius:10px;">

| Feature | Admin | Project Admin | Member |
|--------|:-----:|:-------------:|:------:|
| Create Projects | ✔ | ✖ | ✖ |
| Edit/Delete Projects | ✔ | ✖ | ✖ |
| Manage Members | ✔ | ✖ | ✖ |
| Create/Modify Tasks | ✔ | ✔ | ✖ |
| View Tasks | ✔ | ✔ | ✔ |
| Update Subtasks | ✔ | ✔ | ✔ |
| Add/Delete Subtasks | ✔ | ✔ | ✖ |
| Manage Notes | ✔ | ✖ | ✖ |
| View Notes | ✔ | ✔ | ✔ |

</div>

---

# 📡 **API Endpoints**

## 🔐 Authentication — `/api/v1/auth`
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

## 🗂 Projects — `/api/v1/projects`
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

# 🔒 **Current Security**
- JWT access + refresh tokens  
- bcrypt password hashing  
- Email verification  
- Input validation  
- RBAC middleware  
- CORS protection  
- File validation  

---

# 🚀 **Production Security To-Do**
- Helmet headers  
- Rate limiting  
- Throttling  
- CSRF protection  
- XSS sanitization  
- Token blacklist  
- Suspicious login alerts  

---

<div align="center">

## 💙 Thanks for Checking Out the Project!

If you like this project, consider ⭐ starring the repository.

</div>
