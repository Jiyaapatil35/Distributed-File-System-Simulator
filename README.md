# Distributed File System Simulator

A **team-scoped distributed file system simulator** built as an academic project to demonstrate distributed storage concepts, approval workflows, and team-based access control.  
The system simulates **primary–replica node storage**, **two-step approval workflows**, and **event-based notifications** using a modern Node.js stack.

> **Academic Team Project**  
> **Duration:** September 2025 – January 2026  
> **Team Size:** 4 Members  
> **Context:** 5th Sem Mini Project


## Project Overview

This application simulates a distributed file storage environment for teams.  
Each team operates in isolation and has:

- A **primary storage node**
- Optional **0–3 replica (backup) nodes**
- A **two-step approval workflow** for file operations
- A **notification system** for tracking workflow events

**File Workflow:**

1. Member creates/edits/deletes a file → status `pending_confirmation`
2. Member confirms change → status `pending_approval`, notification sent to leader
3. Team leader approves → file synced to replicas, status `synced`  
   or rejects → rollback/revert changes


## Key Features

- **Team-based access control** with leader and members
- **Primary + replica node storage simulation**
- **Two-step approval workflow** (Confirm → Approve/Reject)
- **Notification system** for file and approval events
- **Strict team isolation** via session-based scoping
- **Web UI** built with EJS templates
- In-memory file upload handling (text-based storage)


## Tech Stack

- **Backend:** Node.js, Express.js  
- **Database:** MongoDB with Mongoose  
- **Templating Engine:** EJS  
- **Session Management:** express-session  
- **File Uploads:** Multer (in-memory)  
- **Flash Messages:** connect-flash  


## Key Directories

- **controllers/** – Business logic for teams, files, nodes, notifications  
- **models/** – Mongoose schemas  
- **routes/** – Express route mappings  
- **views/** – EJS templates  
- **public/** – Static assets (CSS, JS)  


## How to run (Development)
1. Clone the repository and open it.
   
```bash
git clone <your-repository-url>
cd distributed-file-system-simulator
```

2. Install dependencies:

```powershell
npm install
```

3. Create a `.env` file in the project root with the following keys (example):

```
MONGO_URI=mongodb://localhost:27017/your-db
SESSION_SECRET=some-secret
PORT=3000
```

4. Start the server (recommended with nodemon for development):

```powershell
node server.js
```

5. Visit `http://localhost:3000`

## Environment Variables
- `MONGO_URI` — MongoDB connection string
- `SESSION_SECRET` — session secret for express-session
- `PORT` — port to run the server (default 3000)


Enjoy working with the simulator!
