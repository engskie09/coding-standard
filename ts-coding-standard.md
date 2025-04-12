# TypeScript Coding Standards

## Table of Contents

1. [Introduction](#introduction)
2. [Repositories](#repositories)
   - [ts-node-express-mongoose](#ts-node-express-mongoose)
     - [ts-node-express-mongoose: Project Structure](#ts-node-express-mongoose-project-structure)
     - [ts-node-express-mongoose: Naming Conventions](#ts-node-express-mongoose-naming-conventions)
     - [ts-node-express-mongoose: API Service Design](#ts-node-express-mongoose-api-service-design)
   - [ts-node-react-vite-material](#ts-node-react-vite-material)
     - [Project Structure](#project-structure-ts-node-react-vite-material)
     - [Naming Conventions](#naming-conventions-ts-node-react-vite-material)
     - [Component Organization](#component-organization-ts-node-react-vite-material)
3. [Shared Guidelines](#shared-guidelines)
   - [Import and Module Guidelines](#import-and-module-guidelines)
   - [Type Safety and Best Practices](#type-safety-and-best-practices)
   - [Clean Code Tips](#clean-code-tips)
   - [Linting and Formatting](#linting-and-formatting)

## Introduction

This guide focuses on a practical set of coding standards shared across several core repositories:

- `ts-node-express-mongoose`: Backend API server built with Node.js, Express, and Mongoose (MongoDB)
- `ts-node-react-vite-material`: Frontend web application built with React, Vite, and Material UI

It outlines best practices in **project structure**, **naming conventions**, and **service layer design** for both backend and frontend,  
ensuring that each codebase remains **clean**, **consistent**, and **scalable** as the project evolves.

## Repositories

### ts-node-express-mongoose

#### ts-node-express-mongoose: Project Structure

The project should be organized by domain or feature-based folders. Each feature should contain its own models, services, routers, and utilities.

Example layout:

```bash
src/
├── model/
│   └── sample.model.ts
├── router/
│   └── sample.router.ts
├── service/
│   └── sample.service.ts
├── util/
│   └── sample.util.ts
└── index.ts
```

#### ts-node-express-mongoose: Naming Conventions

- Files should be named using `kebab-case`, and use consistent suffixes to indicate their role.
- Use `*.dto.ts` for Data Transfer Objects, `*.router.ts` for route definitions, and `*.service.ts` for business logic.

Examples:

- `user.dto.ts` should define interfaces or types like:
```ts
interface IFetchAccountsRequest {
  page: number;
  size: number;
}
```

- `user.router.ts` should register routes clearly:
```ts
router.get('/fetch-accounts/:page/:size', fetchAccounts);
```

- `user.service.ts` should contain the actual implementation logic:
```ts
const fetchAccounts = () => {};
```

**Summary of Naming Conventions:**
| File Type         | Naming Pattern      | Purpose                          |
|------------------|---------------------|----------------------------------|
| DTO files         | `user.dto.ts`       | Data structure definitions       |
| Router files      | `user.router.ts`    | Route setup and controller glue |
| Service files     | `user.service.ts`   | Business logic implementation   |
