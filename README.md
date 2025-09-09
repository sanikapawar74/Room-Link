# Pune Roomie (Room Link)

Full-stack prototype to post and browse broker-free room rentals in Pune.

## Stack
- Backend: Java 21, Spring Boot 3, Spring Security (JWT), Spring Data JPA (Hibernate), PostgreSQL
- Frontend: React 18 + Vite, MUI, React Router, React Leaflet, Axios

## Quick start (Windows, PowerShell)

1) Start PostgreSQL (Docker Desktop required):

```powershell
cd "e:\Room Link"
docker compose up -d
```

If Docker is not installed/running, install Docker Desktop and retry.

2) Configure Java & Maven, then run backend:
- Install Java 21 (Temurin/Oracle) and Apache Maven 3.9+
- Update DB creds in `backend/src/main/resources/application.yml` if needed.

```powershell
cd "e:\Room Link\backend"
mvn -DskipTests spring-boot:run
```

Backend will listen on http://localhost:8080

3) Run frontend (Vite dev server):

```powershell
cd "e:\Room Link\frontend"
npm install
npm run dev
```

Frontend will serve on http://localhost:5173

## Default flows
- Register: POST /api/auth/register
- Login: POST /api/auth/login (returns JWT). Frontend stores token in localStorage.
- Get approved listings: GET /api/listings
- Get listing by id: GET /api/listings/{id}
- Create listing (auth): POST /api/listings
- My listings (auth): GET /api/listings/my-listings
- Image upload (auth): POST /api/upload (returns { url })

## Notes
- CORS allows http://localhost:5173 by default.
- Image uploads are stored under `uploads/` and served at `/uploads/*` by backend.
- JWT secret in `application.yml` is a base64 HS256 sample; change for production.

## Troubleshooting
- Docker not running: Install/start Docker Desktop, then rerun `docker compose up -d`.
- Maven not found: Install Maven 3.9+, ensure `mvn -v` works in PowerShell.
- Port conflicts: Change ports in `application.yml` (backend) or `vite.config.ts` (frontend).
