# Overview

An application supporting collation for information to produce a medical consultants' theatre run sheet.

The application architecture is similar to many SaaS applications, but technology choices are kept simple to allow it to be distributed for installation as a package into Linux (or WSL) to allow complete control over data processing.

# Architecture
## Frontend
* Vue 3 with Composition API
  * Pinia state management 
  * Vue Router
  * Axios — HTTP client for API calls
* TypeScript
* Vite


## Backend
* Node.js
  * Fastify
  * Drizzle ORM
  * better-sqlite3
  * Zod / fastify-zod
* SQLite


## Tooling & DX
* tsx or ts-node — Run TypeScript directly in Node during development
* ESLint + Prettier — Consistent code style across frontend and backend
* Vitest — Testing framework that integrates naturally with the 
* Vite ecosystem (works for both frontend and backend)
* dotenv — Environment variable management

# Project Structure (Monorepo-lite)
A simple two-folder layout works well without needing a full monorepo tool:

```
/features    ← markdown files of feature specifications
  INDEX.md   ← list of features

/src
  /client    ← Vue + Vite app
  /server    ← Fastify + Drizzle API
  /shared    ← common TypeScript interfaces (request/response shapes, enums, etc.).
```