# Full Stack Authentication System

This project is a comprehensive authentication system with a Node.js/Express backend and a Next.js frontend.

Live Demo : https://frontend-production-50fe.up.railway.app/

Postman Collection: https://orange-escape-693012.postman.co/workspace/Personal-Workspace~33c15f4c-baf4-483d-8491-e263dc7ed470/collection/24497684-f7dbd756-5a95-495e-b312-67dad21afca6?action=share&creator=24497684
## Features

- User registration and login
- Email verification
- Password reset functionality
- Google OAuth integration
- JWT-based authentication
- Role-based access control (public, authenticated, admin)
- Rate limiting and security features
- Real-time updates using Socket.IO
- Responsive design using Tailwind CSS

## Tech Stack

### Backend
- Node.js
- Express.js
- MongoDB with Mongoose
- Passport.js for authentication
- JWT for token-based authentication
- Nodemailer for email services
- Socket.IO for real-time features

### Frontend
- Next.js 13 (App Router)
- React
- Tailwind CSS
- Axios for API requests
- Socket.IO client for real-time features
- Zod for form validation



## Setup and Installation

### Prerequisites
- Node.js (v14 or later)
- MongoDB
- Docker and Docker Compose (for containerized setup)

### Environment Variables

## 1. Backend (.env file in backend directory):
   
`PORT`=5000

`NODE_ENV`=development

`MONGODB_URI`="mongodb+srv://suryatech128:surya@authsystem.vgpfu.mongodb.net/auth?retryWrites=true&w=majority&appName=authsystem"

`EMAIL_HOST`="smtp.gmail.com"

`EMAIL_PORT`=587

`EMAIL_USER`="suryatech128@gmail.com"

`EMAIL_PASS`="uetk ywbo bljk bubc"

`EMAIL_FROM`="suryatech128@gmail.com"

`ACCESS_TOKEN_SECRET`="test_access_token_secret"

`REFRESH_TOKEN_SECRET`="test_refresh_token_secret"

`FRONTEND_URL`="http://localhost:3000"

`RATE_LIMIT_WINDOW_MS`=900000

`RATE_LIMIT_MAX`=100

`GOOGLE_CLIENT_ID`="35998161146-curhb31ut84oluvvagh8re4r41gpoopm.apps.googleusercontent.com"

`GOOGLE_CLIENT_SECRET`="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"

## 2. Frontend (.env.local file in frontend directory):
   
`NEXT_PUBLIC_API_URL`=[http://localhost:5000](http://localhost:5000)


### Running Locally

1. Clone the repository:
git clone [https://y2y_auth.git](https://y2y_auth.git)
cd y2y_auth

2. Install dependencies:
cd backend && npm install
cd ../frontend && npm install

3. Start the backend:
cd backend
npm run dev

4. In a new terminal, start the frontend:
cd frontend
npm run dev

5. Access the application at `http://localhost:3000`

### Running with Docker

1. Ensure Docker and Docker Compose are installed on your system.

2. Build and run the containers:
docker-compose up --build

3. Access the application at `http://localhost:3000`

To stop the containers:
docker-compose down


## API Routes

### Auth Routes
- `POST /api/auth/register`: Register a new user
- `POST /api/auth/login`: Login user
- `POST /api/auth/refresh-token`: Refresh access token
- `POST /api/auth/logout`: Logout user
- `GET /api/auth/verify-email/:token`: Verify user's email
- `POST /api/auth/forgot-password`: Initiate password reset
- `POST /api/auth/reset-password/:token`: Reset password
- `GET /api/auth/google`: Initiate Google OAuth flow
- `GET /api/auth/google/callback`: Google OAuth callback

### User Routes
- `GET /api/users/profile`: Get user profile
- `PUT /api/users/profile`: Update user profile
- `PUT /api/users/change-password`: Change user password

### Admin Routes
- `GET /api/admin/users`: Get all users (admin only)
- `PUT /api/admin/users/:userId`: Update user (admin only)
- `PUT /api/admin/users/:userId/reset-password`: Reset user's password (admin only)

## Frontend Pages

- `/`: Home page
- `/login`: User login page
- `/register`: User registration page
- `/dashboard`: User dashboard (protected route)
- `/profile`: User profile page (protected route)
- `/admin`: Admin dashboard (admin-only route)
- `/forgot-password`: Forgot password page
- `/reset-password/[token]`: Reset password page
- `/verify-email/[token]`: Email verification page
- `/auth-callback`: OAuth callback handler

## Authentication Flow

1. User registers or logs in
2. Backend sends JWT tokens (access and refresh)
3. Frontend stores tokens in localStorage
4. Access token is sent with each API request
5. If access token expires, refresh token is used to get a new access token
6. On logout, tokens are cleared from localStorage

## Development

### Backend
- Run in development mode: `npm run dev`
- The server will restart automatically on file changes

### Frontend
- Run in development mode: `npm run dev`
- The app will be available at `http://localhost:3000`

## Production Deployment

### Backend
1. Set `NODE_ENV=production` in your deployment environment
2. Ensure all environment variables are set
3. Run `npm start` to start the server

### Frontend
1. Create a production build: `npm run build`
2. Start the production server: `npm start`


This README provides a comprehensive overview of your entire project, including both the frontend and backend components. It covers the project structure, features, setup instructions for both local and Docker environments, API routes, frontend pages, and other important details.

To run the project locally:

1. Follow the "Running Locally" instructions in the README.
2. Make sure to set up the environment variables as described.
3. Run the backend and frontend in separate terminal windows.


To run the project using Docker:

1. Ensure Docker and Docker Compose are installed on your system.
2. Follow the "Running with Docker" instructions in the README.
3. Use `docker-compose up --build` to start the entire application.
