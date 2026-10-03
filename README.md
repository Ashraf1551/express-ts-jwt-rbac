# Express TypeScript JWT RBAC API

This project is a backend API built with Node.js, Express, TypeScript, PostgreSQL, and JWT authentication. It demonstrates how to implement role-based access control (RBAC) and secure protected routes.

## Features

- User authentication with email and password
- JWT access token generation
- Refresh token flow
- Role-based route protection
- PostgreSQL database integration
- Cookie-based refresh token storage
- Centralized error handling
- Modular Express project structure

## Tech Stack

- Node.js
- Express.js
- TypeScript
- PostgreSQL
- `pg`
- `jsonwebtoken`
- `bcryptjs`
- `dotenv`
- `cors`
- `cookie-parser`

## Project Structure

```bash
src/
  app.ts
  server.ts
  config/
    index.ts
  db/
    index.ts
  middleware/
    auth.ts
    globalErrorHandler.ts
    logger.ts
  modules/
    auth/
      auth.controller.ts
      auth.route.ts
      auth.service.ts
    profile/
      profile.controller.ts
      profile.route.ts
      profile.service.ts
    user/
      user.controller.ts
      user.interface.ts
      user.route.ts
      user.service.ts
  types/
    index.ts
  utility/
    sendResponse.ts
```

## Setup

1. Clone the project:

```bash
git clone <repository-url>
cd express-ts-jwt-rbac
```

2. Install dependencies:

```bash
npm install
```

3. Start the development server:

```bash
npm run dev
```

> Make sure your `.env` file is already created with the required database and JWT environment variables before running the app.

## Main Routes

| Method | Route                     | Description                                        |
| ------ | ------------------------- | -------------------------------------------------- |
| POST   | `/api/auth/login`         | Login a user and generate JWT tokens               |
| POST   | `/api/auth/refresh-token` | Generate a new access token from the refresh token |
| POST   | `/api/users`              | Create a new user                                  |
| GET    | `/api/users`              | Get all users                                      |
| GET    | `/api/users/:id`          | Get a single user by ID                            |
| PUT    | `/api/users/:id`          | Update a user                                      |
| DELETE | `/api/users/:id`          | Delete a user                                      |
| POST   | `/api/profile`            | Create a user profile                              |

## What I Learned

This project helped me understand how a real backend authentication system works in a modular Express application.

### 1. Express and TypeScript basics

I learned how to configure an Express app with TypeScript, use middleware, and organize endpoints in a clean project structure.

### 2. JWT authentication flow

I understood how access tokens and refresh tokens are created, verified, and used to protect APIs.

### 3. Role-based access control

I learned how to restrict certain routes based on a user role such as `admin`, `agent`, or `user` using middleware.

### 4. PostgreSQL integration

I learned how to connect a Node.js backend to PostgreSQL using the `pg` package and create database tables for application data.

### 5. Password security

I learned how to hash and compare passwords securely with `bcryptjs` instead of storing raw password values.

### 6. Middleware and request lifecycle

I saw how middleware can handle logging, parsing JSON data, cookies, CORS, and authorization before the main route logic runs.

### 7. Clean backend architecture

This project reinforced the importance of separating logic into routes, controllers, services, and database layers for maintainability.

### 8. Error handling

I learned how centralized error middleware helps return consistent responses and prevents the app from crashing unexpectedly.

## Notes

This is a great beginner-to-intermediate backend project and can be expanded with features like:

- registration and validation
- password reset
- email verification
- admin dashboard APIs
- testing with Jest or Vitest
- more advanced RBAC policies

## License

This project is for learning and educational purposes.