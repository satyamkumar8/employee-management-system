# Employee Management System

A full-stack **Employee Management System (EMS)** built with the MERN stack, providing role-based employee management, attendance tracking, leave workflows, dashboards, and dynamic payslip generation.

The application follows an enterprise-style **admin-provisioned account model**, where employee accounts are created by authorized administrators rather than through public registration.

---

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

Frontend → Vercel
Backend → Render
Database → MongoDB Atlas


🛠️ Technology Stack
Frontend
React.js
Vite
Tailwind CSS
React Router DOM
Axios
React Context API
Lucide React
html2pdf.js
Backend
Node.js
Express.js
Mongoose
JWT
bcrypt
Nodemailer
Inngest
Database
MongoDB Atlas
Deployment
Vercel
Render
MongoDB Atlas
🔐 Authentication & Authorization

The application uses JWT-based authentication combined with role-based access control (RBAC).

Authentication Flow
User Login
    ↓
Backend verifies credentials
    ↓
Password checked using bcrypt
    ↓
JWT generated
    ↓
Authenticated session
    ↓
JWT attached to protected API requests
    ↓
Backend middleware validates token
    ↓
Access granted based on user role

The application supports two roles:

Admin
Employee

Admin-only operations are protected at the backend level.

🧑‍💼 Employee Provisioning

The system follows a provision-only architecture.

Employees do not create their own accounts. Instead, an administrator creates and provisions employee accounts.

Admin
  ↓
Creates Employee
  ↓
Assigns Employee Role
  ↓
Employee Credentials Created
  ↓
Employee Logs In
  ↓
Employee Portal

This models a realistic enterprise HR workflow.

📊 Core Modules
Employee Management

Administrators can:

Create employees
Update employee information
Assign roles
Manage employee records
Attendance

Employees can mark attendance while the system maintains daily attendance records.

A unique employee/date combination prevents duplicate attendance entries.

Leave Management

Employees can submit leave requests.

Administrators can:

View requests
Approve requests
Reject requests
Payslips

Administrators can generate employee payslips containing:

Basic salary
Allowances
Deductions
Net salary

Payslips can be generated as PDF documents.

Dashboard

The admin dashboard provides centralized information about:

Employees
Attendance
Leave activity
Payroll
⏱️ Background Jobs

The project uses Inngest for scheduled background processing.

For example, the system can identify active employees who do not have an attendance record for the day and process the attendance workflow automatically.

Scheduled Trigger
       ↓
Find Active Employees
       ↓
Check Attendance Records
       ↓
Identify Missing Entries
       ↓
Process Attendance
🗄️ Database Design

The application uses MongoDB Atlas with Mongoose.

Main entities include:

User
 ├── authentication
 ├── password hash
 └── role

Employee
 ├── profile information
 ├── department
 ├── salary
 └── user reference

Attendance
 ├── employee reference
 ├── date
 └── status

Leave
 ├── employee reference
 ├── start date
 ├── end date
 ├── reason
 └── status

Payslip
 ├── employee reference
 ├── salary details
 ├── month/year
 ├── deductions
 └── net salary
📁 Project Structure
employee-management-system/
│
├── backend/
│   ├── models/
│   ├── routes/
│   ├── middleware/
│   ├── utils/
│   ├── inngest/
│   └── server.js
│
├── frontend/
│   ├── src/
│   │   ├── api/
│   │   ├── components/
│   │   ├── context/
│   │   ├── pages/
│   │   └── App.jsx
│   └── vercel.json
│
└── README.md
⚙️ Local Setup
Prerequisites
Node.js
npm
MongoDB Atlas account or MongoDB instance
Clone Repository
git clone https://github.com/satyamkumar8/employee-management-system.git
cd employee-management-system
Backend
cd backend
npm install

Create a .env file:

PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
EMAIL_USER=your_email
EMAIL_PASS=your_email_app_password

Start the backend:

npm start
Frontend

Open another terminal:

cd frontend
npm install
npm run dev
🌐 Deployment

The project uses a separated deployment architecture:

Vercel
   ↓
React Frontend
   ↓
REST API
   ↓
Render
   ↓
Node.js + Express
   ↓
MongoDB Atlas

This allows the frontend, backend and database to be managed independently.

🔎 Recruiter Demo Flow
Admin
Login as administrator
Open Employees
Create an employee
Assign the Employee role
Employee
Login using the new credentials
Mark attendance
Apply for leave
Admin
Login again
Open Leaves
Approve/reject the request
Open Payslips
Generate the employee payslip
💡 Engineering Highlights

This project demonstrates practical experience with:

Full-stack web application development
React component architecture
REST API development
MongoDB schema design
JWT authentication
Role-based access control
Protected routes
Background job processing
PDF generation
Cloud deployment
Frontend/backend separation
Environment-based configuration
🔮 Future Improvements
Redis caching
AWS S3 for file/document storage
WebSocket-based real-time notifications
Automated email notifications
Expanded automated testing
CI/CD pipeline
Centralized logging and monitoring
👨‍💻 Author

Satyam Kumar

Computer Science & Engineering

LinkedIn:
https://linkedin.com/in/satyamkumar8
