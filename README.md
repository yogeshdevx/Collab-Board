# Collab Board

A full-stack collaborative project management tool similar to Trello or Asana.

This project includes both the backend and frontend in one Node.js app. The backend API and WebSocket server are in `server.js`, and the frontend files are served from the `public` folder.

## Features

- User registration and login
- Group projects with member access
- Project boards with task cards
- Task assignment, status, priority, due dates, and descriptions
- Comments inside tasks
- Real-time notifications and board updates using WebSockets
- JSON file persistence, so no database setup is required

## Run Locally

```bash
node server.js
```

Open `http://localhost:3000`.

The app creates `data/db.json` automatically the first time it runs.

Demo login:

```text
demo@example.com
demo123
```

## Deploy On Render

Deploy this project as a Render **Web Service**. You do not need a separate frontend deployment because `server.js` serves the files in the `public` folder.

Use these Render settings:

```text
Language: Node
Build Command: npm install
Start Command: node server.js
```

Add this environment variable in Render:

```text
TOKEN_SECRET=your-long-random-secret
```

After deployment, open the Render URL. The same URL serves:

- Frontend pages from `public`
- Backend API routes from `/api`
- Realtime WebSocket updates from `/ws`

## Important Deployment Note

The app currently stores data in `data/db.json`. This is fine for a demo or college project, but Render's normal filesystem can reset after redeploys. For a production app, use a real database such as PostgreSQL, MongoDB, or attach persistent storage.
