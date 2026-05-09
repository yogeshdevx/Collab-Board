# Collab Board

Collab Board is a full-stack project management app inspired by tools like Trello and Asana. It helps teams create projects, manage task boards, assign work, discuss tasks, and receive realtime updates.

The app is built as one Node.js project. The backend, API, authentication, WebSocket server, and static frontend are served from the same app, so it does not need a separate frontend deployment.

## What You Can Do

- Register and log in as a user
- Create group projects
- View project boards with task cards
- Create, edit, assign, and organize tasks
- Set task priority, status, due date, and description
- Comment inside tasks for team communication
- Receive realtime board updates and notifications with WebSockets
- Run locally without setting up a database

## Tech Stack

- Node.js
- Built-in HTTP server
- WebSockets
- Vanilla HTML, CSS, and JavaScript
- JSON file storage

## Project Structure

```text
.
├── server.js
├── package.json
├── README.md
└── public
    ├── index.html
    ├── app.js
    └── styles.css
```

## Try It Locally

First, make sure Node.js is installed on your computer.

Clone the repository:

```bash
git clone YOUR_REPOSITORY_URL
cd YOUR_REPOSITORY_FOLDER
```

Start the app:

```bash
node server.js
```

Open this URL in your browser:

```text
http://localhost:3000
```

## Demo Login

The app creates a demo user automatically the first time it runs.

```text
Email: demo@example.com
Password: demo123
```

You can also register a new account from the login page.

## Data Storage

The app stores local data in:

```text
data/db.json
```

This file is created automatically when the app runs for the first time. No database setup is required for local testing.

## Deploying

This project can be deployed as a Node.js Web Service on platforms like Render.

Recommended Render settings:

```text
Language: Node
Build Command: npm install
Start Command: node server.js
```

Add this environment variable:

```text
TOKEN_SECRET=your-long-random-secret
```

After deployment, the same live URL serves:

- The frontend from `public`
- The backend API from `/api`
- Realtime updates from `/ws`

## Important Note For Deployment

This project uses JSON file storage, which is simple and good for demos. On many hosting platforms, local files can reset after redeploys. For production use, replace `data/db.json` with a real database such as PostgreSQL, MongoDB, or another persistent storage option.
