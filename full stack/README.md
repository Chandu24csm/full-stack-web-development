# FitZone Gym Management System

Full-stack gym management app built with HTML, CSS, JavaScript, React, Node.js, Express, and SQLite.

## Features
- Register gym members and save contact information
- Assign a membership plan, monthly fee, joining date, and status
- View, search, and filter member records
- Edit and delete members
- Dashboard totals: total members, active members, monthly recurring fee total, and active plan types
- SQLite persistence, server-side validation, and REST API

## Requirements
- Node.js 18 or newer and npm
- Internet for the first dependency installation

## Run the project
1. Extract the ZIP file.
2. Open the extracted `fitzone-gym-management` folder in VS Code.
3. Open Terminal → New Terminal.
4. Install packages:
   ```bash
   npm install
   ```
5. Start the frontend and backend:
   ```bash
   npm run dev
   ```
6. Open the local Vite URL shown in the terminal, usually `http://localhost:5173`.

The API runs at `http://localhost:5000`. The `server/gym.db` SQLite database is created automatically.

## API endpoints
| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/health` | Health check |
| GET | `/api/members` | List gym members |
| POST | `/api/members` | Add member |
| PUT | `/api/members/:id` | Update member |
| DELETE | `/api/members/:id` | Delete member |

## Folder structure
```text
fitzone-gym-management/
├── index.html
├── package.json
├── vite.config.js
├── README.md
├── server/
│   └── server.js
└── src/
    ├── main.jsx
    ├── App.jsx
    └── styles.css
```

## How it works
- React renders the dashboard and membership forms.
- Browser requests use `/api/members`.
- Vite forwards API requests to Express on port 5000 during development.
- Express validates the input and performs parameterized SQLite queries.
- The returned JSON updates the React interface.
- Member records persist in `server/gym.db` after server restarts.

## Notes
- Monthly revenue is the sum of the monthly fee field for all Active members. It is a dashboard estimate, not a payment-processing or accounting ledger.
- `npm start` starts the API server only; `npm run dev` starts both frontend and backend.
