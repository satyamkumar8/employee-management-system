# Employee Management System

A full-stack **Employee Management System (EMS)** built with the MERN stack, providing role-based employee management, attendance tracking, leave workflows, dashboards, and dynamic payslip generation.

The application is designed around an enterprise-style **admin-provisioned account model**, where employees are created by an administrator rather than registering themselves.

## 🚀 Live Demo

**Frontend:**  
https://employee-management-system-ten-delta.vercel.app/

**Backend API:**  
https://employee-management-api-le4u.onrender.com


---

## 📌 Key Features

### Admin

- Secure administrator login
- Employee provisioning and management
- Employee profile management
- Attendance monitoring
- Leave request approval/rejection
- Dashboard statistics
- Payslip generation
- Role-based access control

### Employee

- Secure login
- Personal dashboard
- Attendance marking
- Leave application
- Leave-status tracking
- Profile information
- Payslip viewing/download

### System Features

- JWT-based authentication
- Role-based authorization
- Password hashing with bcrypt
- Protected API routes
- Protected frontend routes
- Automated attendance processing
- PDF payslip generation
- RESTful API architecture
- Responsive UI

---

## 🏗️ Architecture

```text
                    ┌──────────────────────┐
                    │      React App       │
                    │   Vite + Tailwind    │
                    └──────────┬───────────┘
                               │
                         Axios / REST API
                               │
                               ▼
                    ┌──────────────────────┐
                    │   Node.js + Express  │
                    │       Backend        │
                    └──────────┬───────────┘
                               │
                ┌──────────────┼───────────────┐
                │              │               │
                ▼              ▼               ▼
          Authentication   Business Logic   Background Jobs
           JWT + bcrypt     REST Routes       Inngest
                │              │
                └──────────────┼───────────────┘
                               ▼
                    ┌──────────────────────┐
                    │      MongoDB Atlas   │
                    │       Database       │
                    └──────────────────────┘

Frontend Deployment → Vercel
Backend Deployment  → Render
Database            → MongoDB Atlas
