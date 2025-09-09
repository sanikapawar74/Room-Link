
# Pune Roomie (Room Link)

Broker-free room rental platform for Pune. Post, browse, and manage listings with ease.

---

## Features
- User registration & JWT-based authentication
- Post, browse, and manage room listings
- Interactive map view (React Leaflet)
- Image upload and preview
- RESTful API (Spring Boot)
- PostgreSQL persistence
- Modern UI (MUI,VITE, React)

---

## Architecture
```
Frontend (React + Vite) <-> Backend (Spring Boot) <-> PostgreSQL (Docker)
```
![Architecture Diagram](https://raw.githubusercontent.com/sanikapawar74/Room-Link/main/docs/architecture.png)

---


## Stack
- **Backend:** Java 21, Spring Boot 3, Spring Security (JWT), Spring Data JPA (Hibernate), PostgreSQL
- **Frontend:** React 18 + Vite, MUI, React Router, React Leaflet, Axios

---


## Quick Start

### Windows (PowerShell)
1. Start PostgreSQL (Docker Desktop required):
	```powershell
	cd "e:\Room Link"
	docker compose up -d
	```
2. Configure Java & Maven, then run backend:
	- Install Java 21 (Temurin/Oracle) and Apache Maven 3.9+
	- Update DB creds in `backend/src/main/resources/application.yml` if needed.
	```powershell
	cd "e:\Room Link\backend"
	mvn -DskipTests spring-boot:run
	```
	Backend: http://localhost:8080
3. Run frontend (Vite dev server):
	```powershell
	cd "e:\Room Link\frontend"
	npm install
	npm run dev
	```
	Frontend: http://localhost:5173

### Linux/Mac
1. Start PostgreSQL (Docker required):
	```bash
	cd "~/Room Link"
	docker compose up -d
	```
2. Configure Java & Maven, then run backend:
	- Install Java 21 and Maven 3.9+
	- Update DB creds in `backend/src/main/resources/application.yml` if needed.
	```bash
	cd "~/Room Link/backend"
	./mvnw spring-boot:run
	```
	Backend: http://localhost:8080
3. Run frontend (Vite dev server):
	```bash
	cd "~/Room Link/frontend"
	npm install
	npm run dev
	```
	Frontend: http://localhost:5173

---


## API Endpoints
- **Register:** `POST /api/auth/register`
- **Login:** `POST /api/auth/login` (returns JWT; stored in localStorage)
- **Get Listings:** `GET /api/listings`
- **Get Listing by ID:** `GET /api/listings/{id}`
- **Create Listing (auth):** `POST /api/listings`
- **My Listings (auth):** `GET /api/listings/my-listings`
- **Image Upload (auth):** `POST /api/upload` (returns `{ url }`)

---


## Configuration & Environment
- **CORS:** Allows `http://localhost:5173` by default
- **Uploads:** Images stored in `uploads/`, served at `/uploads/*`
- **JWT Secret:** Change sample secret in `application.yml` for production
- **Ports:** Backend (`application.yml`), Frontend (`vite.config.ts`)

---

## Deployment
- **Netlify:** Static frontend hosting (see `netlify.toml`)
- **Railway:** Backend deployment (see `railway.json`)


---

## Troubleshooting
- **Docker not running:** Install/start Docker Desktop, rerun `docker compose up -d`
- **Maven not found:** Install Maven 3.9+, ensure `mvn -v` works
- **Port conflicts:** Change ports in config files

---

## Contributing
Pull requests welcome! For major changes, open an issue first to discuss what you’d like to change.

---

## License
MIT

---

## Resources
- [Spring Boot Docs](https://spring.io/projects/spring-boot)
- [React Docs](https://react.dev/)
- [Docker Docs](https://docs.docker.com/)
- [PostgreSQL Docs](https://www.postgresql.org/docs/)
- [MUI Docs](https://mui.com/)
