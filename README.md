# CareerPulse | Full-Stack Job Portal Web Application
### MCA Academic Project — Full-Stack MERN Implementation

A modern, responsive, and robust Job Portal web application built with **React.js, Bootstrap 5, Node.js, Express.js, and MongoDB**. Engineered specifically for academic final-year project demonstration, viva examinations, and portfolio presentation.

---

## 🌟 Key Features & Role-Based Workflows

### 1. Authentication & Security
- **JWT-Based Authentication**: Secure stateless token issuance and verification.
- **bcrypt Password Hashing**: Salted hashing prevents storing plain-text credentials.
- **Role-Based Authorization (RBAC)**: Distinct permissions for `jobseeker`, `recruiter`, and `admin`.
- **Protected Routes**: Frontend and backend guarded against unauthorized access.
- **Auto-Logout & Session Recovery**: Smooth token expiration handling.

### 2. Job Seeker Module
- **Registration & Profile**: Complete profile with education, total experience, technical skills, and resume upload (PDF/DOC/DOCX).
- **Search & Filtering**: Search by job title, company, or keyword. Filter sidebar with category, job type (Full-time, Part-time, Remote, Contract, Internship), and experience level.
- **Job Details View**: View salary range, location, requirements, company overview, and application deadlines.
- **One-Click Application**: Apply with existing profile resume or upload a custom resume and write an optional cover letter.
- **Live Status Tracking**: Real-time tracking of applied positions across states: `Applied` ➔ `Reviewed` ➔ `Shortlisted` ➔ `Interviewing` ➔ `Accepted` / `Rejected`.

### 3. Recruiter Module
- **Recruiter Dashboard**: Analytics metrics on total posted jobs, active openings, candidate applications, and shortlisted profiles.
- **Company Profile Management**: Edit official company information, headquarters, website, and company overview.
- **Job Posting & Management**: Post new jobs, edit existing postings, toggle active/closed status, and delete postings.
- **Applicant Pipeline & Review**: View candidates by job or across all postings, download applicant resumes, read cover letters, and update candidate hiring stages in real time.

### 4. Administrator Module
- **Platform Analytics**: Comprehensive statistics on total users, job seekers, recruiters, jobs, active postings, and applications.
- **User Moderation**: View all registered accounts, filter by role, and delete unauthorized accounts with cascading cleanup.
- **Job Moderation**: Review all platform job postings and delete inappropriate listings.
- **Application Monitoring**: Monitor all applications submitted across the system.

---

## 💻 Technology Stack

### Frontend
- **React.js (v18)**: Component-based reactive UI
- **Bootstrap 5 (v5.3)**: Modern responsive grid, modals, alerts, cards, and tables
- **Bootstrap Icons**: Intuitive iconography
- **React Router (v6)**: Declarative client-side routing & route protection
- **Axios**: HTTP client with request and response JWT interceptors
- **Vite**: Ultra-fast build tool and development server

### Backend
- **Node.js (v18+)**: Asynchronous JavaScript runtime
- **Express.js (v4)**: RESTful API server framework
- **MongoDB & Mongoose (v8)**: NoSQL document database and schema modeling
- **JSON Web Tokens (jsonwebtoken)**: Secure token authentication
- **bcryptjs**: Password encryption
- **Multer**: Multipart form data handling for resume file uploads
- **CORS & dotenv**: Cross-origin resource sharing & environment configuration

---

## 📁 Project Structure

