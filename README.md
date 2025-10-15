# Campus-Resource-Management-System
The Campus Resource Management System is real-world, technically strong, and can easily scale into a professional-level full-stack project.

 A complete roadmap so you know exactly what to do from start to finish.


---

🎯 Project Overview

Goal:
A web app for colleges/universities to manage and book shared resources — classrooms, labs, seminar halls, projectors, or sports venues — efficiently.

Core Problem:
Currently, bookings are handled manually or via spreadsheets → causes double booking, miscommunication, and no centralized record.

Your Solution:
A full-stack platform that enables authenticated users (students, staff, admin) to:

Book resources.

Approve or reject requests.

Track resource availability.

View analytics (usage reports).



---

🏗 Tech Stack

Frontend: React + TailwindCSS
Backend: Node.js + Express.js
Database: PostgreSQL 
Authentication: JWT (JSON Web Token)
Other Tools:

Prisma / Sequelize ORM

Nodemailer (email alerts)

FullCalendar.js (for resource booking visualization)

Docker (optional, for deployment)



---

🧩 System Architecture

Frontend (React)
   ↓ REST API
Backend (Express.js)
   ↓
Database (PostgreSQL)

The backend exposes endpoints like /api/bookings, /api/resources, /api/users.

The frontend calls these APIs and manages the UI state.



---

📊 Database Schema

users

Column	Type	Description

id	INT (PK)	User ID
name	VARCHAR	User’s name
email	VARCHAR (unique)	Login email
password	VARCHAR	Hashed password
role	ENUM(‘student’, ‘staff’, ‘admin’)	Role type



---

resources

Column	Type	Description

id	INT (PK)	Resource ID
name	VARCHAR	e.g. “Lab 102”, “Projector A”
category	VARCHAR	e.g. “Lab”, “Classroom”, “Equipment”
capacity	INT	Optional (e.g. number of seats)
location	VARCHAR	Building/room
available	BOOLEAN	Resource availability flag



---

bookings

Column	Type	Description

id	INT (PK)	Booking ID
user_id	INT (FK users.id)	Who booked
resource_id	INT (FK resources.id)	Which resource
start_time	DATETIME	Booking start
end_time	DATETIME	Booking end
status	ENUM(‘pending’, ‘approved’, ‘rejected’)	Admin decision



---

notifications

Column	Type	Description

id	INT (PK)	Notification ID
user_id	INT (FK users.id)	Target user
message	TEXT	Notification text
read	BOOLEAN	Read/unread status



---

🧠 Feature Breakdown

Phase 1: Core (MVP)

User login/signup

Role-based authentication (JWT)

Add/view resources (admin only)

Book a resource (student/staff)

Prevent double bookings (validate time overlap)

Admin approves/rejects bookings


Phase 2: Enhancement

Email or in-app notifications on booking updates

Search/filter resources

Booking calendar view (FullCalendar.js)

Analytics dashboard (usage trends, frequent users)


Phase 3: Advanced (optional)

Mobile-friendly UI (React responsive)

Integrate Google Calendar API

Resource QR code check-in

Containerization with Docker

CI/CD + Cloud deployment (Render, Vercel, AWS)



---

🗓 Implementation Plan (2–3 Months)

Week	Focus	Tasks

1	Setup	Initialize repo, Node + Express + React setup, connect DB
2	Auth	Build register/login + JWT + roles
3–4	Core	CRUD for resources, booking logic, overlap prevention
5–6	Admin	Approval system, email notifications, dashboard
7	UI Polish	Calendar integration, filtering, responsive layout
8–9	Deploy	Testing, Dockerization, deployment to Render/Vercel



---

🧰 Example Endpoints

Endpoint	Method	Role	Description

/api/auth/register	POST	all	Create user
/api/auth/login	POST	all	Login user
/api/resources	GET	all	List all resources
/api/resources	POST	admin	Add resource
/api/bookings	POST	student/staff	Request booking
/api/bookings/:id/approve	PUT	admin	Approve booking
/api/bookings/my	GET	student/staff	View my bookings



---



---

Would you like me to give you the step-by-step coding guide (with folder structure and initial code setup) next — starting with backend setup (Express + PostgreSQL + JWT)?
