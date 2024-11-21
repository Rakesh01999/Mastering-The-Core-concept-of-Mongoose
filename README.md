
# Mongoose Concepts and Project Setup

## Table of Contents
- [Introduction](#introduction)
- [Installation and Setup](#installation-and-setup)
- [Scripts](#scripts)
- [Environment Variables](#environment-variables)
- [TypeScript and ESLint Configuration](#typescript-and-eslint-configuration)
- [Project Structure](#project-structure)
- [Key Features and Concepts](#key-features-and-concepts)
- [GitHub Repository](#github-repository)
- [References](#references)

---

## Introduction

This project explores the core concepts of **Mongoose** with a focus on creating and managing a MongoDB database in a Node.js and TypeScript environment. It demonstrates setting up Express.js, integrating TypeScript, linting with ESLint and Prettier, and designing modular architecture with the MVC pattern.

---

## Installation and Setup

Follow these steps to set up the project:

1. **Initialize the Project:**
   ```bash
   mkdir first-project
   cd first-project
   npm init -y
   code .
   ```

2. **Install Dependencies:**
   ```bash
   npm install express mongoose cors dotenv
   npm install --save-dev typescript ts-node-dev @types/node @types/express @types/cors eslint @typescript-eslint/parser @typescript-eslint/eslint-plugin eslint-config-prettier
   ```

3. **Initialize TypeScript Configuration:**
   ```bash
   tsc --init
   ```

4. **Adjust TypeScript Configuration (`tsconfig.json`):**
   ```json
   {
     "include": ["src"],
     "exclude": ["node_modules"]
   }
   ```

5. **Set Execution Policy (Windows Only):**
   Open PowerShell as Administrator and run:
   ```bash
   Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
   ```

6. **Add Scripts in `package.json`:**
   ```json
   "scripts": {
     "build": "tsc",
     "lint": "eslint src/**/*.ts",
     "start": "node ./dist/server.js",
     "dev": "ts-node-dev src/server.ts"
   }
   ```

---

## Scripts

- `npm run build` - Compiles TypeScript into JavaScript.
- `npm run lint` - Lints the code using ESLint.
- `npm run start` - Runs the compiled server.
- `npm run dev` - Runs the server in development mode with live reload.

---

## Environment Variables

Create a `.env` file in the root directory and add the following:

```
PORT=5000
DATABASE_URL=mongodb+srv://<username>:<password>@cluster0.mongodb.net/first-project?retryWrites=true&w=majority&appName=Cluster0
```

Replace `<username>` and `<password>` with your MongoDB Atlas credentials.

---

## TypeScript and ESLint Configuration

- **TypeScript Compiler Options:**
  - Adjust the `rootDir` and `outDir` in `tsconfig.json`.
  - Ensure `"include": ["src"]` and `"exclude": ["node_modules"]`.

- **ESLint Setup:**  
  Configured to enforce consistent formatting, avoid unused variables, and support TypeScript.

- **Prettier Integration:**
  Installed and configured to ensure code formatting consistency.

---

## Project Structure

```
first-project/
├── src/
│   ├── app/
│   │   ├── modules/
│   │   │   ├── student/
│   │   │   │   ├── student.interface.ts
│   │   │   │   ├── student.model.ts
│   │   │   │   ├── student.controller.ts
│   │   │   │   ├── student.service.ts
│   ├── server.ts
├── dist/
├── .env
├── tsconfig.json
├── eslint.config.mjs
├── package.json
└── README.md
```

---

## Key Features and Concepts

1. **Mongoose Schema and Models:**
   - Define schemas and models for a `Student` with detailed types.

2. **Interface Design:**
   - Example `Student` interface:
     ```typescript
     export type Student = {
       id: string;
       name: {
         firstName: string;
         middleName?: string;
         lastName: string;
       };
       gender: "male" | "female";
       dateOfBirth: string;
       email: string;
       contactNo: string;
       emergencyContactNo: string;
       bloodGroup: "A+" | "A-" | "B+" | "B-" | "AB+" | "AB-" | "O+" | "O-";
       presentAddress: string;
       permanentAddress: string;
       guardian: {
         fatherName: string;
         motherName: string;
       };
     };
     ```

3. **Modular Architecture:**
   - Follows the MVC (Model-View-Controller) pattern for scalability.

4. **Linting and Prettier:**
   - Ensures clean and readable code with consistent formatting.

---

## GitHub Repository

Access the repository [here](https://github.com/Apollo-Level2-Web-Dev/Level2-Batch4-PH-University-Server/tree/mastering-mongoose).

---

## References

1. **Linting Setup:** [LogRocket Blog](https://blog.logrocket.com/linting-typescript-eslint-prettier)
2. **TypeScript + Express Guide:** [Dev.to Article](https://dev.to/shafayat/-express-typescript-eslint-prettiersetup-5fhg)
3. **Mongoose Documentation:** [Mongoose Official Site](https://mongoosejs.com/)

---