```text
Job Portal/
├── client/                          # React Frontend
│   ├── public/
│   ├── src/
│   │   ├── components/              # Reusable UI components
│   │   │   ├── Navbar.jsx           # Role-aware responsive navigation
│   │   │   ├── Footer.jsx           # Modern academic project footer
│   │   │   ├── ProtectedRoute.jsx   # Role authorization wrapper
│   │   │   ├── JobCard.jsx          # Job card with badges & tags
│   │   │   ├── StatCard.jsx         # Metric summary card
│   │   │   ├── LoadingSpinner.jsx   # Feedback spinner
│   │   │   └── AlertMessage.jsx     # Alert feedback banners
│   │   ├── context/
│   │   │   └── AuthContext.jsx      # Authentication & user state
│   │   ├── pages/                   # Application pages
│   │   │   ├── Home.jsx             # Hero search & featured jobs
│   │   │   ├── Login.jsx            # 1-click evaluation demo login
│   │   │   ├── Register.jsx         # Candidate / recruiter registration
│   │   │   ├── Jobs.jsx             # Search, filter sidebar, pagination
│   │   │   ├── JobDetails.jsx       # Job details & application modal
│   │   │   ├── SeekerDashboard.jsx  # Candidate workspace & status tracker
│   │   │   ├── RecruiterDashboard.jsx# Recruiter jobs & pipeline hub
│   │   │   ├── AdminDashboard.jsx   # Admin statistics & moderation
│   │   │   ├── Profile.jsx          # Profile editor & resume upload
│   │   │   ├── PostJob.jsx          # Job posting form
│   │   │   ├── EditJob.jsx          # Job editing form
│   │   │   ├── MyApplications.jsx   # Candidate applications list
│   │   │   ├── Applicants.jsx       # Candidate resume & status reviewer
│   │   │   ├── CompanyProfile.jsx   # Recruiter company information
│   │   │   └── NotFound.jsx         # 404 error page
│   │   ├── services/                # Axios REST API services
│   │   │   ├── api.js               # Axios instance with JWT interceptor
│   │   │   ├── authService.js
│   │   │   ├── jobService.js
│   │   │   ├── applicationService.js
│   │   │   ├── companyService.js
│   │   │   └── adminService.js
│   │   ├── App.jsx                  # Main routing configuration
│   │   ├── index.css                # Custom theme styling & badges
│   │   └── main.jsx                 # React root
│   ├── index.html
│   ├── package.json
│   └── vite.config.js
│
├── server/                          # Express & Node.js Backend
│   ├── config/
│   │   └── db.js                    # Database connector (with auto-memory fallback)
│   ├── controllers/                 # Request business logic
│   │   ├── authController.js
│   │   ├── userController.js
│   │   ├── jobController.js
│   │   ├── applicationController.js
│   │   ├── companyController.js
│   │   └── adminController.js
│   ├── middleware/                  # Express middlewares
│   │   ├── authMiddleware.js        # JWT verification
│   │   ├── roleMiddleware.js        # RBAC role guards
│   │   ├── uploadMiddleware.js      # Multer resume document uploads
│   │   └── errorHandler.js          # Central error formatting
│   ├── models/                      # Mongoose Database Models
│   │   ├── User.js
│   │   ├── Company.js
│   │   ├── Job.js
│   │   └── Application.js
│   ├── routes/                      # REST API endpoints
│   │   ├── authRoutes.js
│   │   ├── userRoutes.js
│   │   ├── jobRoutes.js
│   │   ├── applicationRoutes.js
│   │   ├── companyRoutes.js
│   │   └── adminRoutes.js
│   ├── seed/                        # Sample demo data
│   │   ├── seedData.js              # Rich demo profiles, jobs & companies
│   │   └── seed.js                  # Database seeder script
│   ├── uploads/                     # Resume storage directory
│   │   └── resumes/
│   ├── .env                         # Server environment variables
│   ├── package.json
│   └── server.js                    # Express application entry point
│
├── .env.example                     # Environment template
├── README.md                        # Documentation & setup guide
└── package.json                     # Root orchestrator scripts
```

---

## ⚡ Quick Start & Setup Instructions

