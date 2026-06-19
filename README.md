# Product Management Dashboard

A clean, full-stack product management application with an admin panel and a storefront UI. The repo contains a Node/Express backend and a Vite + React frontend.

**Tech summary:**
- **Frontend:** React, Vite, Tailwind CSS
- **Backend:** Node.js, Express, MongoDB (Mongoose), JWT, Multer

**Repository layout (key folders):**
- `backend/` — Express API, models, routes, services, `scripts/seed.js`
- `frontend/` — Vite + React app and components
- `uploads/` — persisted file uploads (images)

**Note:** `backend/node_modules/` and `frontend/node_modules/` are ignored by `.gitignore`.

**Requirements**
- Node.js 18+ (or compatible LTS)
- npm or yarn
- MongoDB (Atlas or local) — connection via environment variable

**Environment variables (backend)**
- `PORT` — server port (default: `5000`)
- `MONGO_URI` — MongoDB connection string
- `JWT_SECRET` — secret for signing JWT tokens
- `USE_MEMORY_DB` — optional; set `true` to use in-memory DB for dev

Getting started — local (recommended)

1) Backend

```bash
cd backend
npm install
# create a .env file with MONGO_URI, JWT_SECRET (and optional PORT)
npm run seed   # optional: seed the database with sample data
npm run dev    # starts server (commonly on http://localhost:5000)
```

Seed script: `backend/scripts/seed.js` seeds users and products used by the frontend/admin UI.

2) Frontend

```bash
cd frontend
npm install
npm run dev    # starts dev server (commonly on http://localhost:5173)
```

Build for production

```bash
cd frontend
npm run build
# serve the static files from any static host or integrate with backend as needed
```

Docker (optional)
```bash
docker-compose up --build
# brings up both backend and frontend if docker-compose.yml is configured
```

API and features (high level)
- Auth: `/api/login`, `/api/register` (JWT-based)
- Products: CRUD endpoints under `/api/products`
- Users: admin-only user management endpoints
- Image uploads saved under `uploads/` via the backend upload middleware

Development tips
- Admin-only routes live in `frontend/src/components/auth/` (`AdminRoute.jsx`) and backend `middleware/auth.js`.
- Use the seed script to quickly create an admin user for testing.

Where to look in the code
- Backend entry: `backend/src/index.js`
- DB config: `backend/src/config/db.js`
- Seed data: `backend/scripts/seed.js`
- Frontend entry: `frontend/src/main.jsx`

Contributing
- Fork, create a feature branch, run tests (if present), open a PR with a clear description.

License & contact
- Add your preferred license file (`LICENSE`) or update this README.
- Questions or help: open an issue in this repo.

---
This README was generated to provide clear local setup and development guidance for the project.
