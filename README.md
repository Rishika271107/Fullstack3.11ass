# FullStack Authentication with Axios

This project demonstrates a centralized Axios API utility for handling JWT authentication in a React frontend with an Express backend.

## Features

- Centralized Axios instance with interceptors
- Automatic JWT token attachment to requests
- Global 401 error handling with auto-logout
- Protected backend routes with JWT middleware
- React frontend with login, register, and dashboard

## Setup

### Backend

```bash
cd backend
npm install
npm start
```

### Frontend

```bash
cd frontend
npm install
npm start
```

## API Endpoints

- `POST /api/auth/login` - User login
- `POST /api/auth/register` - User registration
- `GET /api/protected` - Protected data (requires authentication)

## How it works

1. **Axios Interceptors**: The `api.js` file creates an Axios instance with request and response interceptors.
2. **Request Interceptor**: Automatically attaches JWT token from localStorage to Authorization header.
3. **Response Interceptor**: Handles 401 errors by clearing localStorage and redirecting to login.
4. **Backend Middleware**: `authenticateToken` middleware verifies JWT tokens on protected routes.

## Testing

1. Register a new user
2. Login to get a token
3. Access the dashboard to see protected data
4. Try accessing protected data without token (should redirect to login)
5. Check Network tab to see Authorization headers
