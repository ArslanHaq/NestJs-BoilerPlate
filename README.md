# NestJS Boilerplate

A small NestJS starter that shows the building blocks behind larger APIs: JWT authentication, route guards, DTO validation and error handling. Data is kept in memory, so it runs without a database.

## What's inside

- **JWT auth:** `POST /auth/login` returns a token, and `GET /auth/profile` returns the signed-in user
- **Global auth guard** protects every route, and a `@SkipAuth()` decorator marks public ones
- **Password hashing** with bcrypt
- **Custom guard:** `BeltGuard` checks a condition before a ninja can be created, as an example of a permission-style guard
- **Validation** with class-validator DTOs and `ValidationPipe`
- **Error handling** with Nest's built-in exceptions (`NotFoundException`, `UnauthorizedException`)
- **Unit tests** for controllers, services and guards

## Endpoints

| Method | Path | Description |
|---|---|---|
| `POST` | `/auth/login` | Sign in and get a JWT |
| `GET` | `/auth/profile` | Current user (needs a token) |
| `POST` / `GET` | `/users` | Create or list users |
| `GET` | `/users/:username` | Get a user |
| `PATCH` / `DELETE` | `/users/:id` | Update or delete a user |
| `GET` / `POST` | `/ninjas` | List or create ninjas |
| `GET` / `PUT` / `DELETE` | `/ninjas/:id` | Get, update or delete a ninja |

## Getting started

```bash
npm install
npm run start:dev   # http://localhost:3000
```

Send the token as `Authorization: Bearer <token>` on protected routes.

> The JWT secret in `src/auth/constants.ts` is a placeholder. Move it to an environment variable before using this in a real project.

## Scripts

| Command | What it does |
|---|---|
| `npm run start:dev` | Start in watch mode |
| `npm test` | Unit tests |
| `npm run test:e2e` | End-to-end tests |
| `npm run lint` | Run ESLint |

## How it was built

Each feature (pipes and validation, error handling, guards, authentication, authorization) was added on its own branch and merged through a pull request. The commit history shows the steps.