### Prerequisites
1. **Node.js**: Version 18.0.0 or later ([Download Node.js](https://nodejs.org/)).
2. **MongoDB** *(Optional)*: If you have local MongoDB or MongoDB Atlas, configure it in `server/.env`.
   > **Note on Zero-Config Academic Running**: If MongoDB is not running locally, the server automatically initializes an in-memory MongoDB engine and seeds demo data on launch! You can run the application immediately out of the box!

---

### Step 1: Install Dependencies

From the root project directory:
```bash
# Install backend dependencies
cd server
npm install

# Install frontend dependencies
cd ../client
npm install
```

---

### Step 2: Environment Configuration

The environment file is already configured at `server/.env`. If you want to customize it:
```env
PORT=5000
NODE_ENV=development
MONGO_URI=mongodb://127.0.0.1:27017/jobportal
JWT_SECRET=jobportal_super_secret_jwt_key_2026_mca
JWT_EXPIRES_IN=7d
MAX_FILE_SIZE=5242880
```

---

### Step 3: (Optional) Seed the Database

To reset and seed 12 realistic tech jobs, companies, seekers, and applications:
```bash
cd server
npm run seed
```

---

### Step 4: Run the Application

#### Terminal 1 — Start Backend Server:
```bash
cd server
npm start
```
*Backend runs on: `http://localhost:5000` (API: `http://localhost:5000/api`)*

#### Terminal 2 — Start Frontend Application:
```bash
cd client
npm run dev
```
*Frontend runs on: `http://localhost:5173`*

Open **`http://localhost:5173`** in your browser!

---

## 🔑 Demo Login Credentials

For demonstration, academic viva, and testing, the application includes pre-configured accounts:

| Role | Email | Password | Description |
| :--- | :--- | :--- | :--- |
| **Admin** | `admin@jobportal.com` | `Password123` | Full access to platform stats, user deletion, job moderation |
| **Recruiter 1** | `recruiter@techcorp.com` | `Password123` | TechCorp Solutions (posts jobs, reviews applicants, changes status) |
| **Recruiter 2** | `david@cloudinnovations.io` | `Password123` | CloudInnovations (posts cloud & DevOps jobs) |
| **Job Seeker 1** | `rahul@example.com` | `Password123` | Candidate with React & Node.js skills, active applications |
| **Job Seeker 2** | `priya@example.com` | `Password123` | Candidate with UI/UX & React skills, accepted application |

> **Pro-Tip**: The **Sign In page** includes quick **1-Click Demo Buttons** so examiners can log into any role instantly with a single click!

---

## 📡 REST API Documentation

### Authentication (`/api/auth`)
| Method | Endpoint | Access | Description |
| :--- | :--- | :--- | :--- |
| `POST` | `/api/auth/register` | Public | Register new user (`jobseeker` or `recruiter`) |
| `POST` | `/api/auth/login` | Public | Login and obtain JWT token |
| `GET` | `/api/auth/me` | Private | Retrieve current authenticated user session |

### User Profile (`/api/users`)
| Method | Endpoint | Access | Description |
| :--- | :--- | :--- | :--- |
| `GET` | `/api/users/profile` | Private | Fetch user profile data |
| `PUT` | `/api/users/profile` | Private | Update user profile & upload resume file |
| `GET` | `/api/users/resume/:filename` | Private | Download / view candidate resume |

### Jobs (`/api/jobs`)
| Method | Endpoint | Access | Description |
| :--- | :--- | :--- | :--- |
| `GET` | `/api/jobs` | Public | Search & filter jobs (keyword, location, category, type, experience) |
| `GET` | `/api/jobs/:id` | Public | Get single job details (shows application status if logged in) |
| `POST` | `/api/jobs` | Recruiter/Admin | Post a new job |
| `PUT` | `/api/jobs/:id` | Recruiter/Admin | Update job posting or toggle active/closed |
| `DELETE` | `/api/jobs/:id` | Recruiter/Admin | Delete job posting & associated applications |
| `GET` | `/api/jobs/recruiter/my` | Recruiter/Admin | Get all jobs posted by the logged-in recruiter |

### Applications (`/api/applications`)
| Method | Endpoint | Access | Description |
| :--- | :--- | :--- | :--- |
| `POST` | `/api/applications` | Job Seeker | Apply for a job with resume file & cover letter |
| `GET` | `/api/applications/my` | Job Seeker | Get all jobs applied by candidate with live status |
| `GET` | `/api/applications/job/:jobId` | Recruiter/Admin | Get applicants for a specific job |
| `GET` | `/api/applications/recruiter/all` | Recruiter/Admin | Get all applicants across all recruiter's jobs |
| `PUT` | `/api/applications/:id/status` | Recruiter/Admin | Update candidate status (`Shortlisted`, `Accepted`, etc.) |

### Companies (`/api/companies`)
| Method | Endpoint | Access | Description |
| :--- | :--- | :--- | :--- |
| `GET` | `/api/companies` | Public | List all registered companies |
| `GET` | `/api/companies/my` | Recruiter/Admin | Get recruiter's company profile |
| `GET` | `/api/companies/:id` | Public | Get company profile and active jobs |
| `POST` | `/api/companies` | Recruiter/Admin | Create company profile |
| `PUT` | `/api/companies/:id` | Recruiter/Admin | Update company profile |

### Admin Moderation (`/api/admin`)
| Method | Endpoint | Access | Description |
| :--- | :--- | :--- | :--- |
| `GET` | `/api/admin/stats` | Admin | Get platform statistics & metrics |
| `GET` | `/api/admin/users` | Admin | List all registered users (filter by role & search) |
| `DELETE` | `/api/admin/users/:id` | Admin | Delete user account & cascade cleanup |
| `GET` | `/api/admin/jobs` | Admin | View all platform jobs |
| `DELETE` | `/api/admin/jobs/:id` | Admin | Delete inappropriate job listing |
| `GET` | `/api/admin/applications` | Admin | View all submitted applications across platform |

---

## 🛡️ Security Implementation
1. **Password Encryption**: Handled through a Mongoose `pre('save')` hook with `bcryptjs.genSalt(10)`.
2. **Token Security**: Tokens are signed with HMAC SHA256 and sent via `Authorization: Bearer <token>`.
3. **Password Protection**: Passwords are automatically stripped from API responses via `userSchema.methods.toJSON`.
4. **File Validation**: Multer storage sanitizes filenames and validates extensions (`.pdf`, `.doc`, `.docx`) with a 5MB size limit.
5. **NoSQL Injection & Validation**: Mongoose strictly validates data types and rejects malformed documents.

---

## 🎓 Academic Project Submission Checklist
- [x] Full-Stack MERN Architecture (React, Node, Express, MongoDB)
- [x] Modern, professional Bootstrap 5 design (responsive across devices)
- [x] 3 User Roles (Job Seeker, Recruiter, Admin) with distinct portals
- [x] JWT Authentication & bcrypt password hashing
- [x] Resume upload, download, and profile management
- [x] Job search by title, location, category, job type, and experience
- [x] Recruiter applicant tracking and status updating
- [x] Admin dashboard with statistics and moderation
- [x] Seed script with 12 realistic tech jobs & sample accounts
- [x] 1-Click Demo Login buttons for effortless demonstration
- [x] Production build tested and verified
