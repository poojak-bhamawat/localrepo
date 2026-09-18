# Book My Ticket
Book My Ticket is a full-stack, real-time movie ticket booking web application featuring interactive seat selection grids, temporary hold locks, JWT authentication, booking history management, Socket.IO live synchronization, and a PostgreSQL database backend.
The project is built using HTML5, CSS3, Vanilla JavaScript, Vite, Node.js, Express, Socket.IO, and PostgreSQL, providing an easy-to-understand codebase for developers of all skill levels.
This repository is especially suitable for first-time open-source contributors looking to work on web application UI, real-time WebSockets, backend REST APIs, and full-stack database integration.
## About the Project
Book My Ticket brings seamless cinematic ticketing, real-time seat reservation, and operational booking management into one unified, modern full-stack interface.
## Current Features
- *JWT Authentication & Security —* Secure user registration and login workflows powered by JSON Web Tokens (JWT) and bcrypt password hashing.
- *Movie & Showtime Selection —* Interactive selection interface for exploring available film listings, showtimes, and screening slots.
- *Interactive Seat Selection Grid —* Dynamic visual seating matrix for viewing seat availability, picking preferred locations, and viewing visual states.
- *Temporary Seat Holding & Release —* Time-limited seat reservation holding mechanism to prevent double-booking across concurrent user sessions.
- *Booking & History Management —* Instant reservation confirmation, booking cancellations, and historical booking lookup views.
- *Real-Time Seat Synchronization —* WebSocket-powered live state updates using Socket.IO Client and Server for real-time occupancy updates.
- *PostgreSQL & Express REST API Backend —* Node.js Express server integrated with PostgreSQL database schema migrations and seat-reset utilities.
## Tech Stack
This project uses modern web & Node.js technologies:
- *Frontend:* HTML5, CSS3, Vanilla JavaScript (ES6+), Vite, Socket.IO Client
- *Backend:* Node.js, Express.js, Socket.IO, JWT (jsonwebtoken), bcrypt, Dotenv
- *Database:* PostgreSQL with custom SQL migration scripts
- *Tools & Utilities:* Git, GitHub, npm, Docker Compose, Render (render.yaml)
No heavy client-side JavaScript frameworks are required.
## Project Structure
```text
book-my-ticket/
│
├── backend/                # Express REST API & Socket.IO server backend
│   ├── config/             # Database and server configurations
│   ├── controllers/        # Request handlers for authentication, seats, and bookings
│   ├── database/           # Database setup and connection logic
│   ├── middleware/         # Express middleware (JWT authentication, validation)
│   ├── routes/             # API route definitions (auth, seats, bookings)
│   ├── index.mjs           # Express application entry point & Socket.IO initialization
│   ├── migrate.mjs         # PostgreSQL database schema migration script
│   ├── reset-seats.mjs     # Administrative utility script to reset seat states
│   ├── docker-compose.yml  # Container setup for local development
│   └── package.json        # Backend dependencies and scripts
│
├── frontend/               # Vite-powered client application frontend
│   ├── public/             # Static public assets (images, icons)
│   │   └── assets/         # App graphics and media files
│   ├── index.html          # Main single-page ticket booking interface
│   ├── main.js             # Client UI handlers, seat matrix logic, & Socket.IO connection
│   ├── style.css           # Application design stylesheet
│   ├── vite.config.js      # Vite build tool configuration
│   └── package.json        # Frontend dependencies and scripts
│
├── render.yaml             # Render cloud deployment blueprint configuration
└── README.md               # Main project documentation
Getting Started & Installation
Prerequisites
Make sure you have the following installed on your machine:

Node.js 18+
npm
PostgreSQL
Git
Environment Variables
Create a .env file inside the backend/ directory.

Standard PostgreSQL Connection:

env


DATABASE_URL=postgresql://user:password@host:5432/dbname
JWT_SECRET=your_secret_key
NODE_ENV=development
PORT=8080
Local PostgreSQL Setup:

env


DB_HOST=localhost
DB_PORT=5432
DB_USER=postgres
DB_PASSWORD=your_password
DB_NAME=booking_db
JWT_SECRET=your_secret_key
NODE_ENV=development
PORT=8080
Note: Never commit .env files or sensitive credentials to GitHub.

Quick Start Guide
Clone the Repository

bash


git clone https://github.com/hacktober2k26/book-my-ticket.git
cd book-my-ticket
Install Backend Dependencies

bash


cd backend
npm install
Install Frontend Dependencies

bash


cd ../frontend
npm install
Run Database Migration

bash


cd ../backend
node migrate.mjs
Start the Backend Server

bash


npm start
(Server starts on port 8080 by default)

Start the Frontend Development Server

bash


cd ../frontend
npm run dev
(Frontend usually runs at http://localhost:5173)

Useful Utility Commands
Backend:
npm start — Launch production server
npm run dev — Launch dev server with hot reload
npm run reset:seats — Reset seat states back to available
Frontend:
npm run dev — Start Vite local dev server
npm run build — Build production distribution bundle
npm run preview — Preview production build locally
API Overview
Method	Endpoint	Description
POST	/auth/register	Register a new user account
POST	/auth/login	Authenticate user and receive JWT token
GET	/seats?movie=<name>&time=<slot>	Fetch current seating layout and state
POST	/book/hold/:id?movie=<name>&time=<slot>	Place a temporary hold lock on a seat
POST	/book/release/:id?movie=<name>&time=<slot>	Release a temporarily held seat
POST	/book/confirm?movie=<name>&time=<slot>	Confirm seat reservation and create booking
GET	/book/my-bookings	Retrieve authenticated user's booking history
DELETE	/book/cancel/:bookingId	Cancel an existing booking reservation
Open Bugs
These are existing problems in the project that contributors can help fix.

ID	Issue	Difficulty	Area
B-01	Improve frontend error handling and user feedback notices	Beginner	Frontend / UI
B-02	Improve seat-selection visual states and CSS styling	Beginner	HTML / CSS
B-03	Improve authentication form validation feedback	Beginner	JavaScript / Auth
B-04	Fix and improve responsive layout on smaller screen sizes	Beginner	HTML / CSS
B-05	Real-time seat state synchronization drops connection under load	Intermediate	Node.js / Socket.IO
B-06	Booking transaction error handling fails gracefully on rollbacks	Intermediate	Backend / PostgreSQL
B-07	Backend lacks automated API and booking flow integration tests	Intermediate	Testing / QA
B-08	REST API documentation missing request payload examples	Beginner	Documentation
Feature Ideas
These features can be added to improve the application.

ID	Feature	Difficulty	Area
F-01	Movie search bar and category filter controls	Beginner	JavaScript / UI
F-02	Downloadable booking receipt with QR code generation	Intermediate	JavaScript / Frontend
F-03	Automated email booking confirmation notifications	Intermediate	Node.js / Backend
F-04	Admin dashboard for managing movies, showtimes, and seats	Intermediate	Fullstack / API
F-05	Online payment gateway integration (Stripe / Razorpay)	Advanced	Fullstack / Payments
F-06	Real-time occupancy analytics & booking metrics dashboard	Intermediate	Fullstack / Analytics
F-07	Full keyboard accessibility (a11y) & modal focus traps	Intermediate	HTML / Accessibility
F-08	Automated GitHub Actions CI/CD deployment pipeline	Intermediate	DevOps / GitHub
Difficulty Guide
Not sure which issue to choose?

Beginner
Good starting point if this is your first contribution.

Usually involves:

HTML link, form, & script tag cleanups
Removing debug console logs or improving feedback notices
Small CSS visual adjustments or layout fixes
Documentation updates and API schema parameter tweaks
Intermediate
Requires some familiarity with JavaScript, DOM manipulation, Node.js, or SQL database APIs.

Usually involves:

Connecting frontend fetch() API calls to backend endpoints
Managing Socket.IO WebSocket client/server events
Writing PostgreSQL transaction queries or schema migration scripts
Adding graceful error handling middleware and automated tests
Advanced
Suitable for contributors who are comfortable working with larger full-stack architectures.

Usually involves:

Third-party payment gateway integration and webhook handling
Real-time fault tolerance for high-concurrency booking locks
Complete role-based admin dashboard routing and authorization
Performance tuning, containerization, and production CI/CD setup
How to Contribute
If you find an issue you'd like to work on:

Open the Issues section of this repository.
Read the issue description carefully.
Check whether someone is already working on it.
Comment on the issue if you want to work on it.
Fork the repository and create your branch (git checkout -b feature/your-feature-name).
Test your changes locally.
Create a Pull Request explaining what you changed.
You don't need to be an experienced developer to contribute. Start with an issue that matches your current skill level and learn as you go.

Thank you for taking the time to contribute to Book My Ticket.

Every contribution counts — whether it is a small CSS fix, a JavaScript improvement, documentation update, or a completely new feature.