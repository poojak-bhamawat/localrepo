# Book My Ticket

**Book My Ticket** is a full-stack movie ticket booking application that allows users to browse movies and showtimes, select seats, authenticate securely, and manage their bookings.

The project is built for practical full-stack development and open-source contributions.

---

## About the Project

Book My Ticket provides a simple movie-ticket booking experience with a frontend connected to a Node.js backend and PostgreSQL database.

It includes user authentication, movie/showtime selection, seat selection, temporary seat holding, booking confirmation, cancellation, and booking history. Socket.IO is used for real-time communication.

---

## Features

* User registration and login with JWT authentication
* Movie and showtime selection
* Interactive seat selection
* Temporary seat holding and release
* Booking confirmation and cancellation
* View booking history
* Real-time seat communication using Socket.IO
* PostgreSQL database integration
* Responsive frontend

---

## Tech Stack

### Frontend

* HTML
* CSS
* JavaScript
* Vite
* Socket.IO Client

### Backend

* Node.js
* Express.js
* PostgreSQL
* JWT
* bcrypt
* Socket.IO
* dotenv

### Tools

* Git
* GitHub
* npm
* VS Code

---

## Project Structure

```text
book-my-ticket/
│
├── backend/
│   ├── config/
│   ├── controllers/
│   ├── database/
│   ├── middleware/
│   ├── routes/
│   ├── index.mjs
│   ├── migrate.mjs
│   ├── reset-seats.mjs
│   ├── package.json
│   └── docker-compose.yml
│
├── frontend/
│   ├── public/
│   │   └── assets/
│   ├── index.html
│   ├── main.js
│   ├── vite.config.js
│   └── package.json
│
├── render.yaml
└── README.md
```

---

## Prerequisites

Make sure you have:

* Node.js 18+
* npm
* PostgreSQL
* Git

---

## Environment Variables

Create a `.env` file inside the `backend` directory.

```env
DATABASE_URL=postgresql://user:password@host:5432/dbname
JWT_SECRET=your_secret_key
NODE_ENV=development
PORT=8080
```

For a local PostgreSQL setup:

```env
DB_HOST=localhost
DB_PORT=5432
DB_USER=postgres
DB_PASSWORD=your_password
DB_NAME=booking_db
JWT_SECRET=your_secret_key
NODE_ENV=development
PORT=8080
```

Do not commit `.env` files or sensitive credentials to GitHub.

---

## Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/hacktober2k26/book-my-ticket.git
cd book-my-ticket
```

### 2. Install Dependencies

Backend:

```bash
cd backend
npm install
```

Frontend:

```bash
cd ../frontend
npm install
```

### 3. Configure the Database

Create the `.env` file inside `backend` and add your PostgreSQL credentials.

### 4. Run Database Migration

```bash
cd ../backend
node migrate.mjs
```

### 5. Start the Backend

```bash
npm start
```

The backend runs on port `8080` by default.

### 6. Start the Frontend

Open another terminal:

```bash
cd frontend
npm run dev
```

The frontend will normally be available at:

```text
http://localhost:5173
```

---

## Useful Commands

### Backend

```bash
npm start
npm run dev
npm run reset:seats
```

### Frontend

```bash
npm run dev
npm run build
npm run preview
```

---

## API Overview

### Authentication

```http
POST /auth/register
POST /auth/login
```

### Seats

```http
GET /seats?movie=<movie>&time=<slot>
```

### Booking

```http
POST /book/hold/:id?movie=<movie>&time=<slot>
POST /book/release/:id?movie=<movie>&time=<slot>
POST /book/confirm?movie=<movie>&time=<slot>
GET /book/my-bookings
DELETE /book/cancel/:bookingId
```

---

## Open Bugs

The following are potential issues that contributors can investigate and improve:

| ID   | Bug / Improvement                                 | Difficulty   |
| ---- | ------------------------------------------------- | ------------ |
| B-01 | Improve frontend error handling and user feedback | Beginner     |
| B-02 | Improve seat-selection UI and visual states       | Beginner     |
| B-03 | Improve authentication form validation            | Beginner     |
| B-04 | Improve responsive design on smaller screens      | Beginner     |
| B-05 | Improve real-time seat synchronization            | Intermediate |
| B-06 | Improve booking transaction and error handling    | Intermediate |
| B-07 | Add automated API and booking-flow tests          | Intermediate |
| B-08 | Improve API documentation and examples            | Beginner     |

> These are suggested contribution areas. Please check the repository Issues before starting work.

---

## Contribution Ideas

Contributors can also work on:

* Movie search and filtering
* Improved booking UI
* Booking receipts or QR codes
* Email booking confirmation
* Accessibility improvements
* Admin dashboard
* Payment integration
* Booking analytics
* CI/CD integration

---

## How to Contribute

1. Fork the repository.
2. Create a new branch.

```bash
git checkout -b feature/your-feature-name
```

3. Make and test your changes.
4. Commit your changes.

```bash
git add .
git commit -m "feat: describe your change"
```

5. Push your branch.

```bash
git push origin feature/your-feature-name
```

6. Open a Pull Request with a clear description of your changes.

### Contribution Guidelines

* Keep changes focused on the selected issue or feature.
* Follow the existing project structure.
* Do not commit secrets or `.env` files.
* Test your changes before creating a Pull Request.
* Avoid unnecessary changes to unrelated files.
* Use clear commit messages.
* Update the README when setup or functionality changes.

---

## Future Improvements

* Online payment integration
* QR-code based tickets
* Email booking confirmation
* Movie search and filtering
* Admin dashboard
* Booking analytics
* Automated testing
* CI/CD integration
* Improved accessibility

---

## License

Please refer to the repository for the current license information.

---

## Contributing

Contributions, bug fixes, new features, and documentation improvements are welcome.

**Fork it, build it, improve it, and contribute to open source.**
