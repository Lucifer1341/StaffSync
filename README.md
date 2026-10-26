# StaffSync - HR Management (MERN)

Roles: HR, Manager, Employee. JWT auth, role-based access.

## Run
Need Node 16+, MongoDB running locally.

```bash
# terminal 1
cd server
npm install
npm run seed      # demo users
npm run dev       # http://localhost:5000

# terminal 2
cd client
npm install
npm run dev       # http://localhost:3000
```

Edit `server/.env` (MONGO_URI, JWT_SECRET) if needed.

## Demo logins
| Role | Email | Password |
|---|---|---|
| HR | hr@staffsync.com | hr1234 |
| Manager | manager@staffsync.com | mgr1234 |
| Employee | employee@staffsync.com | emp1234 |

## Features
- HR: employee CRUD, assign managers, approve leaves, view all attendance, post announcements/news
- Manager: view team, approve/reject team leaves, team attendance, create training programs for team
- Employee: apply leave, check in/out, edit personal record, view news + assigned training

## API (all under /api, JWT Bearer)
- auth: POST /register, POST /login, GET /me
- users: GET /, POST /, PUT /:id, DELETE /:id (HR), PUT /me/profile
- leaves: POST /, GET /mine, GET / (HR/Mgr), PUT /:id/status
- attendance: POST /checkin, POST /checkout, GET /mine, GET / (HR/Mgr)
- announcements: GET /, POST /, DELETE /:id (HR)
- trainings: GET /, POST /, DELETE /:id (HR/Mgr)

Test with Postman: login first, copy token, set `Authorization: Bearer <token>`.
