# TaskMgr - Task Management System

This repository serves as the root workspace linking the **Frontend** and **Backend** repositories.

> 📘 **Full Documentation**
>
> -   **Frontend Details**: See [taskmgr-client](https://github.com/safdar-azeem/taskmgr-client) for UI features, components, and styling.
> -   **Backend Details**: See [taskmgr-api](https://github.com/safdar-azeem/taskmgr-api) for API endpoints, database schema, and authentication flows.

---

## ⚡ Quick Start Guide

### 1. Prerequisites

-   **Node.js** (v20+)
-   **MongoDB** (Running locally or cloud)
-   **Git**

### 2. Clone & Install

Run the following commands to set up the project and install dependencies for both the API and Client:

```bash
# 1. Clone with submodules
git clone --recursive [https://github.com/safdar-azeem/taskmgr.git](https://github.com/safdar-azeem/taskmgr.git)

# 2. Enter project folder
cd taskmgr

# 3. Install all dependencies (Root, Client, and API)
yarn install

```

### 3. Configure Environment (`.env`)

You must create a `.env` file in each sub-folder.

**A. Frontend Config** (`taskmgr-client/.env`)

```env
VITE_API_URL=http://localhost:4003/api

```

**B. Backend Config** (`taskmgr-api/.env`)

```env
# Server Configuration
NODE_ENV=development
PORT=4003

# Database
MONGODB_URI=mongodb://localhost:27017/task-mgmt-db

# JWT Configuration
JWT_SECRET=your_super_secret_jwt_key_here
JWT_EXPIRES_IN=1d

# Redis Configuration
REDIS_HOST=127.0.0.1
REDIS_PORT=6379
# REDIS_URL=redis://username:password@host:port (for production)

# Email Configuration (Gmail example)
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=your-email@gmail.com
EMAIL_PASS=your-app-specific-password
```

---

## 🚀 Run the Application

You need to run the **Backend** and **Frontend** in separate terminals.

### Terminal 1: Start Backend API

```bash
# From root folder
yarn dev:api

```

_Server runs at: http://localhost:4003_

### Terminal 2: Start Frontend Client

```bash
# From root folder
yarn dev:client

```

_Client runs at: http://localhost:5173_

---

## 🛠️ Helper Commands

| Command                         | Description                            |
| ------------------------------- | -------------------------------------- |
| `yarn dev:api`                  | Starts the Backend server only         |
| `yarn dev:client`               | Starts the Frontend application only   |
| `yarn install:all`              | Installs dependencies for both folders |
| `git submodule update --remote` | Pulls latest code for both submodules  |

**Built with ❤️ by Safdar Azeem**
