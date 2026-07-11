# Social Media Marketing Panel

A full-stack social media marketing panel built with a React/Vite frontend and an Express/MongoDB backend. The app supports user authentication, admin workflows, order handling, balance updates, and transaction tracking.

## Features

- User login with JWT-based authentication
- Admin dashboard for managing services, users, and balances
- User dashboard for placing orders and viewing transactions
- Password change and user management flows
- MongoDB-backed data models for users, services, orders, and transactions

## Tech Stack

- Frontend: React 19, Vite, React Router, Axios, Tailwind CSS
- Backend: Node.js, Express, Mongoose, JWT, bcrypt, cookie parsing
- Database: MongoDB

## Project Structure

```text
backend/
	index.js
	controllers/
	middelwares/
	models/
	routes/
	utils/
frontend/
	src/
		components/
		context/
		pages/
		service/
```

## Prerequisites

- Node.js 18 or newer
- npm
- MongoDB connection string

## Setup

Install dependencies for each app separately:

```bash
cd backend
npm install

cd ../frontend
npm install
```

## Environment Variables

Create a `.env` file inside `backend/` with the values used by the server:

```env
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
API_URL=your_external_api_url
API_KEY=your_external_api_key
```

Notes:

- `MONGO_URI` is required by `backend/utils/db.js`
- `JWT_SECRET` is used for login tokens and route validation
- `API_URL` and `API_KEY` are consumed by admin/user controller flows that talk to external services

## Run Locally

### Backend

The backend currently listens on port `3000`.

```bash
cd backend
node index.js
```

### Frontend

```bash
cd frontend
npm run dev
```

## Local Development Notes

The current frontend is configured to call the deployed backend at:

```text
https://social-media-marketing-panel.onrender.com
```

If you want to run everything locally, update the API base URL in `frontend/src/service/api.js` and make sure the backend CORS allowlist in `backend/index.js` includes your local frontend origin.

## Available Scripts

### Frontend

- `npm run dev` - start the Vite dev server
- `npm run build` - build for production
- `npm run lint` - run ESLint
- `npm run preview` - preview the production build

### Backend

The backend does not currently define npm scripts. Start it directly with `node index.js`.

## Deployment

The codebase already contains deployment-oriented configuration for Vercel on the frontend and a hosted backend URL in the client API layer. If you change the deployment targets, update the hardcoded URLs in the frontend and the CORS origin list in `backend/index.js`.

## Common Endpoints

The backend exposes routes for authentication, admin actions, and user actions. Common paths include:

- `/login`
- `/me`
- `/admin/*`
- `/user/*`

## License

No license has been specified yet.
